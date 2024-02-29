# Azure OpenAI Service の **On Your Data** のハンズオン

LLM が持っている情報に、Promptに独自のデータを追加する事で、新たな文書の作成を行う事が出来ます。

このハンズオンでは、それを体験します。

ドキュメントはこちらです。

Azure OpenAI On Your Data:
https://learn.microsoft.com/ja-jp/azure/ai-services/openai/concepts/use-your-data?tabs=ai-search

# ビジネス上の目的
鎌倉時代の武将の「二階堂行政」について知る事です。

ネットで検索したら目的は達成できてしまうのですが😅公開情報を使わざるを得ないので、ご容赦ください。

以下のPromptを使ってください。

Prompt:
```cmd
二階堂行政について教えてください
```

シナリオネタ - @nohanaga さんのBlog:

https://qiita.com/nohanaga/items/f710cac82072b63bc73f

# 準備
- Azure の Subscription
    - 期間限定の**無料版**もあります
    - https://azure.microsoft.com/ja-jp/pricing/free-services/
- データ
    - このGitHubのリポジトリをダウンロードしてください。
    - https://github.com/dahatake/busho-index
    - ![zipダウンロード](/AzureOpenAI_AddYourOwnData/images/donwload-data-file.jpg)

# 1. Azure OpenAI Service の作成とモデルのデプロイ

Azure OpenAI Service を、作成します
    - ベクトル用にEmbeddingのモデルも使用します。こちらのドキュメントを参考にして、GPTとEmbeddingの両方が利用可能なリージョンを選択してください。
        - https://learn.microsoft.com/ja-JP/azure/ai-services/openai/concepts/models#embeddings-models
    - **Japan East** もあります😊

Azure OpenAI Service を作成しただけでは、Promptが楽しめません。モデルをデプロイします。

手順:

- Azure Portal にログイン
    - https://portal.azure.com/
- Azure OpenAI Service の作成
- Azure OpenAI Studio に移動
    - https://oai.azure.com/
- [モデル]に移動して、GPT-4 あるいは GPT-35-xxx の任意のモデルを選択。[デプロイ]から、デプロイを実行
- 同じく[text-embedding-ada-002]のモデルのデプロイも行います。これは、のちに Azure AI Search を使ってデータのベクトル化を行うためのものです。

こちらの公式ドキュメントも参考にしてください。

Azure OpenAI Service リソースを作成してデプロイする:
https://learn.microsoft.com/ja-jp/azure/ai-services/openai/how-to/create-resource?pivots=web-portal

# 2. GPTの「二階堂行政」の情報を確認

手順:

- [プレイグラウンド]の[チャット]にて、Promotを入力
    - GPTには、二階堂行正に関する情報がないため (おそらく)、**ハルシネーション**を起こしているコトが確認できます。あるいは、ハルシネーションまで行かなくても「分からない」といった種類の文章を作成するかもしれません。

出力例:
![出力例](/AzureOpenAI_AddYourOwnData/images/1st-prompt.jpg)


# 3. Web アプリケーション展開用の Azure の Resouce Group を作成

Azure OpenAI Serviceの PlayGround の情報を使ってWebアプリを作成します。そのウィザードで Resource Group の作成が出来ません。
Webアプリケーション用ですので。この後、諸々作成するAzureのサービスとは別がいいかもしれません。ハンズオンですと、一つのリソースグループで大丈夫です。

Azure の Portal から作成してください。

# 4. Azure Blob Storage の作成とファイルのアップロード

Azure Portal から、Azure Storage を作成します。Storage Account を作成すると、Blob Storage も使えるようになります。

ストレージ アカウントを作成する:
https://learn.microsoft.com/ja-jp/azure/storage/common/storage-account-create?tabs=azure-portal

手順:
- GitHubから、ダウンロードしたファイルの中の [Data] フォルダーのテキストファイルを全て Blob Storage の任意のコンテナーにアップロードします
    - アップロードの方法は何でも構いません
    - Azure Portal の Azure Storage Account の中に[ストレージ ブラウザー]があって、そこからアップロードもできます
    - Azure Storage Explore というツールもあります。
        - https://azure.microsoft.com/ja-jp/products/storage/storage-explorer/


# 5. Azure AI Search の作成と、インデックスの作成

ファイルが複数ある場合には、全文検索エンジンが便利です。Azure OpenAI Service の On Your Data では、Azure AI Search との紐づけが簡単にできます。

**!!! 注意 !!!**
- **Free (無料版)** は、on your data でサポートされていません

手順:
- Azure Portal から、Azure AI Search を作成します。
- [データのインポートとベクター化]のウィザードを起動して、インデックスの作成を行います
    - Blob Storage と Embedding 用にデプロイ済みの Azure OpenAI Service を選択します
    - インデックス作成のスケジュールは「1度」にしましょう
    - クイックスタート: 垂直統合 (プレビュー)
    - https://learn.microsoft.com/ja-jp/azure/search/search-get-started-portal-import-vectors

Indexerのジョブが完了するまで待ちます。Azure Portalの[インデクサー]の[成功したドキュメント]で、いくつのファイルのインデックス化+ベクター化が終了しているのかを確認できます。

- [インデックス]から作成したインデックスを選択します
- [検索エクスプローラー]で、実際に全文検索が出来ます。以下の単語で検索してみましょう。

```cmd
二階堂行政
```

何かの文章がヒットすればOKです。

# 6. Azure OpenAI Service の on your data にて、検索エンジンとの紐づけを行う

手順:
- Azure OpenAI Studio に移動します
- [プレイグラウンド]-[チャット]に移動します
- 画面の左側に[データを追加する]があります。それを選択して、on your data のウィザードを起動させます
    - データソース: Azure AI Search
    - [ベクトル検索を検索リソースに追加します]: オン
    - [検索の種類]: ベクトル

Prompt:
```cmd
二階堂行政について教えてください
```


# 6. PlayGround から、Webアプリを展開

Azure Web App にサンプルコードを使っての展開が出来ます。

- Azure OpenAI Studio の[プレイグラウンド]のまま。先ほどの画面ですね。
- 画面右上の[配置先]から[新しいWebアプリ]を選択
- 全ての項目を入力する。チェックボックスは全てオンにして、作成します。
    - 若干料金はかかりますが

作成されたAzure のサービスは以下の様になっています。このウィザードで作成されるのは以下です。
- App Service プラン
- App Service
- Azure Cosmos DB アカウント

![展開後](/AzureOpenAI_AddYourOwnData/images/buildapp.jpg)

展開には実際には、こちらのコードを利用しているようです。つまり、こちらのリポジトリーをForkして、カスタマイズして使えば、プロトタイプを、もう少し製品版に近づけられると思います。

https://github.com/microsoft/sample-app-aoai-chatGPT

**!!! 注意 !!!**

展開しても、直ぐにアプリケーションが使えるわけではありません。**10分くらい**余裕をみてください。休憩ですね😊

# 7. アプリケーションを試す

Azure Web App が作成されています。チャットの履歴データは Azure Cosmos DB に入っています。

- Azure Portal の Azure Web App から、作成したアプリケーションを起動します。
- Prompt を入力して、出力を確認します。

- 幾度かPromptを行うと、過去の履歴が画面上から確認できます
    - これは、Azure Cosmos DB に格納されています



# 8. クリーンアップ

Azure Portal から、作成したリソースグループを削除します。リソースグループを削除すると、その中にある全てのサービスを依存関係を考慮した上で削除してくれます。
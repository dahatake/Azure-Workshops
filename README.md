# Azure Workshop Contents

Azure の Hands-on-Lab や Workshop 用のコンテンツのリンク集です。

自社あるいは Community の勉強会など、どうぞ自由にご活用ください。

- [Azure Functions](#azure-functions)
- [Azure Kubernetes Services](#azure-Kubernetes-services)
- [機械学習一通り](#機械学習一通り)
- [Cognitive Service](#Cognitive-Service)
- [Azure Machine Learning](#Azure-Machine-Learning)
- [Cosmos DB](#Cosmos-DB)

- [SQL Database](#SQL-Database)
- [Azure Synapse Analytics](#Azure-Synapse-Anaytics)

- [Azure Databricks](#Azure-Databricks)
- [Azure Data Explorer](#Azure-Data-Explorer)
- [Azure Search](#Azure-Search)
- [Power BI](#Power-BI)
- [IoT](#IoT)
- [Azure DevOps](#Azure-DevOps)

- [High Availability System](#High-Availability-System)
- [Senario Type Application](#Senario-Type-Application)


# 1.  諸々網羅しているもの

## Microsoft Cloud Workshop

Azure のかなりの数のサービスのコンテンツです。英語ですが、皆さんなら読めるかと!

https://microsoftcloudworkshop.com/

## Microsoft Hands-on Labs

Azure だけでなく、様々な Microsoft Technology のハンズオンラボコンテンツです。

`Self-paced Labs` の自習式のハンズオンです。操作用に仮想マシンまで用意されています。

https://www.microsoft.com/handsonlabs/selfpacedlabs/

## What is What The Hack?

手順書のあるハンズオンではなく、チャレンジ・課題ベースの Hackathonコンテンツです。Hands-on 系をやった後で、是非こうした課題解決型のものに取り組める時間を作りたいものです。

https://github.com/microsoft/whatthehack


## Azure Citadel

同じく Azure のかなりの数のサービスのコンテンツです。各国の Community の皆さんでメンテナンスされている、ハンズオン・ワークショップ用のコンテンツです。こちらも同じく英語のみ😅

https://azurecitadel.com/

# 2. 個別製品・サービス

## Azure Functions

1. Serverless Workshop

    Azure Functions, Logic App, EventGrid など一通り。Durable Functions もあります!

    https://github.com/codingwithsasquatch/serverless_ninjas_workshop

2. Static Web page

    HTML ベースのユーザー インターフェイスを表示するシンプルな Web アプリケーションをデプロイします。 サーバーレス バックエンドにより、アプリケーションで画像をアップロードし、その画像について説明するキャプションを自動的に取得できます

    https://docs.microsoft.com/ja-jp/azure/functions/tutorial-static-website-serverless-api-with-database

## Azure Kubernetes Services 

1. Java ベースの AKS 一通り (@yoshioterada さん)

    kubernetes のインストール、管理のためのツール群、Service Mesh、そして、VNet と MySQL 起動までを一通り。

    https://github.com/yoshioterada/k8s-Azure-Container-Service-AKS--on-Azure

2. 一通り (@yokawasa)

    こちらも、インストール、構成管理など、一通り。

    https://github.com/yokawasa/azure-container-labs

## 機械学習一通り

1. 機械学習の入門からデータサイエンティスト手前まで

Global AI Nights の日本開催で利用したコンテンツです。MVP の方々の多大なるご尽力です。非常にわかりやすいチャレンジ構成になっています。

https://aka.ms/AA603s1

2. Cognitive, Azure ML, Bot まで一通り

Azure を使った Pre-Trained Model, Custom Model, Bot Application についてのコンテンツです。

https://azure.github.io/learnAnalytics-public/

## Cognitive Service

1. Speech x Java (@yoshioterada さん)

    Microsoft Translator はテキスト(英語)からテキスト(日本語)の翻訳のほか、音声データ(wavファイル)からテキストへ翻訳などができます。本ハンズオンでは、テキストからテキストの翻訳、音声からテキストへの翻訳の２種類の翻訳の実装方法について紹介します。

    https://github.com/yoshioterada/MS-Translator-Speech-HoL

2. Xamarin (@ayako さん)

    まずは Cognitive Services を利用したアプリケーションに触れ、Cognitive Services の利用方法について学習します。その後、Cognitive Services Face API を活用 して、取り込んだ画像を分析して人間の顔に関する情報 (年齢、性別、表情) を出力するアプリを、マルチプラットフォーム向け(Windows, iOS, Android) の開発環境である Xamarin を用いたアプリケーションとして構築します

    https://github.com/ayako/CognitiveXamarinHOL_201806

3. Logic App x Power Platform (@ayako さん)

    Microsoft PowerApps & Flow / Azure Locig Apps からノンコーディングで Cognitive Services を活用したアプリを開発するハンズオンです

    https://github.com/ayako/NonCodingCognitive_201806

## Azure Machine Learning

1. Deep Learning Lab - Azure Machine Learning Hands-on

    学習用の Python スクリプトを、どう制御していくのかを体験できます。

    最初のものが終わったら、自分のあるいは外部にある既存の学習用 Python スクリプトを適合して実行してみてください。

    https://github.com/DeepLearningLab/AML-Handson?fbclid=IwAR0ukYdflpwTAR4f78xXf627g_M7y8W343fXrhUY5opQC9JRJHbGDRoP6jQ

2. TensorFlow ベース (@tsmatz さん)

    Azure Machine Learning を使っての、データ準備、学習、展開までを一通り。

    https://github.com/tsmatz/azure-ml-tensorflow-complete-sample

3. CustomAI Course for the AI Airlift

    3つのコースから成っています。
    - Azure Databricks and its integration with Azure Machine Learning Services
    - Continuous Integration and Continuous Delivery (CI/CD)
    - Deep learning with Azure Machine Learning Services using VS Cod

    https://azure.github.io/LearnAI-CustomAI-Airlift/

4. 強化学習 - ChainerRL


    Minecraftで深層強化学習 ハンズオン (@keisuke-umezawa さん)

    Azure Data Science VM を使って、Minecraft をシミュレーター環境として動かす深層強化学習を行います

    https://qiita.com/keisuke-umezawa/items/fcf5d00474e244217a5e

5. BERT

    NLP で人気のある BERT を使って、MLOps まで実装します

    https://github.com/microsoft/bert-stack-overflow

    BERT on Azure のサンプルはこちら:

    https://github.com/Microsoft/AzureML-BERT

## Cosmos DB

1. SQL API

    Azure Cosmos DB using the SQL API, JavaScript and .NET Core SDK

    https://cosmosdb.github.io/labs/

## Azure Databricks

1. NYC Taxi public data
    
    誰もが知っている NYC Taxi のデータですが、小さなデータが増え続けるパターンをどう処理していくか、という意味でも価値があろうかと思います。

    Data Engineering | Data Science

    の両方を行えますね😊

    https://github.com/microsoft/Azure-Databricks-NYC-Taxi-Workshop


2. DataBricks での機械学習 - 入門編 (@tsmatz さん)

    https://github.com/tsmatz/azure-databricks-exercise


3. Predictive Analytics with Spark in Azure Databricks

    how to use the Spark MLLib library to build machine learning solutions in a Spark Azure HDInsight cluster
    
    https://microsoftlearning.github.io/databricks-ml/

4. Anomaly Detection and Predictive Maintenanc

    簡単な異常検知と予測保全に関するものです

    https://azure.github.io/LearnAI-ADPM/

## SQL Database

1. SQL Server and SQL Database Workshop and Labs

    ソフトウェアとしてのSQL Server も含めた、Data処理、Big Data Cluster、on Kubernetes、Data Science、Machine Learning などもカバー。初学者から、新機能を試したいエキスパートまでおススメです。


  https://microsoft.github.io/sqlworkshops/

## Azure Synapse Anaytics

1. Azure Synapse Analytics end-to-end solution

  Synapseの概念を実感する上で、非常によくできたコンテンツ。実際に大きなデータ量を扱いますので、全て実行するのに結構時間はかかります...

   https://github.com/microsoft/MCW-Azure-Synapse-Analytics-end-to-end-solution

2. Azure Synapse Analytics Workshop (level 400, 4 days)

  これもよくできたコンテンツです。特にとばしがちな、データ加工の部分をデータフローを丁寧に使ってやります。Parquet, JSONのデータのJOINも。そして、Synapse内部での機械学習を使った Model 作成とデプロイもあり😊

  https://github.com/solliancenet/azure-synapse-analytics-workshop-400


## Azure Data Explorer

1. End-To-End の操作

    インスタンスを作成する事から始めて、Power BI からの接続。複数の KQL 実行まで。

    https://aka.ms/adx.lab

## Azure Search

1. Azure Search - Cognitive Search

    Blob上のファイルのクローリング (インデッキシング) 時に、ファイル内部を解析し、結果を Search Indexの列として追加する、深層学習の応用例になります。

    https://azure.github.io/LearnAI-KnowledgeMiningBootcamp/

## Power BI

1. お気軽ハンズオン

    Power BI Desktop を使っての基本的な作業手順を体験します。

    [PowerBI-Hands-on](/PowerBI/README.md)

1. ガイド付き学習

    公式なのですが、まずはここから...

    https://docs.microsoft.com/ja-jp/power-bi/guided-learning/

2. 自習書

    若干古いですが。

    公式なもの:

    http://aka.ms/pbi_self-learning01

    同じく、上記のスクリプト

    http://aka.ms/pbi_self-learning02

## IoT

1. IoT 全部

    実機前提の Azure IoT 利用イメージがつかめる大作です。

    https://github.com/ms-iotkithol-jp/IoTKitHoLV4

2. with Jetson TX 2

    JETSON TX2のサンプルの、jetson-inferenceのimagenet-cameraの画像認識結果をAzure IoT Hubに送信する改造手順を説明します

    https://github.com/ms-iotkithol-jp/nvidia-jetson-tx2

## Azure DevOps

公式なのですが、よくまとまっています。

https://www.azuredevopslabs.com/

## High Availability System

止められないシステムを実現するための各種 Azure Services

https://github.com/microsoft/MCW-Business-continuity-and-disaster-recovery

## Senario Type Application

個別サービスを組み合わせてのアプリケーションのシナリオです。

1. ベンディングマシーン

    ![Image](https://github.com/Microsoft/MCW-Intelligent-vending-machines/raw/master/Hands-on%20lab/media/preferred-solution-architecture.png)

    https://github.com/Microsoft/MCW-Intelligent-Vending-Machines

    ハンズオンはこちらから。
    https://github.com/Microsoft/MCW-Intelligent-vending-machines/blob/master/Hands-on%20lab/HOL%20step-by-step%20-%20Intelligent%20vending%20machines.md

2. Big Data Vizualization

    データの加工と可視化に注力。

    https://github.com/AzureWorkshops/Big-Data-Visualization-New/blob/master/docs/00_Overview.md

    ![image](https://github.com/Microsoft/MCW-Big-data-and-visualization/raw/master/Whiteboard%20design%20session/media/high-level-overview.png)

    ハンズオン:
    https://github.com/Microsoft/MCW-Big-data-and-visualization/tree/master/Hands-on%20lab

3. Pre-Trained と 独自 Train でのDeep Learning

    Spark Cluster をベースに、Cognigive Services と 独自開発モデルの組み合わせ。

    https://github.com/Microsoft/MCW-Cognitive-Services-and-Deep-Learning

    ![image](https://github.com/Microsoft/MCW-Cognitive-services-and-deep-learning/raw/master/Hands-on%20lab/media/image2.png)

    ハンズオンはこちら。
    https://github.com/Microsoft/MCW-Cognitive-services-and-deep-learning/blob/master/Hands-on%20lab/HOL%20step-by%20step%20-%20Cognitive%20services%20and%20deep%20learning.md#exercise-3-create-and-deploy-a-tensorflow-model

4. 動画解析

    Video Indexer と Serverless サービスを駆使したアプリです

    https://github.com/Microsoft/MCW-Media-AI

    ![image](https://github.com/Microsoft/MCW-Media-AI/raw/master/Hands-on%20lab/images/Hands-onlabstep-by-step-MediaAIimages/media/image2.png)

    ハンズオンはこのあたり
    https://github.com/Microsoft/MCW-Media-AI/blob/master/Hands-on%20lab/HOL%20step-by-step%20-%20Media%20AI.md

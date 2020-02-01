---
title: Creare un'applicazione .NET per Apache Spark in Ubuntu
description: Informazioni su come creare un'applicazione .NET per Apache Spark in Ubuntu
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: a12c861d0f231910f715a13fd41d1f3f0d6748a7
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76928043"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-ubuntu"></a><span data-ttu-id="22cb9-103">Informazioni su come creare un'applicazione .NET per Apache Spark in Ubuntu</span><span class="sxs-lookup"><span data-stu-id="22cb9-103">Learn how to build your .NET for Apache Spark application on Ubuntu</span></span>

<span data-ttu-id="22cb9-104">Questo articolo illustra come creare .NET per applicazioni Apache Spark in Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="22cb9-104">This article teaches you how to build your .NET for Apache Spark applications on Ubuntu.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="22cb9-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="22cb9-105">Prerequisites</span></span>

<span data-ttu-id="22cb9-106">Se sono già disponibili tutti i prerequisiti seguenti, passare alla procedura di [compilazione](#build) .</span><span class="sxs-lookup"><span data-stu-id="22cb9-106">If you already have all of the following prerequisites, skip to the [build](#build) steps.</span></span>

1. <span data-ttu-id="22cb9-107">Scaricare e installare **[.net core 2,1 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** o l'SDK di **[.NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)** : l'installazione dell'SDK consente di aggiungere la `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="22cb9-107">Download and install **[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** or the **[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1)** - installing the SDK adds the `dotnet` toolchain to your path.</span></span>  <span data-ttu-id="22cb9-108">Sono supportati .NET Core 2,1, 2,2 e 3,1.</span><span class="sxs-lookup"><span data-stu-id="22cb9-108">.NET Core 2.1, 2.2 and 3.1 are supported.</span></span>

2. <span data-ttu-id="22cb9-109">Installare **[OpenJDK 8](https://openjdk.java.net/install/)** .</span><span class="sxs-lookup"><span data-stu-id="22cb9-109">Install **[OpenJDK 8](https://openjdk.java.net/install/)**.</span></span> 

   - <span data-ttu-id="22cb9-110">È possibile usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="22cb9-110">You can use the following command:</span></span>

   ```bash
   sudo apt install openjdk-8-jdk
   ```

   * <span data-ttu-id="22cb9-111">Verificare che sia possibile eseguire `java` dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="22cb9-111">Verify you are able to run `java` from your command-line.</span></span>       

      <span data-ttu-id="22cb9-112">Esempio di output di versione Java:</span><span class="sxs-lookup"><span data-stu-id="22cb9-112">Sample java -version output:</span></span>
          
      ```bash
      openjdk version "1.8.0_191"
      OpenJDK Runtime Environment (build 1.8.0_191-8u191-b12-2ubuntu0.18.04.1-b12)
      OpenJDK 64-Bit Server VM (build 25.191-b12, mixed mode)
      ```

   * <span data-ttu-id="22cb9-113">Se sono già installate più versioni di OpenJDK e si vuole selezionare OpenJDK 8, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="22cb9-113">If you already have multiple OpenJDK versions installed and want to select OpenJDK 8, use the following command:</span></span>

      ```bash
      sudo update-alternatives --config java
      ```

3. <span data-ttu-id="22cb9-114">Installare **[Apache Maven 3.6.0 +](https://maven.apache.org/download.cgi)** .</span><span class="sxs-lookup"><span data-stu-id="22cb9-114">Install **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)**.</span></span>

   * <span data-ttu-id="22cb9-115">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="22cb9-115">Run the following command:</span></span>

      ```bash
      mkdir -p ~/bin/maven
      cd ~/bin/maven
      wget https://www-us.apache.org/dist/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz
      tar -xvzf apache-maven-3.6.0-bin.tar.gz
      ln -s apache-maven-3.6.0 current
      export M2_HOME=~/bin/maven/current
      export PATH=${M2_HOME}/bin:${PATH}
      source ~/.bashrc
      ```
       
       <span data-ttu-id="22cb9-116">Si noti che queste variabili di ambiente andranno perse quando si chiude il terminale.</span><span class="sxs-lookup"><span data-stu-id="22cb9-116">Note that these environment variables will be lost when you close your terminal.</span></span> <span data-ttu-id="22cb9-117">Se si desidera che le modifiche siano permanenti, aggiungere le righe `export` al file di `~/.bashrc`.</span><span class="sxs-lookup"><span data-stu-id="22cb9-117">If you want the changes to be permanent, add the `export` lines to your `~/.bashrc` file.</span></span>

   * <span data-ttu-id="22cb9-118">Verificare che sia possibile eseguire `mvn` dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="22cb9-118">Verify you are able to run `mvn` from your command-line</span></span>       

       <span data-ttu-id="22cb9-119">Esempio di MVN-Version output:</span><span class="sxs-lookup"><span data-stu-id="22cb9-119">Sample mvn -version output:</span></span>
       
       ```
       Apache Maven 3.6.0 (97c98ec64a1fdfee7767ce5ffb20918da4f719f3; 2018-10-24T18:41:47Z)
       Maven home: ~/bin/apache-maven-3.6.0
       Java version: 1.8.0_191, vendor: Oracle Corporation, runtime: /usr/lib/jvm/java-8-openjdk-amd64/jre
       Default locale: en, platform encoding: UTF-8
       OS name: "linux", version: "4.4.0-17763-microsoft", arch: "amd64", family: "unix"
       ```

4. <span data-ttu-id="22cb9-120">Installare **[Apache Spark 2.3 +](https://spark.apache.org/downloads.html)** .</span><span class="sxs-lookup"><span data-stu-id="22cb9-120">Install **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)**.</span></span>
<span data-ttu-id="22cb9-121">Scaricare [Apache Spark 2.3 +](https://spark.apache.org/downloads.html) ed estrarlo in una cartella locale, ad esempio `~/bin/spark-2.3.2-bin-hadoop2.7`.</span><span class="sxs-lookup"><span data-stu-id="22cb9-121">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder (e.g., `~/bin/spark-2.3.2-bin-hadoop2.7`).</span></span> <span data-ttu-id="22cb9-122">(Le versioni di Spark supportate sono 2,3. \*, 2.4.0, 2.4.1, 2.4.3 e 2.4.4)</span><span class="sxs-lookup"><span data-stu-id="22cb9-122">(The supported spark versions are 2.3.\*, 2.4.0, 2.4.1, 2.4.3 and 2.4.4)</span></span>

   ```bash
   tar -xvzf /path/to/spark-2.3.2-bin-hadoop2.7.tgz -C ~/bin/spark-2.3.2-bin-hadoop2.7
   ```

   * <span data-ttu-id="22cb9-123">Aggiungere le [variabili di ambiente](https://www.java.com/en/download/help/path.xml) necessarie `SPARK_HOME` (ad esempio, `~/bin/spark-2.3.2-bin-hadoop2.7/`) e `PATH` (ad esempio, `$SPARK_HOME/bin:$PATH`)</span><span class="sxs-lookup"><span data-stu-id="22cb9-123">Add the necessary [environment variables](https://www.java.com/en/download/help/path.xml) `SPARK_HOME` (e.g., `~/bin/spark-2.3.2-bin-hadoop2.7/`) and `PATH` (e.g., `$SPARK_HOME/bin:$PATH`)</span></span>

      ```bash
      export SPARK_HOME=~/bin/spark-2.3.2-hadoop2.7
      export PATH="$SPARK_HOME/bin:$PATH"
      source ~/.bashrc
      ```
       
      <span data-ttu-id="22cb9-124">Si noti che queste variabili di ambiente andranno perse quando si chiude il terminale.</span><span class="sxs-lookup"><span data-stu-id="22cb9-124">Note that these environment variables will be lost when you close your terminal.</span></span> <span data-ttu-id="22cb9-125">Se si desidera che le modifiche siano permanenti, aggiungere le righe `export` al file di `~/.bashrc`.</span><span class="sxs-lookup"><span data-stu-id="22cb9-125">If you want the changes to be permanent, add the `export` lines to your `~/.bashrc` file.</span></span>

   * <span data-ttu-id="22cb9-126">Verificare che sia possibile eseguire `spark-shell` dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="22cb9-126">Verify you are able to run `spark-shell` from your command-line.</span></span>

      <span data-ttu-id="22cb9-127">Esempio di output della console:</span><span class="sxs-lookup"><span data-stu-id="22cb9-127">Sample console output:</span></span>
      
      ```
      Welcome to
            ____              __
           / __/__  ___ _____/ /__
          _\ \/ _ \/ _ `/ __/  '_/
         /___/ .__/\_,_/_/ /_/\_\   version 2.3.2
            /_/

      Using Scala version 2.11.8 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_201)
      Type in expressions to have them evaluated.
      Type :help for more information.

      scala> sc
      res0: org.apache.spark.SparkContext = org.apache.spark.SparkContext@6eaa6b0c
      ```                      

<span data-ttu-id="22cb9-128">Assicurarsi di essere in grado di eseguire `dotnet`, `java`, `mvn``spark-shell` dalla riga di comando prima di passare alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="22cb9-128">Make sure you are able to run `dotnet`, `java`, `mvn`, `spark-shell` from your command-line before you move to the next section.</span></span> <span data-ttu-id="22cb9-129">Si ritiene che esista un metodo migliore?</span><span class="sxs-lookup"><span data-stu-id="22cb9-129">Feel there is a better way?</span></span> <span data-ttu-id="22cb9-130">[Apri un problema](https://github.com/dotnet/spark/issues) per contribuire.</span><span class="sxs-lookup"><span data-stu-id="22cb9-130">Please [open an issue](https://github.com/dotnet/spark/issues) and feel free to contribute.</span></span>

## <a name="build"></a><span data-ttu-id="22cb9-131">Compila</span><span class="sxs-lookup"><span data-stu-id="22cb9-131">Build</span></span>

<span data-ttu-id="22cb9-132">Per la parte restante di questa guida, è necessario aver clonato .NET per Apache Spark repository nel computer, ad esempio `~/dotnet.spark/`.</span><span class="sxs-lookup"><span data-stu-id="22cb9-132">For the remainder of this guide, you will need to have cloned the .NET for Apache Spark repository into your machine e.g., `~/dotnet.spark/`.</span></span>

```bash
git clone https://github.com/dotnet/spark.git ~/dotnet.spark
```

### <a name="build-net-for-spark-scala-extensions-layer"></a><span data-ttu-id="22cb9-133">Compilazione di .NET per il livello estensioni Spark scala</span><span class="sxs-lookup"><span data-stu-id="22cb9-133">Build .NET for Spark Scala extensions layer</span></span>

<span data-ttu-id="22cb9-134">Quando si invia un'applicazione .NET, .NET per Apache Spark ha la logica necessaria scritta in scala che informa Apache Spark come gestire le richieste (ad esempio, la richiesta di creare una nuova sessione di Spark, la richiesta di trasferimento dei dati dal lato .NET al lato JVM e così via).</span><span class="sxs-lookup"><span data-stu-id="22cb9-134">When you submit a .NET application, .NET for Apache Spark has the necessary logic written in Scala that informs Apache Spark how to handle your requests (e.g., request to create a new Spark Session, request to transfer data from .NET side to JVM side etc.).</span></span> <span data-ttu-id="22cb9-135">Questa logica si trova in [.NET per Apache Spark codice sorgente scala](https://github.com/dotnet/spark/tree/master/src/scala).</span><span class="sxs-lookup"><span data-stu-id="22cb9-135">This logic can be found in the [.NET for Apache Spark Scala Source Code](https://github.com/dotnet/spark/tree/master/src/scala).</span></span>

<span data-ttu-id="22cb9-136">Il passaggio successivo consiste nel compilare .NET per Apache Spark livello di estensione scala:</span><span class="sxs-lookup"><span data-stu-id="22cb9-136">The next step is to build the .NET for Apache Spark Scala extension layer:</span></span>

```bash
cd src/scala
mvn clean package 
```

<span data-ttu-id="22cb9-137">Verranno visualizzati i file jar creati per le versioni di Spark supportate:</span><span class="sxs-lookup"><span data-stu-id="22cb9-137">You should see JARs created for the supported Spark versions:</span></span>

* `microsoft-spark-2.3.x/target/microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x/target/microsoft-spark-2.4.x-<version>.jar`

### <a name="build-net-sample-applications-using-net-core-cli"></a><span data-ttu-id="22cb9-138">Compilazione di applicazioni .NET di esempio mediante interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="22cb9-138">Build .NET sample applications using .NET Core CLI</span></span>

<span data-ttu-id="22cb9-139">In questa sezione viene illustrato come compilare le [applicazioni di esempio](https://github.com/dotnet/spark/tree/master/examples) per .net per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="22cb9-139">This section explains how to build the [sample applications](https://github.com/dotnet/spark/tree/master/examples) for .NET for Apache Spark.</span></span> <span data-ttu-id="22cb9-140">Questi passaggi consentiranno di comprendere il processo di compilazione globale per qualsiasi applicazione .NET per Spark.</span><span class="sxs-lookup"><span data-stu-id="22cb9-140">These steps will help in understanding the overall building process for any .NET for Spark application.</span></span>

1. <span data-ttu-id="22cb9-141">Creare il ruolo di lavoro:</span><span class="sxs-lookup"><span data-stu-id="22cb9-141">Build the worker:</span></span>

   ```dotnetcli
   cd ~/dotnet.spark/src/csharp/Microsoft.Spark.Worker/
   dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   ```
      
   <span data-ttu-id="22cb9-142">Esempio di output della console:</span><span class="sxs-lookup"><span data-stu-id="22cb9-142">Sample console output:</span></span>

   ```bash
   user@machine:/home/user/dotnet.spark/src/csharp/Microsoft.Spark.Worker$ dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.
      
      Restore completed in 36.03 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark.Worker/Microsoft.Spark.Worker.csproj.
      Restore completed in 35.94 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark/Microsoft.Spark.csproj.
      Microsoft.Spark -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark/Debug/netstandard2.0/Microsoft.Spark.dll
      Microsoft.Spark.Worker -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/Microsoft.Spark.Worker.dll
      Microsoft.Spark.Worker -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish/
   ```

2. <span data-ttu-id="22cb9-143">Compilare gli esempi:</span><span class="sxs-lookup"><span data-stu-id="22cb9-143">Build the samples:</span></span>

   ```dotnetcli
   cd ~/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples/
   dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   ```
      
   <span data-ttu-id="22cb9-144">Esempio di output della console:</span><span class="sxs-lookup"><span data-stu-id="22cb9-144">Sample console output:</span></span>

   ```bash
   user@machine:/home/user/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples$ dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

      Restore completed in 37.11 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark/Microsoft.Spark.csproj.
      Restore completed in 281.63 ms for /home/user/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples/Microsoft.Spark.CSharp.Examples.csproj.
      Microsoft.Spark -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark/Debug/netstandard2.0/Microsoft.Spark.dll
      Microsoft.Spark.CSharp.Examples -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/Microsoft.Spark.CSharp.Examples.dll
      Microsoft.Spark.CSharp.Examples -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish/
   ```  

## <a name="run-the-net-for-spark-sample-applications"></a><span data-ttu-id="22cb9-145">Eseguire .NET per applicazioni di esempio Spark</span><span class="sxs-lookup"><span data-stu-id="22cb9-145">Run the .NET for Spark sample applications</span></span>

<span data-ttu-id="22cb9-146">Una volta creati gli esempi, è possibile usare `spark-submit` per inviare le app .NET Core.</span><span class="sxs-lookup"><span data-stu-id="22cb9-146">Once you build the samples, you can use `spark-submit` to submit your .NET Core apps.</span></span> <span data-ttu-id="22cb9-147">Assicurarsi di aver seguito la sezione [prerequisiti](#prerequisites) e installato Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="22cb9-147">Make sure you have followed the [prerequisites](#prerequisites) section and installed Apache Spark.</span></span>

1. <span data-ttu-id="22cb9-148">Impostare la variabile di ambiente `DOTNET_WORKER_DIR` o `PATH` per includere il percorso in cui è stato generato il file binario `Microsoft.Spark.Worker` (ad esempio, `~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish`).</span><span class="sxs-lookup"><span data-stu-id="22cb9-148">Set the `DOTNET_WORKER_DIR` or `PATH` environment variable to include the path where the `Microsoft.Spark.Worker` binary has been generated (e.g., `~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish`).</span></span>

   ```bash
   export DOTNET_WORKER_DIR=~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish
   ```

2. <span data-ttu-id="22cb9-149">Aprire un terminale e passare alla directory in cui è stato generato il file binario dell'app, ad esempio `~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish`.</span><span class="sxs-lookup"><span data-stu-id="22cb9-149">Open a terminal and go to the directory where your app binary has been generated (e.g., `~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish`).</span></span>

   ```bash
   cd ~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish
   ```

3. <span data-ttu-id="22cb9-150">L'esecuzione dell'app segue la struttura di base:</span><span class="sxs-lookup"><span data-stu-id="22cb9-150">Running your app follows the basic structure:</span></span>

   ```bash
   spark-submit \
     [--jars <any-jars-your-app-is-dependent-on>] \
     --class org.apache.spark.deploy.dotnet.DotnetRunner \
     --master local \
     <path-to-microsoft-spark-jar> \
     <path-to-your-app-binary> <argument(s)-to-your-app>
   ```

   <span data-ttu-id="22cb9-151">Di seguito sono riportati alcuni esempi che è possibile eseguire:</span><span class="sxs-lookup"><span data-stu-id="22cb9-151">Here are some examples you can run:</span></span>

   * <span data-ttu-id="22cb9-152">**[Microsoft. Spark. examples. SQL. batch. Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span><span class="sxs-lookup"><span data-stu-id="22cb9-152">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span></span>

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Batch.Basic $SPARK_HOME/examples/src/main/resources/people.json
      ```

   * <span data-ttu-id="22cb9-153">**[Microsoft. Spark. examples. SQL. streaming. StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="22cb9-153">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span></span>

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredNetworkWordCount localhost 9999
      ```

   * <span data-ttu-id="22cb9-154">**[Microsoft. Spark. examples. SQL. streaming. StructuredKafkaWordCount (Maven accessibile)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="22cb9-154">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (maven accessible)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

      ```bash
      spark-submit \
      --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
      ```

   * <span data-ttu-id="22cb9-155">**[Microsoft. Spark. examples. SQL. streaming. StructuredKafkaWordCount (jar forniti)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="22cb9-155">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (jars provided)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

      ```bash
      spark-submit \
      --jars path/to/net.jpountz.lz4/lz4-1.3.0.jar,path/to/org.apache.kafka/kafka-clients-0.10.0.1.jar,path/to/org.apache.spark/spark-sql-kafka-0-10_2.11-2.3.2.jar,`path/to/org.slf4j/slf4j-api-1.7.6.jar,path/to/org.spark-project.spark/unused-1.0.0.jar,path/to/org.xerial.snappy/snappy-java-1.1.2.6.jar \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
       ```

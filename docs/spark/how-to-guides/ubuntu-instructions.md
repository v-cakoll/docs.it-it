---
title: Creare un'applicazione .NET per Apache Spark in Ubuntu
description: Informazioni su come creare un'applicazione .NET per Apache Spark in Ubuntu
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 078d080f4ce293875d8fea8c3e804736b28a2eaf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620937"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-ubuntu"></a>Informazioni su come creare un'applicazione .NET per Apache Spark in Ubuntu

Questo articolo illustra come creare .NET per applicazioni Apache Spark in Ubuntu.

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a>Prerequisiti

Se sono già disponibili tutti i prerequisiti seguenti, passare alla procedura di [compilazione](#build) .

1. Scaricare e installare **[.net core 2,1 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** o l'SDK di **[.NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)** : l'installazione dell'SDK consente di aggiungere la stessa `dotnet` alla propria strada.  Sono supportati .NET Core 2,1, 2,2 e 3,1.

2. Installare **[OpenJDK 8](https://openjdk.java.net/install/)**.

   - È possibile usare il comando seguente:

   ```bash
   sudo apt install openjdk-8-jdk
   ```

   * Verificare che sia possibile eseguire `java` dalla riga di comando.

      Esempio di output di versione Java:

      ```bash
      openjdk version "1.8.0_191"
      OpenJDK Runtime Environment (build 1.8.0_191-8u191-b12-2ubuntu0.18.04.1-b12)
      OpenJDK 64-Bit Server VM (build 25.191-b12, mixed mode)
      ```

   * Se sono già installate più versioni di OpenJDK e si vuole selezionare OpenJDK 8, usare il comando seguente:

      ```bash
      sudo update-alternatives --config java
      ```

3. Installare **[Apache Maven 3.6.0 +](https://maven.apache.org/download.cgi)**.

   * Eseguire il comando seguente:

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

       Si noti che queste variabili di ambiente andranno perse quando si chiude il terminale. Se si desidera che le modifiche siano permanenti, aggiungere le `export` righe al `~/.bashrc` file.

   * Verificare che sia possibile eseguire `mvn` dalla riga di comando

       Esempio di MVN-Version output:

       ```
       Apache Maven 3.6.0 (97c98ec64a1fdfee7767ce5ffb20918da4f719f3; 2018-10-24T18:41:47Z)
       Maven home: ~/bin/apache-maven-3.6.0
       Java version: 1.8.0_191, vendor: Oracle Corporation, runtime: /usr/lib/jvm/java-8-openjdk-amd64/jre
       Default locale: en, platform encoding: UTF-8
       OS name: "linux", version: "4.4.0-17763-microsoft", arch: "amd64", family: "unix"
       ```

4. Installare **[Apache Spark 2.3 +](https://spark.apache.org/downloads.html)**.
Scaricare [Apache Spark 2.3 +](https://spark.apache.org/downloads.html) ed estrarlo in una cartella locale (ad esempio, `~/bin/spark-2.3.2-bin-hadoop2.7` ). (Le versioni di Spark supportate sono 2,3. *, 2.4.0, 2.4.1, 2.4.3 e 2.4.4)

   ```bash
   tar -xvzf /path/to/spark-2.3.2-bin-hadoop2.7.tgz -C ~/bin/spark-2.3.2-bin-hadoop2.7
   ```

   * Aggiungere le [variabili di ambiente](https://www.java.com/en/download/help/path.xml) necessarie `SPARK_HOME` (ad esempio, `~/bin/spark-2.3.2-bin-hadoop2.7/` ) e `PATH` (ad esempio, `$SPARK_HOME/bin:$PATH` )

      ```bash
      export SPARK_HOME=~/bin/spark-2.3.2-hadoop2.7
      export PATH="$SPARK_HOME/bin:$PATH"
      source ~/.bashrc
      ```

      Si noti che queste variabili di ambiente andranno perse quando si chiude il terminale. Se si desidera che le modifiche siano permanenti, aggiungere le `export` righe al `~/.bashrc` file.

   * Verificare che sia possibile eseguire `spark-shell` dalla riga di comando.

      Esempio di output della console:

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

Assicurarsi di essere in grado di eseguire `dotnet` , `java` , `mvn` , `spark-shell` dalla riga di comando prima di passare alla sezione successiva. Si ritiene che esista un metodo migliore? [Apri un problema](https://github.com/dotnet/spark/issues) per contribuire.

## <a name="build"></a>Compilare

Per la parte restante di questa guida, è necessario aver clonato .NET per Apache Spark repository nel `~/dotnet.spark/` computer, ad esempio.

```bash
git clone https://github.com/dotnet/spark.git ~/dotnet.spark
```

### <a name="build-net-for-spark-scala-extensions-layer"></a>Compilazione di .NET per il livello estensioni Spark scala

Quando si invia un'applicazione .NET, .NET per Apache Spark ha la logica necessaria scritta in scala che informa Apache Spark come gestire le richieste (ad esempio, la richiesta di creare una nuova sessione di Spark, la richiesta di trasferimento dei dati dal lato .NET al lato JVM e così via). Questa logica si trova in [.NET per Apache Spark codice sorgente scala](https://github.com/dotnet/spark/tree/master/src/scala).

Il passaggio successivo consiste nel compilare .NET per Apache Spark livello di estensione scala:

```bash
cd src/scala
mvn clean package
```

Verranno visualizzati i file jar creati per le versioni di Spark supportate:

* `microsoft-spark-2.3.x/target/microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x/target/microsoft-spark-2.4.x-<version>.jar`

### <a name="build-net-sample-applications-using-net-core-cli"></a>Compilazione di applicazioni .NET di esempio mediante interfaccia della riga di comando di .NET Core

In questa sezione viene illustrato come compilare le [applicazioni di esempio](https://github.com/dotnet/spark/tree/master/examples) per .net per Apache Spark. Questi passaggi consentiranno di comprendere il processo di compilazione globale per qualsiasi applicazione .NET per Spark.

1. Creare il ruolo di lavoro:

   ```dotnetcli
   cd ~/dotnet.spark/src/csharp/Microsoft.Spark.Worker/
   dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   ```

   Esempio di output della console:

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

2. Compilare gli esempi:

   ```dotnetcli
   cd ~/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples/
   dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   ```

   Esempio di output della console:

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

## <a name="run-the-net-for-spark-sample-applications"></a>Eseguire .NET per applicazioni di esempio Spark

Una volta creati gli esempi, è possibile usare `spark-submit` per inviare le app .NET Core. Assicurarsi di aver seguito la sezione [prerequisiti](#prerequisites) e installato Apache Spark.

1. Impostare la `DOTNET_WORKER_DIR` `PATH` variabile di ambiente o in modo da includere il percorso in cui `Microsoft.Spark.Worker` è stato generato il file binario (ad esempio, `~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish` ).

   ```bash
   export DOTNET_WORKER_DIR=~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish
   ```

2. Aprire un terminale e passare alla directory in cui è stato generato il file binario dell'applicazione (ad esempio, `~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish` ).

   ```bash
   cd ~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish
   ```

3. L'esecuzione dell'app segue la struttura di base:

   ```bash
   spark-submit \
     [--jars <any-jars-your-app-is-dependent-on>] \
     --class org.apache.spark.deploy.dotnet.DotnetRunner \
     --master local \
     <path-to-microsoft-spark-jar> \
     <path-to-your-app-binary> <argument(s)-to-your-app>
   ```

   Di seguito sono riportati alcuni esempi che è possibile eseguire:

   * **[Microsoft.Spark.Examples.Sql.Batch. Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Batch.Basic $SPARK_HOME/examples/src/main/resources/people.json
      ```

   * **[Microsoft. Spark. examples. SQL. streaming. StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredNetworkWordCount localhost 9999
      ```

   * **[Microsoft. Spark. examples. SQL. streaming. StructuredKafkaWordCount (Maven accessibile)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

      ```bash
      spark-submit \
      --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
      ```

   * **[Microsoft. Spark. examples. SQL. streaming. StructuredKafkaWordCount (jar forniti)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

      ```bash
      spark-submit \
      --jars path/to/net.jpountz.lz4/lz4-1.3.0.jar,path/to/org.apache.kafka/kafka-clients-0.10.0.1.jar,path/to/org.apache.spark/spark-sql-kafka-0-10_2.11-2.3.2.jar,`path/to/org.slf4j/slf4j-api-1.7.6.jar,path/to/org.spark-project.spark/unused-1.0.0.jar,path/to/org.xerial.snappy/snappy-java-1.1.2.6.jar \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
       ```

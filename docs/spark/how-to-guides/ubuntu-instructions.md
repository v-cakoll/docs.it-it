---
title: Creare un'applicazione .NET per Apache Spark su Ubuntu
description: Scopri come creare l'applicazione .NET per Apache Spark su Ubuntu
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 6dd6f60bb89a51c47fe17182fc47de818cd00b80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187566"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-ubuntu"></a>Scopri come creare l'applicazione .NET per Apache Spark su Ubuntu

Questo articolo illustra come creare le applicazioni .NET for Apache Spark su Ubuntu.

## <a name="prerequisites"></a>Prerequisites

Se si dispone già di tutti i prerequisiti seguenti, passare alle istruzioni di [compilazione.](#build)

1. Scaricare e installare **[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** o **[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1)** - l'installazione di SDK aggiunge la `dotnet` toolchain al percorso.  .NET Core 2.1, 2.2 e 3.1 sono supportati.

2. Installare **[OpenJDK 8](https://openjdk.java.net/install/)**.

   - È possibile utilizzare il seguente comando:

   ```bash
   sudo apt install openjdk-8-jdk
   ```

   * Verificare di essere `java` stati eseguiti dalla riga di comando.

      Esempio di output java -version:

      ```bash
      openjdk version "1.8.0_191"
      OpenJDK Runtime Environment (build 1.8.0_191-8u191-b12-2ubuntu0.18.04.1-b12)
      OpenJDK 64-Bit Server VM (build 25.191-b12, mixed mode)
      ```

   * Se sono già installate più versioni di OpenJDK e si desidera selezionare OpenJDK 8, utilizzare il comando seguente:

      ```bash
      sudo update-alternatives --config java
      ```

3. Installare **[Apache Maven 3.6.0](https://maven.apache.org/download.cgi)**.

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

       Si noti che queste variabili di ambiente andranno perse quando si chiude il terminale. Se si desidera che le modifiche `export` siano `~/.bashrc` permanenti, aggiungere le righe al file.

   * Verificare di essere `mvn` in grado di eseguire dalla riga di comando

       Esempio di output mvn -version:Sample mvn -version output:

       ```
       Apache Maven 3.6.0 (97c98ec64a1fdfee7767ce5ffb20918da4f719f3; 2018-10-24T18:41:47Z)
       Maven home: ~/bin/apache-maven-3.6.0
       Java version: 1.8.0_191, vendor: Oracle Corporation, runtime: /usr/lib/jvm/java-8-openjdk-amd64/jre
       Default locale: en, platform encoding: UTF-8
       OS name: "linux", version: "4.4.0-17763-microsoft", arch: "amd64", family: "unix"
       ```

4. Installare **[Apache Spark 2.3](https://spark.apache.org/downloads.html)**.
Scaricare [Apache Spark 2.3](https://spark.apache.org/downloads.html) ed estrarlo in una `~/bin/spark-2.3.2-bin-hadoop2.7`cartella locale (ad esempio, ). (Le versioni di spark supportate sono 2.3., 2.4.0, 2.4.1, 2.4.3 e 2.4.4)

   ```bash
   tar -xvzf /path/to/spark-2.3.2-bin-hadoop2.7.tgz -C ~/bin/spark-2.3.2-bin-hadoop2.7
   ```

   * Aggiungere le [variabili](https://www.java.com/en/download/help/path.xml) `SPARK_HOME` di ambiente necessarie `~/bin/spark-2.3.2-bin-hadoop2.7/`(ad esempio, ) e `PATH` (ad esempio, `$SPARK_HOME/bin:$PATH`)

      ```bash
      export SPARK_HOME=~/bin/spark-2.3.2-hadoop2.7
      export PATH="$SPARK_HOME/bin:$PATH"
      source ~/.bashrc
      ```

      Si noti che queste variabili di ambiente andranno perse quando si chiude il terminale. Se si desidera che le modifiche `export` siano `~/.bashrc` permanenti, aggiungere le righe al file.

   * Verificare di essere `spark-shell` stati eseguiti dalla riga di comando.

      Output della console di esempio:

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

Assicurarsi di essere `dotnet`in `java` `mvn`grado `spark-shell` di eseguire , , , dalla riga di comando prima di passare alla sezione successiva. Senti che c'è un modo migliore? Si prega di [aprire un problema](https://github.com/dotnet/spark/issues) e sentitevi liberi di contribuire.

## <a name="build"></a>Compilare

Per il resto di questa guida, è necessario aver clonato il repository .NET for `~/dotnet.spark/`Apache Spark nel computer, ad esempio .

```bash
git clone https://github.com/dotnet/spark.git ~/dotnet.spark
```

### <a name="build-net-for-spark-scala-extensions-layer"></a>Creare il livello delle estensioni .NET per Spark ScalaBuild .NET for Spark Scala extensions layer

Quando si invia un'applicazione .NET, .NET per Apache Spark dispone della logica necessaria scritta in Scala che informa Apache Spark come gestire le richieste (ad esempio, richiedere di creare una nuova sessione Spark, richiesta di trasferire i dati dal lato .NET al lato JVM e così via). Questa logica è disponibile in [.NET per Apache Spark Scala Source Code](https://github.com/dotnet/spark/tree/master/src/scala).

Il passaggio successivo consiste nel compilare il livello di estensione .NET per Apache Spark Scala:The next step is to build the .NET for Apache Spark Scala extension layer:

```bash
cd src/scala
mvn clean package
```

Dovresti vedere i file JAR creati per le versioni Spark supportate:

* `microsoft-spark-2.3.x/target/microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x/target/microsoft-spark-2.4.x-<version>.jar`

### <a name="build-net-sample-applications-using-net-core-cli"></a>Creare applicazioni di esempio .NET usando l'interfaccia della riga di comando di .NET CoreBuild .NET sample applications using .NET Core CLI

In questa sezione viene illustrato come compilare le applicazioni di [esempio](https://github.com/dotnet/spark/tree/master/examples) per .NET per Apache Spark. Questi passaggi consentono di comprendere il processo di compilazione generale per qualsiasi .NET per l'applicazione Spark.These steps will help in understanding the overall building process for any .NET for Spark application.

1. Creare il worker:

   ```dotnetcli
   cd ~/dotnet.spark/src/csharp/Microsoft.Spark.Worker/
   dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   ```

   Output della console di esempio:

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

2. Compilare gli esempi:Build the samples:

   ```dotnetcli
   cd ~/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples/
   dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   ```

   Output della console di esempio:

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

## <a name="run-the-net-for-spark-sample-applications"></a>Eseguire .NET per le applicazioni di esempio SparkRun the .NET for Spark sample applications

Dopo aver compilato gli esempi, è possibile usare per inviare le app .NET Core.Once you build the samples, you can use `spark-submit` to submit your .NET Core apps. Assicurarsi di aver seguito la sezione [dei prerequisiti](#prerequisites) e di aver installato Apache Spark.

1. Impostare `DOTNET_WORKER_DIR` `PATH` la variabile di ambiente `Microsoft.Spark.Worker` o per includere il percorso `~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish`in cui è stato generato il file binario (ad esempio, ).

   ```bash
   export DOTNET_WORKER_DIR=~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish
   ```

2. Apri un terminale e vai alla directory in cui è `~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish`stato generato il file binario dell'app (ad esempio, ).

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

   Ecco alcuni esempi che puoi eseguire:

   * **[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Batch.Basic $SPARK_HOME/examples/src/main/resources/people.json
      ```

   * **[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredNetworkWordCount localhost 9999
      ```

   * **[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (maven accessibile)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

      ```bash
      spark-submit \
      --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
      ```

   * **[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (jars provided)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

      ```bash
      spark-submit \
      --jars path/to/net.jpountz.lz4/lz4-1.3.0.jar,path/to/org.apache.kafka/kafka-clients-0.10.0.1.jar,path/to/org.apache.spark/spark-sql-kafka-0-10_2.11-2.3.2.jar,`path/to/org.slf4j/slf4j-api-1.7.6.jar,path/to/org.spark-project.spark/unused-1.0.0.jar,path/to/org.xerial.snappy/snappy-java-1.1.2.6.jar \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
       ```

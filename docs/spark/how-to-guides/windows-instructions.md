---
title: Creare un'applicazione .NET per Apache Spark in Windows
description: Informazioni su come creare .NET per Apache Spark applicazione in Windows.
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: how-to
ms.openlocfilehash: 640459c8c80b6d798718b89d4965802cdacd6c63
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628657"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-windows"></a>Informazioni su come creare un'applicazione .NET per Apache Spark in Windows

Questo articolo illustra come creare .NET per applicazioni Apache Spark in Windows.

## <a name="prerequisites"></a>Prerequisites

Se sono già disponibili tutti i prerequisiti seguenti, passare alla procedura di [compilazione](#build) .

  1. Scaricare e installare il **[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** -l'installazione dell'SDK consente di aggiungere la `dotnet` di questo sistema al percorso. Sono supportati .NET Core 2,1, 2,2 e 3,1.
  2. Installare **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (versione 16,3 o successiva). La versione community è completamente gratuita. Quando si configura l'installazione, includere almeno questi componenti:
     * Sviluppo per desktop .NET
       * Tutti i componenti necessari
         * Strumenti di sviluppo per .NET Framework 4.6.1
     * Sviluppo multipiattaforma .NET Core
       * Tutti i componenti necessari
  3. Installare **[Java 1,8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)** . 
     - Selezionare la versione appropriata per il sistema operativo in uso. Ad esempio, *JDK-8u201-Windows-x64. exe* per computer Windows x64.
     - Installare usando il programma di installazione e verificare che sia possibile eseguire `java` dalla riga di comando.
  4. Installare **[Apache Maven 3.6.0 +](https://maven.apache.org/download.cgi)** .
     - Scaricare [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip).
     - Estrarre i file in una directory locale. Ad esempio, * C:\bin\apache-Maven-3.6.0\*.
     - Aggiungere Apache Maven alla [variabile di ambiente PATH](https://www.java.com/en/download/help/path.xml). Ad esempio, *C:\bin\apache-Maven-3.6.0\Bin*.
     - Verificare che sia possibile eseguire `mvn` dalla riga di comando.
  5. Installare **[Apache Spark 2.3 +](https://spark.apache.org/downloads.html)** .
     - Scaricare [Apache Spark 2.3 +](https://spark.apache.org/downloads.html) ed estrarlo in una cartella locale (ad esempio, *C:\bin\spark-2.3.2-bin-hadoop2.7\*) usando [7-zip](https://www.7-zip.org/). (Le versioni di Spark supportate sono 2,3.* , 2.4.0, 2.4.1, 2.4.3 e 2.4.4)
     - Aggiungere una [nuova variabile di ambiente](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`. Ad esempio, * C:\bin\spark-2.3.2-bin-hadoop2.7\*.

       ```powershell
       set SPARK_HOME=C:\bin\spark-2.3.2-bin-hadoop2.7\       
       ```

     - Aggiungere Apache Spark alla [variabile di ambiente PATH](https://www.java.com/en/download/help/path.xml). Ad esempio, *C:\bin\spark-2.3.2-bin-hadoop2.7\bin*.

       ```powershell       
       set PATH=%SPARK_HOME%\bin;%PATH%
       ```
     
     - Verificare che sia possibile eseguire `spark-shell` dalla riga di comando.        
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

        </details>

  6. Installare **[file winutils](https://github.com/steveloughran/winutils)** .
     - Scaricare `winutils.exe` Binary dal [repository file winutils](https://github.com/steveloughran/winutils). È necessario selezionare la versione di Hadoop con la quale è stata compilata la distribuzione Spark. Per exammple, usare Hadoop-2.7.1 per Spark 2.3.2.
     - Salvare `winutils.exe` file binario in una directory di propria scelta. Ad esempio, *C:\hadoop\bin*.
     - Impostare `HADOOP_HOME` per riflettere la directory con file winutils. exe (senza bin). Ad esempio, usando la riga di comando:

       ```powershell
       set HADOOP_HOME=C:\hadoop
       ```

     - Impostare la variabile di ambiente PATH in modo da includere `%HADOOP_HOME%\bin`. Ad esempio, usando la riga di comando:

       ```powershell
       set PATH=%HADOOP_HOME%\bin;%PATH%
       ```

Assicurarsi di essere in grado di eseguire `dotnet`, `java`, `mvn``spark-shell` dalla riga di comando prima di passare alla sezione successiva. Si ritiene che esista un metodo migliore? [Apri un problema](https://github.com/dotnet/spark/issues) e potrai collaborare.

> [!NOTE]
> Una nuova istanza della riga di comando può essere obbligatoria se sono state aggiornate variabili di ambiente.

## <a name="build"></a>Compilare

Per la parte restante di questa guida, è necessario aver clonato .NET per Apache Spark repository nel computer. È possibile scegliere qualsiasi percorso per il repository clonato. Ad esempio, * C:\github\dotnet-Spark\*.

```bash
git clone https://github.com/dotnet/spark.git C:\github\dotnet-spark
```

### <a name="build-net-for-apache-spark-scala-extensions-layer"></a>Compilazione di .NET per Apache Spark livello estensioni scala

Quando si invia un'applicazione .NET, .NET per Apache Spark ha la logica necessaria scritta in scala che informa Apache Spark come gestire le richieste (ad esempio, la richiesta di creare una nuova sessione di Spark, la richiesta di trasferimento dei dati dal lato .NET al lato JVM e così via). Questa logica si trova in [.NET per il codice sorgente Spark scala](https://github.com/dotnet/spark/tree/master/src/scala).

Indipendentemente dal fatto che si usi .NET Framework o .NET Core, sarà necessario compilare .NET per Apache Spark livello di estensione scala:

```powershell
cd src\scala
mvn clean package 
```

Verranno visualizzati i file jar creati per le versioni di Spark supportate:

* `microsoft-spark-2.3.x\target\microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x\target\microsoft-spark-2.4.x-<version>.jar`

### <a name="build-the-net-for-spark-sample-applications"></a>Compilare .NET per le applicazioni di esempio Spark

In questa sezione viene illustrato come compilare le [applicazioni di esempio](https://github.com/dotnet/spark/tree/master/examples) per .net per Apache Spark. Questi passaggi consentiranno di comprendere il processo di compilazione globale per qualsiasi applicazione .NET per Spark.

#### <a name="using-visual-studio-for-net-framework"></a>Uso di Visual Studio per .NET Framework

  1. Aprire `src\csharp\Microsoft.Spark.sln` in Visual Studio e compilare il progetto `Microsoft.Spark.CSharp.Examples` sotto la cartella `examples` (questo compilerà a sua volta anche il progetto di binding .NET). Se lo si desidera, è possibile scrivere codice personalizzato nel progetto `Microsoft.Spark.Examples` (' input_file. JSON ' in questo esempio è un file JSON con i dati con i quali si vuole creare il frame di dati):
  
      ```csharp
        // Instantiate a session
        var spark = SparkSession
            .Builder()
            .AppName("Hello Spark!")
            .GetOrCreate();

        // Create initial DataFrame
        DataFrame df = spark.Read().Json(input_file.json);

        // Print schema
        df.PrintSchema();

        // Apply a filter and show results
        df.Filter(df["age"] > 21).Show();
      ```

     Una volta completata la compilazione, i file binari appropriati generati nella directory di output vengono visualizzati.     
     Esempio di output della console:
     
      ```powershell
            Directory: C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461


        Mode                LastWriteTime         Length Name
        ----                -------------         ------ ----
        -a----         3/6/2019  12:18 AM         125440 Apache.Arrow.dll
        -a----        3/16/2019  12:00 AM          13824 Microsoft.Spark.CSharp.Examples.exe
        -a----        3/16/2019  12:00 AM          19423 Microsoft.Spark.CSharp.Examples.exe.config
        -a----        3/16/2019  12:00 AM           2720 Microsoft.Spark.CSharp.Examples.pdb
        -a----        3/16/2019  12:00 AM         143360 Microsoft.Spark.dll
        -a----        3/16/2019  12:00 AM          63388 Microsoft.Spark.pdb
        -a----        3/16/2019  12:00 AM          34304 Microsoft.Spark.Worker.exe
        -a----        3/16/2019  12:00 AM          19423 Microsoft.Spark.Worker.exe.config
        -a----        3/16/2019  12:00 AM          11900 Microsoft.Spark.Worker.pdb
        -a----        3/16/2019  12:00 AM          23552 Microsoft.Spark.Worker.xml
        -a----        3/16/2019  12:00 AM         332363 Microsoft.Spark.xml
        ------------------------------------------- More framework files -------------------------------------
      ```     

#### <a name="using-net-core-cli-for-net-core"></a>Uso di interfaccia della riga di comando di .NET Core per .NET Core

> [!NOTE]
> Attualmente si sta lavorando sull'automazione delle compilazioni .NET Core per Spark .NET. Fino ad allora, siamo lieti di eseguire alcuni passaggi manualmente.

  1. Creare il ruolo di lavoro:

      ```powershell
      cd C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```
      
      Esempio di output della console:

      ```powershell
      PS C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker> dotnet publish -f netcoreapp2.1 -r win10-x64
      Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
      Copyright (C) Microsoft Corporation. All rights reserved.

        Restore completed in 299.95 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark\Microsoft.Spark.csproj.
        Restore completed in 306.62 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\Microsoft.Spark.Worker.csproj.
        Microsoft.Spark -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark\Debug\netstandard2.0\Microsoft.Spark.dll
        Microsoft.Spark.Worker -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\Microsoft.Spark.Worker.dll
        Microsoft.Spark.Worker -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish\
      ```    

  2. Compilare gli esempi:

      ```powershell
      cd C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```
   
      Esempio di output della console:

      ```powershell
      PS C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples> dotnet publish -f netcoreapp2.1 -r win10-x64
      Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
      Copyright (C) Microsoft Corporation. All rights reserved.

        Restore completed in 44.22 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark\Microsoft.Spark.csproj.
        Restore completed in 336.94 ms for C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\Microsoft.Spark.CSharp.Examples.csproj.
        Microsoft.Spark -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark\Debug\netstandard2.0\Microsoft.Spark.dll
        Microsoft.Spark.CSharp.Examples -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\Microsoft.Spark.CSharp.Examples.dll
        Microsoft.Spark.CSharp.Examples -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish\
      ```     

## <a name="run-the-net-for-spark-sample-applications"></a>Eseguire .NET per applicazioni di esempio Spark

Una volta creati gli esempi, sarà possibile eseguirli tramite `spark-submit` indipendentemente dal fatto che la destinazione sia .NET Framework o .NET Core. Assicurarsi di aver seguito la sezione [prerequisiti](#prerequisites) e installato Apache Spark.

  1. Impostare la variabile di ambiente `DOTNET_WORKER_DIR` o `PATH` per includere il percorso in cui è stato generato il file binario `Microsoft.Spark.Worker` (ad esempio, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461* per .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish* per .NET Core):

      ```powershell
      set DOTNET_WORKER_DIR=C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish
      ```
  
  2. Aprire PowerShell e passare alla directory in cui è stato generato il file binario dell'app, ad esempio *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461* per .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish* per .NET Core:

      ```powershell
      cd C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish
      ```

  3. L'esecuzione dell'app segue la struttura di base:

     ```powershell
     spark-submit.cmd `
       [--jars <any-jars-your-app-is-dependent-on>] `
       --class org.apache.spark.deploy.dotnet.DotnetRunner `
       --master local `
       <path-to-microsoft-spark-jar> `
       <path-to-your-app-exe> <argument(s)-to-your-app>
     ```

     Di seguito sono riportati alcuni esempi che è possibile eseguire:

     - **[Microsoft. Spark. examples. SQL. batch. Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Batch.Basic %SPARK_HOME%\examples\src\main\resources\people.json
         ```

     - **[Microsoft. Spark. examples. SQL. streaming. StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkWordCount localhost 9999
         ```

     - **[Microsoft. Spark. examples. SQL. streaming. StructuredKafkaWordCount (Maven accessibile)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

         ```powershell
         spark-submit.cmd `
         --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
         ```

     - **[Microsoft. Spark. examples. SQL. streaming. StructuredKafkaWordCount (jar forniti)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

         ```powershell
         spark-submit.cmd 
         --jars path\to\net.jpountz.lz4\lz4-1.3.0.jar,path\to\org.apache.kafka\kafka-clients-0.10.0.1.jar,path\to\org.apache.spark\spark-sql-kafka-0-10_2.11-2.3.2.jar,`path\to\org.slf4j\slf4j-api-1.7.6.jar,path\to\org.spark-project.spark\unused-1.0.0.jar,path\to\org.xerial.snappy\snappy-java-1.1.2.6.jar `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
          ```

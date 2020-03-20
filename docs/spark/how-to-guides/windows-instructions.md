---
title: Creare un'applicazione .NET per Apache Spark in Windows
description: Informazioni su come creare l'applicazione .NET per Apache Spark in Windows.
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: how-to
ms.openlocfilehash: cb7154185fc9aa08bc447cb846798995301a6651
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79185752"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-windows"></a><span data-ttu-id="c7237-103">Scopri come creare l'applicazione .NET per Apache Spark in Windows</span><span class="sxs-lookup"><span data-stu-id="c7237-103">Learn how to build your .NET for Apache Spark application on Windows</span></span>

<span data-ttu-id="c7237-104">Questo articolo illustra come creare le applicazioni .NET for Apache Spark in Windows.</span><span class="sxs-lookup"><span data-stu-id="c7237-104">This article teaches you how to build your .NET for Apache Spark applications on Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c7237-105">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="c7237-105">Prerequisites</span></span>

<span data-ttu-id="c7237-106">Se si dispone già di tutti i prerequisiti seguenti, passare alle istruzioni di [compilazione.](#build)</span><span class="sxs-lookup"><span data-stu-id="c7237-106">If you already have all of the following prerequisites, skip to the [build](#build) steps.</span></span>

  1. <span data-ttu-id="c7237-107">Scaricare e installare **[.NET Core SDK:](https://dotnet.microsoft.com/download/dotnet-core/2.1)** l'installazione dell'SDK aggiungerà la `dotnet` toolchain al percorso.</span><span class="sxs-lookup"><span data-stu-id="c7237-107">Download and install the **[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** - installing the SDK will add the `dotnet` toolchain to your path.</span></span> <span data-ttu-id="c7237-108">.NET Core 2.1, 2.2 e 3.1 sono supportati.</span><span class="sxs-lookup"><span data-stu-id="c7237-108">.NET Core 2.1, 2.2 and 3.1 are supported.</span></span>
  2. <span data-ttu-id="c7237-109">Installare **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (versione 16.3 o successiva).</span><span class="sxs-lookup"><span data-stu-id="c7237-109">Install **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (Version 16.3 or later).</span></span> <span data-ttu-id="c7237-110">La versione Community è completamente gratuita.</span><span class="sxs-lookup"><span data-stu-id="c7237-110">The Community version is completely free.</span></span> <span data-ttu-id="c7237-111">Quando si configura l'installazione, includere almeno questi componenti:</span><span class="sxs-lookup"><span data-stu-id="c7237-111">When configuring your installation, include these components at minimum:</span></span>
     * <span data-ttu-id="c7237-112">Sviluppo per desktop .NET</span><span class="sxs-lookup"><span data-stu-id="c7237-112">.NET desktop development</span></span>
       * <span data-ttu-id="c7237-113">Tutti i componenti necessari</span><span class="sxs-lookup"><span data-stu-id="c7237-113">All Required Components</span></span>
         * <span data-ttu-id="c7237-114">Strumenti di sviluppo per .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="c7237-114">.NET Framework 4.6.1 Development Tools</span></span>
     * <span data-ttu-id="c7237-115">Sviluppo multipiattaforma .NET Core</span><span class="sxs-lookup"><span data-stu-id="c7237-115">.NET Core cross-platform development</span></span>
       * <span data-ttu-id="c7237-116">Tutti i componenti necessari</span><span class="sxs-lookup"><span data-stu-id="c7237-116">All Required Components</span></span>
  3. <span data-ttu-id="c7237-117">Installare **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)**.</span><span class="sxs-lookup"><span data-stu-id="c7237-117">Install **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)**.</span></span>
     - <span data-ttu-id="c7237-118">Selezionare la versione appropriata per il sistema operativo in uso.</span><span class="sxs-lookup"><span data-stu-id="c7237-118">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="c7237-119">Ad esempio, *jdk-8u201-windows-x64.exe* per computer Windows x64.</span><span class="sxs-lookup"><span data-stu-id="c7237-119">For example, *jdk-8u201-windows-x64.exe* for Windows x64 machine.</span></span>
     - <span data-ttu-id="c7237-120">Eseguire l'installazione utilizzando il programma `java` di installazione e verificare che sia possibile eseguire dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c7237-120">Install using the installer and verify you are able to run `java` from your command line.</span></span>
  4. <span data-ttu-id="c7237-121">Installare **[Apache Maven 3.6.0](https://maven.apache.org/download.cgi)**.</span><span class="sxs-lookup"><span data-stu-id="c7237-121">Install **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)**.</span></span>
     - <span data-ttu-id="c7237-122">Scaricare [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip).</span><span class="sxs-lookup"><span data-stu-id="c7237-122">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip).</span></span>
     - <span data-ttu-id="c7237-123">Estrarre i file in una directory locale.</span><span class="sxs-lookup"><span data-stu-id="c7237-123">Extract to a local directory.</span></span> <span data-ttu-id="c7237-124">Ad esempio, "C:"bin" apache-maven-3.6.0\*.</span><span class="sxs-lookup"><span data-stu-id="c7237-124">For example, \*C:\bin\apache-maven-3.6.0\*.</span></span>
     - <span data-ttu-id="c7237-125">Aggiungere Apache Maven alla [variabile di ambiente PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="c7237-125">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="c7237-126">Ad esempio, *C:.bin apache-maven-3.6.0.bin*.</span><span class="sxs-lookup"><span data-stu-id="c7237-126">For example, *C:\bin\apache-maven-3.6.0\bin*.</span></span>
     - <span data-ttu-id="c7237-127">Verificare di essere `mvn` stati eseguiti dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c7237-127">Verify you are able to run `mvn` from your command-line.</span></span>
  5. <span data-ttu-id="c7237-128">Installare **[Apache Spark 2.3](https://spark.apache.org/downloads.html)**.</span><span class="sxs-lookup"><span data-stu-id="c7237-128">Install **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)**.</span></span>
     - <span data-ttu-id="c7237-129">Scaricare [Apache Spark 2.3](https://spark.apache.org/downloads.html) ed estrarlo in una cartella locale (ad esempio, *C:\* [7-zip](https://www.7-zip.org/) (Le versioni di spark supportate sono 2.3.*, 2.4.0, 2.4.1, 2.4.3 e 2.4.4)</span><span class="sxs-lookup"><span data-stu-id="c7237-129">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder (for example, *C:\bin\spark-2.3.2-bin-hadoop2.7\*) using [7-zip](https://www.7-zip.org/). (The supported spark versions are 2.3.*, 2.4.0, 2.4.1, 2.4.3 and 2.4.4)</span></span>
     - <span data-ttu-id="c7237-130">Aggiungere una [nuova variabile](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`di ambiente .</span><span class="sxs-lookup"><span data-stu-id="c7237-130">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`.</span></span> <span data-ttu-id="c7237-131">Ad esempio, spark-2.3.2-bin-hadoop2.7\*.</span><span class="sxs-lookup"><span data-stu-id="c7237-131">For example, \*C:\bin\spark-2.3.2-bin-hadoop2.7\*.</span></span>

       ```powershell
       set SPARK_HOME=C:\bin\spark-2.3.2-bin-hadoop2.7\
       ```

     - <span data-ttu-id="c7237-132">Aggiungere Apache Spark alla [variabile di ambiente PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="c7237-132">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="c7237-133">Ad esempio, *C:.bin spark-2.3.2-bin-hadoop2.7.bin*.</span><span class="sxs-lookup"><span data-stu-id="c7237-133">For example, *C:\bin\spark-2.3.2-bin-hadoop2.7\bin*.</span></span>

       ```powershell
       set PATH=%SPARK_HOME%\bin;%PATH%
       ```

     - <span data-ttu-id="c7237-134">Verificare di essere `spark-shell` stati eseguiti dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c7237-134">Verify you are able to run `spark-shell` from your command-line.</span></span>
        <span data-ttu-id="c7237-135">Output della console di esempio:</span><span class="sxs-lookup"><span data-stu-id="c7237-135">Sample console output:</span></span>

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

  6. <span data-ttu-id="c7237-136">Installare **[WinUtils](https://github.com/steveloughran/winutils)**.</span><span class="sxs-lookup"><span data-stu-id="c7237-136">Install **[WinUtils](https://github.com/steveloughran/winutils)**.</span></span>
     - <span data-ttu-id="c7237-137">Scaricare `winutils.exe` il file binario dal [repository WinUtils](https://github.com/steveloughran/winutils).</span><span class="sxs-lookup"><span data-stu-id="c7237-137">Download `winutils.exe` binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="c7237-138">È necessario selezionare la versione di Hadoop con cui è stata compilata la distribuzione Spark.</span><span class="sxs-lookup"><span data-stu-id="c7237-138">You should select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="c7237-139">Per exammple, utilizzare hadoop-2.7.1 per Spark 2.3.2.</span><span class="sxs-lookup"><span data-stu-id="c7237-139">For exammple, use hadoop-2.7.1 for Spark 2.3.2.</span></span>
     - <span data-ttu-id="c7237-140">Salvare `winutils.exe` il file binario in una directory di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="c7237-140">Save `winutils.exe` binary to a directory of your choice.</span></span> <span data-ttu-id="c7237-141">Ad esempio, *C:.*</span><span class="sxs-lookup"><span data-stu-id="c7237-141">For example, *C:\hadoop\bin*.</span></span>
     - <span data-ttu-id="c7237-142">Impostare `HADOOP_HOME` per riflettere la directory con winutils.exe (senza bin).</span><span class="sxs-lookup"><span data-stu-id="c7237-142">Set `HADOOP_HOME` to reflect the directory with winutils.exe (without bin).</span></span> <span data-ttu-id="c7237-143">Ad esempio, utilizzando la riga di comando:</span><span class="sxs-lookup"><span data-stu-id="c7237-143">For instance, using command-line:</span></span>

       ```powershell
       set HADOOP_HOME=C:\hadoop
       ```

     - <span data-ttu-id="c7237-144">Impostare la variabile `%HADOOP_HOME%\bin`di ambiente PATH in modo da includere .</span><span class="sxs-lookup"><span data-stu-id="c7237-144">Set PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span> <span data-ttu-id="c7237-145">Ad esempio, utilizzando la riga di comando:</span><span class="sxs-lookup"><span data-stu-id="c7237-145">For instance, using command line:</span></span>

       ```powershell
       set PATH=%HADOOP_HOME%\bin;%PATH%
       ```

<span data-ttu-id="c7237-146">Assicurarsi di essere `dotnet`in `java` `mvn`grado `spark-shell` di eseguire , , , dalla riga di comando prima di passare alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="c7237-146">Make sure you are able to run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span> <span data-ttu-id="c7237-147">Senti che c'è un modo migliore?</span><span class="sxs-lookup"><span data-stu-id="c7237-147">Feel there is a better way?</span></span> <span data-ttu-id="c7237-148">[Apri un problema](https://github.com/dotnet/spark/issues) e sentiti libero di contribuire.</span><span class="sxs-lookup"><span data-stu-id="c7237-148">[Open an issue](https://github.com/dotnet/spark/issues) and feel free to contribute.</span></span>

> [!NOTE]
> <span data-ttu-id="c7237-149">Se sono state aggiornate variabili di ambiente, potrebbe essere necessaria una nuova istanza della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c7237-149">A new instance of the command line may be required if any environment variables were updated.</span></span>

## <a name="build"></a><span data-ttu-id="c7237-150">Compilare</span><span class="sxs-lookup"><span data-stu-id="c7237-150">Build</span></span>

<span data-ttu-id="c7237-151">Per il resto di questa guida, è necessario aver clonato il repository .NET per Apache Spark nel computer.</span><span class="sxs-lookup"><span data-stu-id="c7237-151">For the remainder of this guide, you will need to have cloned the .NET for Apache Spark repository into your machine.</span></span> <span data-ttu-id="c7237-152">È possibile scegliere qualsiasi posizione per il repository clonato.</span><span class="sxs-lookup"><span data-stu-id="c7237-152">You can choose any location for the cloned repository.</span></span> <span data-ttu-id="c7237-153">Ad esempio, spark di sè\*:</span><span class="sxs-lookup"><span data-stu-id="c7237-153">For example, \*C:\github\dotnet-spark\*.</span></span>

```bash
git clone https://github.com/dotnet/spark.git C:\github\dotnet-spark
```

### <a name="build-net-for-apache-spark-scala-extensions-layer"></a><span data-ttu-id="c7237-154">Creare il livello delle estensioni .NET for Apache Spark Scala</span><span class="sxs-lookup"><span data-stu-id="c7237-154">Build .NET for Apache Spark Scala extensions layer</span></span>

<span data-ttu-id="c7237-155">Quando si invia un'applicazione .NET, .NET per Apache Spark dispone della logica necessaria scritta in Scala che informa Apache Spark come gestire le richieste (ad esempio, richiedere di creare una nuova sessione Spark, richiedere di trasferire i dati dal lato .NET al lato JVM e così via).</span><span class="sxs-lookup"><span data-stu-id="c7237-155">When you submit a .NET application, .NET for Apache Spark has the necessary logic written in Scala that informs Apache Spark how to handle your requests (for example, request to create a new Spark Session, request to transfer data from .NET side to JVM side etc.).</span></span> <span data-ttu-id="c7237-156">Questa logica è disponibile in [.NET per Spark Scala Source Code](https://github.com/dotnet/spark/tree/master/src/scala).</span><span class="sxs-lookup"><span data-stu-id="c7237-156">This logic can be found in the [.NET for Spark Scala Source Code](https://github.com/dotnet/spark/tree/master/src/scala).</span></span>

<span data-ttu-id="c7237-157">Indipendentemente dal fatto che si utilizzi .NET Framework o .NET Core, sarà necessario compilare il livello di estensione di .NET per Apache Spark Scala:</span><span class="sxs-lookup"><span data-stu-id="c7237-157">Regardless of whether you are using .NET Framework or .NET Core, you will need to build the .NET for Apache Spark Scala extension layer:</span></span>

```powershell
cd src\scala
mvn clean package
```

<span data-ttu-id="c7237-158">Dovresti vedere i file JAR creati per le versioni Spark supportate:</span><span class="sxs-lookup"><span data-stu-id="c7237-158">You should see JARs created for the supported Spark versions:</span></span>

* `microsoft-spark-2.3.x\target\microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x\target\microsoft-spark-2.4.x-<version>.jar`

### <a name="build-the-net-for-spark-sample-applications"></a><span data-ttu-id="c7237-159">Compilare .NET per le applicazioni di esempio SparkBuild the .NET for Spark sample applications</span><span class="sxs-lookup"><span data-stu-id="c7237-159">Build the .NET for Spark sample applications</span></span>

<span data-ttu-id="c7237-160">In questa sezione viene illustrato come compilare le applicazioni di [esempio](https://github.com/dotnet/spark/tree/master/examples) per .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="c7237-160">This section explains how to build the [sample applications](https://github.com/dotnet/spark/tree/master/examples) for .NET for Apache Spark.</span></span> <span data-ttu-id="c7237-161">Questi passaggi consentono di comprendere il processo di compilazione generale per qualsiasi .NET per l'applicazione Spark.These steps will help in understanding the overall building process for any .NET for Spark application.</span><span class="sxs-lookup"><span data-stu-id="c7237-161">These steps will help in understanding the overall building process for any .NET for Spark application.</span></span>

#### <a name="using-visual-studio-for-net-framework"></a><span data-ttu-id="c7237-162">Utilizzo di Visual Studio per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c7237-162">Using Visual Studio for .NET Framework</span></span>

  1. <span data-ttu-id="c7237-163">Aprire `src\csharp\Microsoft.Spark.sln` in Visual Studio `Microsoft.Spark.CSharp.Examples` e `examples` compilare il progetto nella cartella (questo a sua volta compilare anche il progetto di associazioni .NET).</span><span class="sxs-lookup"><span data-stu-id="c7237-163">Open `src\csharp\Microsoft.Spark.sln` in Visual Studio and build the `Microsoft.Spark.CSharp.Examples` project under the `examples` folder (this will in turn build the .NET bindings project as well).</span></span> <span data-ttu-id="c7237-164">Se si desidera, è possibile scrivere `Microsoft.Spark.Examples` il proprio codice nel progetto (il 'input_file.json' in questo esempio è un file json con i dati con cui si desidera creare il frame di dati):</span><span class="sxs-lookup"><span data-stu-id="c7237-164">If you want, you can write your own code in the `Microsoft.Spark.Examples` project (the 'input_file.json' in this example is a json file with the data you want to create the dataframe with):</span></span>
  
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

     <span data-ttu-id="c7237-165">Una volta completata la compilazione, verranno visualizzati i file binari appropriati prodotti nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="c7237-165">Once the build is successful, you will see the appropriate binaries produced in the output directory.</span></span>
     <span data-ttu-id="c7237-166">Output della console di esempio:</span><span class="sxs-lookup"><span data-stu-id="c7237-166">Sample console output:</span></span>

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

#### <a name="using-net-core-cli-for-net-core"></a><span data-ttu-id="c7237-167">Uso dell'interfaccia della riga di comando di .NET Core per .NET CoreUsing .NET Core CLI for .NET Core</span><span class="sxs-lookup"><span data-stu-id="c7237-167">Using .NET Core CLI for .NET Core</span></span>

> [!NOTE]
> <span data-ttu-id="c7237-168">Attualmente stiamo lavorando sull'automazione delle build di .NET Core per Spark .NET.</span><span class="sxs-lookup"><span data-stu-id="c7237-168">We are currently working on automating .NET Core builds for Spark .NET.</span></span> <span data-ttu-id="c7237-169">Fino ad allora, apprezziamo la vostra pazienza nell'eseguire alcuni dei passaggi manualmente.</span><span class="sxs-lookup"><span data-stu-id="c7237-169">Until then, we appreciate your patience in performing some of the steps manually.</span></span>

  1. <span data-ttu-id="c7237-170">Creare il worker:</span><span class="sxs-lookup"><span data-stu-id="c7237-170">Build the worker:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```

      <span data-ttu-id="c7237-171">Output della console di esempio:</span><span class="sxs-lookup"><span data-stu-id="c7237-171">Sample console output:</span></span>

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

  2. <span data-ttu-id="c7237-172">Compilare gli esempi:Build the samples:</span><span class="sxs-lookup"><span data-stu-id="c7237-172">Build the samples:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```

      <span data-ttu-id="c7237-173">Output della console di esempio:</span><span class="sxs-lookup"><span data-stu-id="c7237-173">Sample console output:</span></span>

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

## <a name="run-the-net-for-spark-sample-applications"></a><span data-ttu-id="c7237-174">Eseguire .NET per le applicazioni di esempio SparkRun the .NET for Spark sample applications</span><span class="sxs-lookup"><span data-stu-id="c7237-174">Run the .NET for Spark sample applications</span></span>

<span data-ttu-id="c7237-175">Una volta compilati gli esempi, `spark-submit` eseguirli avverrà indipendentemente dal fatto che la destinazione sia .NET Framework o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c7237-175">Once you build the samples, running them will be through `spark-submit` regardless of whether you are targeting .NET Framework or .NET Core.</span></span> <span data-ttu-id="c7237-176">Assicurarsi di aver seguito la sezione [dei prerequisiti](#prerequisites) e di aver installato Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="c7237-176">Make sure you have followed the [prerequisites](#prerequisites) section and installed Apache Spark.</span></span>

  1. <span data-ttu-id="c7237-177">Impostare `DOTNET_WORKER_DIR` `PATH` la variabile di ambiente `Microsoft.Spark.Worker` o in modo da includere il percorso in cui è stato generato il file binario (ad esempio, *C:* *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish*</span><span class="sxs-lookup"><span data-stu-id="c7237-177">Set the `DOTNET_WORKER_DIR` or `PATH` environment variable to include the path where the `Microsoft.Spark.Worker` binary has been generated (for example, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461* for .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish* for .NET Core):</span></span>

      ```powershell
      set DOTNET_WORKER_DIR=C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish
      ```
  
  2. <span data-ttu-id="c7237-178">Aprire Powershell e passare alla directory in cui è stato generato il file binario dell'app (ad esempio, *C:* *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish*</span><span class="sxs-lookup"><span data-stu-id="c7237-178">Open Powershell and go to the directory where your app binary has been generated (for example, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461* for .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish* for .NET Core):</span></span>

      ```powershell
      cd C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish
      ```

  3. <span data-ttu-id="c7237-179">L'esecuzione dell'app segue la struttura di base:</span><span class="sxs-lookup"><span data-stu-id="c7237-179">Running your app follows the basic structure:</span></span>

     ```powershell
     spark-submit.cmd `
       [--jars <any-jars-your-app-is-dependent-on>] `
       --class org.apache.spark.deploy.dotnet.DotnetRunner `
       --master local `
       <path-to-microsoft-spark-jar> `
       <path-to-your-app-exe> <argument(s)-to-your-app>
     ```

     <span data-ttu-id="c7237-180">Ecco alcuni esempi che puoi eseguire:</span><span class="sxs-lookup"><span data-stu-id="c7237-180">Here are some examples you can run:</span></span>

     - <span data-ttu-id="c7237-181">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span><span class="sxs-lookup"><span data-stu-id="c7237-181">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Batch.Basic %SPARK_HOME%\examples\src\main\resources\people.json
         ```

     - <span data-ttu-id="c7237-182">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="c7237-182">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkWordCount localhost 9999
         ```

     - <span data-ttu-id="c7237-183">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (maven accessibile)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="c7237-183">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (maven accessible)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
         ```

     - <span data-ttu-id="c7237-184">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (jars provided)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="c7237-184">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (jars provided)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd
         --jars path\to\net.jpountz.lz4\lz4-1.3.0.jar,path\to\org.apache.kafka\kafka-clients-0.10.0.1.jar,path\to\org.apache.spark\spark-sql-kafka-0-10_2.11-2.3.2.jar,`path\to\org.slf4j\slf4j-api-1.7.6.jar,path\to\org.spark-project.spark\unused-1.0.0.jar,path\to\org.xerial.snappy\snappy-java-1.1.2.6.jar `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
          ```

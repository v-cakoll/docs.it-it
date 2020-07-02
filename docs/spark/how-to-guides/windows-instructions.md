---
title: Creare un'applicazione .NET per Apache Spark in Windows
description: Informazioni su come creare .NET per Apache Spark applicazione in Windows.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: how-to
ms.openlocfilehash: 6d52e5be8c8e528880eece5a9b46fb08933c1eb3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617665"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-windows"></a><span data-ttu-id="85e6a-103">Informazioni su come creare un'applicazione .NET per Apache Spark in Windows</span><span class="sxs-lookup"><span data-stu-id="85e6a-103">Learn how to build your .NET for Apache Spark application on Windows</span></span>

<span data-ttu-id="85e6a-104">Questo articolo illustra come creare .NET per applicazioni Apache Spark in Windows.</span><span class="sxs-lookup"><span data-stu-id="85e6a-104">This article teaches you how to build your .NET for Apache Spark applications on Windows.</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a><span data-ttu-id="85e6a-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="85e6a-105">Prerequisites</span></span>

<span data-ttu-id="85e6a-106">Se sono già disponibili tutti i prerequisiti seguenti, passare alla procedura di [compilazione](#build) .</span><span class="sxs-lookup"><span data-stu-id="85e6a-106">If you already have all of the following prerequisites, skip to the [build](#build) steps.</span></span>

  1. <span data-ttu-id="85e6a-107">Scaricare e installare il **[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** -l'installazione dell'SDK consente di aggiungere la relativa pagina `dotnet` al percorso.</span><span class="sxs-lookup"><span data-stu-id="85e6a-107">Download and install the **[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** - installing the SDK will add the `dotnet` toolchain to your path.</span></span> <span data-ttu-id="85e6a-108">Sono supportati .NET Core 2,1, 2,2 e 3,1.</span><span class="sxs-lookup"><span data-stu-id="85e6a-108">.NET Core 2.1, 2.2 and 3.1 are supported.</span></span>
  2. <span data-ttu-id="85e6a-109">Installare **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (versione 16,3 o successiva).</span><span class="sxs-lookup"><span data-stu-id="85e6a-109">Install **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (Version 16.3 or later).</span></span> <span data-ttu-id="85e6a-110">La versione community è completamente gratuita.</span><span class="sxs-lookup"><span data-stu-id="85e6a-110">The Community version is completely free.</span></span> <span data-ttu-id="85e6a-111">Quando si configura l'installazione, includere almeno questi componenti:</span><span class="sxs-lookup"><span data-stu-id="85e6a-111">When configuring your installation, include these components at minimum:</span></span>
     * <span data-ttu-id="85e6a-112">Sviluppo per desktop .NET</span><span class="sxs-lookup"><span data-stu-id="85e6a-112">.NET desktop development</span></span>
       * <span data-ttu-id="85e6a-113">Tutti i componenti necessari</span><span class="sxs-lookup"><span data-stu-id="85e6a-113">All Required Components</span></span>
         * <span data-ttu-id="85e6a-114">Strumenti di sviluppo per .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="85e6a-114">.NET Framework 4.6.1 Development Tools</span></span>
     * <span data-ttu-id="85e6a-115">Sviluppo multipiattaforma .NET Core</span><span class="sxs-lookup"><span data-stu-id="85e6a-115">.NET Core cross-platform development</span></span>
       * <span data-ttu-id="85e6a-116">Tutti i componenti necessari</span><span class="sxs-lookup"><span data-stu-id="85e6a-116">All Required Components</span></span>
  3. <span data-ttu-id="85e6a-117">Installare **[Java 1,8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)**.</span><span class="sxs-lookup"><span data-stu-id="85e6a-117">Install **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)**.</span></span>
     - <span data-ttu-id="85e6a-118">Selezionare la versione appropriata per il sistema operativo in uso.</span><span class="sxs-lookup"><span data-stu-id="85e6a-118">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="85e6a-119">Ad esempio, *jdk-8u201-windows-x64.exe* per computer Windows x64.</span><span class="sxs-lookup"><span data-stu-id="85e6a-119">For example, *jdk-8u201-windows-x64.exe* for Windows x64 machine.</span></span>
     - <span data-ttu-id="85e6a-120">Installare usando il programma di installazione e verificare che sia possibile eseguire `java` dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="85e6a-120">Install using the installer and verify you are able to run `java` from your command line.</span></span>
  4. <span data-ttu-id="85e6a-121">Installare **[Apache Maven 3.6.0 +](https://maven.apache.org/download.cgi)**.</span><span class="sxs-lookup"><span data-stu-id="85e6a-121">Install **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)**.</span></span>
     - <span data-ttu-id="85e6a-122">Scaricare [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip).</span><span class="sxs-lookup"><span data-stu-id="85e6a-122">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip).</span></span>
     - <span data-ttu-id="85e6a-123">Estrarre i file in una directory locale.</span><span class="sxs-lookup"><span data-stu-id="85e6a-123">Extract to a local directory.</span></span> <span data-ttu-id="85e6a-124">Ad esempio \* C:\bin\apache-Maven-3.6.0 \* .</span><span class="sxs-lookup"><span data-stu-id="85e6a-124">For example, \*C:\bin\apache-maven-3.6.0\*.</span></span>
     - <span data-ttu-id="85e6a-125">Aggiungere Apache Maven alla [variabile di ambiente PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="85e6a-125">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="85e6a-126">Ad esempio, *C:\bin\apache-Maven-3.6.0\Bin*.</span><span class="sxs-lookup"><span data-stu-id="85e6a-126">For example, *C:\bin\apache-maven-3.6.0\bin*.</span></span>
     - <span data-ttu-id="85e6a-127">Verificare che sia possibile eseguire `mvn` dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="85e6a-127">Verify you are able to run `mvn` from your command-line.</span></span>
  5. <span data-ttu-id="85e6a-128">Installare **[Apache Spark 2.3 +](https://spark.apache.org/downloads.html)**.</span><span class="sxs-lookup"><span data-stu-id="85e6a-128">Install **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)**.</span></span>
     - <span data-ttu-id="85e6a-129">Scaricare [Apache Spark 2.3 +](https://spark.apache.org/downloads.html) ed estrarlo in una cartella locale (ad esempio, *C:\bin\spark-2.3.2-bin-hadoop2.7 \* ) usando [7-zip](https://www.7-zip.org/). (Le versioni di Spark supportate sono 2,3.*, 2.4.0, 2.4.1, 2.4.3 e 2.4.4)</span><span class="sxs-lookup"><span data-stu-id="85e6a-129">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder (for example, *C:\bin\spark-2.3.2-bin-hadoop2.7\*) using [7-zip](https://www.7-zip.org/). (The supported spark versions are 2.3.*, 2.4.0, 2.4.1, 2.4.3 and 2.4.4)</span></span>
     - <span data-ttu-id="85e6a-130">Aggiungere una [nuova variabile di ambiente](https://www.java.com/en/download/help/path.xml) `SPARK_HOME` .</span><span class="sxs-lookup"><span data-stu-id="85e6a-130">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`.</span></span> <span data-ttu-id="85e6a-131">Ad esempio \* C:\bin\spark-2.3.2-bin-hadoop2.7 \* .</span><span class="sxs-lookup"><span data-stu-id="85e6a-131">For example, \*C:\bin\spark-2.3.2-bin-hadoop2.7\*.</span></span>

       ```powershell
       set SPARK_HOME=C:\bin\spark-2.3.2-bin-hadoop2.7\
       ```

     - <span data-ttu-id="85e6a-132">Aggiungere Apache Spark alla [variabile di ambiente PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="85e6a-132">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="85e6a-133">Ad esempio, *C:\bin\spark-2.3.2-bin-hadoop2.7\bin*.</span><span class="sxs-lookup"><span data-stu-id="85e6a-133">For example, *C:\bin\spark-2.3.2-bin-hadoop2.7\bin*.</span></span>

       ```powershell
       set PATH=%SPARK_HOME%\bin;%PATH%
       ```

     - <span data-ttu-id="85e6a-134">Verificare che sia possibile eseguire `spark-shell` dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="85e6a-134">Verify you are able to run `spark-shell` from your command-line.</span></span>
        <span data-ttu-id="85e6a-135">Esempio di output della console:</span><span class="sxs-lookup"><span data-stu-id="85e6a-135">Sample console output:</span></span>

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

  6. <span data-ttu-id="85e6a-136">Installare **[file winutils](https://github.com/steveloughran/winutils)**.</span><span class="sxs-lookup"><span data-stu-id="85e6a-136">Install **[WinUtils](https://github.com/steveloughran/winutils)**.</span></span>
     - <span data-ttu-id="85e6a-137">Scaricare il `winutils.exe` file binario dal [repository file winutils](https://github.com/steveloughran/winutils).</span><span class="sxs-lookup"><span data-stu-id="85e6a-137">Download `winutils.exe` binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="85e6a-138">È necessario selezionare la versione di Hadoop con la quale è stata compilata la distribuzione Spark.</span><span class="sxs-lookup"><span data-stu-id="85e6a-138">You should select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="85e6a-139">Per exammple, usare Hadoop-2.7.1 per Spark 2.3.2.</span><span class="sxs-lookup"><span data-stu-id="85e6a-139">For exammple, use hadoop-2.7.1 for Spark 2.3.2.</span></span>
     - <span data-ttu-id="85e6a-140">Salvare `winutils.exe` il file binario in una directory di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="85e6a-140">Save `winutils.exe` binary to a directory of your choice.</span></span> <span data-ttu-id="85e6a-141">Ad esempio, *C:\hadoop\bin*.</span><span class="sxs-lookup"><span data-stu-id="85e6a-141">For example, *C:\hadoop\bin*.</span></span>
     - <span data-ttu-id="85e6a-142">Impostare `HADOOP_HOME` per riflettere la directory con winutils.exe (senza bin).</span><span class="sxs-lookup"><span data-stu-id="85e6a-142">Set `HADOOP_HOME` to reflect the directory with winutils.exe (without bin).</span></span> <span data-ttu-id="85e6a-143">Ad esempio, usando la riga di comando:</span><span class="sxs-lookup"><span data-stu-id="85e6a-143">For instance, using command-line:</span></span>

       ```powershell
       set HADOOP_HOME=C:\hadoop
       ```

     - <span data-ttu-id="85e6a-144">Imposta la variabile di ambiente PATH da includere `%HADOOP_HOME%\bin` .</span><span class="sxs-lookup"><span data-stu-id="85e6a-144">Set PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span> <span data-ttu-id="85e6a-145">Ad esempio, usando la riga di comando:</span><span class="sxs-lookup"><span data-stu-id="85e6a-145">For instance, using command line:</span></span>

       ```powershell
       set PATH=%HADOOP_HOME%\bin;%PATH%
       ```

<span data-ttu-id="85e6a-146">Assicurarsi di essere in grado di eseguire `dotnet` , `java` , `mvn` , `spark-shell` dalla riga di comando prima di passare alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="85e6a-146">Make sure you are able to run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span> <span data-ttu-id="85e6a-147">Si ritiene che esista un metodo migliore?</span><span class="sxs-lookup"><span data-stu-id="85e6a-147">Feel there is a better way?</span></span> <span data-ttu-id="85e6a-148">[Apri un problema](https://github.com/dotnet/spark/issues) e potrai collaborare.</span><span class="sxs-lookup"><span data-stu-id="85e6a-148">[Open an issue](https://github.com/dotnet/spark/issues) and feel free to contribute.</span></span>

> [!NOTE]
> <span data-ttu-id="85e6a-149">Una nuova istanza della riga di comando può essere obbligatoria se sono state aggiornate variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="85e6a-149">A new instance of the command line may be required if any environment variables were updated.</span></span>

## <a name="build"></a><span data-ttu-id="85e6a-150">Compilare</span><span class="sxs-lookup"><span data-stu-id="85e6a-150">Build</span></span>

<span data-ttu-id="85e6a-151">Per la parte restante di questa guida, è necessario aver clonato .NET per Apache Spark repository nel computer.</span><span class="sxs-lookup"><span data-stu-id="85e6a-151">For the remainder of this guide, you will need to have cloned the .NET for Apache Spark repository into your machine.</span></span> <span data-ttu-id="85e6a-152">È possibile scegliere qualsiasi percorso per il repository clonato.</span><span class="sxs-lookup"><span data-stu-id="85e6a-152">You can choose any location for the cloned repository.</span></span> <span data-ttu-id="85e6a-153">Ad esempio \* C:\github\dotnet-Spark \* .</span><span class="sxs-lookup"><span data-stu-id="85e6a-153">For example, \*C:\github\dotnet-spark\*.</span></span>

```bash
git clone https://github.com/dotnet/spark.git C:\github\dotnet-spark
```

### <a name="build-net-for-apache-spark-scala-extensions-layer"></a><span data-ttu-id="85e6a-154">Compilazione di .NET per Apache Spark livello estensioni scala</span><span class="sxs-lookup"><span data-stu-id="85e6a-154">Build .NET for Apache Spark Scala extensions layer</span></span>

<span data-ttu-id="85e6a-155">Quando si invia un'applicazione .NET, .NET per Apache Spark ha la logica necessaria scritta in scala che informa Apache Spark come gestire le richieste (ad esempio, la richiesta di creare una nuova sessione di Spark, la richiesta di trasferimento dei dati dal lato .NET al lato JVM e così via).</span><span class="sxs-lookup"><span data-stu-id="85e6a-155">When you submit a .NET application, .NET for Apache Spark has the necessary logic written in Scala that informs Apache Spark how to handle your requests (for example, request to create a new Spark Session, request to transfer data from .NET side to JVM side etc.).</span></span> <span data-ttu-id="85e6a-156">Questa logica si trova in [.NET per il codice sorgente Spark scala](https://github.com/dotnet/spark/tree/master/src/scala).</span><span class="sxs-lookup"><span data-stu-id="85e6a-156">This logic can be found in the [.NET for Spark Scala Source Code](https://github.com/dotnet/spark/tree/master/src/scala).</span></span>

<span data-ttu-id="85e6a-157">Indipendentemente dal fatto che si usi .NET Framework o .NET Core, sarà necessario compilare .NET per Apache Spark livello di estensione scala:</span><span class="sxs-lookup"><span data-stu-id="85e6a-157">Regardless of whether you are using .NET Framework or .NET Core, you will need to build the .NET for Apache Spark Scala extension layer:</span></span>

```powershell
cd src\scala
mvn clean package
```

<span data-ttu-id="85e6a-158">Verranno visualizzati i file jar creati per le versioni di Spark supportate:</span><span class="sxs-lookup"><span data-stu-id="85e6a-158">You should see JARs created for the supported Spark versions:</span></span>

* `microsoft-spark-2.3.x\target\microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x\target\microsoft-spark-2.4.x-<version>.jar`

### <a name="build-the-net-for-spark-sample-applications"></a><span data-ttu-id="85e6a-159">Compilare .NET per le applicazioni di esempio Spark</span><span class="sxs-lookup"><span data-stu-id="85e6a-159">Build the .NET for Spark sample applications</span></span>

<span data-ttu-id="85e6a-160">In questa sezione viene illustrato come compilare le [applicazioni di esempio](https://github.com/dotnet/spark/tree/master/examples) per .net per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="85e6a-160">This section explains how to build the [sample applications](https://github.com/dotnet/spark/tree/master/examples) for .NET for Apache Spark.</span></span> <span data-ttu-id="85e6a-161">Questi passaggi consentiranno di comprendere il processo di compilazione globale per qualsiasi applicazione .NET per Spark.</span><span class="sxs-lookup"><span data-stu-id="85e6a-161">These steps will help in understanding the overall building process for any .NET for Spark application.</span></span>

#### <a name="using-visual-studio-for-net-framework"></a><span data-ttu-id="85e6a-162">Uso di Visual Studio per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="85e6a-162">Using Visual Studio for .NET Framework</span></span>

  1. <span data-ttu-id="85e6a-163">Aprire `src\csharp\Microsoft.Spark.sln` in Visual Studio e compilare il `Microsoft.Spark.CSharp.Examples` progetto nella `examples` cartella. questa operazione compilerà a sua volta anche il progetto di binding .NET.</span><span class="sxs-lookup"><span data-stu-id="85e6a-163">Open `src\csharp\Microsoft.Spark.sln` in Visual Studio and build the `Microsoft.Spark.CSharp.Examples` project under the `examples` folder (this will in turn build the .NET bindings project as well).</span></span> <span data-ttu-id="85e6a-164">Se si vuole, è possibile scrivere codice personalizzato nel `Microsoft.Spark.Examples` progetto (il "input_file.json" in questo esempio è un file JSON con i dati con i quali si vuole creare il frame di dati):</span><span class="sxs-lookup"><span data-stu-id="85e6a-164">If you want, you can write your own code in the `Microsoft.Spark.Examples` project (the 'input_file.json' in this example is a json file with the data you want to create the dataframe with):</span></span>
  
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

     <span data-ttu-id="85e6a-165">Una volta completata la compilazione, i file binari appropriati generati nella directory di output vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="85e6a-165">Once the build is successful, you will see the appropriate binaries produced in the output directory.</span></span>
     <span data-ttu-id="85e6a-166">Esempio di output della console:</span><span class="sxs-lookup"><span data-stu-id="85e6a-166">Sample console output:</span></span>

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

#### <a name="using-net-core-cli-for-net-core"></a><span data-ttu-id="85e6a-167">Uso di interfaccia della riga di comando di .NET Core per .NET Core</span><span class="sxs-lookup"><span data-stu-id="85e6a-167">Using .NET Core CLI for .NET Core</span></span>

> [!NOTE]
> <span data-ttu-id="85e6a-168">Attualmente si sta lavorando sull'automazione delle compilazioni .NET Core per Spark .NET.</span><span class="sxs-lookup"><span data-stu-id="85e6a-168">We are currently working on automating .NET Core builds for Spark .NET.</span></span> <span data-ttu-id="85e6a-169">Fino ad allora, siamo lieti di eseguire alcuni passaggi manualmente.</span><span class="sxs-lookup"><span data-stu-id="85e6a-169">Until then, we appreciate your patience in performing some of the steps manually.</span></span>

  1. <span data-ttu-id="85e6a-170">Creare il ruolo di lavoro:</span><span class="sxs-lookup"><span data-stu-id="85e6a-170">Build the worker:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```

      <span data-ttu-id="85e6a-171">Esempio di output della console:</span><span class="sxs-lookup"><span data-stu-id="85e6a-171">Sample console output:</span></span>

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

  2. <span data-ttu-id="85e6a-172">Compilare gli esempi:</span><span class="sxs-lookup"><span data-stu-id="85e6a-172">Build the samples:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```

      <span data-ttu-id="85e6a-173">Esempio di output della console:</span><span class="sxs-lookup"><span data-stu-id="85e6a-173">Sample console output:</span></span>

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

## <a name="run-the-net-for-spark-sample-applications"></a><span data-ttu-id="85e6a-174">Eseguire .NET per applicazioni di esempio Spark</span><span class="sxs-lookup"><span data-stu-id="85e6a-174">Run the .NET for Spark sample applications</span></span>

<span data-ttu-id="85e6a-175">Una volta creati gli esempi, l'esecuzione avverrà `spark-submit` indipendentemente dal fatto che la destinazione sia .NET Framework o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="85e6a-175">Once you build the samples, running them will be through `spark-submit` regardless of whether you are targeting .NET Framework or .NET Core.</span></span> <span data-ttu-id="85e6a-176">Assicurarsi di aver seguito la sezione [prerequisiti](#prerequisites) e installato Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="85e6a-176">Make sure you have followed the [prerequisites](#prerequisites) section and installed Apache Spark.</span></span>

  1. <span data-ttu-id="85e6a-177">Impostare la `DOTNET_WORKER_DIR` `PATH` variabile di ambiente o in modo da includere il percorso in cui `Microsoft.Spark.Worker` è stato generato il file binario, ad esempio *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461* per .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish* per .NET Core:</span><span class="sxs-lookup"><span data-stu-id="85e6a-177">Set the `DOTNET_WORKER_DIR` or `PATH` environment variable to include the path where the `Microsoft.Spark.Worker` binary has been generated (for example, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461* for .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish* for .NET Core):</span></span>

      ```powershell
      set DOTNET_WORKER_DIR=C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish
      ```
  
  2. <span data-ttu-id="85e6a-178">Aprire PowerShell e passare alla directory in cui è stato generato il file binario dell'app, ad esempio *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461* per .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish* per .NET Core:</span><span class="sxs-lookup"><span data-stu-id="85e6a-178">Open Powershell and go to the directory where your app binary has been generated (for example, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461* for .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish* for .NET Core):</span></span>

      ```powershell
      cd C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish
      ```

  3. <span data-ttu-id="85e6a-179">L'esecuzione dell'app segue la struttura di base:</span><span class="sxs-lookup"><span data-stu-id="85e6a-179">Running your app follows the basic structure:</span></span>

     ```powershell
     spark-submit.cmd `
       [--jars <any-jars-your-app-is-dependent-on>] `
       --class org.apache.spark.deploy.dotnet.DotnetRunner `
       --master local `
       <path-to-microsoft-spark-jar> `
       <path-to-your-app-exe> <argument(s)-to-your-app>
     ```

     <span data-ttu-id="85e6a-180">Di seguito sono riportati alcuni esempi che è possibile eseguire:</span><span class="sxs-lookup"><span data-stu-id="85e6a-180">Here are some examples you can run:</span></span>

     - <span data-ttu-id="85e6a-181">**[Microsoft.Spark.Examples.Sql.Batch. Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span><span class="sxs-lookup"><span data-stu-id="85e6a-181">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Batch.Basic %SPARK_HOME%\examples\src\main\resources\people.json
         ```

     - <span data-ttu-id="85e6a-182">**[Microsoft. Spark. examples. SQL. streaming. StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="85e6a-182">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkWordCount localhost 9999
         ```

     - <span data-ttu-id="85e6a-183">**[Microsoft. Spark. examples. SQL. streaming. StructuredKafkaWordCount (Maven accessibile)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="85e6a-183">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (maven accessible)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
         ```

     - <span data-ttu-id="85e6a-184">**[Microsoft. Spark. examples. SQL. streaming. StructuredKafkaWordCount (jar forniti)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="85e6a-184">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (jars provided)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd
         --jars path\to\net.jpountz.lz4\lz4-1.3.0.jar,path\to\org.apache.kafka\kafka-clients-0.10.0.1.jar,path\to\org.apache.spark\spark-sql-kafka-0-10_2.11-2.3.2.jar,`path\to\org.slf4j\slf4j-api-1.7.6.jar,path\to\org.spark-project.spark\unused-1.0.0.jar,path\to\org.xerial.snappy\snappy-java-1.1.2.6.jar `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
          ```

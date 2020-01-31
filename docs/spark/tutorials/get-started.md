---
title: Introduzione a .NET per Apache Spark
description: Informazioni su come eseguire un'app .NET per Apache Spark usando .NET Core in Windows.
ms.date: 11/04/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 679ee7660e96504768a781e1e384acab80362736
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743209"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="a8d0f-103">Esercitazione: Introduzione a .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a8d0f-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="a8d0f-104">Questa esercitazione illustra come eseguire un'app .NET per Apache Spark con .NET Core in Windows.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="a8d0f-105">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="a8d0f-106">Preparare l'ambiente Windows per .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a8d0f-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="a8d0f-107">Scrivere la prima applicazione .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a8d0f-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="a8d0f-108">Creazione ed esecuzione di un'applicazione .NET semplice per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a8d0f-108">Build and run your simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="a8d0f-109">Preparare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="a8d0f-109">Prepare your environment</span></span>

<span data-ttu-id="a8d0f-110">Prima di iniziare a scrivere l'app, è necessario configurare alcune dipendenze dei prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="a8d0f-111">Se è possibile eseguire `dotnet`, `java`, `mvn``spark-shell` dall'ambiente della riga di comando, l'ambiente è già pronto ed è possibile passare alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-111">If you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="a8d0f-112">Se non è possibile eseguire uno o tutti i comandi, seguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="a8d0f-113">1. installare .NET</span><span class="sxs-lookup"><span data-stu-id="a8d0f-113">1. Install .NET</span></span>

<span data-ttu-id="a8d0f-114">Per iniziare a creare app .NET, è necessario scaricare e installare .NET SDK (Software Development Kit).</span><span class="sxs-lookup"><span data-stu-id="a8d0f-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="a8d0f-115">scaricare e installare [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span><span class="sxs-lookup"><span data-stu-id="a8d0f-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span> <span data-ttu-id="a8d0f-116">L'installazione dell'SDK consente di aggiungere la toolchain `dotnet` a PATH.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="a8d0f-117">Una volta installato il .NET Core SDK, aprire un nuovo prompt dei comandi ed eseguire `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-117">Once you've installed the .NET Core SDK, open a new command prompt and run `dotnet`.</span></span>

<span data-ttu-id="a8d0f-118">Se il comando viene eseguito e stampa le informazioni su come usare dotnet, può passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="a8d0f-119">Se viene visualizzato un errore di `'dotnet' is not recognized as an internal or external command`, assicurarsi di aprire un **nuovo** prompt dei comandi prima di eseguire il comando.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="a8d0f-120">2. installare Java</span><span class="sxs-lookup"><span data-stu-id="a8d0f-120">2. Install Java</span></span>

<span data-ttu-id="a8d0f-121">Installare [Java 8,1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span><span class="sxs-lookup"><span data-stu-id="a8d0f-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

<span data-ttu-id="a8d0f-122">Selezionare la versione appropriata per il sistema operativo in uso.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="a8d0f-123">Ad esempio, selezionare **jdk-8u201-windows-x64.exe** per un computer Windows x64.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span> <span data-ttu-id="a8d0f-124">Usare quindi il comando `java` per verificare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-124">Then, use the command `java` to verify the installation.</span></span>

![Download Java](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-7-zip"></a><span data-ttu-id="a8d0f-126">3. installare 7-zip</span><span class="sxs-lookup"><span data-stu-id="a8d0f-126">3. Install 7-zip</span></span>

<span data-ttu-id="a8d0f-127">Apache Spark viene scaricato come file con estensione TGZ compresso.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="a8d0f-128">Per estrarre il file, usare un programma di estrazione, ad esempio 7-zip.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-128">Use an extraction program, like 7-zip, to extract the file.</span></span>

* <span data-ttu-id="a8d0f-129">Visita [7-download zip](https://www.7-zip.org/).</span><span class="sxs-lookup"><span data-stu-id="a8d0f-129">Visit [7-Zip downloads](https://www.7-zip.org/).</span></span>
* <span data-ttu-id="a8d0f-130">Nella prima tabella della pagina selezionare il download x64 a 32 bit x86 o a 64 bit, a seconda del sistema operativo in uso.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-130">In the first table on the page, select the 32-bit x86 or 64-bit x64 download, depending on your operating system.</span></span>
* <span data-ttu-id="a8d0f-131">Al termine del download, eseguire il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-131">When the download completes, run the installer.</span></span>

![Download 7Zip](https://dotnet.microsoft.com/static/images/7-zip-downloads.png?v=W6qWtFC1tTMKv3YGXz7lBa9F3M22uWyTvkMmunyroNk)

### <a name="4-install-apache-spark"></a><span data-ttu-id="a8d0f-133">4. installare Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a8d0f-133">4. Install Apache Spark</span></span>

<span data-ttu-id="a8d0f-134">[Scaricare e installare Apache Spark](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="a8d0f-134">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="a8d0f-135">È necessario effettuare una selezione dalla versione 2,3. \* o 2.4.0, 2.4.1, 2.4.3 o 2.4.4 (.NET per Apache Spark non è compatibile con le altre versioni di Apache Spark).</span><span class="sxs-lookup"><span data-stu-id="a8d0f-135">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, or 2.4.4 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="a8d0f-136">I comandi usati nei passaggi seguenti presuppongono che siano stati [scaricati e installati Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span><span class="sxs-lookup"><span data-stu-id="a8d0f-136">The commands used in the following steps assume you have [downloaded and installed Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span></span> <span data-ttu-id="a8d0f-137">Se si vuole usare una versione diversa, sostituire **2.4.1** con il numero di versione appropriato.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-137">If you wish to use a different version, replace **2.4.1** with the appropriate version number.</span></span> <span data-ttu-id="a8d0f-138">Estrarre quindi il file con estensione **tar** e i file di Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-138">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="a8d0f-139">Per estrarre il file con **estensione tar** annidato:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-139">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="a8d0f-140">Individuare il file **Spark-2.4.1-bin-Hadoop 2.7. tgz** scaricato.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-140">Locate the **spark-2.4.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="a8d0f-141">Fare clic con il pulsante destro del mouse sul file e selezionare **7-zip-> estrarre qui**.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-141">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="a8d0f-142">**Spark-2.4.1-bin-Hadoop 2.7. tar** viene creato insieme al file **. tgz** scaricato.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-142">**spark-2.4.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="a8d0f-143">Per estrarre i file di Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-143">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="a8d0f-144">Fare clic con il pulsante destro del mouse su **Spark-2.4.1-bin-Hadoop 2.7. tar** e selezionare **7-zip-> Estrai file...**</span><span class="sxs-lookup"><span data-stu-id="a8d0f-144">Right click on **spark-2.4.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="a8d0f-145">Immettere **C:\bin** nel campo **Estrai** in.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-145">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="a8d0f-146">Deselezionare la casella di controllo sotto il campo **Estrai in** .</span><span class="sxs-lookup"><span data-stu-id="a8d0f-146">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="a8d0f-147">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-147">Select **OK**.</span></span>
* <span data-ttu-id="a8d0f-148">I file Apache Spark vengono estratti in C:\bin\spark-2.4.1-bin-hadoop2.7</span><span class="sxs-lookup"><span data-stu-id="a8d0f-148">The Apache Spark files are extracted to C:\bin\spark-2.4.1-bin-hadoop2.7</span></span>\

![Installare Spark](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

<span data-ttu-id="a8d0f-150">Eseguire i comandi seguenti per impostare le variabili di ambiente usate per individuare Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-150">Run the following commands to set the environment variables used to locate Apache Spark:</span></span>

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

<span data-ttu-id="a8d0f-151">Dopo aver installato tutti gli elementi e impostato le variabili di ambiente, aprire un **nuovo** prompt dei comandi ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-151">Once you've installed everything and set your environment variables, open a **new** command prompt and run the following command:</span></span>

`%SPARK_HOME%\bin\spark-submit --version`

<span data-ttu-id="a8d0f-152">Se il comando esegue e stampa le informazioni sulla versione, è possibile passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-152">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="a8d0f-153">Se viene visualizzato un messaggio di errore `'spark-submit' is not recognized as an internal or external command`, assicurarsi di aprire un **nuovo** prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-153">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="a8d0f-154">5. installare .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a8d0f-154">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="a8d0f-155">Scaricare la versione [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) da .net per Apache Spark github.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-155">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="a8d0f-156">Ad esempio, se si è in un computer Windows e si prevede di usare .NET Core, [scaricare la versione di Windows x64 netcoreapp 2.1](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip).</span><span class="sxs-lookup"><span data-stu-id="a8d0f-156">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp2.1 release](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip).</span></span>

<span data-ttu-id="a8d0f-157">Per estrarre Microsoft. Spark. Worker:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-157">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="a8d0f-158">Individuare il file **Microsoft. Spark. Worker. netcoreapp 2.1. Win-x64-0.6.0. zip** scaricato.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-158">Locate the **Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="a8d0f-159">Fare clic con il pulsante destro del mouse e selezionare **7-zip-> Estrai file...** .</span><span class="sxs-lookup"><span data-stu-id="a8d0f-159">Right click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="a8d0f-160">Immettere **C:\bin** nel campo **Estrai** in.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-160">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="a8d0f-161">Deselezionare la casella di controllo sotto il campo **Estrai in** .</span><span class="sxs-lookup"><span data-stu-id="a8d0f-161">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="a8d0f-162">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-162">Select **OK**.</span></span>

![Installare .NET Spark](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils"></a><span data-ttu-id="a8d0f-164">6. installare file winutils</span><span class="sxs-lookup"><span data-stu-id="a8d0f-164">6. Install WinUtils</span></span>

<span data-ttu-id="a8d0f-165">.NET per Apache Spark richiede l'installazione di file winutils insieme a Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-165">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="a8d0f-166">[Scaricare file winutils. exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span><span class="sxs-lookup"><span data-stu-id="a8d0f-166">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="a8d0f-167">Quindi, copiare file winutils in **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-167">Then, copy WinUtils into **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="a8d0f-168">Se si usa una versione diversa di Hadoop, annotata alla fine del nome della cartella di installazione di Spark, [selezionare la versione di file winutils](https://github.com/steveloughran/winutils) compatibile con la versione di Hadoop.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-168">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="a8d0f-169">7. impostare DOTNET_WORKER_DIR e controllare le dipendenze</span><span class="sxs-lookup"><span data-stu-id="a8d0f-169">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="a8d0f-170">Eseguire il comando seguente per impostare la variabile di ambiente `DOTNET_WORKER_DIR`, che viene usata dalle app .NET per individuare .NET per Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-170">Run the following command to set the `DOTNET_WORKER_DIR` Environment Variable, which is used by .NET apps to locate .NET for Apache Spark:</span></span>

`setx DOTNET_WORKER_DIR "C:\bin\Microsoft.Spark.Worker-0.6.0"`

<span data-ttu-id="a8d0f-171">Infine, verificare che sia possibile eseguire `dotnet`, `java`, `mvn``spark-shell` dalla riga di comando prima di passare alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-171">Finally, double-check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="a8d0f-172">Scrivere un'app .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a8d0f-172">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="a8d0f-173">1. creare un'app console</span><span class="sxs-lookup"><span data-stu-id="a8d0f-173">1. Create a console app</span></span>

<span data-ttu-id="a8d0f-174">Al prompt dei comandi eseguire i comandi seguenti per creare una nuova applicazione console:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-174">In your command prompt, run the following commands to create a new console application:</span></span>

```console
dotnet new console -o mySparkApp
cd mySparkApp
```

<span data-ttu-id="a8d0f-175">Il comando `dotnet` crea un'applicazione `new` di tipo `console` automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-175">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="a8d0f-176">Il parametro `-o` crea una directory denominata *mySparkApp* in cui l'app viene archiviata e la popola con i file necessari.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-176">The `-o` parameter creates a directory named *mySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="a8d0f-177">Il comando `cd mySparkApp` imposta la directory sulla directory dell'app appena creata.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-177">The `cd mySparkApp` command changes the directory to the app directory you just created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="a8d0f-178">2. installare il pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="a8d0f-178">2. Install NuGet package</span></span>

<span data-ttu-id="a8d0f-179">Per usare .NET per Apache Spark in un'app, installare il pacchetto Microsoft. Spark.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-179">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="a8d0f-180">Al prompt dei comandi eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-180">In your command prompt, run the following command:</span></span>

`dotnet add package Microsoft.Spark --version 0.6.0`

### <a name="3-code-your-app"></a><span data-ttu-id="a8d0f-181">3. scrivere un codice per l'app</span><span class="sxs-lookup"><span data-stu-id="a8d0f-181">3. Code your app</span></span>

<span data-ttu-id="a8d0f-182">Aprire *Program.cs* in Visual Studio Code o in qualsiasi editor di testo e sostituire tutto il codice con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-182">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a Spark session.
            var spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            var words = dataFrame
                .Select(Functions.Split(Functions.Col("value"), " ").Alias("words"))
                .Select(Functions.Explode(Functions.Col("words"))
                .Alias("word"))
                .GroupBy("word")
                .Count()
                .OrderBy(Functions.Col("count").Desc());

            // Show results.
            words.Show();

            // Stop Spark session.
            spark.Stop();
        }
    }
}
```

### <a name="4-add-data-file"></a><span data-ttu-id="a8d0f-183">4. aggiungere un file di dati</span><span class="sxs-lookup"><span data-stu-id="a8d0f-183">4. Add data file</span></span>

<span data-ttu-id="a8d0f-184">L'app elabora un file contenente righe di testo.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-184">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="a8d0f-185">Creare un file *input. txt* nella directory *mySparkApp* , contenente il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-185">Create an *input.txt* file in your *mySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="a8d0f-186">Eseguire l'app .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a8d0f-186">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="a8d0f-187">Eseguire il comando seguente per compilare l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-187">Run the following command to build your application:</span></span>

   ```dotnetcli
   dotnet build
   ```

2. <span data-ttu-id="a8d0f-188">Eseguire il comando seguente per inviare l'applicazione da eseguire su Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-188">Run the following command to submit your application to run on Apache Spark:</span></span>

   ```powershell
   %SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local bin\Debug\netcoreapp3.0\microsoft-spark-2.4.x-0.6.0.jar dotnet bin\Debug\netcoreapp3.0\mySparkApp.dll
   ```

3. <span data-ttu-id="a8d0f-189">Quando l'app viene eseguita, i dati di conteggio delle parole del file *input. txt* vengono scritti nella console.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-189">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

<span data-ttu-id="a8d0f-190">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-190">Congratulations!</span></span> <span data-ttu-id="a8d0f-191">È stata creata ed eseguita un'app .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-191">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a8d0f-192">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a8d0f-192">Next steps</span></span>

<span data-ttu-id="a8d0f-193">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-193">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="a8d0f-194">Preparare l'ambiente Windows per .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a8d0f-194">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="a8d0f-195">Scrivere la prima applicazione .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a8d0f-195">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="a8d0f-196">Creazione ed esecuzione di un'applicazione .NET semplice per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a8d0f-196">Build and run your simple .NET for Apache Spark application</span></span>

<span data-ttu-id="a8d0f-197">Per visualizzare un video che illustra i passaggi precedenti, vedere la [serie di video .NET per Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span><span class="sxs-lookup"><span data-stu-id="a8d0f-197">To see a video explaining the steps above, checkout the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="a8d0f-198">Per altre informazioni, vedere la pagina delle risorse.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-198">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="a8d0f-199">Risorse di .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a8d0f-199">.NET for Apache Spark Resources</span></span>](../resources/index.md)

---
title: Introduzione a .NET per Apache Spark
description: Scopri come eseguire un'app .NET per Apache Spark usando .NET Core in Windows, MacOS e Ubuntu.
ms.date: 01/31/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7375c385245a05d7dc29d5df89d875bf6cb4141a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187547"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="0dead-103">Esercitazione: Introduzione a .NET per Apache SparkTutorial: Get started with .NET for Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0dead-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="0dead-104">Questa esercitazione illustra come eseguire un'app .NET per Apache Spark usando .NET Core in Windows, MacOS e Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="0dead-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows, MacOS, and Ubuntu.</span></span>

<span data-ttu-id="0dead-105">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="0dead-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="0dead-106">Preparare l'ambiente per .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0dead-106">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="0dead-107">Scrivere la prima applicazione .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0dead-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="0dead-108">Compilare ed eseguire la semplice applicazione .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0dead-108">Build and run your simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="0dead-109">Preparare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="0dead-109">Prepare your environment</span></span>

<span data-ttu-id="0dead-110">Prima di iniziare a scrivere l'app, è necessario configurare alcune dipendenze dei prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="0dead-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="0dead-111">Se è `dotnet`possibile `java` `mvn`eseguire `spark-shell` , , , dall'ambiente della riga di comando, l'ambiente è già pronto ed è possibile passare alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="0dead-111">If you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="0dead-112">Se non è possibile eseguire uno o tutti i comandi, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="0dead-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="0dead-113">1. Installare .NET</span><span class="sxs-lookup"><span data-stu-id="0dead-113">1. Install .NET</span></span>

<span data-ttu-id="0dead-114">Per iniziare a creare app .NET, è necessario scaricare e installare .NET SDK (Software Development Kit).</span><span class="sxs-lookup"><span data-stu-id="0dead-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="0dead-115">Scaricare e installare [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="0dead-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span> <span data-ttu-id="0dead-116">L'installazione dell'SDK consente di aggiungere la toolchain `dotnet` a PATH.</span><span class="sxs-lookup"><span data-stu-id="0dead-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="0dead-117">Dopo aver installato .NET Core SDK, aprire un nuovo `dotnet`prompt dei comandi o un nuovo terminale ed eseguire .</span><span class="sxs-lookup"><span data-stu-id="0dead-117">Once you've installed the .NET Core SDK, open a new command prompt or terminal and run `dotnet`.</span></span>

<span data-ttu-id="0dead-118">Se il comando viene eseguito e stampa informazioni su come utilizzare dotnet, è possibile passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="0dead-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="0dead-119">Se viene `'dotnet' is not recognized as an internal or external command` visualizzato un errore, assicurarsi di aver aperto un nuovo prompt dei comandi o un **nuovo** terminale prima di eseguire il comando.</span><span class="sxs-lookup"><span data-stu-id="0dead-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt or terminal before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="0dead-120">2. Installare Java</span><span class="sxs-lookup"><span data-stu-id="0dead-120">2. Install Java</span></span>

<span data-ttu-id="0dead-121">Installare [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) per Windows e MacOS o [OpenJDK 8](https://openjdk.java.net/install/) per Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="0dead-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) for Windows and MacOS, or [OpenJDK 8](https://openjdk.java.net/install/) for Ubuntu.</span></span>

<span data-ttu-id="0dead-122">Selezionare la versione appropriata per il sistema operativo in uso.</span><span class="sxs-lookup"><span data-stu-id="0dead-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="0dead-123">Ad esempio, selezionare **jdk-8u201-windows-x64.exe** per un computer Windows x64 (come illustrato di seguito) o **jdk-8u231-macosx-x64.dmg** per MacOS.</span><span class="sxs-lookup"><span data-stu-id="0dead-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine (as shown below) or **jdk-8u231-macosx-x64.dmg** for MacOS.</span></span> <span data-ttu-id="0dead-124">Quindi, utilizzare `java` il comando per verificare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="0dead-124">Then, use the command `java` to verify the installation.</span></span>

![Java Scarica](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a><span data-ttu-id="0dead-126">3. Installare il software di compressione</span><span class="sxs-lookup"><span data-stu-id="0dead-126">3. Install compression software</span></span>

<span data-ttu-id="0dead-127">Apache Spark viene scaricato come file .tgz compresso.</span><span class="sxs-lookup"><span data-stu-id="0dead-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="0dead-128">Per estrarre il file, utilizzare un programma di estrazione, ad esempio [7](https://www.7-zip.org/) zip o [Win.ip.](https://www.winzip.com/)</span><span class="sxs-lookup"><span data-stu-id="0dead-128">Use an extraction program, like [7-Zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/), to extract the file.</span></span>

### <a name="4-install-apache-spark"></a><span data-ttu-id="0dead-129">4. Installare Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0dead-129">4. Install Apache Spark</span></span>

<span data-ttu-id="0dead-130">[Scaricare e installare Apache Spark](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="0dead-130">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="0dead-131">È necessario scegliere tra la versione 2.3.o o 2.4.0, 2.4.1, 2.4.3 o 2.4.4 (.NET per Apache Spark non è compatibile con altre versioni di Apache Spark).</span><span class="sxs-lookup"><span data-stu-id="0dead-131">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, or 2.4.4 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="0dead-132">I comandi utilizzati nei passaggi seguenti presuppongono che sia stato [scaricato e installato Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span><span class="sxs-lookup"><span data-stu-id="0dead-132">The commands used in the following steps assume you have [downloaded and installed Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span></span> <span data-ttu-id="0dead-133">Se si desidera utilizzare una versione diversa, sostituire **2.4.1** con il numero di versione appropriato.</span><span class="sxs-lookup"><span data-stu-id="0dead-133">If you wish to use a different version, replace **2.4.1** with the appropriate version number.</span></span> <span data-ttu-id="0dead-134">Quindi, estrarre il file **.tar** e i file Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="0dead-134">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="0dead-135">Per estrarre il file **.tar** nidificato:</span><span class="sxs-lookup"><span data-stu-id="0dead-135">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="0dead-136">Individuare il file **spark-2.4.1-bin-hadoop2.7.tgz** scaricato.</span><span class="sxs-lookup"><span data-stu-id="0dead-136">Locate the **spark-2.4.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="0dead-137">Fare clic con il pulsante destro del mouse sul file e selezionare **7-zip -> Estrai qui**.</span><span class="sxs-lookup"><span data-stu-id="0dead-137">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="0dead-138">**spark-2.4.1-bin-hadoop2.7.tar** viene creato insieme al file **.tgz** scaricato.</span><span class="sxs-lookup"><span data-stu-id="0dead-138">**spark-2.4.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="0dead-139">Per estrarre i file Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="0dead-139">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="0dead-140">Fare clic con il pulsante destro del mouse su **spark-2.4.1-bin-hadoop2.7.tar** e selezionare **7-zip -> Estrarre i file...**</span><span class="sxs-lookup"><span data-stu-id="0dead-140">Right click on **spark-2.4.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="0dead-141">Nel campo **Estrai** in, estrai **C:**</span><span class="sxs-lookup"><span data-stu-id="0dead-141">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="0dead-142">Deselezionare la casella di controllo sotto il campo **Estrai in.**</span><span class="sxs-lookup"><span data-stu-id="0dead-142">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="0dead-143">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="0dead-143">Select **OK**.</span></span>
* <span data-ttu-id="0dead-144">I file di Apache Spark vengono estratti in C:</span><span class="sxs-lookup"><span data-stu-id="0dead-144">The Apache Spark files are extracted to C:\bin\spark-2.4.1-bin-hadoop2.7\</span></span>

![Installare Spark](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

<span data-ttu-id="0dead-146">Eseguire i comandi seguenti per impostare le variabili di ambiente utilizzate per individuare Apache Spark in **Windows:**</span><span class="sxs-lookup"><span data-stu-id="0dead-146">Run the following commands to set the environment variables used to locate Apache Spark on **Windows**:</span></span>

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

<span data-ttu-id="0dead-147">Eseguire i comandi seguenti per impostare le variabili di ambiente utilizzate per individuare Apache Spark su **MacOS** e **Ubuntu**:</span><span class="sxs-lookup"><span data-stu-id="0dead-147">Run the following commands to set the environment variables used to locate Apache Spark on **MacOS** and **Ubuntu**:</span></span>

```bash
export SPARK_HOME=~/bin/spark-2.4.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

<span data-ttu-id="0dead-148">Dopo aver installato tutto e impostato le variabili di ambiente, aprire un nuovo prompt dei comandi o un **nuovo** terminale ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0dead-148">Once you've installed everything and set your environment variables, open a **new** command prompt or terminal and run the following command:</span></span>

`%SPARK_HOME%\bin\spark-submit --version`

<span data-ttu-id="0dead-149">Se il comando viene eseguito e stampa le informazioni sulla versione, è possibile passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="0dead-149">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="0dead-150">Se viene `'spark-submit' is not recognized as an internal or external command` visualizzato un errore, assicurarsi di aver aperto un **nuovo** prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="0dead-150">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="0dead-151">5. Installare .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0dead-151">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="0dead-152">Scaricare la versione Microsoft.Spark.Worker da .NET per Apache Spark GitHub.Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span><span class="sxs-lookup"><span data-stu-id="0dead-152">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="0dead-153">Ad esempio, se si utilizza un computer Windows e si prevede di utilizzare .NET Core, [scaricare la versione x64 netcoreapp3.1 di Windows.](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip)</span><span class="sxs-lookup"><span data-stu-id="0dead-153">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp3.1 release](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip).</span></span>

<span data-ttu-id="0dead-154">Per estrarre Microsoft.Spark.Worker:</span><span class="sxs-lookup"><span data-stu-id="0dead-154">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="0dead-155">Individuare il file **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** scaricato.</span><span class="sxs-lookup"><span data-stu-id="0dead-155">Locate the **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="0dead-156">Fare clic con il pulsante destro del mouse e selezionare **7-zip -> Estrai file...**.</span><span class="sxs-lookup"><span data-stu-id="0dead-156">Right click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="0dead-157">Nel campo **Estrai** in, estrai **C:**</span><span class="sxs-lookup"><span data-stu-id="0dead-157">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="0dead-158">Deselezionare la casella di controllo sotto il campo **Estrai in.**</span><span class="sxs-lookup"><span data-stu-id="0dead-158">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="0dead-159">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="0dead-159">Select **OK**.</span></span>

![Installare .NET Spark](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils-windows-only"></a><span data-ttu-id="0dead-161">6. Installare WinUtils (solo Windows)</span><span class="sxs-lookup"><span data-stu-id="0dead-161">6. Install WinUtils (Windows only)</span></span>

<span data-ttu-id="0dead-162">.NET per Apache Spark richiede l'installazione di WinUtils insieme a Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="0dead-162">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="0dead-163">[Scaricare winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span><span class="sxs-lookup"><span data-stu-id="0dead-163">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="0dead-164">Quindi, copiare WinUtils in **C:**</span><span class="sxs-lookup"><span data-stu-id="0dead-164">Then, copy WinUtils into **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="0dead-165">Se si utilizza una versione diversa di Hadoop, annotata alla fine del nome della cartella di installazione di Spark, [selezionare la versione di WinUtils](https://github.com/steveloughran/winutils) compatibile con la versione di Hadoop in uso.</span><span class="sxs-lookup"><span data-stu-id="0dead-165">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="0dead-166">7. Impostare DOTNET_WORKER_DIR e controllare le dipendenze</span><span class="sxs-lookup"><span data-stu-id="0dead-166">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="0dead-167">Eseguire uno dei comandi seguenti `DOTNET_WORKER_DIR` per impostare la variabile di ambiente, che viene utilizzata dalle app .NET per individuare .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="0dead-167">Run one of the following commands to set the `DOTNET_WORKER_DIR` Environment Variable, which is used by .NET apps to locate .NET for Apache Spark.</span></span>

<span data-ttu-id="0dead-168">In **Windows**creare una [nuova variabile](https://www.java.com/en/download/help/path.xml) `DOTNET_WORKER_DIR` di ambiente e impostarla sulla directory in cui è `C:\bin\Microsoft.Spark.Worker\`stato scaricato ed estrarre Microsoft.Spark.Worker, ad esempio .</span><span class="sxs-lookup"><span data-stu-id="0dead-168">On **Windows**, create a [new environment variable](https://www.java.com/en/download/help/path.xml) `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, `C:\bin\Microsoft.Spark.Worker\`).</span></span>

<span data-ttu-id="0dead-169">In **MacOS**, creare una `export DOTNET_WORKER_DIR <your_path>` nuova variabile di ambiente utilizzando e impostarla sulla directory in cui è stato scaricato ed estratto microsoft.Spark.Worker (ad esempio, */bin/Microsoft.Spark.Worker/*).</span><span class="sxs-lookup"><span data-stu-id="0dead-169">On **MacOS**, create a new environment variable using `export DOTNET_WORKER_DIR <your_path>` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, *~/bin/Microsoft.Spark.Worker/*).</span></span>

<span data-ttu-id="0dead-170">In **Ubuntu**, creare una [nuova variabile](https://help.ubuntu.com/community/EnvironmentVariables) `DOTNET_WORKER_DIR` di ambiente e impostarla sulla directory in cui è stato scaricato ed estratto Microsoft.Spark.Worker (ad esempio, */bin/Microsoft.Spark.Worker*).</span><span class="sxs-lookup"><span data-stu-id="0dead-170">On **Ubuntu**, create a [new environment variable](https://help.ubuntu.com/community/EnvironmentVariables) `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, *~/bin/Microsoft.Spark.Worker*).</span></span>

<span data-ttu-id="0dead-171">Infine, verificare che sia `dotnet` `java`possibile `mvn` `spark-shell` eseguire , , , dalla riga di comando prima di passare alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="0dead-171">Finally, double-check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="0dead-172">Scrivere un'app .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0dead-172">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="0dead-173">1. Creare un'app console</span><span class="sxs-lookup"><span data-stu-id="0dead-173">1. Create a console app</span></span>

<span data-ttu-id="0dead-174">Nel prompt dei comandi o nel terminale, eseguire i comandi seguenti per creare una nuova applicazione console:</span><span class="sxs-lookup"><span data-stu-id="0dead-174">In your command prompt or terminal, run the following commands to create a new console application:</span></span>

```dotnetcli
dotnet new console -o mySparkApp
cd mySparkApp
```

<span data-ttu-id="0dead-175">Il `dotnet` comando `new` crea automaticamente `console` un'applicazione di tipo.</span><span class="sxs-lookup"><span data-stu-id="0dead-175">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="0dead-176">Il `-o` parametro crea una directory denominata *mySparkApp* in cui è archiviata l'app e la popola con i file necessari.</span><span class="sxs-lookup"><span data-stu-id="0dead-176">The `-o` parameter creates a directory named *mySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="0dead-177">Il `cd mySparkApp` comando modifica la directory in base alla directory dell'app appena creata.</span><span class="sxs-lookup"><span data-stu-id="0dead-177">The `cd mySparkApp` command changes the directory to the app directory you just created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="0dead-178">2. Installare il pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="0dead-178">2. Install NuGet package</span></span>

<span data-ttu-id="0dead-179">Per usare .NET per Apache Spark in un'app, installa il pacchetto Microsoft.Spark.</span><span class="sxs-lookup"><span data-stu-id="0dead-179">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="0dead-180">Nel prompt dei comandi o nel terminale, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0dead-180">In your command prompt or terminal, run the following command:</span></span>

`dotnet add package Microsoft.Spark --version 0.8.0`

### <a name="3-code-your-app"></a><span data-ttu-id="0dead-181">3. Codifica la tua app</span><span class="sxs-lookup"><span data-stu-id="0dead-181">3. Code your app</span></span>

<span data-ttu-id="0dead-182">Aprire *Program.cs* in Visual Studio Code o in qualsiasi editor di testo e sostituire tutto il codice con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0dead-182">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a Spark session.
            SparkSession spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            DataFrame words = dataFrame
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

### <a name="4-create-and-add-a-data-file"></a><span data-ttu-id="0dead-183">4. Creare e aggiungere un file di dati</span><span class="sxs-lookup"><span data-stu-id="0dead-183">4. Create and add a data file</span></span>

<span data-ttu-id="0dead-184">Apri il prompt dei comandi o il terminale e accedi alla cartella dell'app.</span><span class="sxs-lookup"><span data-stu-id="0dead-184">Open your command prompt or terminal and navigate into your app folder.</span></span>

```bash
cd <your-app-output-directory>
```

<span data-ttu-id="0dead-185">L'app elabora un file contenente righe di testo.</span><span class="sxs-lookup"><span data-stu-id="0dead-185">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="0dead-186">Creare un file *input.txt* nella directory *mySparkApp,* contenente il seguente testo:</span><span class="sxs-lookup"><span data-stu-id="0dead-186">Create an *input.txt* file in your *mySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="0dead-187">Eseguire l'app .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0dead-187">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="0dead-188">Eseguire il comando seguente per compilare l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="0dead-188">Run the following command to build your application:</span></span>

   ```dotnetcli
   dotnet build
   ```

2. <span data-ttu-id="0dead-189">Eseguire il comando seguente per inviare l'applicazione per l'esecuzione su Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="0dead-189">Run the following command to submit your application to run on Apache Spark:</span></span>

   ```console
   spark-submit \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --master local \
   microsoft-spark-2.4.x-<version>.jar \
   dotnet HelloSpark.dll
   ```

   > [!NOTE]
   > <span data-ttu-id="0dead-190">Questo comando presuppone che sia stato scaricato Apache Spark e che `spark-submit`sia stato aggiunto alla variabile di ambiente PATH per poter utilizzare .</span><span class="sxs-lookup"><span data-stu-id="0dead-190">This command assumes you have downloaded Apache Spark and added it to your PATH environment variable to be able to use `spark-submit`.</span></span> <span data-ttu-id="0dead-191">In caso contrario, è necessario utilizzare il percorso completo (ad esempio, *C:* *~/spark/bin/spark-submit*</span><span class="sxs-lookup"><span data-stu-id="0dead-191">Otherwise, you'd have to use the full path (for example, *C:\bin\apache-spark\bin\spark-submit* or *~/spark/bin/spark-submit*).</span></span>

3. <span data-ttu-id="0dead-192">Quando l'app viene eseguita, i dati del conteggio delle parole del file *input.txt* vengono scritti nella console.</span><span class="sxs-lookup"><span data-stu-id="0dead-192">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

<span data-ttu-id="0dead-193">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="0dead-193">Congratulations!</span></span> <span data-ttu-id="0dead-194">È stata creata ed eseguita un'app .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="0dead-194">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0dead-195">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0dead-195">Next steps</span></span>

<span data-ttu-id="0dead-196">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="0dead-196">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="0dead-197">Preparare l'ambiente Windows per .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0dead-197">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="0dead-198">Scrivere la prima applicazione .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0dead-198">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="0dead-199">Compilare ed eseguire la semplice applicazione .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0dead-199">Build and run your simple .NET for Apache Spark application</span></span>

<span data-ttu-id="0dead-200">Per un video che illustra i passaggi precedenti, estrarre la [serie di video .NET per Apache Spark 101.](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App)</span><span class="sxs-lookup"><span data-stu-id="0dead-200">To see a video explaining the steps above, checkout the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="0dead-201">Per altre informazioni, vedere la pagina delle risorse.</span><span class="sxs-lookup"><span data-stu-id="0dead-201">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="0dead-202">Risorse di .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0dead-202">.NET for Apache Spark Resources</span></span>](../resources/index.md)

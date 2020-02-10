---
title: Introduzione a .NET per Apache Spark
description: Scopri come eseguire un'app .NET per Apache Spark usando .NET Core in Windows, MacOS e Ubuntu.
ms.date: 01/31/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 018c21804bf942233e07039281d7ec22a6bef763
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092317"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="63acb-103">Esercitazione: Introduzione a .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="63acb-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="63acb-104">Questa esercitazione illustra come eseguire un'app .NET per Apache Spark usando .NET Core in Windows, MacOS e Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="63acb-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows, MacOS, and Ubuntu.</span></span>

<span data-ttu-id="63acb-105">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="63acb-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="63acb-106">Preparare l'ambiente per .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="63acb-106">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="63acb-107">Scrivere la prima applicazione .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="63acb-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="63acb-108">Creazione ed esecuzione di un'applicazione .NET semplice per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="63acb-108">Build and run your simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="63acb-109">Preparare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="63acb-109">Prepare your environment</span></span>

<span data-ttu-id="63acb-110">Prima di iniziare a scrivere l'app, è necessario configurare alcune dipendenze dei prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="63acb-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="63acb-111">Se è possibile eseguire `dotnet`, `java`, `mvn``spark-shell` dall'ambiente della riga di comando, l'ambiente è già pronto ed è possibile passare alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="63acb-111">If you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="63acb-112">Se non è possibile eseguire uno o tutti i comandi, seguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="63acb-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="63acb-113">1. installare .NET</span><span class="sxs-lookup"><span data-stu-id="63acb-113">1. Install .NET</span></span>

<span data-ttu-id="63acb-114">Per iniziare a creare app .NET, è necessario scaricare e installare .NET SDK (Software Development Kit).</span><span class="sxs-lookup"><span data-stu-id="63acb-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="63acb-115">Scaricare e installare [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="63acb-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span> <span data-ttu-id="63acb-116">L'installazione dell'SDK consente di aggiungere la toolchain `dotnet` a PATH.</span><span class="sxs-lookup"><span data-stu-id="63acb-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="63acb-117">Una volta installato il .NET Core SDK, aprire un nuovo prompt dei comandi o un terminale ed eseguire `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="63acb-117">Once you've installed the .NET Core SDK, open a new command prompt or terminal and run `dotnet`.</span></span>

<span data-ttu-id="63acb-118">Se il comando viene eseguito e stampa le informazioni su come usare dotnet, può passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="63acb-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="63acb-119">Se viene visualizzato un errore di `'dotnet' is not recognized as an internal or external command`, assicurarsi di avere aperto un **nuovo** prompt dei comandi o un terminale prima di eseguire il comando.</span><span class="sxs-lookup"><span data-stu-id="63acb-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt or terminal before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="63acb-120">2. installare Java</span><span class="sxs-lookup"><span data-stu-id="63acb-120">2. Install Java</span></span>

<span data-ttu-id="63acb-121">Installare [Java 8,1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) per Windows e MacOS o [OpenJDK 8](https://openjdk.java.net/install/) per Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="63acb-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) for Windows and MacOS, or [OpenJDK 8](https://openjdk.java.net/install/) for Ubuntu.</span></span>

<span data-ttu-id="63acb-122">Selezionare la versione appropriata per il sistema operativo in uso.</span><span class="sxs-lookup"><span data-stu-id="63acb-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="63acb-123">Ad esempio, selezionare **JDK-8u201-Windows-x64. exe** per un computer Windows x64 (come illustrato di seguito) o **JDK-8u231-macosx-x64. dmg** per MacOS.</span><span class="sxs-lookup"><span data-stu-id="63acb-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine (as shown below) or **jdk-8u231-macosx-x64.dmg** for MacOS.</span></span> <span data-ttu-id="63acb-124">Usare quindi il comando `java` per verificare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="63acb-124">Then, use the command `java` to verify the installation.</span></span>

![Download Java](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a><span data-ttu-id="63acb-126">3. installare il software di compressione</span><span class="sxs-lookup"><span data-stu-id="63acb-126">3. Install compression software</span></span>

<span data-ttu-id="63acb-127">Apache Spark viene scaricato come file con estensione TGZ compresso.</span><span class="sxs-lookup"><span data-stu-id="63acb-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="63acb-128">Per estrarre il file, usare un programma di estrazione, ad esempio [7-zip](https://www.7-zip.org/) o [WinZip](https://www.winzip.com/).</span><span class="sxs-lookup"><span data-stu-id="63acb-128">Use an extraction program, like [7-Zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/), to extract the file.</span></span>

### <a name="4-install-apache-spark"></a><span data-ttu-id="63acb-129">4. installare Apache Spark</span><span class="sxs-lookup"><span data-stu-id="63acb-129">4. Install Apache Spark</span></span>

<span data-ttu-id="63acb-130">[Scaricare e installare Apache Spark](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="63acb-130">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="63acb-131">È necessario effettuare una selezione dalla versione 2,3. \* o 2.4.0, 2.4.1, 2.4.3 o 2.4.4 (.NET per Apache Spark non è compatibile con le altre versioni di Apache Spark).</span><span class="sxs-lookup"><span data-stu-id="63acb-131">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, or 2.4.4 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="63acb-132">I comandi usati nei passaggi seguenti presuppongono che siano stati [scaricati e installati Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span><span class="sxs-lookup"><span data-stu-id="63acb-132">The commands used in the following steps assume you have [downloaded and installed Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span></span> <span data-ttu-id="63acb-133">Se si vuole usare una versione diversa, sostituire **2.4.1** con il numero di versione appropriato.</span><span class="sxs-lookup"><span data-stu-id="63acb-133">If you wish to use a different version, replace **2.4.1** with the appropriate version number.</span></span> <span data-ttu-id="63acb-134">Estrarre quindi il file con estensione **tar** e i file di Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="63acb-134">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="63acb-135">Per estrarre il file con **estensione tar** annidato:</span><span class="sxs-lookup"><span data-stu-id="63acb-135">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="63acb-136">Individuare il file **Spark-2.4.1-bin-Hadoop 2.7. tgz** scaricato.</span><span class="sxs-lookup"><span data-stu-id="63acb-136">Locate the **spark-2.4.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="63acb-137">Fare clic con il pulsante destro del mouse sul file e selezionare **7-zip-> estrarre qui**.</span><span class="sxs-lookup"><span data-stu-id="63acb-137">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="63acb-138">**Spark-2.4.1-bin-Hadoop 2.7. tar** viene creato insieme al file **. tgz** scaricato.</span><span class="sxs-lookup"><span data-stu-id="63acb-138">**spark-2.4.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="63acb-139">Per estrarre i file di Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="63acb-139">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="63acb-140">Fare clic con il pulsante destro del mouse su **Spark-2.4.1-bin-Hadoop 2.7. tar** e selezionare **7-zip-> Estrai file...**</span><span class="sxs-lookup"><span data-stu-id="63acb-140">Right click on **spark-2.4.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="63acb-141">Immettere **C:\bin** nel campo **Estrai** in.</span><span class="sxs-lookup"><span data-stu-id="63acb-141">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="63acb-142">Deselezionare la casella di controllo sotto il campo **Estrai in** .</span><span class="sxs-lookup"><span data-stu-id="63acb-142">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="63acb-143">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="63acb-143">Select **OK**.</span></span>
* <span data-ttu-id="63acb-144">I file Apache Spark vengono estratti in C:\bin\spark-2.4.1-bin-hadoop2.7</span><span class="sxs-lookup"><span data-stu-id="63acb-144">The Apache Spark files are extracted to C:\bin\spark-2.4.1-bin-hadoop2.7</span></span>\

![Installare Spark](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

<span data-ttu-id="63acb-146">Eseguire i comandi seguenti per impostare le variabili di ambiente usate per individuare Apache Spark in **Windows**:</span><span class="sxs-lookup"><span data-stu-id="63acb-146">Run the following commands to set the environment variables used to locate Apache Spark on **Windows**:</span></span>

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

<span data-ttu-id="63acb-147">Eseguire i comandi seguenti per impostare le variabili di ambiente usate per individuare Apache Spark in **MacOS** e **Ubuntu**:</span><span class="sxs-lookup"><span data-stu-id="63acb-147">Run the following commands to set the environment variables used to locate Apache Spark on **MacOS** and **Ubuntu**:</span></span>

```bash
export SPARK_HOME=~/bin/spark-2.4.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

<span data-ttu-id="63acb-148">Dopo aver installato tutti gli elementi e impostato le variabili di ambiente, aprire un **nuovo** prompt dei comandi o un terminale ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="63acb-148">Once you've installed everything and set your environment variables, open a **new** command prompt or terminal and run the following command:</span></span>

`%SPARK_HOME%\bin\spark-submit --version`

<span data-ttu-id="63acb-149">Se il comando esegue e stampa le informazioni sulla versione, è possibile passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="63acb-149">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="63acb-150">Se viene visualizzato un messaggio di errore `'spark-submit' is not recognized as an internal or external command`, assicurarsi di aprire un **nuovo** prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="63acb-150">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="63acb-151">5. installare .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="63acb-151">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="63acb-152">Scaricare la versione [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) da .net per Apache Spark github.</span><span class="sxs-lookup"><span data-stu-id="63acb-152">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="63acb-153">Ad esempio, se si è in un computer Windows e si prevede di usare .NET Core, [scaricare la versione di Windows x64 netcoreapp 3.1](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip).</span><span class="sxs-lookup"><span data-stu-id="63acb-153">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp3.1 release](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip).</span></span>

<span data-ttu-id="63acb-154">Per estrarre Microsoft. Spark. Worker:</span><span class="sxs-lookup"><span data-stu-id="63acb-154">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="63acb-155">Individuare il file **Microsoft. Spark. Worker. netcoreapp 3.1. Win-x64-0.8.0. zip** scaricato.</span><span class="sxs-lookup"><span data-stu-id="63acb-155">Locate the **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="63acb-156">Fare clic con il pulsante destro del mouse e selezionare **7-zip-> Estrai file...** .</span><span class="sxs-lookup"><span data-stu-id="63acb-156">Right click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="63acb-157">Immettere **C:\bin** nel campo **Estrai** in.</span><span class="sxs-lookup"><span data-stu-id="63acb-157">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="63acb-158">Deselezionare la casella di controllo sotto il campo **Estrai in** .</span><span class="sxs-lookup"><span data-stu-id="63acb-158">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="63acb-159">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="63acb-159">Select **OK**.</span></span>

![Installare .NET Spark](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils-windows-only"></a><span data-ttu-id="63acb-161">6. installare file winutils (solo Windows)</span><span class="sxs-lookup"><span data-stu-id="63acb-161">6. Install WinUtils (Windows only)</span></span>

<span data-ttu-id="63acb-162">.NET per Apache Spark richiede l'installazione di file winutils insieme a Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="63acb-162">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="63acb-163">[Scaricare file winutils. exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span><span class="sxs-lookup"><span data-stu-id="63acb-163">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="63acb-164">Quindi, copiare file winutils in **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span><span class="sxs-lookup"><span data-stu-id="63acb-164">Then, copy WinUtils into **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="63acb-165">Se si usa una versione diversa di Hadoop, annotata alla fine del nome della cartella di installazione di Spark, [selezionare la versione di file winutils](https://github.com/steveloughran/winutils) compatibile con la versione di Hadoop.</span><span class="sxs-lookup"><span data-stu-id="63acb-165">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="63acb-166">7. impostare DOTNET_WORKER_DIR e controllare le dipendenze</span><span class="sxs-lookup"><span data-stu-id="63acb-166">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="63acb-167">Eseguire uno dei comandi seguenti per impostare la variabile di ambiente `DOTNET_WORKER_DIR`, che viene usata dalle app .NET per individuare .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="63acb-167">Run one of the following commands to set the `DOTNET_WORKER_DIR` Environment Variable, which is used by .NET apps to locate .NET for Apache Spark.</span></span>

<span data-ttu-id="63acb-168">In **Windows**creare una [nuova variabile di ambiente](https://www.java.com/en/download/help/path.xml) `DOTNET_WORKER_DIR` e impostarla sulla directory in cui è stato scaricato ed Estratto Microsoft. Spark. Worker, ad esempio `C:\bin\Microsoft.Spark.Worker\`.</span><span class="sxs-lookup"><span data-stu-id="63acb-168">On **Windows**, create a [new environment variable](https://www.java.com/en/download/help/path.xml) `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, `C:\bin\Microsoft.Spark.Worker\`).</span></span>

<span data-ttu-id="63acb-169">In **MacOS**creare una nuova variabile di ambiente usando `export DOTNET_WORKER_DIR <your_path>` e impostarla sulla directory in cui è stato scaricato ed Estratto Microsoft. Spark. Worker (ad esempio *~/bin/Microsoft.Spark.Worker/* ).</span><span class="sxs-lookup"><span data-stu-id="63acb-169">On **MacOS**, create a new environment variable using `export DOTNET_WORKER_DIR <your_path>` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, *~/bin/Microsoft.Spark.Worker/*).</span></span> 

<span data-ttu-id="63acb-170">In **Ubuntu**creare una [nuova variabile di ambiente](https://help.ubuntu.com/community/EnvironmentVariables) `DOTNET_WORKER_DIR` e impostarla sulla directory in cui è stato scaricato ed Estratto Microsoft. Spark. Worker (ad esempio *~/bin/Microsoft.Spark.Worker*).</span><span class="sxs-lookup"><span data-stu-id="63acb-170">On **Ubuntu**, create a [new environment variable](https://help.ubuntu.com/community/EnvironmentVariables) `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, *~/bin/Microsoft.Spark.Worker*).</span></span>

<span data-ttu-id="63acb-171">Infine, verificare che sia possibile eseguire `dotnet`, `java`, `mvn``spark-shell` dalla riga di comando prima di passare alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="63acb-171">Finally, double-check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="63acb-172">Scrivere un'app .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="63acb-172">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="63acb-173">1. creare un'app console</span><span class="sxs-lookup"><span data-stu-id="63acb-173">1. Create a console app</span></span>

<span data-ttu-id="63acb-174">Nel prompt dei comandi o nel terminale eseguire i comandi seguenti per creare una nuova applicazione console:</span><span class="sxs-lookup"><span data-stu-id="63acb-174">In your command prompt or terminal, run the following commands to create a new console application:</span></span>

```dotnetcli
dotnet new console -o mySparkApp
cd mySparkApp
```

<span data-ttu-id="63acb-175">Il comando `dotnet` crea un'applicazione `new` di tipo `console` automaticamente.</span><span class="sxs-lookup"><span data-stu-id="63acb-175">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="63acb-176">Il parametro `-o` crea una directory denominata *mySparkApp* in cui l'app viene archiviata e la popola con i file necessari.</span><span class="sxs-lookup"><span data-stu-id="63acb-176">The `-o` parameter creates a directory named *mySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="63acb-177">Il comando `cd mySparkApp` imposta la directory sulla directory dell'app appena creata.</span><span class="sxs-lookup"><span data-stu-id="63acb-177">The `cd mySparkApp` command changes the directory to the app directory you just created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="63acb-178">2. installare il pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="63acb-178">2. Install NuGet package</span></span>

<span data-ttu-id="63acb-179">Per usare .NET per Apache Spark in un'app, installare il pacchetto Microsoft. Spark.</span><span class="sxs-lookup"><span data-stu-id="63acb-179">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="63acb-180">Nel prompt dei comandi o nel terminale eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="63acb-180">In your command prompt or terminal, run the following command:</span></span>

`dotnet add package Microsoft.Spark --version 0.8.0`

### <a name="3-code-your-app"></a><span data-ttu-id="63acb-181">3. scrivere un codice per l'app</span><span class="sxs-lookup"><span data-stu-id="63acb-181">3. Code your app</span></span>

<span data-ttu-id="63acb-182">Aprire *Program.cs* in Visual Studio Code o in qualsiasi editor di testo e sostituire tutto il codice con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="63acb-182">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

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

### <a name="4-create-and-add-a-data-file"></a><span data-ttu-id="63acb-183">4. creare e aggiungere un file di dati</span><span class="sxs-lookup"><span data-stu-id="63acb-183">4. Create and add a data file</span></span>

<span data-ttu-id="63acb-184">Aprire il prompt dei comandi o il terminale e passare alla cartella dell'app.</span><span class="sxs-lookup"><span data-stu-id="63acb-184">Open your command prompt or terminal and navigate into your app folder.</span></span>

```bash
cd <your-app-output-directory>
```

<span data-ttu-id="63acb-185">L'app elabora un file contenente righe di testo.</span><span class="sxs-lookup"><span data-stu-id="63acb-185">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="63acb-186">Creare un file *input. txt* nella directory *mySparkApp* , contenente il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="63acb-186">Create an *input.txt* file in your *mySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="63acb-187">Eseguire l'app .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="63acb-187">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="63acb-188">Eseguire il comando seguente per compilare l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="63acb-188">Run the following command to build your application:</span></span>

   ```dotnetcli
   dotnet build
   ```

2. <span data-ttu-id="63acb-189">Eseguire il comando seguente per inviare l'applicazione da eseguire su Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="63acb-189">Run the following command to submit your application to run on Apache Spark:</span></span>

   ```console
   spark-submit \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --master local \
   microsoft-spark-2.4.x-<version>.jar \
   dotnet HelloSpark.dll
   ```

   > [!NOTE]
   > <span data-ttu-id="63acb-190">Questo comando presuppone che sia stato scaricato Apache Spark e che sia stato aggiunto alla variabile di ambiente PATH per poter usare `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="63acb-190">This command assumes you have downloaded Apache Spark and added it to your PATH environment variable to be able to use `spark-submit`.</span></span> <span data-ttu-id="63acb-191">In caso contrario, è necessario usare il percorso completo (ad esempio, *C:\bin\apache-spark\bin\spark-Submit* o *~/Spark/bin/Spark-Submit*).</span><span class="sxs-lookup"><span data-stu-id="63acb-191">Otherwise, you'd have to use the full path (for example, *C:\bin\apache-spark\bin\spark-submit* or *~/spark/bin/spark-submit*).</span></span>

3. <span data-ttu-id="63acb-192">Quando l'app viene eseguita, i dati di conteggio delle parole del file *input. txt* vengono scritti nella console.</span><span class="sxs-lookup"><span data-stu-id="63acb-192">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

<span data-ttu-id="63acb-193">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="63acb-193">Congratulations!</span></span> <span data-ttu-id="63acb-194">È stata creata ed eseguita un'app .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="63acb-194">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="63acb-195">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="63acb-195">Next steps</span></span>

<span data-ttu-id="63acb-196">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="63acb-196">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="63acb-197">Preparare l'ambiente Windows per .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="63acb-197">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="63acb-198">Scrivere la prima applicazione .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="63acb-198">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="63acb-199">Creazione ed esecuzione di un'applicazione .NET semplice per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="63acb-199">Build and run your simple .NET for Apache Spark application</span></span>

<span data-ttu-id="63acb-200">Per visualizzare un video che illustra i passaggi precedenti, vedere la [serie di video .NET per Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span><span class="sxs-lookup"><span data-stu-id="63acb-200">To see a video explaining the steps above, checkout the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="63acb-201">Per altre informazioni, vedere la pagina delle risorse.</span><span class="sxs-lookup"><span data-stu-id="63acb-201">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="63acb-202">Risorse di .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="63acb-202">.NET for Apache Spark Resources</span></span>](../resources/index.md)

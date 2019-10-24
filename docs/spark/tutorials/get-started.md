---
title: Introduzione a .NET per Apache Spark
description: Informazioni su come eseguire un'app .NET per Apache Spark usando .NET Core in Windows.
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 19efc8412d834d73069c61e1cc1ccd9e5eb8593b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774367"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="fba66-103">Esercitazione: Introduzione a .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="fba66-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="fba66-104">Questa esercitazione illustra come eseguire un'app .NET per Apache Spark con .NET Core in Windows.</span><span class="sxs-lookup"><span data-stu-id="fba66-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="fba66-105">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="fba66-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="fba66-106">Preparare l'ambiente Windows per .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="fba66-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="fba66-107">Scaricare **Microsoft.Spark.Worker**</span><span class="sxs-lookup"><span data-stu-id="fba66-107">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="fba66-108">Creare ed eseguire un'applicazione .NET per Apache Spark semplice</span><span class="sxs-lookup"><span data-stu-id="fba66-108">Build and run a simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="fba66-109">Preparare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="fba66-109">Prepare your environment</span></span>

<span data-ttu-id="fba66-110">Prima di iniziare, verificare che sia possibile eseguire `dotnet`, `java`, `mvn`, `spark-shell` dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="fba66-110">Before you begin, make sure you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line.</span></span> <span data-ttu-id="fba66-111">Se l'ambiente è già preparato, è possibile passare alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="fba66-111">If your environment is already prepared, you can skip to the next section.</span></span> <span data-ttu-id="fba66-112">Se non è possibile eseguire uno o tutti i comandi, seguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="fba66-112">If you cannot run any or all of the commands, follow the steps below.</span></span>

1. <span data-ttu-id="fba66-113">Scaricare e installare [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="fba66-113">Download and install the [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span> <span data-ttu-id="fba66-114">L'installazione dell'SDK consente di aggiungere la toolchain `dotnet` a PATH.</span><span class="sxs-lookup"><span data-stu-id="fba66-114">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span> <span data-ttu-id="fba66-115">Usare il comando `dotnet --version` di PowerShell per verificare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="fba66-115">Use the PowerShell command `dotnet --version` to verify the installation.</span></span>

2. <span data-ttu-id="fba66-116">Installare [Visual Studio 2017](https://www.visualstudio.com/downloads/) o [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) con gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="fba66-116">Install [Visual Studio 2017](https://www.visualstudio.com/downloads/) or [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) with the latest updates.</span></span> <span data-ttu-id="fba66-117">È possibile usare l'edizione Community, Professional o Enterprise.</span><span class="sxs-lookup"><span data-stu-id="fba66-117">You can use Community, Professional, or Enterprise.</span></span> <span data-ttu-id="fba66-118">La versione Community è gratuita.</span><span class="sxs-lookup"><span data-stu-id="fba66-118">The Community version is free.</span></span>

   <span data-ttu-id="fba66-119">Scegliere i carichi di lavoro seguenti durante l'installazione:</span><span class="sxs-lookup"><span data-stu-id="fba66-119">Choose the following workloads during installation:</span></span>
      * <span data-ttu-id="fba66-120">Sviluppo per desktop .NET</span><span class="sxs-lookup"><span data-stu-id="fba66-120">.NET desktop development</span></span>
          * <span data-ttu-id="fba66-121">Tutti i componenti richiesti</span><span class="sxs-lookup"><span data-stu-id="fba66-121">All required components</span></span>
          * <span data-ttu-id="fba66-122">Strumenti di sviluppo per .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="fba66-122">.NET Framework 4.6.1 Development Tools</span></span>
      * <span data-ttu-id="fba66-123">Sviluppo multipiattaforma .NET Core</span><span class="sxs-lookup"><span data-stu-id="fba66-123">.NET Core cross-platform development</span></span>
          * <span data-ttu-id="fba66-124">Tutti i componenti richiesti</span><span class="sxs-lookup"><span data-stu-id="fba66-124">All required components</span></span>

3. <span data-ttu-id="fba66-125">Installare [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span><span class="sxs-lookup"><span data-stu-id="fba66-125">Install [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

    * <span data-ttu-id="fba66-126">Selezionare la versione appropriata per il sistema operativo in uso.</span><span class="sxs-lookup"><span data-stu-id="fba66-126">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="fba66-127">Ad esempio, selezionare **jdk-8u201-windows-x64.exe** per un computer Windows x64.</span><span class="sxs-lookup"><span data-stu-id="fba66-127">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span>
    * <span data-ttu-id="fba66-128">Usare il comando `java -version` di PowerShell per verificare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="fba66-128">Use the PowerShell command `java -version` to verify the installation.</span></span>

4. <span data-ttu-id="fba66-129">Installare [Apache Maven 3.6.0+](https://maven.apache.org/download.cgi).</span><span class="sxs-lookup"><span data-stu-id="fba66-129">Install [Apache Maven 3.6.0+](https://maven.apache.org/download.cgi).</span></span>
    * <span data-ttu-id="fba66-130">Scaricare [Apache Maven 3.6.2](http://mirror.metrocast.net/apache/maven/maven-3/3.6.2/binaries/apache-maven-3.6.2-bin.zip).</span><span class="sxs-lookup"><span data-stu-id="fba66-130">Download [Apache Maven 3.6.2](http://mirror.metrocast.net/apache/maven/maven-3/3.6.2/binaries/apache-maven-3.6.2-bin.zip).</span></span>
    * <span data-ttu-id="fba66-131">Estrarre i file in una directory locale.</span><span class="sxs-lookup"><span data-stu-id="fba66-131">Extract to a local directory.</span></span> <span data-ttu-id="fba66-132">Ad esempio `c:\bin\apache-maven-3.6.2\`.</span><span class="sxs-lookup"><span data-stu-id="fba66-132">For example, `c:\bin\apache-maven-3.6.2\`.</span></span>
    * <span data-ttu-id="fba66-133">Aggiungere Apache Maven alla [variabile di ambiente PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="fba66-133">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="fba66-134">Se i file vengono estratti in `c:\bin\apache-maven-3.6.2\`, aggiungere `c:\bin\apache-maven-3.6.2\bin` a PATH.</span><span class="sxs-lookup"><span data-stu-id="fba66-134">If you extracted to `c:\bin\apache-maven-3.6.2\`, you would add `c:\bin\apache-maven-3.6.2\bin` to your PATH.</span></span>
    * <span data-ttu-id="fba66-135">Usare il comando `mvn -version` di PowerShell per verificare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="fba66-135">Use the PowerShell command `mvn -version` to verify the installation.</span></span>

5. <span data-ttu-id="fba66-136">Installare [Apache Spark 2.3+](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="fba66-136">Install [Apache Spark 2.3+](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="fba66-137">Apache Spark 2.4+ non è supportato.</span><span class="sxs-lookup"><span data-stu-id="fba66-137">Apache Spark 2.4+ isn't supported.</span></span>
    * <span data-ttu-id="fba66-138">Scaricare [Apache Spark 2.3+](https://spark.apache.org/downloads.html) ed estrarre i file in una cartella locale usando uno strumento come [7-zip](https://www.7-zip.org/) o [WinZip](https://www.winzip.com/).</span><span class="sxs-lookup"><span data-stu-id="fba66-138">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder using a tool like [7-zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/).</span></span> <span data-ttu-id="fba66-139">Ad esempio, è possibile estrarre i file in `c:\bin\spark-2.3.2-bin-hadoop2.7\`.</span><span class="sxs-lookup"><span data-stu-id="fba66-139">For example, you might extract it to `c:\bin\spark-2.3.2-bin-hadoop2.7\`.</span></span>
    * <span data-ttu-id="fba66-140">Aggiungere Apache Spark alla [variabile di ambiente PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="fba66-140">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="fba66-141">Se i file vengono estratti in `c:\bin\spark-2.3.2-bin-hadoop2.7\`, aggiungere `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` a PATH.</span><span class="sxs-lookup"><span data-stu-id="fba66-141">If you extracted to `c:\bin\spark-2.3.2-bin-hadoop2.7\`, you would add `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` to your PATH.</span></span>
    * <span data-ttu-id="fba66-142">Aggiungere una [nuova variabile di ambiente](https://www.java.com/en/download/help/path.xml) denominata `SPARK_HOME`.</span><span class="sxs-lookup"><span data-stu-id="fba66-142">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) called `SPARK_HOME`.</span></span> <span data-ttu-id="fba66-143">Se i file sono stati estratti in `C:\bin\spark-2.3.2-bin-hadoop2.7\`, usare `C:\bin\spark-2.3.2-bin-hadoop2.7\` per **Valore della variabile**.</span><span class="sxs-lookup"><span data-stu-id="fba66-143">If you extracted to `C:\bin\spark-2.3.2-bin-hadoop2.7\`, use  `C:\bin\spark-2.3.2-bin-hadoop2.7\` for the **Variable value**.</span></span>
    * <span data-ttu-id="fba66-144">Verificare che sia possibile eseguire `spark-shell` dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="fba66-144">Verify you are able to run `spark-shell` from your command line.</span></span>

6. <span data-ttu-id="fba66-145">Installare [WinUtils](https://github.com/steveloughran/winutils).</span><span class="sxs-lookup"><span data-stu-id="fba66-145">Set up [WinUtils](https://github.com/steveloughran/winutils).</span></span>
    * <span data-ttu-id="fba66-146">Scaricare il file binario **winutils.exe** dal [repository WinUtils](https://github.com/steveloughran/winutils).</span><span class="sxs-lookup"><span data-stu-id="fba66-146">Download the **winutils.exe** binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="fba66-147">Selezionare la versione di Hadoop con la quale è stata compilata la distribuzione Spark.</span><span class="sxs-lookup"><span data-stu-id="fba66-147">Select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="fba66-148">Ad esempio, si usa **hadoop-2.7.1** per **Spark 2.3.2**.</span><span class="sxs-lookup"><span data-stu-id="fba66-148">For example, you use **hadoop-2.7.1** for **Spark 2.3.2**.</span></span> <span data-ttu-id="fba66-149">La versione di Hadoop viene indicata alla fine del nome della cartella di installazione di Spark.</span><span class="sxs-lookup"><span data-stu-id="fba66-149">The Hadoop version is annotated at the end of your Spark install folder name.</span></span>
    * <span data-ttu-id="fba66-150">Salvare il file binario **winutils.exe** in una directory a propria scelta.</span><span class="sxs-lookup"><span data-stu-id="fba66-150">Save the **winutils.exe** binary to a directory of your choice.</span></span> <span data-ttu-id="fba66-151">Ad esempio `c:\hadoop\bin`.</span><span class="sxs-lookup"><span data-stu-id="fba66-151">For example, `c:\hadoop\bin`.</span></span>
    * <span data-ttu-id="fba66-152">Impostare `HADOOP_HOME` in modo che rispecchi la directory con **winutils.exe** senza `bin`.</span><span class="sxs-lookup"><span data-stu-id="fba66-152">Set `HADOOP_HOME` to reflect the directory with **winutils.exe** without `bin`.</span></span> <span data-ttu-id="fba66-153">Ad esempio `c:\hadoop`.</span><span class="sxs-lookup"><span data-stu-id="fba66-153">For example, `c:\hadoop`.</span></span>
    * <span data-ttu-id="fba66-154">Impostare la variabile di ambiente PATH per includere `%HADOOP_HOME%\bin`.</span><span class="sxs-lookup"><span data-stu-id="fba66-154">Set the PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span>

<span data-ttu-id="fba66-155">Verificare che sia possibile eseguire `dotnet`, `java`, `mvn`, `spark-shell` dalla riga di comando prima di passare alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="fba66-155">Double check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="download-the-microsoftsparkworker-release"></a><span data-ttu-id="fba66-156">Scaricare Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="fba66-156">Download the Microsoft.Spark.Worker release</span></span>

1. <span data-ttu-id="fba66-157">Scaricare [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) dalla pagina di GitHub dei rilasci per .NET per Apache Spark nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="fba66-157">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub Releases page to your local machine.</span></span> <span data-ttu-id="fba66-158">Ad esempio, è possibile scaricarlo nel percorso `c:\bin\Microsoft.Spark.Worker\`.</span><span class="sxs-lookup"><span data-stu-id="fba66-158">For example, you might download it to the path, `c:\bin\Microsoft.Spark.Worker\`.</span></span>

2. <span data-ttu-id="fba66-159">Creare una [nuova variabile di ambiente](https://www.java.com/en/download/help/path.xml) denominata `DOTNET_WORKER_DIR` e impostarla sulla directory in cui è stato scaricato ed estratto **Microsoft.Spark.Worker**.</span><span class="sxs-lookup"><span data-stu-id="fba66-159">Create a [new environment variable](https://www.java.com/en/download/help/path.xml) called `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the **Microsoft.Spark.Worker**.</span></span> <span data-ttu-id="fba66-160">Ad esempio `c:\bin\Microsoft.Spark.Worker`.</span><span class="sxs-lookup"><span data-stu-id="fba66-160">For example, `c:\bin\Microsoft.Spark.Worker`.</span></span>

## <a name="clone-the-net-for-apache-spark-github-repo"></a><span data-ttu-id="fba66-161">Clonare il repository GitHub di .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="fba66-161">Clone the .NET for Apache Spark GitHub repo</span></span>

<span data-ttu-id="fba66-162">Usare il comando [GitBash](https://gitforwindows.org/) seguente per clonare il repository di .NET per Apache Spark nel computer.</span><span class="sxs-lookup"><span data-stu-id="fba66-162">Use the following [GitBash](https://gitforwindows.org/) command to clone the .NET for Apache Spark repo to your machine.</span></span>

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="fba66-163">Scrivere un'app .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="fba66-163">Write a .NET for Apache Spark app</span></span>

1. <span data-ttu-id="fba66-164">Aprire **Visual Studio** e passare a **File > Crea nuovo progetto > App console (.NET Core**).</span><span class="sxs-lookup"><span data-stu-id="fba66-164">Open **Visual Studio** and navigate to **File > Create New Project > Console App (.NET Core)**.</span></span> <span data-ttu-id="fba66-165">Denominare l'applicazione **HelloSpark**.</span><span class="sxs-lookup"><span data-stu-id="fba66-165">Name the application **HelloSpark**.</span></span>

2. <span data-ttu-id="fba66-166">Installare il [pacchetto NuGet Microsoft.Spark](https://www.nuget.org/profiles/spark).</span><span class="sxs-lookup"><span data-stu-id="fba66-166">Install the [Microsoft.Spark NuGet package](https://www.nuget.org/profiles/spark).</span></span> <span data-ttu-id="fba66-167">Per altre informazioni sull'installazione di pacchetti NuGet, vedere [Diversi modi per installare un pacchetto NuGet](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span><span class="sxs-lookup"><span data-stu-id="fba66-167">For more information on installing NuGet packages, see [Different ways to install a NuGet Package](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span></span>

3. <span data-ttu-id="fba66-168">In **Esplora soluzioni** aprire **Program.cs** e scrivere il codice C# seguente:</span><span class="sxs-lookup"><span data-stu-id="fba66-168">In **Solution Explorer**, open **Program.cs** and write the following C# code:</span></span>

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. <span data-ttu-id="fba66-169">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="fba66-169">Build the solution.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="fba66-170">Eseguire l'app .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="fba66-170">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="fba66-171">Aprire **PowerShell** e impostare la directory sulla cartella in cui è archiviata l'app.</span><span class="sxs-lookup"><span data-stu-id="fba66-171">Open **PowerShell** and change the directory to the folder where your app is stored.</span></span>

   ```powershell
   cd <your-app-output-directory>
   ```

2. <span data-ttu-id="fba66-172">Creare un file denominato **people.json** con il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="fba66-172">Create a file called **people.json** with the following content:</span></span>

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. <span data-ttu-id="fba66-173">Usare il comando di PowerShell seguente per eseguire l'app:</span><span class="sxs-lookup"><span data-stu-id="fba66-173">Use the following PowerShell command to run your app:</span></span>

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

<span data-ttu-id="fba66-174">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="fba66-174">Congratulations!</span></span> <span data-ttu-id="fba66-175">È stata creata ed eseguita un'app .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="fba66-175">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fba66-176">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="fba66-176">Next steps</span></span>

<span data-ttu-id="fba66-177">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="fba66-177">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="fba66-178">Preparare l'ambiente Windows per .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="fba66-178">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="fba66-179">Scaricare **Microsoft.Spark.Worker**</span><span class="sxs-lookup"><span data-stu-id="fba66-179">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="fba66-180">Creare ed eseguire un'applicazione .NET per Apache Spark semplice</span><span class="sxs-lookup"><span data-stu-id="fba66-180">Build and run a simple .NET for Apache Spark application</span></span>

<span data-ttu-id="fba66-181">Per altre informazioni, vedere la pagina delle risorse.</span><span class="sxs-lookup"><span data-stu-id="fba66-181">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="fba66-182">Risorse di .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="fba66-182">.NET for Apache Spark Resources</span></span>](../resources/index.md)

---
title: Distribuire un'applicazione .NET per Apache Spark in Azure HDInsight
description: Informazioni su come distribuire un'applicazione .NET per Apache Spark in HDInsight.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 9da0e0fd83d70887109c63a5e95ec0b0b31a2edd
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928478"
---
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="6d31c-103">Distribuire un'applicazione .NET per Apache Spark in Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="6d31c-103">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="6d31c-104">Questa esercitazione illustra come distribuire un'applicazione .NET per Apache Spark in Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="6d31c-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Azure HDInsight.</span></span>

<span data-ttu-id="6d31c-105">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="6d31c-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="6d31c-106">Preparare Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="6d31c-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="6d31c-107">Pubblicare l'app Spark .NET</span><span class="sxs-lookup"><span data-stu-id="6d31c-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="6d31c-108">Distribuire l'app in Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="6d31c-108">Deploy your app to Azure HDInsight</span></span>
> * <span data-ttu-id="6d31c-109">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="6d31c-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6d31c-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6d31c-110">Prerequisites</span></span>

<span data-ttu-id="6d31c-111">Prima di iniziare, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d31c-111">Before you start, do the following:</span></span>

* <span data-ttu-id="6d31c-112">Scaricare [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span><span class="sxs-lookup"><span data-stu-id="6d31c-112">Download [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span>
* <span data-ttu-id="6d31c-113">Scaricare [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="6d31c-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="6d31c-114">Si tratta di uno script helper che verrà usato in seguito per copiare i file dipendenti di .NET per Apache Spark nei nodi di lavoro del cluster Spark.</span><span class="sxs-lookup"><span data-stu-id="6d31c-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="6d31c-115">Preparare le dipendenze dei nodi di lavoro</span><span class="sxs-lookup"><span data-stu-id="6d31c-115">Prepare worker dependencies</span></span>

<span data-ttu-id="6d31c-116">**Microsoft. Spark.Worker** è un componente back-end che risiede nei singoli nodi di lavoro del cluster Spark.</span><span class="sxs-lookup"><span data-stu-id="6d31c-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="6d31c-117">Quando si vuole eseguire una funzione definita dall'utente C#, Spark deve comprendere come avviare CLR .NET per eseguire la funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="6d31c-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="6d31c-118">**Microsoft. Spark.Worker** offre una raccolta di classi per Spark che consentono di abilitare questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6d31c-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="6d31c-119">Selezionare una versione netcoreapp Linux di [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) da distribuire nel cluster.</span><span class="sxs-lookup"><span data-stu-id="6d31c-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="6d31c-120">Ad esempio, se si vuole usare `.NET for Apache Spark v0.1.0` con `netcoreapp2.1`, scaricare [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="6d31c-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="6d31c-121">Caricare `Microsoft.Spark.Worker.<release>.tar.gz` e [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) in un file system distribuito (ad esempio, HDFS, WASB, ADLS) a cui può accedere il cluster.</span><span class="sxs-lookup"><span data-stu-id="6d31c-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="6d31c-122">Preparare .NET per l'app Apache Spark</span><span class="sxs-lookup"><span data-stu-id="6d31c-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="6d31c-123">Per creare l'app, seguire l'esercitazione [Introduzione](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="6d31c-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="6d31c-124">Pubblicare l'app Spark .NET come indipendente.</span><span class="sxs-lookup"><span data-stu-id="6d31c-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="6d31c-125">In Linux è possibile eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="6d31c-125">You can run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="6d31c-126">Produrre `<your app>.zip` per i file pubblicati.</span><span class="sxs-lookup"><span data-stu-id="6d31c-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="6d31c-127">In Linux è possibile eseguire il comando seguente con `zip`.</span><span class="sxs-lookup"><span data-stu-id="6d31c-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="6d31c-128">Caricare il file seguente in un file system distribuito, ad esempio HDFS, WASB, ADLS, a cui può accedere il cluster:</span><span class="sxs-lookup"><span data-stu-id="6d31c-128">Upload the following to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to:</span></span>

   * <span data-ttu-id="6d31c-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Questo file jar è incluso nel pacchetto NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) e viene posizionato nella directory di output di compilazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="6d31c-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="6d31c-130">I file (come i file di dipendenza o i dati comuni accessibili a ogni ruolo di lavoro) o gli assembly (ad esempio le DLL che contengono funzioni definite dall'utente o librerie da cui dipende `app`), vengono inseriti nella directory di lavoro di ogni executor.</span><span class="sxs-lookup"><span data-stu-id="6d31c-130">Files (like dependency files or common data accessible to every worker) or Assemblies (like DLLs that contain your user-defined functions or libraries that your `app` depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-azure-hdinsight-spark"></a><span data-ttu-id="6d31c-131">Distribuire in Azure HDInsight Spark</span><span class="sxs-lookup"><span data-stu-id="6d31c-131">Deploy to Azure HDInsight Spark</span></span>

<span data-ttu-id="6d31c-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) è l'implementazione Microsoft di Apache Spark nel cloud che consente agli utenti di avviare e configurare cluster Spark in Azure.</span><span class="sxs-lookup"><span data-stu-id="6d31c-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) is the Microsoft implementation of Apache Spark in the cloud that allows users to launch and configure Spark clusters in Azure.</span></span> <span data-ttu-id="6d31c-133">È possibile usare cluster HDInsight Spark per elaborare i dati archiviati in [Archiviazione di Azure](https://azure.microsoft.com/services/storage/) o in [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).</span><span class="sxs-lookup"><span data-stu-id="6d31c-133">You can use HDInsight Spark clusters to process your data stored in [Azure Storage](https://azure.microsoft.com/services/storage/) or [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).</span></span>

> [!NOTE]
> <span data-ttu-id="6d31c-134">Azure HDInsight Spark è basato su Linux.</span><span class="sxs-lookup"><span data-stu-id="6d31c-134">Azure HDInsight Spark is Linux-based.</span></span> <span data-ttu-id="6d31c-135">Se si è interessati a distribuire l'app in Azure HDInsight Spark, assicurarsi che l'app sia compatibile con .NET Standard e che venga usato il [compilatore .NET Core](https://dotnet.microsoft.com/download) per compilare l'app.</span><span class="sxs-lookup"><span data-stu-id="6d31c-135">If you are interested in deploying your app to Azure HDInsight Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="6d31c-136">Distribuire Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="6d31c-136">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="6d31c-137">Questo passaggio è necessario solo una volta per il cluster.</span><span class="sxs-lookup"><span data-stu-id="6d31c-137">This step is only required once for your cluster.</span></span>

<span data-ttu-id="6d31c-138">Eseguire `install-worker.sh` nel cluster usando [azioni script di HDInsight](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span><span class="sxs-lookup"><span data-stu-id="6d31c-138">Run `install-worker.sh` on the cluster using [HDInsight Script Actions](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span></span>

|<span data-ttu-id="6d31c-139">Impostazione</span><span class="sxs-lookup"><span data-stu-id="6d31c-139">Setting</span></span>|<span data-ttu-id="6d31c-140">Value</span><span class="sxs-lookup"><span data-stu-id="6d31c-140">Value</span></span>|
|-------|-----|
|<span data-ttu-id="6d31c-141">Tipo di script</span><span class="sxs-lookup"><span data-stu-id="6d31c-141">Script type</span></span>|<span data-ttu-id="6d31c-142">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="6d31c-142">Custom</span></span>|
|<span data-ttu-id="6d31c-143">NOME</span><span class="sxs-lookup"><span data-stu-id="6d31c-143">Name</span></span>|<span data-ttu-id="6d31c-144">Installare Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="6d31c-144">Install Microsoft.Spark.Worker</span></span>|
|<span data-ttu-id="6d31c-145">URI script Bash</span><span class="sxs-lookup"><span data-stu-id="6d31c-145">Bash script URI</span></span>|<span data-ttu-id="6d31c-146">URI in cui è stato caricato `install-worker.sh`.</span><span class="sxs-lookup"><span data-stu-id="6d31c-146">The URI to which you uploaded `install-worker.sh`.</span></span> <span data-ttu-id="6d31c-147">Ad esempio: `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span><span class="sxs-lookup"><span data-stu-id="6d31c-147">For example, `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span></span>|
|<span data-ttu-id="6d31c-148">Tipi di nodo</span><span class="sxs-lookup"><span data-stu-id="6d31c-148">Node type(s)</span></span>|<span data-ttu-id="6d31c-149">Lavoro</span><span class="sxs-lookup"><span data-stu-id="6d31c-149">Worker</span></span>|
|<span data-ttu-id="6d31c-150">Parametri</span><span class="sxs-lookup"><span data-stu-id="6d31c-150">Parameters</span></span>|<span data-ttu-id="6d31c-151">Parametri per `install-worker.sh`.</span><span class="sxs-lookup"><span data-stu-id="6d31c-151">Parameters to `install-worker.sh`.</span></span> <span data-ttu-id="6d31c-152">Ad esempio, se `install-worker.sh` viene caricato in Azure Data Lake Gen2, sarà `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.</span><span class="sxs-lookup"><span data-stu-id="6d31c-152">For example, if you uploaded `install-worker.sh` to Azure Data Lake Gen 2 then it would be `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.</span></span>|

![Immagine dell'azione script](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a><span data-ttu-id="6d31c-154">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="6d31c-154">Run your app</span></span>

<span data-ttu-id="6d31c-155">È possibile inviare il processo ad Azure HDInsight usando `spark-submit` o Apache Livy.</span><span class="sxs-lookup"><span data-stu-id="6d31c-155">You can submit your job to Azure HDInsight using `spark-submit` or Apache Livy.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="6d31c-156">Usare spark-submit</span><span class="sxs-lookup"><span data-stu-id="6d31c-156">Use spark-submit</span></span>

<span data-ttu-id="6d31c-157">È possibile usare il comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) per inviare processi .NET per Apache Spark ad Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="6d31c-157">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>
 
1. <span data-ttu-id="6d31c-158">`ssh` in uno dei nodi head del cluster.</span><span class="sxs-lookup"><span data-stu-id="6d31c-158">`ssh` into one of the head nodes in your cluster.</span></span>

1. <span data-ttu-id="6d31c-159">Esegui `spark-submit`:</span><span class="sxs-lookup"><span data-stu-id="6d31c-159">Run `spark-submit`:</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a><span data-ttu-id="6d31c-160">Usare Apache Livy</span><span class="sxs-lookup"><span data-stu-id="6d31c-160">Use Apache Livy</span></span>

<span data-ttu-id="6d31c-161">È possibile usare [Apache Livy](https://livy.incubator.apache.org/), l'API REST di Apache Spark, per inviare i processi .NET per Apache Spark a un cluster Azure HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="6d31c-161">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="6d31c-162">Per altre informazioni, vedere [Processi remoti con Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span><span class="sxs-lookup"><span data-stu-id="6d31c-162">For more information, see [Remote jobs with Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="6d31c-163">In Linux è possibile eseguire il comando seguente con `curl`:</span><span class="sxs-lookup"><span data-stu-id="6d31c-163">You can run the following command on Linux using `curl`:</span></span>

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.dotnet.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a><span data-ttu-id="6d31c-164">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6d31c-164">Next steps</span></span>

<span data-ttu-id="6d31c-165">In questa esercitazione è stata distribuita un'applicazione .NET per Apache Spark in Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="6d31c-165">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="6d31c-166">Per altre informazioni su HDInsight, continuare con la documentazione di Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="6d31c-166">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6d31c-167">Documentazione di Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="6d31c-167">Azure HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)

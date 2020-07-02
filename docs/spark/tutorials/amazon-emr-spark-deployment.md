---
title: Distribuire un'applicazione .NET per Apache Spark in Amazon EMR Spark
description: Informazioni su come distribuire un'applicazione .NET per Apache Spark in Amazon EMR Spark.
ms.date: 06/25/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c6cf26044693c5d923d11e1bbc72232e7009fe73
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618259"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a><span data-ttu-id="cfffa-103">Distribuire un'applicazione .NET per Apache Spark in Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="cfffa-103">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>

<span data-ttu-id="cfffa-104">Questa esercitazione illustra come distribuire un'applicazione .NET per Apache Spark in Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="cfffa-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Amazon EMR Spark.</span></span>

<span data-ttu-id="cfffa-105">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="cfffa-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="cfffa-106">Preparare Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="cfffa-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="cfffa-107">Pubblicare l'app Spark .NET</span><span class="sxs-lookup"><span data-stu-id="cfffa-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="cfffa-108">Distribuire l'app in Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="cfffa-108">Deploy your app to Amazon EMR Spark</span></span>
> * <span data-ttu-id="cfffa-109">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="cfffa-109">Run your app</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a><span data-ttu-id="cfffa-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cfffa-110">Prerequisites</span></span>

<span data-ttu-id="cfffa-111">Prima di iniziare, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cfffa-111">Before you start, do the following:</span></span>

* <span data-ttu-id="cfffa-112">Scaricare l'[interfaccia della riga di comando di AWS](https://aws.amazon.com/cli/).</span><span class="sxs-lookup"><span data-stu-id="cfffa-112">Download the [AWS CLI](https://aws.amazon.com/cli/).</span></span>
* <span data-ttu-id="cfffa-113">Scaricare [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="cfffa-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="cfffa-114">Si tratta di uno script helper che verrà usato in seguito per copiare i file dipendenti di .NET per Apache Spark nei nodi di lavoro del cluster Spark.</span><span class="sxs-lookup"><span data-stu-id="cfffa-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="cfffa-115">Preparare le dipendenze dei nodi di lavoro</span><span class="sxs-lookup"><span data-stu-id="cfffa-115">Prepare worker dependencies</span></span>

<span data-ttu-id="cfffa-116">**Microsoft. Spark. Worker** è un componente back-end che risiede nei singoli nodi del ruolo di lavoro del cluster Spark.</span><span class="sxs-lookup"><span data-stu-id="cfffa-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="cfffa-117">Quando si vuole eseguire una funzione definita dall'utente C#, Spark deve comprendere come avviare CLR .NET per eseguire la funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="cfffa-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="cfffa-118">**Microsoft. Spark.Worker** offre una raccolta di classi per Spark che consentono di abilitare questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="cfffa-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="cfffa-119">Selezionare una versione netcoreapp Linux di [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) da distribuire nel cluster.</span><span class="sxs-lookup"><span data-stu-id="cfffa-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="cfffa-120">Ad esempio, se si vuole usare `.NET for Apache Spark v0.1.0` con `netcoreapp2.1`, scaricare [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="cfffa-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="cfffa-121">Caricare `Microsoft.Spark.Worker.<release>.tar.gz` e [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) in un file system distribuito (ad esempio, S3) a cui può accedere il cluster.</span><span class="sxs-lookup"><span data-stu-id="cfffa-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., S3) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="cfffa-122">Preparare .NET per l'app Apache Spark</span><span class="sxs-lookup"><span data-stu-id="cfffa-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="cfffa-123">Per creare l'app, seguire l'esercitazione [Introduzione](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="cfffa-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="cfffa-124">Pubblicare l'app Spark .NET come indipendente.</span><span class="sxs-lookup"><span data-stu-id="cfffa-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="cfffa-125">Eseguire il comando seguente in Linux.</span><span class="sxs-lookup"><span data-stu-id="cfffa-125">Run the following command on Linux.</span></span>

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="cfffa-126">Produrre `<your app>.zip` per i file pubblicati.</span><span class="sxs-lookup"><span data-stu-id="cfffa-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="cfffa-127">Eseguire il comando seguente in Linux con `zip`.</span><span class="sxs-lookup"><span data-stu-id="cfffa-127">Run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="cfffa-128">Caricare gli elementi seguenti in un file system distribuito (ad esempio, S3) a cui può accedere il cluster:</span><span class="sxs-lookup"><span data-stu-id="cfffa-128">Upload the following items to a distributed file system (e.g., S3) that your cluster has access to:</span></span>

   * <span data-ttu-id="cfffa-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Questo file jar è incluso nel pacchetto NuGet [Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) e si trova nella directory di output di compilazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="cfffa-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="cfffa-130">I file (come i file di dipendenza o i dati comuni accessibili a ogni ruolo di lavoro) o gli assembly (ad esempio le DLL che contengono funzioni definite dall'utente o librerie da cui dipende l'app), vengono inseriti nella directory di lavoro di ogni executor.</span><span class="sxs-lookup"><span data-stu-id="cfffa-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-amazon-emr-spark"></a><span data-ttu-id="cfffa-131">Distribuire in Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="cfffa-131">Deploy to Amazon EMR Spark</span></span>

<span data-ttu-id="cfffa-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) è una piattaforma cluster gestita che semplifica l'esecuzione di framework per Big Data in AWS.</span><span class="sxs-lookup"><span data-stu-id="cfffa-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

> [!NOTE]
> <span data-ttu-id="cfffa-133">Amazon EMR Spark è basato su Linux.</span><span class="sxs-lookup"><span data-stu-id="cfffa-133">Amazon EMR Spark is Linux-based.</span></span> <span data-ttu-id="cfffa-134">Se si è interessati a distribuire l'app in Amazon EMR Spark, pertanto, assicurarsi che l'app sia compatibile con .NET Standard e che venga usato il [compilatore .NET Core](https://dotnet.microsoft.com/download) per compilare l'app.</span><span class="sxs-lookup"><span data-stu-id="cfffa-134">Therefore, if you are interested in deploying your app to Amazon EMR Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="cfffa-135">Distribuire Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="cfffa-135">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="cfffa-136">Questo passaggio è necessario solo in fase di creazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="cfffa-136">This step is only required at cluster creation.</span></span>

<span data-ttu-id="cfffa-137">Eseguire `install-worker.sh` durante la creazione del cluster usando [azioni bootstrap](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span><span class="sxs-lookup"><span data-stu-id="cfffa-137">Run `install-worker.sh` during cluster creation using [Bootstrap Actions](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span></span>

<span data-ttu-id="cfffa-138">Eseguire il comando seguente in Linux usando l'interfaccia della riga di comando di AWS.</span><span class="sxs-lookup"><span data-stu-id="cfffa-138">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr create-cluster \
--name "Test cluster" \
--release-label emr-5.23.0 \
--use-default-roles \
--ec2-attributes KeyName=myKey \
--applications Name=Spark \
--instance-count 3 \
--instance-type m1.medium \
--bootstrap-actions Path=s3://mybucket/<some dir>/install-worker.sh,Name="Install Microsoft.Spark.Worker",Args=["aws","s3://mybucket/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz","/usr/local/bin"]
```

## <a name="run-your-app"></a><span data-ttu-id="cfffa-139">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="cfffa-139">Run your app</span></span>

<span data-ttu-id="cfffa-140">Per eseguire l'app in Amazon EMR Spark, è possibile procedere in due modi: spark-submit e Amazon EMR Steps.</span><span class="sxs-lookup"><span data-stu-id="cfffa-140">There are two ways to run your app in Amazon EMR Spark: spark-submit and Amazon EMR Steps.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="cfffa-141">Usare spark-submit</span><span class="sxs-lookup"><span data-stu-id="cfffa-141">Use spark-submit</span></span>

<span data-ttu-id="cfffa-142">È possibile usare il comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) per inviare processi .NET per Apache Spark ad Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="cfffa-142">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Amazon EMR Spark.</span></span>

1. <span data-ttu-id="cfffa-143">`ssh` in uno dei nodi nel cluster.</span><span class="sxs-lookup"><span data-stu-id="cfffa-143">`ssh` into one of the nodes in the cluster.</span></span>

2. <span data-ttu-id="cfffa-144">Eseguire `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="cfffa-144">Run `spark-submit`.</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a><span data-ttu-id="cfffa-145">Usare Amazon EMR Steps</span><span class="sxs-lookup"><span data-stu-id="cfffa-145">Use Amazon EMR Steps</span></span>

<span data-ttu-id="cfffa-146">È possibile usare [Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) per inviare i processi al framework Spark installato nel cluster EMR.</span><span class="sxs-lookup"><span data-stu-id="cfffa-146">[Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) can be used to submit jobs to the Spark framework installed on the EMR cluster.</span></span>

<span data-ttu-id="cfffa-147">Eseguire il comando seguente in Linux usando l'interfaccia della riga di comando di AWS.</span><span class="sxs-lookup"><span data-stu-id="cfffa-147">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.dotnet.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a><span data-ttu-id="cfffa-148">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cfffa-148">Next steps</span></span>

<span data-ttu-id="cfffa-149">In questa esercitazione è stata distribuita un'applicazione .NET per Apache Spark in Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="cfffa-149">In this tutorial, you deployed your .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="cfffa-150">Per esaminare progetti di esempio di .NET per Apache Spark, passare a GitHub.</span><span class="sxs-lookup"><span data-stu-id="cfffa-150">For .NET for Apache Spark example projects, continue to GitHub.</span></span>

> [!div class="nextstepaction"]
> <span data-ttu-id="cfffa-151">[.NET for Apache Spark samples](https://github.com/dotnet/spark/tree/master/examples) (Esempi di .NET per Apache Spark)</span><span class="sxs-lookup"><span data-stu-id="cfffa-151">[.NET for Apache Spark samples](https://github.com/dotnet/spark/tree/master/examples)</span></span>

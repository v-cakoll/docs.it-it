---
title: Inviare un .NET per Apache Spark processo a databricks
description: Informazioni su come inviare un .NET per Apache Spark processo a databricks con Spark-Submit e set jar.
ms.date: 12/05/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 9cd3d40871d4600660957ec268f192ef3e045845
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838351"
---
# <a name="submit-a-net-for-apache-spark-job-to-databricks"></a><span data-ttu-id="e583a-103">Inviare un .NET per Apache Spark processo a databricks</span><span class="sxs-lookup"><span data-stu-id="e583a-103">Submit a .NET for Apache Spark job to Databricks</span></span>

<span data-ttu-id="e583a-104">Esistono due modi per distribuire .NET per Apache Spark processo a databricks: `spark-submit` e set jar.</span><span class="sxs-lookup"><span data-stu-id="e583a-104">There are two ways to deploy your .NET for Apache Spark job to Databricks: `spark-submit` and Set Jar.</span></span> 

## <a name="deploy-using-spark-submit"></a><span data-ttu-id="e583a-105">Eseguire la distribuzione con Spark-Submit</span><span class="sxs-lookup"><span data-stu-id="e583a-105">Deploy using spark-submit</span></span>

<span data-ttu-id="e583a-106">È possibile usare il comando [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) per inviare .net per Apache Spark processi a databricks.</span><span class="sxs-lookup"><span data-stu-id="e583a-106">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Databricks.</span></span> <span data-ttu-id="e583a-107">`spark-submit` consente l'invio solo a un cluster che viene creato su richiesta.</span><span class="sxs-lookup"><span data-stu-id="e583a-107">`spark-submit` allows submission only to a cluster that gets created on-demand.</span></span>

1. <span data-ttu-id="e583a-108">Passare all'area di lavoro databricks e creare un processo.</span><span class="sxs-lookup"><span data-stu-id="e583a-108">Navigate to your Databricks Workspace and create a job.</span></span> <span data-ttu-id="e583a-109">Scegliere un titolo per il processo e quindi selezionare **Configura Spark-Submit**.</span><span class="sxs-lookup"><span data-stu-id="e583a-109">Choose a title for your job, and then select **Configure spark-submit**.</span></span> <span data-ttu-id="e583a-110">Incollare i parametri seguenti nella configurazione del processo, quindi selezionare **conferma**.</span><span class="sxs-lookup"><span data-stu-id="e583a-110">Paste the following parameters in the job configuration, then select **Confirm**.</span></span>

    ```
    ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
    ```

    > [!NOTE]
    > <span data-ttu-id="e583a-111">Aggiornare il contenuto del parametro precedente in base ai file e alla configurazione specifici.</span><span class="sxs-lookup"><span data-stu-id="e583a-111">Update the contents of the above parameter based on your specific files and configuration.</span></span> <span data-ttu-id="e583a-112">Ad esempio, fare riferimento alla versione del file jar Microsoft. Spark caricato in DBFS e usare il nome appropriato dell'app e il file zip dell'app pubblicata.</span><span class="sxs-lookup"><span data-stu-id="e583a-112">For instance, reference the version of the Microsoft.Spark jar file that you uploaded to DBFS, and use the appropriate name of your app and published app zip file.</span></span>

2. <span data-ttu-id="e583a-113">Passare al processo e selezionare **modifica** per configurare il cluster del processo.</span><span class="sxs-lookup"><span data-stu-id="e583a-113">Navigate to your job and select **Edit** to configure your job's cluster.</span></span> <span data-ttu-id="e583a-114">Impostare la versione di Databricks Runtime in base alla versione di Apache Spark che si desidera utilizzare nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e583a-114">Set the Databricks Runtime Version based on the version of Apache Spark you wish to use in your deployment.</span></span> <span data-ttu-id="e583a-115">Selezionare quindi **Opzioni avanzate > script init**e impostare percorso script init come `dbfs:/spark-dotnet/db-init.sh`.</span><span class="sxs-lookup"><span data-stu-id="e583a-115">Then select **Advanced Options > Init Scripts**, and set Init Script Path as `dbfs:/spark-dotnet/db-init.sh`.</span></span> <span data-ttu-id="e583a-116">Selezionare **conferma** per confermare le impostazioni del cluster.</span><span class="sxs-lookup"><span data-stu-id="e583a-116">Select **Confirm** to confirm your cluster settings.</span></span>

3. <span data-ttu-id="e583a-117">Passare al processo e selezionare **Esegui adesso** per eseguire il processo nel cluster Spark appena configurato.</span><span class="sxs-lookup"><span data-stu-id="e583a-117">Navigate to your job and select **Run Now** to run your job on your newly configured Spark cluster.</span></span> <span data-ttu-id="e583a-118">Sono necessari alcuni minuti per la creazione del cluster del processo.</span><span class="sxs-lookup"><span data-stu-id="e583a-118">It takes a few minutes for the job's cluster to be created.</span></span> <span data-ttu-id="e583a-119">Una volta creato, il processo verrà inviato.</span><span class="sxs-lookup"><span data-stu-id="e583a-119">Once it is created, your job will be submitted.</span></span> <span data-ttu-id="e583a-120">È possibile visualizzare l'output selezionando **cluster** dal menu a sinistra dell'area di lavoro databricks e quindi selezionando **log driver**.</span><span class="sxs-lookup"><span data-stu-id="e583a-120">You can view the output by selecting **Clusters** from the left menu of your Databricks workspace, then select **Driver Logs**.</span></span>

## <a name="deploy-using-set-jar"></a><span data-ttu-id="e583a-121">Eseguire la distribuzione usando set jar</span><span class="sxs-lookup"><span data-stu-id="e583a-121">Deploy using Set Jar</span></span>

<span data-ttu-id="e583a-122">In alternativa, è possibile usare [set jar](https://docs.microsoft.com/azure/databricks/jobs#--create-a-job) nell'area di lavoro di databricks per inviare .net per Apache Spark processi a databricks.</span><span class="sxs-lookup"><span data-stu-id="e583a-122">Alternatively, you can use [Set Jar](https://docs.microsoft.com/azure/databricks/jobs#--create-a-job) in your Databricks workspace to submit .NET for Apache Spark jobs to Databricks.</span></span> <span data-ttu-id="e583a-123">*Set jar* consente l'invio di processi a un cluster attivo esistente.</span><span class="sxs-lookup"><span data-stu-id="e583a-123">*Set Jar* allows job submission to an existing active cluster.</span></span>

### <a name="one-time-setup"></a><span data-ttu-id="e583a-124">Installazione singola</span><span class="sxs-lookup"><span data-stu-id="e583a-124">One-time setup</span></span>

1. <span data-ttu-id="e583a-125">Passare al cluster databricks e selezionare **processi** dal menu a sinistra, quindi **impostare jar**.</span><span class="sxs-lookup"><span data-stu-id="e583a-125">Navigate to your Databricks cluster and select **Jobs** from the left-side menu, followed by **Set JAR**.</span></span>

2. <span data-ttu-id="e583a-126">Caricare il `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar`appropriato.</span><span class="sxs-lookup"><span data-stu-id="e583a-126">Upload the appropriate `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar`.</span></span>

3. <span data-ttu-id="e583a-127">Modificare i parametri seguenti in modo da includere il nome corretto per il file eseguibile pubblicato al posto di `<your-app-name>`:</span><span class="sxs-lookup"><span data-stu-id="e583a-127">Modify the following parameters to include the correct name for the executable that you published in place of `<your-app-name>`:</span></span>

    ```
    Main Class: org.apache.spark.deploy.dotnet.DotnetRunner
    Arguments /dbfs/apps/<your-app-name>.zip <your-app-name>
    ```

4. <span data-ttu-id="e583a-128">Configurare il cluster in modo che punti a un cluster esistente per cui è già stato impostato lo script init.</span><span class="sxs-lookup"><span data-stu-id="e583a-128">Configure the cluster to point to an existing cluster for which you have already set the init script.</span></span>

### <a name="publish-and-run-your-app"></a><span data-ttu-id="e583a-129">Pubblicare ed eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="e583a-129">Publish and run your app</span></span>

1. <span data-ttu-id="e583a-130">Assicurarsi di aver pubblicato l'app e che il codice dell'applicazione non usi `SparkSession.Stop()`.</span><span class="sxs-lookup"><span data-stu-id="e583a-130">Ensure you have published your app, and that your application code does not use `SparkSession.Stop()`.</span></span>

2. <span data-ttu-id="e583a-131">Usare l'interfaccia della riga di comando di [databricks](https://docs.microsoft.com/azure/databricks/dev-tools/databricks-cli) per caricare l'applicazione nel cluster databricks.</span><span class="sxs-lookup"><span data-stu-id="e583a-131">Use [Databricks CLI](https://docs.microsoft.com/azure/databricks/dev-tools/databricks-cli) to upload your application to your Databricks cluster.</span></span> <span data-ttu-id="e583a-132">Ad esempio, usare il comando seguente per caricare l'app pubblicata nel cluster:</span><span class="sxs-lookup"><span data-stu-id="e583a-132">For example, use the following command to upload your published app to your cluster:</span></span>

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
    ```

3. <span data-ttu-id="e583a-133">Se nell'app sono presenti funzioni definite dall'utente, gli assembly di app, ad esempio le dll che contengono funzioni definite dall'utente e le relative dipendenze, devono essere posizionati nella directory di lavoro di ogni *Microsoft. Spark. Worker*.</span><span class="sxs-lookup"><span data-stu-id="e583a-133">If you have any user-defined functions in your app, the app assemblies, such as DLLs that contain user-defined functions along with their dependencies, need to be placed in the working directory of each *Microsoft.Spark.Worker*.</span></span>

    <span data-ttu-id="e583a-134">Caricare gli assembly dell'applicazione nel cluster databricks:</span><span class="sxs-lookup"><span data-stu-id="e583a-134">Upload your application assemblies to your Databricks cluster:</span></span>

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <assembly>.dll dbfs:/apps/dependencies
    ```

    <span data-ttu-id="e583a-135">Rimuovere il commento e modificare la sezione relativa alle dipendenze dell'app in [DB-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) in modo che punti al percorso delle dipendenze dell'app.</span><span class="sxs-lookup"><span data-stu-id="e583a-135">Uncomment and modify the app dependencies section in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) to point to your app dependencies path.</span></span> <span data-ttu-id="e583a-136">Caricare quindi il *DB-init.sh* aggiornato nel cluster:</span><span class="sxs-lookup"><span data-stu-id="e583a-136">Then, upload the updated *db-init.sh* to your cluster:</span></span>

    ```console
    cd <path-to-db-init-and-install-worker>
    databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
    ```

4. <span data-ttu-id="e583a-137">Passare a **databricks cluster > Jobs > [nome processo] > Esegui ora** per eseguire il processo.</span><span class="sxs-lookup"><span data-stu-id="e583a-137">Navigate to **Databricks cluster > Jobs > [Job-name] > Run Now** to run your job.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e583a-138">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e583a-138">Next steps</span></span>

* [<span data-ttu-id="e583a-139">Introduzione a .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="e583a-139">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="e583a-140">Distribuire un'applicazione .NET per Apache Spark in Databricks</span><span class="sxs-lookup"><span data-stu-id="e583a-140">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="e583a-141">Documentazione di Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="e583a-141">Azure Databricks Documentation</span></span>](https://docs.microsoft.com/azure/azure-databricks/)

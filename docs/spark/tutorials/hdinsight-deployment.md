---
title: Distribuire un'applicazione .NET per Apache Spark in Azure HDInsight
description: Informazioni su come distribuire un'applicazione .NET per Apache Spark in HDInsight.
ms.date: 01/23/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 6b8dbe395a5db9631433a5821f5ef2b9ade556f6
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895688"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="5795c-103">Esercitazione: distribuire un'applicazione .NET per Apache Spark in Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="5795c-103">Tutorial: Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="5795c-104">Questa esercitazione illustra come distribuire .NET per Apache Spark app nel cloud tramite un cluster Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="5795c-104">This tutorial teaches you how to deploy your .NET for Apache Spark app to the cloud through an Azure HDInsight cluster.</span></span> <span data-ttu-id="5795c-105">HDInsight semplifica la creazione e la configurazione di un cluster Spark in Azure poiché i cluster Spark in HDInsight sono compatibili con archiviazione di Azure e Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="5795c-105">HDInsight makes it easier to create and configure a Spark cluster in Azure since Spark clusters in HDInsight are compatible with Azure Storage and Azure Data Lake Storage.</span></span>

<span data-ttu-id="5795c-106">In questa esercitazione si apprenderà come:</span><span class="sxs-lookup"><span data-stu-id="5795c-106">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="5795c-107">Accedere agli account di archiviazione usando Azure Storage Explorer.</span><span class="sxs-lookup"><span data-stu-id="5795c-107">Access your storage accounts using Azure Storage Explorer.</span></span>
> * <span data-ttu-id="5795c-108">Creare un cluster HDInsight di Azure.</span><span class="sxs-lookup"><span data-stu-id="5795c-108">Create an Azure HDInsight cluster.</span></span>
> * <span data-ttu-id="5795c-109">Pubblicare .NET per Apache Spark app.</span><span class="sxs-lookup"><span data-stu-id="5795c-109">Publish your .NET for Apache Spark app.</span></span>
> * <span data-ttu-id="5795c-110">Creare ed eseguire un'azione di script HDInsight.</span><span class="sxs-lookup"><span data-stu-id="5795c-110">Create and run an HDInsight script action.</span></span>
> * <span data-ttu-id="5795c-111">Eseguire un'app .NET per Apache Spark in un cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="5795c-111">Run a .NET for Apache Spark app on an HDInsight cluster.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5795c-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5795c-112">Prerequisites</span></span>

<span data-ttu-id="5795c-113">Prima di iniziare, eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5795c-113">Before you start, do the following tasks:</span></span>

* <span data-ttu-id="5795c-114">Se non si ha una sottoscrizione di Azure, creare un [account gratuito](https://azure.microsoft.com/free/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="5795c-114">If you don't have an Azure subscription, create a [free account](https://azure.microsoft.com/free/dotnet/).</span></span>
* <span data-ttu-id="5795c-115">Accedere al [portale di Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="5795c-115">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
* <span data-ttu-id="5795c-116">Installare Azure Storage Explorer nel computer [Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409), [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409)o [MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409) .</span><span class="sxs-lookup"><span data-stu-id="5795c-116">Install Azure Storage Explorer on your [Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409), [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409), or [MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409) computer.</span></span>
* <span data-ttu-id="5795c-117">Completare l'esercitazione [su .NET per Apache Spark-introduzione in 10 minuti](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) .</span><span class="sxs-lookup"><span data-stu-id="5795c-117">Complete the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial.</span></span>

## <a name="access-your-storage-accounts"></a><span data-ttu-id="5795c-118">Accedere agli account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="5795c-118">Access your storage accounts</span></span>

1. <span data-ttu-id="5795c-119">Aprire Azure Storage Explorer.</span><span class="sxs-lookup"><span data-stu-id="5795c-119">Open Azure Storage Explorer.</span></span>

2. <span data-ttu-id="5795c-120">Selezionare **Aggiungi account** nel menu a sinistra e accedere al proprio account Azure.</span><span class="sxs-lookup"><span data-stu-id="5795c-120">Select **Add Account** on the left menu, and sign in to your Azure account.</span></span>

    ![Accedere all'account Azure da Storage Explorer](./media/hdinsight-deployment/signin-azure-storage-explorer.png)

   <span data-ttu-id="5795c-122">Dopo aver eseguito l'accesso, verranno visualizzati tutti gli account di archiviazione disponibili e tutte le risorse caricate negli account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="5795c-122">After you sign in, you should see all storage accounts you have and any resources you have uploaded to your storage accounts.</span></span>

## <a name="create-an-hdinsight-cluster"></a><span data-ttu-id="5795c-123">Creazione di un cluster HDInsight</span><span class="sxs-lookup"><span data-stu-id="5795c-123">Create an HDInsight cluster</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5795c-124">La fatturazione per i cluster HDInsight viene rivalutata al minuto, anche se non vengono usate.</span><span class="sxs-lookup"><span data-stu-id="5795c-124">Billing for HDInsight clusters is prorated per minute, even if you're not using them.</span></span> <span data-ttu-id="5795c-125">Assicurarsi di eliminare il cluster dopo aver finito di usarlo.</span><span class="sxs-lookup"><span data-stu-id="5795c-125">Be sure to delete your cluster after you have finished using it.</span></span> <span data-ttu-id="5795c-126">Per ulteriori informazioni, vedere la sezione [Pulisci risorse in](#clean-up-resources) questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="5795c-126">For more information, see the [Clean up resources](#clean-up-resources) section of this tutorial.</span></span>

1. <span data-ttu-id="5795c-127">Visitare il [portale di Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="5795c-127">Visit the [Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="5795c-128">Selezionare **+ Crea una risorsa**.</span><span class="sxs-lookup"><span data-stu-id="5795c-128">Select **+ Create a resource**.</span></span> <span data-ttu-id="5795c-129">Selezionare quindi **HDInsight** dalla categoria **Analytics** .</span><span class="sxs-lookup"><span data-stu-id="5795c-129">Then, select **HDInsight** from the **Analytics** category.</span></span>

    ![Creare una risorsa HDInsight da portale di Azure](./media/hdinsight-deployment/create-hdinsight-resource.png)

3. <span data-ttu-id="5795c-131">In **Informazioni di base** specificare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5795c-131">Under **Basics**, provide the following values:</span></span>

    |<span data-ttu-id="5795c-132">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5795c-132">Property</span></span>  |<span data-ttu-id="5795c-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5795c-133">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="5795c-134">Subscription</span><span class="sxs-lookup"><span data-stu-id="5795c-134">Subscription</span></span>  | <span data-ttu-id="5795c-135">Dall'elenco a discesa scegliere una delle sottoscrizioni di Azure attive.</span><span class="sxs-lookup"><span data-stu-id="5795c-135">From the drop-down, choose one of your active Azure subscriptions.</span></span> |
    |<span data-ttu-id="5795c-136">Resource group</span><span class="sxs-lookup"><span data-stu-id="5795c-136">Resource group</span></span> | <span data-ttu-id="5795c-137">Specificare se si vuole creare un nuovo gruppo di risorse o usarne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="5795c-137">Specify whether you want to create a new resource group or use an existing one.</span></span> <span data-ttu-id="5795c-138">Un gruppo di risorse è un contenitore con risorse correlate per una soluzione Azure.</span><span class="sxs-lookup"><span data-stu-id="5795c-138">A resource group is a container that holds related resources for an Azure solution.</span></span> |
    |<span data-ttu-id="5795c-139">Nome cluster</span><span class="sxs-lookup"><span data-stu-id="5795c-139">Cluster name</span></span> | <span data-ttu-id="5795c-140">Assegnare un nome al cluster HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="5795c-140">Give a name to your HDInsight Spark cluster.</span></span>|
    |<span data-ttu-id="5795c-141">Location</span><span class="sxs-lookup"><span data-stu-id="5795c-141">Location</span></span>   | <span data-ttu-id="5795c-142">Selezionare una posizione per il gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="5795c-142">Select a location for the resource group.</span></span> <span data-ttu-id="5795c-143">Il modello usa questa posizione per la creazione del cluster e per l'archiviazione del cluster predefinita.</span><span class="sxs-lookup"><span data-stu-id="5795c-143">The template uses this location for creating the cluster as well as for the default cluster storage.</span></span> |
    |<span data-ttu-id="5795c-144">Tipo di cluster</span><span class="sxs-lookup"><span data-stu-id="5795c-144">Cluster type</span></span>| <span data-ttu-id="5795c-145">Selezionare **Spark** come tipo di cluster.</span><span class="sxs-lookup"><span data-stu-id="5795c-145">Select **Spark** as the cluster type.</span></span>|
    |<span data-ttu-id="5795c-146">Versione del cluster</span><span class="sxs-lookup"><span data-stu-id="5795c-146">Cluster version</span></span>|<span data-ttu-id="5795c-147">Questo campo verrà automaticamente popolato con la versione predefinita dopo che è stato selezionato il tipo di cluster.</span><span class="sxs-lookup"><span data-stu-id="5795c-147">This field will autopopulate with the default version once the cluster type has been selected.</span></span> <span data-ttu-id="5795c-148">Selezionare una versione 2,3 o 2,4 di Spark.</span><span class="sxs-lookup"><span data-stu-id="5795c-148">Select a 2.3 or 2.4 version of Spark.</span></span>|
    |<span data-ttu-id="5795c-149">Nome utente dell'account di accesso del cluster</span><span class="sxs-lookup"><span data-stu-id="5795c-149">Cluster login username</span></span>| <span data-ttu-id="5795c-150">Immettere il nome utente dell'account di accesso del cluster.</span><span class="sxs-lookup"><span data-stu-id="5795c-150">Enter the cluster login username.</span></span>  <span data-ttu-id="5795c-151">Il nome predefinito è *admin*.</span><span class="sxs-lookup"><span data-stu-id="5795c-151">The default name is *admin*.</span></span> |
    |<span data-ttu-id="5795c-152">Password di accesso al cluster</span><span class="sxs-lookup"><span data-stu-id="5795c-152">Cluster login password</span></span>| <span data-ttu-id="5795c-153">Immettere una password di accesso.</span><span class="sxs-lookup"><span data-stu-id="5795c-153">Enter any login password.</span></span> |
    |<span data-ttu-id="5795c-154">Nome utente Secure Shell (SSH)</span><span class="sxs-lookup"><span data-stu-id="5795c-154">Secure Shell (SSH) username</span></span>| <span data-ttu-id="5795c-155">Immettere il nome utente SSH.</span><span class="sxs-lookup"><span data-stu-id="5795c-155">Enter the SSH username.</span></span> <span data-ttu-id="5795c-156">Per impostazione predefinita, questo account condivide la stessa password dell'account *Nome utente dell'account di accesso del cluster*.</span><span class="sxs-lookup"><span data-stu-id="5795c-156">By default, this account shares the same password as the *Cluster Login username* account.</span></span> |

4. <span data-ttu-id="5795c-157">Selezionare **Avanti: archiviazione >>** per continuare con la pagina **archiviazione** .</span><span class="sxs-lookup"><span data-stu-id="5795c-157">Select **Next: Storage >>** to continue to the **Storage** page.</span></span> <span data-ttu-id="5795c-158">In **Archiviazione** specificare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5795c-158">Under **Storage**, provide the following values:</span></span>

    |<span data-ttu-id="5795c-159">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5795c-159">Property</span></span>  |<span data-ttu-id="5795c-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5795c-160">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="5795c-161">Tipo di archiviazione primario</span><span class="sxs-lookup"><span data-stu-id="5795c-161">Primary storage type</span></span>|<span data-ttu-id="5795c-162">Usare il valore predefinito **Archiviazione di Azure**.</span><span class="sxs-lookup"><span data-stu-id="5795c-162">Use the default value **Azure Storage**.</span></span>|
    |<span data-ttu-id="5795c-163">Metodo di selezione</span><span class="sxs-lookup"><span data-stu-id="5795c-163">Selection method</span></span>|<span data-ttu-id="5795c-164">Usare il valore predefinito **Selezionare dall'elenco**.</span><span class="sxs-lookup"><span data-stu-id="5795c-164">Use the default value **Select from list**.</span></span>|
    |<span data-ttu-id="5795c-165">Account di archiviazione primario</span><span class="sxs-lookup"><span data-stu-id="5795c-165">Primary storage account</span></span>|<span data-ttu-id="5795c-166">Scegliere la sottoscrizione e uno degli account di archiviazione attivi all'interno di tale sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="5795c-166">Choose your subscription and one of your active storage accounts within that subscription.</span></span>|
    |<span data-ttu-id="5795c-167">Contenitore</span><span class="sxs-lookup"><span data-stu-id="5795c-167">Container</span></span>|<span data-ttu-id="5795c-168">Questo contenitore è il contenitore BLOB specifico nell'account di archiviazione in cui il cluster Cerca i file per l'esecuzione dell'app nel cloud.</span><span class="sxs-lookup"><span data-stu-id="5795c-168">This container is the specific blob container in your storage account where your cluster looks for files to run your app in the cloud.</span></span> <span data-ttu-id="5795c-169">È possibile assegnargli qualsiasi nome disponibile.</span><span class="sxs-lookup"><span data-stu-id="5795c-169">You can give it any available name.</span></span>|

5. <span data-ttu-id="5795c-170">In **Rivedi e crea** selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="5795c-170">Under **Review + create**, select **Create**.</span></span> <span data-ttu-id="5795c-171">La creazione del cluster richiede circa 20 minuti.</span><span class="sxs-lookup"><span data-stu-id="5795c-171">It takes about 20 minutes to create the cluster.</span></span> <span data-ttu-id="5795c-172">Il cluster deve essere creato prima di continuare con il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="5795c-172">The cluster must be created before you can continue to the next step.</span></span>

## <a name="publish-your-app"></a><span data-ttu-id="5795c-173">Pubblicare l'app</span><span class="sxs-lookup"><span data-stu-id="5795c-173">Publish your app</span></span>

<span data-ttu-id="5795c-174">Successivamente, pubblicare il *mySparkApp* creato in [.NET per Apache Spark-introduzione in 10 minuti](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) , che consente al cluster Spark di accedere a tutti i file necessari per eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="5795c-174">Next, you publish the *mySparkApp* created in the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial, which gives your Spark cluster access to all the files it needs to run your app.</span></span>

1. <span data-ttu-id="5795c-175">Eseguire i comandi seguenti per pubblicare il *mySparkApp*:</span><span class="sxs-lookup"><span data-stu-id="5795c-175">Run the following commands to publish the *mySparkApp*:</span></span>

   <span data-ttu-id="5795c-176">**In Windows:**</span><span class="sxs-lookup"><span data-stu-id="5795c-176">**On Windows:**</span></span>

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

   <span data-ttu-id="5795c-177">**In Linux:**</span><span class="sxs-lookup"><span data-stu-id="5795c-177">**On Linux:**</span></span>

   ```bash
   cd mySparkApp
   foo@bar:~/path/to/app$ dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. <span data-ttu-id="5795c-178">Eseguire le attività seguenti per comprimere i file dell'app pubblicata in modo che sia possibile caricarli facilmente nel cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="5795c-178">Do the following tasks to zip your published app files so that you can easily upload them to your HDInsight cluster.</span></span>

   <span data-ttu-id="5795c-179">**In Windows:**</span><span class="sxs-lookup"><span data-stu-id="5795c-179">**On Windows:**</span></span>

   <span data-ttu-id="5795c-180">Passare a *mySparkApp/bin/Release/netcoreapp 3.0/Ubuntu. 16.04-x64*.</span><span class="sxs-lookup"><span data-stu-id="5795c-180">Navigate to *mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64*.</span></span> <span data-ttu-id="5795c-181">Quindi, fare clic con il pulsante destro del mouse su cartella di **pubblicazione** e selezionare **Invia a > cartella compressa**.</span><span class="sxs-lookup"><span data-stu-id="5795c-181">Then, right-click on **Publish** folder and select **Send to > Compressed (zipped) folder**.</span></span> <span data-ttu-id="5795c-182">Assegnare alla nuova cartella il nome **Publish. zip**.</span><span class="sxs-lookup"><span data-stu-id="5795c-182">Name the new folder **publish.zip**.</span></span>

   <span data-ttu-id="5795c-183">**In Linux eseguire il comando seguente:**</span><span class="sxs-lookup"><span data-stu-id="5795c-183">**On Linux, run the following command:**</span></span>

   ```bash
   zip -r publish.zip
   ```

## <a name="upload-files-to-azure"></a><span data-ttu-id="5795c-184">Caricare file in Azure</span><span class="sxs-lookup"><span data-stu-id="5795c-184">Upload files to Azure</span></span>

<span data-ttu-id="5795c-185">Usare quindi il Azure Storage Explorer per caricare i cinque file seguenti nel contenitore BLOB scelto per l'archiviazione del cluster:</span><span class="sxs-lookup"><span data-stu-id="5795c-185">Next, you use the Azure Storage Explorer to upload the following five files to the blob container you chose for your cluster's storage:</span></span>

* <span data-ttu-id="5795c-186">Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="5795c-186">Microsoft.Spark.Worker</span></span>
* <span data-ttu-id="5795c-187">install-worker.sh</span><span class="sxs-lookup"><span data-stu-id="5795c-187">install-worker.sh</span></span>
* <span data-ttu-id="5795c-188">Publish. zip</span><span class="sxs-lookup"><span data-stu-id="5795c-188">publish.zip</span></span>
* <span data-ttu-id="5795c-189">Microsoft-Spark-2.3. x-0.3.0. jar</span><span class="sxs-lookup"><span data-stu-id="5795c-189">microsoft-spark-2.3.x-0.3.0.jar</span></span>
* <span data-ttu-id="5795c-190">input. txt.</span><span class="sxs-lookup"><span data-stu-id="5795c-190">input.txt.</span></span>

1. <span data-ttu-id="5795c-191">Aprire Azure Storage Explorer e passare all'account di archiviazione dal menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="5795c-191">Open Azure Storage Explorer and navigate to your storage account from the left menu.</span></span> <span data-ttu-id="5795c-192">Eseguire il drill-down nel contenitore BLOB per il cluster in **contenitori BLOB** nell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="5795c-192">Drill down to the blob container for your cluster under **Blob Containers** in your storage account.</span></span>

2. <span data-ttu-id="5795c-193">*Microsoft. Spark. Worker* consente di Apache Spark eseguire l'app, ad esempio qualsiasi funzione definita dall'utente (UDF) che è stata scritta.</span><span class="sxs-lookup"><span data-stu-id="5795c-193">*Microsoft.Spark.Worker* helps Apache Spark execute your app, such as any user-defined functions (UDFs) you may have written.</span></span> <span data-ttu-id="5795c-194">Scaricare [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases/download/v0.3.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.3.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="5795c-194">Download [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.3.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.3.0.tar.gz).</span></span> <span data-ttu-id="5795c-195">Selezionare quindi **carica** in Azure Storage Explorer per caricare il ruolo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5795c-195">Then, select **Upload** in Azure Storage Explorer to upload the worker.</span></span>

   ![Caricare file in Azure Storage Explorer](./media/hdinsight-deployment/upload-files-to-storage.png)

3. <span data-ttu-id="5795c-197">*Install-Worker.sh* è uno script che consente di copiare .net per Apache Spark file dipendenti nei nodi del cluster.</span><span class="sxs-lookup"><span data-stu-id="5795c-197">The *install-worker.sh* is a script that lets you copy .NET for Apache Spark dependent files into the nodes of your cluster.</span></span>

   <span data-ttu-id="5795c-198">Creare un nuovo file denominato **Install-Worker.sh** nel computer locale e incollare il [contenuto di install-Worker.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) disponibile in GitHub.</span><span class="sxs-lookup"><span data-stu-id="5795c-198">Create a new file named **install-worker.sh** your local computer, and paste the [install-worker.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) located on GitHub.</span></span> <span data-ttu-id="5795c-199">Quindi, caricare *Install-Worker.sh* nel contenitore BLOB.</span><span class="sxs-lookup"><span data-stu-id="5795c-199">Then, upload *install-worker.sh* to your blob container.</span></span>

4. <span data-ttu-id="5795c-200">Il cluster richiede il file Publish. zip che contiene i file pubblicati dell'app.</span><span class="sxs-lookup"><span data-stu-id="5795c-200">Your cluster needs the publish.zip file that contains your app's published files.</span></span> <span data-ttu-id="5795c-201">Passare alla cartella pubblicata, **mySparkApp/bin/Release/netcoreapp 3.0/Ubuntu. 16.04-x64**e individuare **Publish. zip**.</span><span class="sxs-lookup"><span data-stu-id="5795c-201">Navigate to your published folder, **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, and locate **publish.zip**.</span></span> <span data-ttu-id="5795c-202">Caricare quindi *Publish. zip* nel contenitore BLOB.</span><span class="sxs-lookup"><span data-stu-id="5795c-202">Then upload *publish.zip* to your blob container.</span></span>

5. <span data-ttu-id="5795c-203">Il cluster necessita del codice dell'applicazione che è stato incluso in un file jar.</span><span class="sxs-lookup"><span data-stu-id="5795c-203">Your cluster needs the application code that was packaged into a jar file.</span></span> <span data-ttu-id="5795c-204">Passare alla cartella pubblicata, **mySparkApp/bin/Release/netcoreapp 3.0/Ubuntu. 16.04-x64**e individuare **Microsoft-Spark-2.3. x-0.3.0. jar**.</span><span class="sxs-lookup"><span data-stu-id="5795c-204">Navigate to your published folder, **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, and locate **microsoft-spark-2.3.x-0.3.0.jar**.</span></span> <span data-ttu-id="5795c-205">Caricare quindi il file jar nel contenitore BLOB.</span><span class="sxs-lookup"><span data-stu-id="5795c-205">Then, upload the jar file to your blob container.</span></span>

   <span data-ttu-id="5795c-206">Potrebbero essere presenti più file con estensione jar (per le versioni 2.3. x e 2.4. x di Spark).</span><span class="sxs-lookup"><span data-stu-id="5795c-206">There may be multiple .jar files (for versions 2.3.x and 2.4.x of Spark).</span></span> <span data-ttu-id="5795c-207">È necessario scegliere il file con estensione jar che corrisponde alla versione di Spark scelta durante la creazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="5795c-207">You need to choose the .jar file that matches the version of Spark you chose during cluster creation.</span></span> <span data-ttu-id="5795c-208">Ad esempio, scegliere *Microsoft-Spark-2.3. x-0.3.0. jar* se si sceglie Spark 2.3.2 durante la creazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="5795c-208">For example, choose *microsoft-spark-2.3.x-0.3.0.jar* if you chose Spark 2.3.2 during cluster creation.</span></span>

6. <span data-ttu-id="5795c-209">Il cluster necessita dell'input per l'app.</span><span class="sxs-lookup"><span data-stu-id="5795c-209">Your cluster needs the input to your app.</span></span> <span data-ttu-id="5795c-210">Passare alla directory **mySparkApp** e individuare **input. txt**.</span><span class="sxs-lookup"><span data-stu-id="5795c-210">Navigate to your **mySparkApp** directory and locate **input.txt**.</span></span> <span data-ttu-id="5795c-211">Caricare il file di input nella directory **User/sshuser** nel contenitore BLOB.</span><span class="sxs-lookup"><span data-stu-id="5795c-211">Upload your input file to the **user/sshuser** directory in your blob container.</span></span> <span data-ttu-id="5795c-212">Ci si connette al cluster tramite SSH e questa cartella è la posizione in cui il cluster cerca l'input.</span><span class="sxs-lookup"><span data-stu-id="5795c-212">You will be connecting to your cluster through ssh, and this folder is where your cluster looks for its input.</span></span> <span data-ttu-id="5795c-213">Il file *input. txt* è l'unico file caricato in una directory specifica.</span><span class="sxs-lookup"><span data-stu-id="5795c-213">The *input.txt* file is the only file uploaded to a specific directory.</span></span>

## <a name="run-the-hdinsight-script-action"></a><span data-ttu-id="5795c-214">Eseguire l'azione di script HDInsight</span><span class="sxs-lookup"><span data-stu-id="5795c-214">Run the HDInsight script action</span></span>

<span data-ttu-id="5795c-215">Quando il cluster è in esecuzione e i file sono stati caricati in Azure, si esegue lo script **Install-Worker.sh** nel cluster.</span><span class="sxs-lookup"><span data-stu-id="5795c-215">Once your cluster is running and you've uploaded your files to Azure, you run the **install-worker.sh** script on the cluster.</span></span>

1. <span data-ttu-id="5795c-216">Passare al cluster HDInsight Spark in portale di Azure, quindi selezionare **azioni script**.</span><span class="sxs-lookup"><span data-stu-id="5795c-216">Navigate to your HDInsight Spark cluster in Azure portal, and then select **Script actions**.</span></span>

2. <span data-ttu-id="5795c-217">Selezionare **+ Invia nuovo** e specificare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5795c-217">Select **+ Submit new** and provide the following values:</span></span>

   |<span data-ttu-id="5795c-218">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5795c-218">Property</span></span>  |<span data-ttu-id="5795c-219">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5795c-219">Description</span></span>  |
   |---------|---------|
   | <span data-ttu-id="5795c-220">Tipo di script</span><span class="sxs-lookup"><span data-stu-id="5795c-220">Script type</span></span> |<span data-ttu-id="5795c-221">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="5795c-221">Custom</span></span>|
   | <span data-ttu-id="5795c-222">Nome</span><span class="sxs-lookup"><span data-stu-id="5795c-222">Name</span></span> | <span data-ttu-id="5795c-223">Installare il ruolo di lavoro</span><span class="sxs-lookup"><span data-stu-id="5795c-223">Install Worker</span></span>|
   | <span data-ttu-id="5795c-224">URI script Bash</span><span class="sxs-lookup"><span data-stu-id="5795c-224">Bash script URI</span></span> |https://mystorageaccount.blob.core.windows.net/mycontainer/install-worker.sh </br> <span data-ttu-id="5795c-225">Per confermare questo URI, fare clic con il pulsante destro del mouse su install-worker.sh in Azure Storage Explorer e scegliere Proprietà.</span><span class="sxs-lookup"><span data-stu-id="5795c-225">To confirm this URI, right-click on install-worker.sh in Azure Storage Explorer and select Properties.</span></span> |
   | <span data-ttu-id="5795c-226">Tipo/i di nodo</span><span class="sxs-lookup"><span data-stu-id="5795c-226">Node type(s)</span></span>| <span data-ttu-id="5795c-227">Worker</span><span class="sxs-lookup"><span data-stu-id="5795c-227">Worker</span></span>|
   | <span data-ttu-id="5795c-228">Parametri</span><span class="sxs-lookup"><span data-stu-id="5795c-228">Parameters</span></span> | <span data-ttu-id="5795c-229">azure</span><span class="sxs-lookup"><span data-stu-id="5795c-229">azure</span></span> </br> wasbs://mycontainer@myStorageAccount.blob.core.windows.net/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz </br> <span data-ttu-id="5795c-230">/usr/local/bin</span><span class="sxs-lookup"><span data-stu-id="5795c-230">/usr/local/bin</span></span>

3. <span data-ttu-id="5795c-231">Selezionare **Crea** per inviare lo script.</span><span class="sxs-lookup"><span data-stu-id="5795c-231">Select **Create** to submit your script.</span></span>

## <a name="run-your-app"></a><span data-ttu-id="5795c-232">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="5795c-232">Run your app</span></span>

1. <span data-ttu-id="5795c-233">Passare al cluster HDInsight Spark in portale di Azure, quindi selezionare **SSH + login cluster**.</span><span class="sxs-lookup"><span data-stu-id="5795c-233">Navigate to your HDInsight Spark cluster in Azure portal, and then select **SSH + Cluster login**.</span></span>

2. <span data-ttu-id="5795c-234">Copiare le informazioni di accesso SSH e incollare l'account di accesso in un terminale.</span><span class="sxs-lookup"><span data-stu-id="5795c-234">Copy the ssh login information and paste the login into a terminal.</span></span> <span data-ttu-id="5795c-235">Accedere al cluster usando la password impostata durante la creazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="5795c-235">Sign in to your cluster using the password you set during cluster creation.</span></span> <span data-ttu-id="5795c-236">Verranno visualizzati messaggi di benvenuto in Ubuntu e Spark.</span><span class="sxs-lookup"><span data-stu-id="5795c-236">You should see messages welcoming you to Ubuntu and Spark.</span></span>

3. <span data-ttu-id="5795c-237">Usare il comando **Spark-Submit** per eseguire l'app nel cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="5795c-237">Use the **spark-submit** command to run your app on your HDInsight cluster.</span></span> <span data-ttu-id="5795c-238">Ricordarsi di **sostituire e** **mystorageaccount** nello script di esempio con i nomi effettivi del contenitore BLOB e dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="5795c-238">Remember to replace **mycontainer** and **mystorageaccount** in the example script with the actual names of your blob container and storage account.</span></span>

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

   <span data-ttu-id="5795c-239">Quando l'app viene eseguita, viene visualizzata la stessa tabella di conteggio delle parole dall'esecuzione locale della Guida introduttiva scritta nella console.</span><span class="sxs-lookup"><span data-stu-id="5795c-239">When your app runs, you see the same word count table from the getting started local run written to the console.</span></span> <span data-ttu-id="5795c-240">Congratulazioni, è stata eseguita la prima applicazione .NET per Apache Spark nel cloud.</span><span class="sxs-lookup"><span data-stu-id="5795c-240">Congratulations, you've run your first .NET for Apache Spark application in the cloud!</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="5795c-241">Pulire le risorse</span><span class="sxs-lookup"><span data-stu-id="5795c-241">Clean up resources</span></span>

<span data-ttu-id="5795c-242">HDInsight Salva i dati in archiviazione di Azure, in modo da poter eliminare in modo sicuro un cluster quando non è in uso.</span><span class="sxs-lookup"><span data-stu-id="5795c-242">HDInsight saves your data in Azure Storage, so you can safely delete a cluster when it is not in use.</span></span> <span data-ttu-id="5795c-243">Vengono addebitati i costi anche per i cluster HDInsight che non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="5795c-243">You are also charged for an HDInsight cluster, even when it is not in use.</span></span> <span data-ttu-id="5795c-244">Poiché i costi per il cluster sono decisamente superiori a quelli per l'archiviazione, economicamente ha senso eliminare i cluster quando non vengono usati.</span><span class="sxs-lookup"><span data-stu-id="5795c-244">Since the charges for the cluster are many times more than the charges for storage, it makes economic sense to delete clusters when they are not in use.</span></span>

<span data-ttu-id="5795c-245">È anche possibile selezionare il nome del gruppo di risorse per aprire la pagina del gruppo di risorse e quindi selezionare **Elimina gruppo di risorse**.</span><span class="sxs-lookup"><span data-stu-id="5795c-245">You can also select the resource group name to open the resource group page, and then select **Delete resource group**.</span></span> <span data-ttu-id="5795c-246">Eliminando il gruppo di risorse, si elimina sia il cluster HDInsight Spark che l'account di archiviazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="5795c-246">By deleting the resource group, you delete both the HDInsight Spark cluster, and the default storage account.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5795c-247">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5795c-247">Next steps</span></span>

<span data-ttu-id="5795c-248">In questa esercitazione è stata distribuita un'applicazione .NET per Apache Spark in Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="5795c-248">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="5795c-249">Per altre informazioni su HDInsight, continuare con la documentazione di Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="5795c-249">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5795c-250">Documentazione di Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="5795c-250">Azure HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)

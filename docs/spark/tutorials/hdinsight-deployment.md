---
title: Distribuire un'applicazione .NET per Apache Spark in Azure HDInsight
description: Informazioni su come distribuire un'applicazione .NET per Apache Spark in HDInsight.
ms.date: 01/23/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 77b57463375c36444532bdd383ec4b3bfe3ab056
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "77504172"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="8ebf4-103">Esercitazione: Distribuire un'applicazione .NET per Apache Spark in Azure HDInsightTutorial: Deploy a .NET for Apache Spark application to Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="8ebf4-103">Tutorial: Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="8ebf4-104">Questa esercitazione illustra come distribuire l'app .NET per Apache Spark nel cloud tramite un cluster Azure HDInsight.This tutorial teaches you how to deploy your .NET for Apache Spark app to the cloud through an Azure HDInsight cluster.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-104">This tutorial teaches you how to deploy your .NET for Apache Spark app to the cloud through an Azure HDInsight cluster.</span></span> <span data-ttu-id="8ebf4-105">HDInsight makes it easier to create and configure a Spark cluster in Azure since Spark clusters in HDInsight are compatible with Azure Storage and Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-105">HDInsight makes it easier to create and configure a Spark cluster in Azure since Spark clusters in HDInsight are compatible with Azure Storage and Azure Data Lake Storage.</span></span>

<span data-ttu-id="8ebf4-106">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="8ebf4-106">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="8ebf4-107">Accedere agli account di archiviazione usando Azure Storage Explorer.Access your storage accounts using Azure Storage Explorer.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-107">Access your storage accounts using Azure Storage Explorer.</span></span>
> * <span data-ttu-id="8ebf4-108">Creare un cluster di Azure HDInsight.Create an Azure HDInsight cluster.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-108">Create an Azure HDInsight cluster.</span></span>
> * <span data-ttu-id="8ebf4-109">Pubblica l'app .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-109">Publish your .NET for Apache Spark app.</span></span>
> * <span data-ttu-id="8ebf4-110">Creare ed eseguire un'azione di script HDInsight.Create and run an HDInsight script action.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-110">Create and run an HDInsight script action.</span></span>
> * <span data-ttu-id="8ebf4-111">Eseguire un'app .NET per Apache Spark in un cluster HDInsight.Run a .NET for Apache Spark app on an HDInsight cluster.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-111">Run a .NET for Apache Spark app on an HDInsight cluster.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8ebf4-112">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="8ebf4-112">Prerequisites</span></span>

<span data-ttu-id="8ebf4-113">Prima di iniziare, eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ebf4-113">Before you start, do the following tasks:</span></span>

* <span data-ttu-id="8ebf4-114">Se non si dispone di una sottoscrizione di Azure, creare un [account gratuito.](https://azure.microsoft.com/free/)</span><span class="sxs-lookup"><span data-stu-id="8ebf4-114">If you don't have an Azure subscription, create a [free account](https://azure.microsoft.com/free/).</span></span>
* <span data-ttu-id="8ebf4-115">Accedere al [portale](https://portal.azure.com/)di Azure .</span><span class="sxs-lookup"><span data-stu-id="8ebf4-115">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
* <span data-ttu-id="8ebf4-116">Installare Azure Storage Explorer nel computer [Windows,](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409) [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409)o [MacOS.](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="8ebf4-116">Install Azure Storage Explorer on your [Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409), [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409), or [MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409) computer.</span></span>
* <span data-ttu-id="8ebf4-117">Completare [.NET per Apache Spark - Introduzione](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) nell'esercitazione di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-117">Complete the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial.</span></span>

## <a name="access-your-storage-accounts"></a><span data-ttu-id="8ebf4-118">Accedere agli account di archiviazioneAccess your storage accounts</span><span class="sxs-lookup"><span data-stu-id="8ebf4-118">Access your storage accounts</span></span>

1. <span data-ttu-id="8ebf4-119">Aprire Azure Storage Explorer.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-119">Open Azure Storage Explorer.</span></span>

2. <span data-ttu-id="8ebf4-120">Selezionare Aggiungi account nel menu a sinistra e accedere all'account Azure.Select **Add Account** on the left menu, and sign in to your Azure account.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-120">Select **Add Account** on the left menu, and sign in to your Azure account.</span></span>

    ![Accedere all'account di Azure da Esplora risorse](./media/hdinsight-deployment/signin-azure-storage-explorer.png)

   <span data-ttu-id="8ebf4-122">Dopo l'accesso, verranno visualizzati tutti gli account di archiviazione di cui si dispone e tutte le risorse caricate negli account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-122">After you sign in, you should see all storage accounts you have and any resources you have uploaded to your storage accounts.</span></span>

## <a name="create-an-hdinsight-cluster"></a><span data-ttu-id="8ebf4-123">Creazione di un cluster HDInsight</span><span class="sxs-lookup"><span data-stu-id="8ebf4-123">Create an HDInsight cluster</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ebf4-124">La fatturazione per i cluster HDInsight viene rivalutata proporzionalmente al minuto, anche se non vengono usati.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-124">Billing for HDInsight clusters is prorated per minute, even if you're not using them.</span></span> <span data-ttu-id="8ebf4-125">Assicurarsi di eliminare il cluster dopo aver finito di usarlo.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-125">Be sure to delete your cluster after you have finished using it.</span></span> <span data-ttu-id="8ebf4-126">Per altre informazioni, vedere la sezione [Pulire le risorse](#clean-up-resources) di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-126">For more information, see the [Clean up resources](#clean-up-resources) section of this tutorial.</span></span>

1. <span data-ttu-id="8ebf4-127">Visitare il [portale di Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="8ebf4-127">Visit the [Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="8ebf4-128">Selezionare **: Crea una risorsa**.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-128">Select **+ Create a resource**.</span></span> <span data-ttu-id="8ebf4-129">Selezionare **quindi HDInsight** dalla categoria Analisi.Then, select HDInsight from the **Analytics** category.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-129">Then, select **HDInsight** from the **Analytics** category.</span></span>

    ![Creare una risorsa HDInsight dal portale di AzureCreate HDInsight resource from Azure portal](./media/hdinsight-deployment/create-hdinsight-resource.png)

3. <span data-ttu-id="8ebf4-131">In **Informazioni di base** specificare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ebf4-131">Under **Basics**, provide the following values:</span></span>

    |<span data-ttu-id="8ebf4-132">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8ebf4-132">Property</span></span>  |<span data-ttu-id="8ebf4-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ebf4-133">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="8ebf4-134">Subscription</span><span class="sxs-lookup"><span data-stu-id="8ebf4-134">Subscription</span></span>  | <span data-ttu-id="8ebf4-135">Nell'elenco a discesa scegliere una delle sottoscrizioni di Azure attive.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-135">From the drop-down, choose one of your active Azure subscriptions.</span></span> |
    |<span data-ttu-id="8ebf4-136">Resource group</span><span class="sxs-lookup"><span data-stu-id="8ebf4-136">Resource group</span></span> | <span data-ttu-id="8ebf4-137">Specificare se si vuole creare un nuovo gruppo di risorse o usarne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-137">Specify whether you want to create a new resource group or use an existing one.</span></span> <span data-ttu-id="8ebf4-138">Un gruppo di risorse è un contenitore con risorse correlate per una soluzione Azure.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-138">A resource group is a container that holds related resources for an Azure solution.</span></span> |
    |<span data-ttu-id="8ebf4-139">Nome cluster</span><span class="sxs-lookup"><span data-stu-id="8ebf4-139">Cluster name</span></span> | <span data-ttu-id="8ebf4-140">Assegnare un nome al cluster HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-140">Give a name to your HDInsight Spark cluster.</span></span>|
    |<span data-ttu-id="8ebf4-141">Location</span><span class="sxs-lookup"><span data-stu-id="8ebf4-141">Location</span></span>   | <span data-ttu-id="8ebf4-142">Selezionare una posizione per il gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-142">Select a location for the resource group.</span></span> <span data-ttu-id="8ebf4-143">Il modello usa questa posizione per la creazione del cluster e per l'archiviazione del cluster predefinita.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-143">The template uses this location for creating the cluster as well as for the default cluster storage.</span></span> |
    |<span data-ttu-id="8ebf4-144">Tipo di cluster</span><span class="sxs-lookup"><span data-stu-id="8ebf4-144">Cluster type</span></span>| <span data-ttu-id="8ebf4-145">Selezionare **Spark** come tipo di cluster.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-145">Select **Spark** as the cluster type.</span></span>|
    |<span data-ttu-id="8ebf4-146">Versione del cluster</span><span class="sxs-lookup"><span data-stu-id="8ebf4-146">Cluster version</span></span>|<span data-ttu-id="8ebf4-147">Questo campo verrà compilato automaticamente con la versione predefinita una volta selezionato il tipo di cluster.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-147">This field will autopopulate with the default version once the cluster type has been selected.</span></span> <span data-ttu-id="8ebf4-148">Selezionare una versione 2.3 o 2.4 di Spark.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-148">Select a 2.3 or 2.4 version of Spark.</span></span>|
    |<span data-ttu-id="8ebf4-149">Nome utente dell'account di accesso del cluster</span><span class="sxs-lookup"><span data-stu-id="8ebf4-149">Cluster login username</span></span>| <span data-ttu-id="8ebf4-150">Immettere il nome utente dell'account di accesso del cluster.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-150">Enter the cluster login username.</span></span>  <span data-ttu-id="8ebf4-151">Il nome predefinito è *admin*.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-151">The default name is *admin*.</span></span> |
    |<span data-ttu-id="8ebf4-152">Password di accesso al cluster</span><span class="sxs-lookup"><span data-stu-id="8ebf4-152">Cluster login password</span></span>| <span data-ttu-id="8ebf4-153">Immettere una password di accesso.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-153">Enter any login password.</span></span> |
    |<span data-ttu-id="8ebf4-154">Nome utente Secure Shell (SSH)</span><span class="sxs-lookup"><span data-stu-id="8ebf4-154">Secure Shell (SSH) username</span></span>| <span data-ttu-id="8ebf4-155">Immettere il nome utente SSH.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-155">Enter the SSH username.</span></span> <span data-ttu-id="8ebf4-156">Per impostazione predefinita, questo account condivide la stessa password dell'account *Nome utente dell'account di accesso del cluster*.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-156">By default, this account shares the same password as the *Cluster Login username* account.</span></span> |

4. <span data-ttu-id="8ebf4-157">Selezionare Avanti: Archiviazione >>per continuare con la pagina **Archiviazione.Select** **Next: Storage >>** to continue to the Storage page.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-157">Select **Next: Storage >>** to continue to the **Storage** page.</span></span> <span data-ttu-id="8ebf4-158">In **Archiviazione** specificare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ebf4-158">Under **Storage**, provide the following values:</span></span>

    |<span data-ttu-id="8ebf4-159">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8ebf4-159">Property</span></span>  |<span data-ttu-id="8ebf4-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ebf4-160">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="8ebf4-161">Tipo di archiviazione primario</span><span class="sxs-lookup"><span data-stu-id="8ebf4-161">Primary storage type</span></span>|<span data-ttu-id="8ebf4-162">Usare il valore predefinito **Archiviazione di Azure**.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-162">Use the default value **Azure Storage**.</span></span>|
    |<span data-ttu-id="8ebf4-163">Metodo di selezione</span><span class="sxs-lookup"><span data-stu-id="8ebf4-163">Selection method</span></span>|<span data-ttu-id="8ebf4-164">Usare il valore predefinito **Selezionare dall'elenco**.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-164">Use the default value **Select from list**.</span></span>|
    |<span data-ttu-id="8ebf4-165">Account di archiviazione primario</span><span class="sxs-lookup"><span data-stu-id="8ebf4-165">Primary storage account</span></span>|<span data-ttu-id="8ebf4-166">Scegliere la sottoscrizione e uno degli account di archiviazione attivi all'interno di tale sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-166">Choose your subscription and one of your active storage accounts within that subscription.</span></span>|
    |<span data-ttu-id="8ebf4-167">Contenitore</span><span class="sxs-lookup"><span data-stu-id="8ebf4-167">Container</span></span>|<span data-ttu-id="8ebf4-168">Questo contenitore è il contenitore BLOB specifico nell'account di archiviazione in cui il cluster cerca i file per eseguire l'app nel cloud.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-168">This container is the specific blob container in your storage account where your cluster looks for files to run your app in the cloud.</span></span> <span data-ttu-id="8ebf4-169">È possibile assegnare qualsiasi nome disponibile.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-169">You can give it any available name.</span></span>|

5. <span data-ttu-id="8ebf4-170">In **Rivedi e crea** selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-170">Under **Review + create**, select **Create**.</span></span> <span data-ttu-id="8ebf4-171">La creazione del cluster richiede circa 20 minuti.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-171">It takes about 20 minutes to create the cluster.</span></span> <span data-ttu-id="8ebf4-172">Il cluster deve essere creato prima di poter continuare con il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-172">The cluster must be created before you can continue to the next step.</span></span>

## <a name="publish-your-app"></a><span data-ttu-id="8ebf4-173">Pubblicare l'app</span><span class="sxs-lookup"><span data-stu-id="8ebf4-173">Publish your app</span></span>

<span data-ttu-id="8ebf4-174">Successivamente, si pubblica *mySparkApp* creata in [.NET per Apache Spark - Introduzione](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) nell'esercitazione di 10 minuti, che consente al cluster Spark di accedere a tutti i file necessari per eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-174">Next, you publish the *mySparkApp* created in the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial, which gives your Spark cluster access to all the files it needs to run your app.</span></span>

1. <span data-ttu-id="8ebf4-175">Eseguire i seguenti comandi per pubblicare *mySparkApp*:</span><span class="sxs-lookup"><span data-stu-id="8ebf4-175">Run the following commands to publish the *mySparkApp*:</span></span>

   <span data-ttu-id="8ebf4-176">**In Windows:**</span><span class="sxs-lookup"><span data-stu-id="8ebf4-176">**On Windows:**</span></span>

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

   <span data-ttu-id="8ebf4-177">**Su Linux:**</span><span class="sxs-lookup"><span data-stu-id="8ebf4-177">**On Linux:**</span></span>

   ```bash
   cd mySparkApp
   foo@bar:~/path/to/app$ dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. <span data-ttu-id="8ebf4-178">Eseguire le attività seguenti per comprimere i file dell'app pubblicati in modo da poterli caricare facilmente nel cluster HDInsight.Do the following tasks to zip your published app files so that you can easily upload them to your HDInsight cluster.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-178">Do the following tasks to zip your published app files so that you can easily upload them to your HDInsight cluster.</span></span>

   <span data-ttu-id="8ebf4-179">**In Windows:**</span><span class="sxs-lookup"><span data-stu-id="8ebf4-179">**On Windows:**</span></span>

   <span data-ttu-id="8ebf4-180">Passare a *mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64*.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-180">Navigate to *mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64*.</span></span> <span data-ttu-id="8ebf4-181">Quindi, fare clic con il pulsante destro del mouse su **Pubblica** cartella e selezionare **Invia a > cartella compressa (compressa).**</span><span class="sxs-lookup"><span data-stu-id="8ebf4-181">Then, right-click on **Publish** folder and select **Send to > Compressed (zipped) folder**.</span></span> <span data-ttu-id="8ebf4-182">Assegnare alla nuova cartella il nome **publish.zip**.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-182">Name the new folder **publish.zip**.</span></span>

   <span data-ttu-id="8ebf4-183">**In Linux, eseguire il comando seguente:**</span><span class="sxs-lookup"><span data-stu-id="8ebf4-183">**On Linux, run the following command:**</span></span>

   ```bash
   zip -r publish.zip
   ```

## <a name="upload-files-to-azure"></a><span data-ttu-id="8ebf4-184">Caricare file in AzureUpload files to Azure</span><span class="sxs-lookup"><span data-stu-id="8ebf4-184">Upload files to Azure</span></span>

<span data-ttu-id="8ebf4-185">Successivamente, si usa Azure Storage Explorer per caricare i cinque file seguenti nel contenitore BLOB scelto per l'archiviazione del cluster:Next, you use the Azure Storage Explorer to upload the following five files to the blob container you chose for your cluster's storage:</span><span class="sxs-lookup"><span data-stu-id="8ebf4-185">Next, you use the Azure Storage Explorer to upload the following five files to the blob container you chose for your cluster's storage:</span></span>

* <span data-ttu-id="8ebf4-186">Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="8ebf4-186">Microsoft.Spark.Worker</span></span>
* <span data-ttu-id="8ebf4-187">install-worker.sh</span><span class="sxs-lookup"><span data-stu-id="8ebf4-187">install-worker.sh</span></span>
* <span data-ttu-id="8ebf4-188">publish.zip</span><span class="sxs-lookup"><span data-stu-id="8ebf4-188">publish.zip</span></span>
* <span data-ttu-id="8ebf4-189">microsoft-spark-2.3.x-0.3.0.jar</span><span class="sxs-lookup"><span data-stu-id="8ebf4-189">microsoft-spark-2.3.x-0.3.0.jar</span></span>
* <span data-ttu-id="8ebf4-190">input.txt.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-190">input.txt.</span></span>

1. <span data-ttu-id="8ebf4-191">Aprire Esplora archivi di Azure e passare all'account di archiviazione dal menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-191">Open Azure Storage Explorer and navigate to your storage account from the left menu.</span></span> <span data-ttu-id="8ebf4-192">Eseguire il drill-down nel contenitore BLOB per il cluster in **Contenitori BLOB** nell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-192">Drill down to the blob container for your cluster under **Blob Containers** in your storage account.</span></span>

2. <span data-ttu-id="8ebf4-193">*Microsoft.Spark.Worker* consente a Apache Spark di eseguire l'app, ad esempio qualsiasi funzione definita dall'utente (UDF) che è stata scritta.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-193">*Microsoft.Spark.Worker* helps Apache Spark execute your app, such as any user-defined functions (UDFs) you may have written.</span></span> <span data-ttu-id="8ebf4-194">Scaricare [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.3.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.3.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="8ebf4-194">Download [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.3.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.3.0.tar.gz).</span></span> <span data-ttu-id="8ebf4-195">Selezionare quindi **Carica** in Azure Storage Explorer per caricare il worker.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-195">Then, select **Upload** in Azure Storage Explorer to upload the worker.</span></span>

   ![Caricare file in Azure Storage Explorer](./media/hdinsight-deployment/upload-files-to-storage.png)

3. <span data-ttu-id="8ebf4-197">Il *install-worker.sh* è uno script che consente di copiare .NET per i file dipendenti da Apache Spark nei nodi del cluster.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-197">The *install-worker.sh* is a script that lets you copy .NET for Apache Spark dependent files into the nodes of your cluster.</span></span>

   <span data-ttu-id="8ebf4-198">Creare un nuovo file denominato **install-worker.sh** computer locale e incollare il contenuto del install-worker.sh disponibile in GitHub.Create a new file named install-worker.sh your local computer, and paste [the install-worker.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) located on GitHub.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-198">Create a new file named **install-worker.sh** your local computer, and paste the [install-worker.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) located on GitHub.</span></span> <span data-ttu-id="8ebf4-199">Caricare quindi *install-worker.sh* nel contenitore BLOB.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-199">Then, upload *install-worker.sh* to your blob container.</span></span>

4. <span data-ttu-id="8ebf4-200">Il cluster richiede il file publish.zip che contiene i file pubblicati dell'app.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-200">Your cluster needs the publish.zip file that contains your app's published files.</span></span> <span data-ttu-id="8ebf4-201">Passare alla cartella pubblicata, **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, e individuare **publish.zip**.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-201">Navigate to your published folder, **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, and locate **publish.zip**.</span></span> <span data-ttu-id="8ebf4-202">Quindi caricare *publish.zip* nel contenitore BLOB.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-202">Then upload *publish.zip* to your blob container.</span></span>

5. <span data-ttu-id="8ebf4-203">Il cluster necessita del codice dell'applicazione incluso in un file jar.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-203">Your cluster needs the application code that was packaged into a jar file.</span></span> <span data-ttu-id="8ebf4-204">Passare alla cartella pubblicata, **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, e individuare **microsoft-spark-2.3.x-0.3.0.jar**.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-204">Navigate to your published folder, **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, and locate **microsoft-spark-2.3.x-0.3.0.jar**.</span></span> <span data-ttu-id="8ebf4-205">Quindi, caricare il file jar nel contenitore BLOB.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-205">Then, upload the jar file to your blob container.</span></span>

   <span data-ttu-id="8ebf4-206">Potrebbero essere presenti più file JAR (per le versioni 2.3.x e 2.4.x di Spark).</span><span class="sxs-lookup"><span data-stu-id="8ebf4-206">There may be multiple .jar files (for versions 2.3.x and 2.4.x of Spark).</span></span> <span data-ttu-id="8ebf4-207">È necessario scegliere il file JAR che corrisponde alla versione di Spark scelta durante la creazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-207">You need to choose the .jar file that matches the version of Spark you chose during cluster creation.</span></span> <span data-ttu-id="8ebf4-208">Ad esempio, scegliere *microsoft-spark-2.3.x-0.3.0.jar* se si sceglie Spark 2.3.2 durante la creazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-208">For example, choose *microsoft-spark-2.3.x-0.3.0.jar* if you chose Spark 2.3.2 during cluster creation.</span></span>

6. <span data-ttu-id="8ebf4-209">Il cluster richiede l'input per l'app.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-209">Your cluster needs the input to your app.</span></span> <span data-ttu-id="8ebf4-210">Passare alla directory **mySparkApp** e individuare **input.txt**.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-210">Navigate to your **mySparkApp** directory and locate **input.txt**.</span></span> <span data-ttu-id="8ebf4-211">Caricare il file di input nella directory **user/sshuser** nel contenitore BLOB.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-211">Upload your input file to the **user/sshuser** directory in your blob container.</span></span> <span data-ttu-id="8ebf4-212">Ci si connetterà al cluster tramite ssh e questa cartella è dove il cluster cerca il suo input.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-212">You will be connecting to your cluster through ssh, and this folder is where your cluster looks for its input.</span></span> <span data-ttu-id="8ebf4-213">Il file *input.txt* è l'unico file caricato in una directory specifica.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-213">The *input.txt* file is the only file uploaded to a specific directory.</span></span>

## <a name="run-the-hdinsight-script-action"></a><span data-ttu-id="8ebf4-214">Eseguire l'azione script HDInsightRun the HDInsight script action</span><span class="sxs-lookup"><span data-stu-id="8ebf4-214">Run the HDInsight script action</span></span>

<span data-ttu-id="8ebf4-215">Dopo che il cluster è in esecuzione e aver caricato i file in Azure, eseguire lo script **di install-worker.sh** nel cluster.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-215">Once your cluster is running and you've uploaded your files to Azure, you run the **install-worker.sh** script on the cluster.</span></span>

1. <span data-ttu-id="8ebf4-216">Passare al cluster HDInsight Spark nel portale di Azure e quindi selezionare **Azioni script**.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-216">Navigate to your HDInsight Spark cluster in Azure portal, and then select **Script actions**.</span></span>

2. <span data-ttu-id="8ebf4-217">Selezionare **Invia nuovo** e specificare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="8ebf4-217">Select **+ Submit new** and provide the following values:</span></span>

   |<span data-ttu-id="8ebf4-218">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8ebf4-218">Property</span></span>  |<span data-ttu-id="8ebf4-219">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ebf4-219">Description</span></span>  |
   |---------|---------|
   | <span data-ttu-id="8ebf4-220">Tipo di script</span><span class="sxs-lookup"><span data-stu-id="8ebf4-220">Script type</span></span> |<span data-ttu-id="8ebf4-221">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="8ebf4-221">Custom</span></span>|
   | <span data-ttu-id="8ebf4-222">Nome</span><span class="sxs-lookup"><span data-stu-id="8ebf4-222">Name</span></span> | <span data-ttu-id="8ebf4-223">Installa lavoratore</span><span class="sxs-lookup"><span data-stu-id="8ebf4-223">Install Worker</span></span>|
   | <span data-ttu-id="8ebf4-224">URI script Bash</span><span class="sxs-lookup"><span data-stu-id="8ebf4-224">Bash script URI</span></span> |https://mystorageaccount.blob.core.windows.net/mycontainer/install-worker.sh </br> <span data-ttu-id="8ebf4-225">Per confermare questo URI, fare clic con il pulsante destro del mouse su install-worker.sh in Esplora archivi di Azure e selezionare Proprietà.To confirm this URI, right-click on install-worker.sh in Azure Storage Explorer and select Properties.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-225">To confirm this URI, right-click on install-worker.sh in Azure Storage Explorer and select Properties.</span></span> |
   | <span data-ttu-id="8ebf4-226">Tipo/i di nodo</span><span class="sxs-lookup"><span data-stu-id="8ebf4-226">Node type(s)</span></span>| <span data-ttu-id="8ebf4-227">Worker</span><span class="sxs-lookup"><span data-stu-id="8ebf4-227">Worker</span></span>|
   | <span data-ttu-id="8ebf4-228">Parametri</span><span class="sxs-lookup"><span data-stu-id="8ebf4-228">Parameters</span></span> | <span data-ttu-id="8ebf4-229">azure</span><span class="sxs-lookup"><span data-stu-id="8ebf4-229">azure</span></span> </br> wasbs://mycontainer@myStorageAccount.blob.core.windows.net/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz </br> <span data-ttu-id="8ebf4-230">/usr/locale/bin</span><span class="sxs-lookup"><span data-stu-id="8ebf4-230">/usr/local/bin</span></span>

3. <span data-ttu-id="8ebf4-231">Selezionare **Crea** per inviare lo script.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-231">Select **Create** to submit your script.</span></span>

## <a name="run-your-app"></a><span data-ttu-id="8ebf4-232">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="8ebf4-232">Run your app</span></span>

1. <span data-ttu-id="8ebf4-233">Passare al cluster HDInsight Spark nel portale di Azure e quindi selezionare **SSH e accesso al cluster.**</span><span class="sxs-lookup"><span data-stu-id="8ebf4-233">Navigate to your HDInsight Spark cluster in Azure portal, and then select **SSH + Cluster login**.</span></span>

2. <span data-ttu-id="8ebf4-234">Copiare le informazioni di accesso ssh e incollare il login in un terminale.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-234">Copy the ssh login information and paste the login into a terminal.</span></span> <span data-ttu-id="8ebf4-235">Accedere al cluster utilizzando la password impostata durante la creazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-235">Sign in to your cluster using the password you set during cluster creation.</span></span> <span data-ttu-id="8ebf4-236">Dovresti vedere messaggi che ti accolgano a Ubuntu e Spark.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-236">You should see messages welcoming you to Ubuntu and Spark.</span></span>

3. <span data-ttu-id="8ebf4-237">Usare il comando spark-submit per eseguire l'app nel cluster HDInsight.Use the **spark-submit** command to run your app on your HDInsight cluster.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-237">Use the **spark-submit** command to run your app on your HDInsight cluster.</span></span> <span data-ttu-id="8ebf4-238">Ricordarsi di sostituire **mycontainer** e **mystorageaccount** nello script di esempio con i nomi effettivi del contenitore BLOB e dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-238">Remember to replace **mycontainer** and **mystorageaccount** in the example script with the actual names of your blob container and storage account.</span></span>

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

   <span data-ttu-id="8ebf4-239">Quando l'app viene eseguita, viene visualizzata la stessa tabella di conteggio delle parole dell'esecuzione locale introduttiva scritta nella console.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-239">When your app runs, you see the same word count table from the getting started local run written to the console.</span></span> <span data-ttu-id="8ebf4-240">Congratulazioni, hai eseguito la tua prima applicazione .NET per Apache Spark nel cloud!</span><span class="sxs-lookup"><span data-stu-id="8ebf4-240">Congratulations, you've run your first .NET for Apache Spark application in the cloud!</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="8ebf4-241">Pulire le risorse</span><span class="sxs-lookup"><span data-stu-id="8ebf4-241">Clean up resources</span></span>

<span data-ttu-id="8ebf4-242">HDInsight salva i dati in Archiviazione di Azure, in modo da poter eliminare in modo sicuro un cluster quando non è in uso.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-242">HDInsight saves your data in Azure Storage, so you can safely delete a cluster when it is not in use.</span></span> <span data-ttu-id="8ebf4-243">Vengono addebitati i costi anche per i cluster HDInsight che non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-243">You are also charged for an HDInsight cluster, even when it is not in use.</span></span> <span data-ttu-id="8ebf4-244">Poiché i costi per il cluster sono decisamente superiori a quelli per l'archiviazione, economicamente ha senso eliminare i cluster quando non vengono usati.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-244">Since the charges for the cluster are many times more than the charges for storage, it makes economic sense to delete clusters when they are not in use.</span></span>

<span data-ttu-id="8ebf4-245">È anche possibile selezionare il nome del gruppo di risorse per aprire la pagina del gruppo di risorse e quindi selezionare **Elimina gruppo di risorse**.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-245">You can also select the resource group name to open the resource group page, and then select **Delete resource group**.</span></span> <span data-ttu-id="8ebf4-246">Eliminando il gruppo di risorse, si elimina sia il cluster HDInsight Spark che l'account di archiviazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-246">By deleting the resource group, you delete both the HDInsight Spark cluster, and the default storage account.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8ebf4-247">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8ebf4-247">Next steps</span></span>

<span data-ttu-id="8ebf4-248">In questa esercitazione è stata distribuita un'applicazione .NET per Apache Spark in Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-248">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="8ebf4-249">Per altre informazioni su HDInsight, continuare con la documentazione di Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="8ebf4-249">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8ebf4-250">Azure HDInsight Documentation</span><span class="sxs-lookup"><span data-stu-id="8ebf4-250">Azure HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)

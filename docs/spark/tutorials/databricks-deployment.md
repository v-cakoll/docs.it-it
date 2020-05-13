---
title: Distribuire un'applicazione .NET per Apache Spark in Databricks
description: Informazioni su come distribuire un'applicazione .NET per Apache Spark in Databricks.
ms.date: 05/11/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 228ddd59023dbd9d63ff392764fb36441a6af23a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379851"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-databricks"></a><span data-ttu-id="f6b7e-103">Esercitazione: distribuire un'applicazione .NET per Apache Spark a databricks</span><span class="sxs-lookup"><span data-stu-id="f6b7e-103">Tutorial: Deploy a .NET for Apache Spark application to Databricks</span></span>

<span data-ttu-id="f6b7e-104">Questa esercitazione illustra come distribuire un'app nel cloud tramite Azure Databricks, una piattaforma di analisi basata su Apache Spark con installazione con un clic, flussi di lavoro semplificati e un'area di lavoro interattiva che consente la collaborazione.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-104">This tutorial teaches you how to deploy your app to the cloud through Azure Databricks, an Apache Spark-based analytics platform with one-click setup, streamlined workflows, and interactive workspace that enables collaboration.</span></span>

<span data-ttu-id="f6b7e-105">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="f6b7e-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="f6b7e-106">Creare un'area di lavoro di Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-106">Create an Azure Databricks workspace.</span></span>
> - <span data-ttu-id="f6b7e-107">Pubblicare .NET per Apache Spark app.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-107">Publish your .NET for Apache Spark app.</span></span>
> - <span data-ttu-id="f6b7e-108">Creare un processo Spark e un cluster Spark.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-108">Create a Spark job and Spark cluster.</span></span>
> - <span data-ttu-id="f6b7e-109">Eseguire l'app nel cluster Spark.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-109">Run your app on the Spark cluster.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f6b7e-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f6b7e-110">Prerequisites</span></span>

<span data-ttu-id="f6b7e-111">Prima di iniziare, eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6b7e-111">Before you start, do the following tasks:</span></span>

* <span data-ttu-id="f6b7e-112">Se non si ha un account Azure, creare un [account gratuito](https://azure.microsoft.com/free/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="f6b7e-112">If you don't have an Azure account, create a [free account](https://azure.microsoft.com/free/dotnet/).</span></span>
* <span data-ttu-id="f6b7e-113">Accedere al [portale di Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="f6b7e-113">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
* <span data-ttu-id="f6b7e-114">Completare l'esercitazione [su .NET per Apache Spark-introduzione in 10 minuti](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) .</span><span class="sxs-lookup"><span data-stu-id="f6b7e-114">Complete the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial.</span></span>

## <a name="create-an-azure-databricks-workspace"></a><span data-ttu-id="f6b7e-115">Creare un'area di lavoro di Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="f6b7e-115">Create an Azure Databricks workspace</span></span>

> [!Note]
> <span data-ttu-id="f6b7e-116">Questa esercitazione non può essere eseguita usando una **sottoscrizione di valutazione gratuita di Azure**.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-116">This tutorial cannot be carried out using **Azure Free Trial Subscription**.</span></span>
> <span data-ttu-id="f6b7e-117">Se l'utente ha un account gratuito, andare al proprio profilo e modificare la sottoscrizione a **con pagamento in base al consumo**.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-117">If you have a free account, go to your profile and change your subscription to **pay-as-you-go**.</span></span> <span data-ttu-id="f6b7e-118">Per altre informazioni, vedere [Account gratuito di Azure](https://azure.microsoft.com/free/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="f6b7e-118">For more information, see [Azure free account](https://azure.microsoft.com/free/dotnet/).</span></span> <span data-ttu-id="f6b7e-119">Quindi [rimuovere il limite di spesa](https://docs.microsoft.com/azure/billing/billing-spending-limit#why-you-might-want-to-remove-the-spending-limit) e [richiedere un aumento della quota](https://docs.microsoft.com/azure/azure-supportability/resource-manager-core-quotas-request) per le vCPU nell'area dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-119">Then, [remove the spending limit](https://docs.microsoft.com/azure/billing/billing-spending-limit#why-you-might-want-to-remove-the-spending-limit), and [request a quota increase](https://docs.microsoft.com/azure/azure-supportability/resource-manager-core-quotas-request) for vCPUs in your region.</span></span> <span data-ttu-id="f6b7e-120">Quando si crea l'area di lavoro Azure Databricks, è possibile selezionare il piano tariffario **Versione di valutazione (Premium - Unità Databricks gratuite per 14 giorni)** per concedere l'accesso gratuito Premium per 14 giorni dell'area di lavoro alle Unità Databricks di Azure.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-120">When you create your Azure Databricks workspace, you can select the **Trial (Premium - 14-Days Free DBUs)** pricing tier to give the workspace access to free Premium Azure Databricks DBUs for 14 days.</span></span>

<span data-ttu-id="f6b7e-121">In questa sezione viene creata un'area di lavoro di Azure Databricks usando il portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-121">In this section, you create an Azure Databricks workspace using the Azure portal.</span></span>

1. <span data-ttu-id="f6b7e-122">Nel portale di Azure selezionare **Crea una risorsa** > **Analisi** > **Azure Databricks**.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-122">In the Azure portal, select **Create a resource** > **Analytics** > **Azure Databricks**.</span></span>

   ![Creare una risorsa Azure Databricks in portale di Azure](./media/databricks-deployment/create-databricks-resource.png)

2. <span data-ttu-id="f6b7e-124">Nella pagina **Servizio Azure Databricks** specificare i valori per creare un'area di lavoro di Databricks.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-124">Under **Azure Databricks Service**, provide the values to create a Databricks workspace.</span></span>

    |<span data-ttu-id="f6b7e-125">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f6b7e-125">Property</span></span>  |<span data-ttu-id="f6b7e-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6b7e-126">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="f6b7e-127">**Nome area di lavoro**</span><span class="sxs-lookup"><span data-stu-id="f6b7e-127">**Workspace name**</span></span>     | <span data-ttu-id="f6b7e-128">Specificare un nome per l'area di lavoro di Databricks.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-128">Provide a name for your Databricks workspace.</span></span>        |
    |<span data-ttu-id="f6b7e-129">**Sottoscrizione**</span><span class="sxs-lookup"><span data-stu-id="f6b7e-129">**Subscription**</span></span>     | <span data-ttu-id="f6b7e-130">Selezionare la sottoscrizione di Azure nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-130">From the drop-down, select your Azure subscription.</span></span>        |
    |<span data-ttu-id="f6b7e-131">**Gruppo di risorse**</span><span class="sxs-lookup"><span data-stu-id="f6b7e-131">**Resource group**</span></span>     | <span data-ttu-id="f6b7e-132">Specificare se si vuole creare un nuovo gruppo di risorse o usarne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-132">Specify whether you want to create a new resource group or use an existing one.</span></span> <span data-ttu-id="f6b7e-133">Un gruppo di risorse è un contenitore con risorse correlate per una soluzione Azure.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-133">A resource group is a container that holds related resources for an Azure solution.</span></span> <span data-ttu-id="f6b7e-134">Per altre informazioni, vedere [Panoramica di Gestione risorse di Microsoft Azure](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview).</span><span class="sxs-lookup"><span data-stu-id="f6b7e-134">For more information, see [Azure Resource Group overview](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview).</span></span> |
    |<span data-ttu-id="f6b7e-135">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="f6b7e-135">**Location**</span></span>     | <span data-ttu-id="f6b7e-136">Selezionare l'area preferita.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-136">Select your preferred region.</span></span> <span data-ttu-id="f6b7e-137">Per informazioni sulle aree disponibili, vedere [servizi di Azure disponibili in base all'area](https://azure.microsoft.com/regions/services/).</span><span class="sxs-lookup"><span data-stu-id="f6b7e-137">For information about available regions, see [Azure services available by region](https://azure.microsoft.com/regions/services/).</span></span>        |
    |<span data-ttu-id="f6b7e-138">**Piano tariffario**</span><span class="sxs-lookup"><span data-stu-id="f6b7e-138">**Pricing Tier**</span></span>     |  <span data-ttu-id="f6b7e-139">Scegliere tra **Standard**, **Premium** e **Versione di valutazione**.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-139">Choose between **Standard**, **Premium**, or **Trial**.</span></span> <span data-ttu-id="f6b7e-140">Per altre informazioni su questi piani tariffari, vedere la [pagina dei prezzi di Databricks](https://azure.microsoft.com/pricing/details/databricks/).</span><span class="sxs-lookup"><span data-stu-id="f6b7e-140">For more information on these tiers, see [Databricks pricing page](https://azure.microsoft.com/pricing/details/databricks/).</span></span>       |
    |<span data-ttu-id="f6b7e-141">**Rete virtuale**</span><span class="sxs-lookup"><span data-stu-id="f6b7e-141">**Virtual Network**</span></span>     |   <span data-ttu-id="f6b7e-142">No</span><span class="sxs-lookup"><span data-stu-id="f6b7e-142">No</span></span>       |

3. <span data-ttu-id="f6b7e-143">Selezionare **Create** (Crea).</span><span class="sxs-lookup"><span data-stu-id="f6b7e-143">Select **Create**.</span></span> <span data-ttu-id="f6b7e-144">La creazione dell'area di lavoro richiede alcuni minuti,</span><span class="sxs-lookup"><span data-stu-id="f6b7e-144">The workspace creation takes a few minutes.</span></span> <span data-ttu-id="f6b7e-145">durante i quali è possibile visualizzare lo stato della distribuzione in **Notifiche**.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-145">During workspace creation, you can view the deployment status in **Notifications**.</span></span>

## <a name="install-azure-databricks-tools"></a><span data-ttu-id="f6b7e-146">Installare gli strumenti di Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="f6b7e-146">Install Azure Databricks tools</span></span>

<span data-ttu-id="f6b7e-147">È possibile usare l'interfaccia della riga di comando di **databricks** per connettersi a Azure Databricks cluster e caricarvi file dal computer locale.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-147">You can use the **Databricks CLI** to connect to Azure Databricks clusters and upload files to them from your local machine.</span></span> <span data-ttu-id="f6b7e-148">I cluster databricks accedono ai file tramite DBFS (file System databricks).</span><span class="sxs-lookup"><span data-stu-id="f6b7e-148">Databricks clusters access files through DBFS (Databricks File System).</span></span>

1. <span data-ttu-id="f6b7e-149">L'interfaccia della riga di comando di databricks richiede Python 3,6 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-149">The Databricks CLI requires Python 3.6 or above.</span></span> <span data-ttu-id="f6b7e-150">Se Python è già installato, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-150">If you already have Python installed, you can skip this step.</span></span>

   <span data-ttu-id="f6b7e-151">**Per Windows:**</span><span class="sxs-lookup"><span data-stu-id="f6b7e-151">**For Windows:**</span></span>

   [<span data-ttu-id="f6b7e-152">Scaricare Python per Windows</span><span class="sxs-lookup"><span data-stu-id="f6b7e-152">Download Python for Windows</span></span>](https://www.python.org/ftp/python/3.7.4/python-3.7.4.exe)

   <span data-ttu-id="f6b7e-153">**Per Linux:** Python è preinstallato nella maggior parte delle distribuzioni di Linux.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-153">**For Linux:** Python comes preinstalled on most Linux distributions.</span></span> <span data-ttu-id="f6b7e-154">Eseguire il comando seguente per visualizzare la versione installata:</span><span class="sxs-lookup"><span data-stu-id="f6b7e-154">Run the following command to see which version you have installed:</span></span>

   ```bash
   python3 --version
   ```

2. <span data-ttu-id="f6b7e-155">Usare PIP per installare l'interfaccia della riga di comando di databricks.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-155">Use pip to install the Databricks CLI.</span></span> <span data-ttu-id="f6b7e-156">Python 3,4 e versioni successive includono PIP per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-156">Python 3.4 and later include pip by default.</span></span> <span data-ttu-id="f6b7e-157">Usare PIP3 per Python 3.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-157">Use pip3 for Python 3.</span></span> <span data-ttu-id="f6b7e-158">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f6b7e-158">Run the following command:</span></span>

   ```bash
   pip3 install databricks-cli
   ```

3. <span data-ttu-id="f6b7e-159">Dopo aver installato l'interfaccia della riga di comando di databricks, aprire un nuovo prompt dei comandi ed eseguire il comando `databricks` .</span><span class="sxs-lookup"><span data-stu-id="f6b7e-159">Once you've installed the Databricks CLI, open a new command prompt and run the command `databricks`.</span></span> <span data-ttu-id="f6b7e-160">Se viene visualizzato un **errore di comando interno o esterno**, verificare che sia stato aperto un nuovo prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-160">If you receive a **'databricks' is not recognized as an internal or external command error**, make sure you opened a new command prompt.</span></span>

## <a name="set-up-azure-databricks"></a><span data-ttu-id="f6b7e-161">Configurare Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="f6b7e-161">Set up Azure Databricks</span></span>

<span data-ttu-id="f6b7e-162">Ora che è stata installata l'interfaccia della riga di comando di databricks, è necessario configurare i dettagli di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-162">Now that you have the Databricks CLI installed, you need to set up authentication details.</span></span>

1. <span data-ttu-id="f6b7e-163">Eseguire il comando dell'interfaccia della riga di comando di databricks `databricks configure --token` .</span><span class="sxs-lookup"><span data-stu-id="f6b7e-163">Run the Databricks CLI command `databricks configure --token`.</span></span>

2. <span data-ttu-id="f6b7e-164">Dopo aver eseguito il comando configure, viene richiesto di immettere un host.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-164">After running the configure command, you are prompted to enter a host.</span></span> <span data-ttu-id="f6b7e-165">L'URL dell'host usa il formato: **https://< \location>. azuredatabricks.NET**.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-165">Your host URL uses the format: **https://<\Location>.azuredatabricks.net**.</span></span> <span data-ttu-id="f6b7e-166">Se, ad esempio, si seleziona **eastus2** durante la creazione del servizio Azure Databricks, l'host sarà **https://eastus2.azuredatabricks.net** .</span><span class="sxs-lookup"><span data-stu-id="f6b7e-166">For instance, if you selected **eastus2** during Azure Databricks Service creation, the host would be **https://eastus2.azuredatabricks.net**.</span></span>

3. <span data-ttu-id="f6b7e-167">Dopo l'immissione dell'host, viene richiesto di immettere un token.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-167">After entering your host, you are prompted to enter a token.</span></span> <span data-ttu-id="f6b7e-168">Nella portale di Azure selezionare **Avvia area di lavoro** per avviare l'area di lavoro Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-168">In the Azure portal, select **Launch Workspace** to launch your Azure Databricks workspace.</span></span>

   ![Avvia Azure Databricks area di lavoro](./media/databricks-deployment/launch-databricks-workspace.png)

4. <span data-ttu-id="f6b7e-170">Nella home page dell'area di lavoro selezionare **impostazioni utente**.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-170">On the home page of your workspace, select **User Settings**.</span></span>

   ![Impostazioni utente nell'area di lavoro Azure Databricks](./media/databricks-deployment/databricks-user-settings.png)

5. <span data-ttu-id="f6b7e-172">Nella pagina impostazioni utente è possibile generare un nuovo token.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-172">On the User Settings page, you can generate a new token.</span></span> <span data-ttu-id="f6b7e-173">Copiare il token generato e incollarlo di nuovo nel prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-173">Copy the generated token and paste it back into your command prompt.</span></span>

   ![Genera un nuovo token di accesso nell'area di lavoro Azure Databricks](./media/databricks-deployment/generate-token.png)

<span data-ttu-id="f6b7e-175">A questo punto dovrebbe essere possibile accedere a tutti i cluster di Azure Databricks creati e caricare i file in DBFS.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-175">You should now be able to access any Azure Databricks clusters you create and upload files to the DBFS.</span></span>

## <a name="download-worker-dependencies"></a><span data-ttu-id="f6b7e-176">Scarica dipendenze di lavoro</span><span class="sxs-lookup"><span data-stu-id="f6b7e-176">Download worker dependencies</span></span>

1. <span data-ttu-id="f6b7e-177">Microsoft. Spark. Worker consente di Apache Spark eseguire l'app, ad esempio qualsiasi funzione definita dall'utente (UDF) che è stata scritta.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-177">Microsoft.Spark.Worker helps Apache Spark execute your app, such as any user-defined functions (UDFs) you may have written.</span></span> <span data-ttu-id="f6b7e-178">Scaricare [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="f6b7e-178">Download [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz).</span></span>

2. <span data-ttu-id="f6b7e-179">*Install-Worker.sh* è uno script che consente di copiare .net per Apache Spark file dipendenti nei nodi del cluster.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-179">The *install-worker.sh* is a script that lets you copy .NET for Apache Spark dependent files into the nodes of your cluster.</span></span>

   <span data-ttu-id="f6b7e-180">Creare un nuovo file denominato **Install-Worker.sh** nel computer locale e incollare il contenuto di [Install-Worker.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) disponibile in GitHub.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-180">Create a new file named **install-worker.sh** on your local computer, and paste the [install-worker.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) located on GitHub.</span></span>

3. <span data-ttu-id="f6b7e-181">*DB-init.sh* è uno script che consente di installare le dipendenze nel cluster Spark di databricks.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-181">The *db-init.sh* is a script that installs dependencies onto your Databricks Spark cluster.</span></span>

   <span data-ttu-id="f6b7e-182">Creare un nuovo file denominato **DB-init.sh** nel computer locale e incollare il contenuto di [DB-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) disponibile in GitHub.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-182">Create a new file named **db-init.sh** on your local computer, and paste the [db-init.sh contents](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) located on GitHub.</span></span>

   <span data-ttu-id="f6b7e-183">Nel file appena creato impostare la `DOTNET_SPARK_RELEASE` variabile su `https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz` .</span><span class="sxs-lookup"><span data-stu-id="f6b7e-183">In the file you just created, set the `DOTNET_SPARK_RELEASE` variable to `https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz`.</span></span> <span data-ttu-id="f6b7e-184">Lasciare invariato il resto del file *DB-init.sh* .</span><span class="sxs-lookup"><span data-stu-id="f6b7e-184">Leave the rest of the *db-init.sh* file as-is.</span></span>

> [!Note]
> <span data-ttu-id="f6b7e-185">Se si usa Windows, verificare che le terminazioni di riga negli script *Install-Worker.sh* e *DB-init.sh* siano di tipo UNIX (LF).</span><span class="sxs-lookup"><span data-stu-id="f6b7e-185">If you are using Windows, verify that the line-endings in your *install-worker.sh* and *db-init.sh* scripts are Unix-style (LF).</span></span> <span data-ttu-id="f6b7e-186">È possibile modificare le terminazioni riga tramite editor di testo come blocco note + + e Atom.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-186">You can change line endings through text editors like Notepad++ and Atom.</span></span>

## <a name="publish-your-app"></a><span data-ttu-id="f6b7e-187">Pubblicare l'app</span><span class="sxs-lookup"><span data-stu-id="f6b7e-187">Publish your app</span></span>

<span data-ttu-id="f6b7e-188">Successivamente, pubblicare il *mySparkApp* creato in [.NET per Apache Spark-introduzione in 10 minuti](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) esercitazione per assicurarsi che il cluster Spark possa accedere a tutti i file necessari per eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-188">Next, you publish the *mySparkApp* created in the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial to ensure your Spark cluster has access to all the files it needs to run your app.</span></span>

1. <span data-ttu-id="f6b7e-189">Eseguire i comandi seguenti per pubblicare il *mySparkApp*:</span><span class="sxs-lookup"><span data-stu-id="f6b7e-189">Run the following commands to publish the *mySparkApp*:</span></span>

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. <span data-ttu-id="f6b7e-190">Eseguire le attività seguenti per comprimere i file dell'app pubblicata in modo che sia possibile caricarli facilmente nel cluster di databricks Spark.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-190">Do the following tasks to zip your published app files so that you can easily upload them to your Databricks Spark cluster.</span></span>

   <span data-ttu-id="f6b7e-191">**In Windows:**</span><span class="sxs-lookup"><span data-stu-id="f6b7e-191">**On Windows:**</span></span>

   <span data-ttu-id="f6b7e-192">Passare a mySparkApp/bin/Release/netcoreapp 3.0/Ubuntu. 16.04-x64.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-192">Navigate to mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64.</span></span> <span data-ttu-id="f6b7e-193">Quindi, fare clic con il pulsante destro del mouse su cartella di **pubblicazione** e selezionare **Invia a > cartella compressa**.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-193">Then, right-click on **Publish** folder and select **Send to > Compressed (zipped) folder**.</span></span> <span data-ttu-id="f6b7e-194">Assegnare alla nuova cartella il nome **Publish. zip**.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-194">Name the new folder **publish.zip**.</span></span>

   <span data-ttu-id="f6b7e-195">**In Linux eseguire il comando seguente:**</span><span class="sxs-lookup"><span data-stu-id="f6b7e-195">**On Linux, run the following command:**</span></span>

   ```bash
   zip -r publish.zip .
   ```

## <a name="upload-files"></a><span data-ttu-id="f6b7e-196">Caricare file</span><span class="sxs-lookup"><span data-stu-id="f6b7e-196">Upload files</span></span>

<span data-ttu-id="f6b7e-197">In questa sezione vengono caricati diversi file in DBFS in modo che il cluster disponga di tutti gli elementi necessari per eseguire l'app nel cloud.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-197">In this section, you upload several files to DBFS so that your cluster has everything it needs to run your app in the cloud.</span></span> <span data-ttu-id="f6b7e-198">Ogni volta che si carica un file in DBFS, assicurarsi di trovarsi nella directory in cui si trova il file nel computer.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-198">Each time you upload a file to the DBFS, make sure you are in the directory where that file is located on your computer.</span></span>

1. <span data-ttu-id="f6b7e-199">Eseguire i comandi seguenti per caricare *DB-init.sh*, *Install-Worker.sh*e *Microsoft. Spark. Worker* in DBFS:</span><span class="sxs-lookup"><span data-stu-id="f6b7e-199">Run the following commands to upload the *db-init.sh*, *install-worker.sh*, and *Microsoft.Spark.Worker* to DBFS:</span></span>

   ```console
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   databricks fs cp Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz dbfs:/spark-dotnet/   Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz
   ```

2. <span data-ttu-id="f6b7e-200">Eseguire i comandi seguenti per caricare i file rimanenti che il cluster dovrà eseguire l'app: la cartella di pubblicazione compresso, *input. txt*e *Microsoft-Spark-2.4. x-0.3.0. jar*.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-200">Run the following commands to upload the remaining files your cluster will need to run your app: the zipped publish folder, *input.txt*, and *microsoft-spark-2.4.x-0.3.0.jar*.</span></span>

   ```console
   cd mySparkApp
   databricks fs cp input.txt dbfs:/input.txt

   cd mySparkApp\bin\Release\netcoreapp3.0\ubuntu.16.04-x64 directory
   databricks fs cp mySparkApp.zip dbfs:/spark-dotnet/publish.zip
   databricks fs cp microsoft-spark-2.4.x-0.6.0.jar dbfs:/spark-dotnet/microsoft-spark-2.4.x-0.6.0.jar
   ```

## <a name="create-a-job"></a><span data-ttu-id="f6b7e-201">Creare un processo</span><span class="sxs-lookup"><span data-stu-id="f6b7e-201">Create a job</span></span>

<span data-ttu-id="f6b7e-202">L'app viene eseguita in Azure Databricks tramite un processo che esegue **Spark-Submit**, che è il comando usato per eseguire .net per Apache Spark processi.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-202">Your app runs on Azure Databricks through a job that runs **spark-submit**, which is the command you use to run .NET for Apache Spark jobs.</span></span>

1. <span data-ttu-id="f6b7e-203">Nell'area di lavoro Azure Databricks selezionare l'icona **processi** , quindi **+ Crea processo**.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-203">In your Azure Databricks Workspace, select the **Jobs** icon and then **+ Create Job**.</span></span>

   ![Creare un processo di Azure Databricks](./media/databricks-deployment/create-job.png)

2. <span data-ttu-id="f6b7e-205">Scegliere un titolo per il processo e quindi selezionare **Configura Spark-Submit**.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-205">Choose a title for your job, and then select **Configure spark-submit**.</span></span>

   ![Configurare Spark-Submit per un processo databricks](./media/databricks-deployment/configure-spark-submit.png)

3. <span data-ttu-id="f6b7e-207">Incollare i parametri seguenti nella configurazione del processo.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-207">Paste the following parameters in the job configuration.</span></span> <span data-ttu-id="f6b7e-208">Selezionare quindi **conferma**.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-208">Then, select **Confirm**.</span></span>

   ```
   ["--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/spark-dotnet/microsoft-spark-2.4.x-0.6.0.jar","/dbfs/spark-dotnet/publish.zip","mySparkApp"]
   ```

## <a name="create-a-cluster"></a><span data-ttu-id="f6b7e-209">Creare un cluster</span><span class="sxs-lookup"><span data-stu-id="f6b7e-209">Create a cluster</span></span>

1. <span data-ttu-id="f6b7e-210">Passare al processo e selezionare **modifica** per configurare il cluster del processo.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-210">Navigate to your job and select **Edit** to configure your job's cluster.</span></span>

2. <span data-ttu-id="f6b7e-211">Impostare il cluster su **Spark 2.4.1**.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-211">Set your cluster to **Spark 2.4.1**.</span></span> <span data-ttu-id="f6b7e-212">Quindi, selezionare **Opzioni avanzate**  >  **script init**.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-212">Then, select **Advanced Options** > **Init Scripts**.</span></span> <span data-ttu-id="f6b7e-213">Impostare percorso script init come `dbfs:/spark-dotnet/db-init.sh` .</span><span class="sxs-lookup"><span data-stu-id="f6b7e-213">Set Init Script Path as `dbfs:/spark-dotnet/db-init.sh`.</span></span>

   ![Configurare il cluster Spark in Azure Databricks](./media/databricks-deployment/cluster-config.png)

3. <span data-ttu-id="f6b7e-215">Selezionare **conferma** per confermare le impostazioni del cluster.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-215">Select **Confirm** to confirm your cluster settings.</span></span>

## <a name="run-your-app"></a><span data-ttu-id="f6b7e-216">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="f6b7e-216">Run your app</span></span>

1. <span data-ttu-id="f6b7e-217">Passare al processo e selezionare **Esegui adesso** per eseguire il processo nel cluster Spark appena configurato.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-217">Navigate to your job and select **Run Now** to run your job on your newly configured Spark cluster.</span></span>

2. <span data-ttu-id="f6b7e-218">La creazione del cluster del processo richiede alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-218">It takes a few minutes for the job's cluster to create.</span></span> <span data-ttu-id="f6b7e-219">Una volta creato, il processo verrà inviato ed è possibile visualizzare l'output.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-219">Once it is created, your job will be submitted, and you can view the output.</span></span>

3. <span data-ttu-id="f6b7e-220">Selezionare **cluster** dal menu a sinistra e quindi il nome e l'esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-220">Select **Clusters** from the left menu, and then the name and run of your job.</span></span>

4. <span data-ttu-id="f6b7e-221">Selezionare **log driver** per visualizzare l'output del processo.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-221">Select **Driver Logs** to view the output of your job.</span></span> <span data-ttu-id="f6b7e-222">Al termine dell'esecuzione dell'app, nella console di output standard viene visualizzata la stessa tabella di conteggio delle parole dell'esecuzione locale di Getting Started.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-222">When your app finishes executing, you see the same word count table from the getting started local run written to the standard output console.</span></span>

   ![Tabella di output del processo Azure Databricks](./media/databricks-deployment/table-output.png)

   <span data-ttu-id="f6b7e-224">Congratulazioni, è stata eseguita la prima applicazione .NET per Apache Spark nel cloud.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-224">Congratulations, you've run your first .NET for Apache Spark application in the cloud!</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="f6b7e-225">Pulire le risorse</span><span class="sxs-lookup"><span data-stu-id="f6b7e-225">Clean up resources</span></span>

<span data-ttu-id="f6b7e-226">Se l'area di lavoro databricks non è più necessaria, è possibile eliminare la risorsa Azure Databricks nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-226">If you no longer need the Databricks workspace, you can delete your Azure Databricks resource in the Azure portal.</span></span> <span data-ttu-id="f6b7e-227">È anche possibile selezionare il nome del gruppo di risorse per aprire la pagina del gruppo di risorse e quindi selezionare **Elimina gruppo di risorse**.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-227">You can also select the resource group name to open the resource group page, and then select **Delete resource group**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f6b7e-228">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f6b7e-228">Next steps</span></span>

<span data-ttu-id="f6b7e-229">In questa esercitazione è stata distribuita un'applicazione .NET per Apache Spark in Databricks.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-229">In this tutorial, you deployed your .NET for Apache Spark application to Databricks.</span></span> <span data-ttu-id="f6b7e-230">Per altre informazioni su Databricks, passare alla documentazione di Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="f6b7e-230">To learn more about Databricks, continue to the Azure Databricks Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f6b7e-231">Documentazione di Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="f6b7e-231">Azure Databricks Documentation</span></span>](https://docs.microsoft.com/azure/azure-databricks/)

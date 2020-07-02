---
title: Installare .NET per Apache Spark nei notebook di Jupyter nei cluster Azure HDInsight Spark
description: Informazioni su come installare .NET per Apache Spark nei notebook Jupyter di Azure HDInsight.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 14babf7a551192b286f309393e3bbff25d4745d5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617743"
---
# <a name="install-net-for-apache-spark-on-jupyter-notebooks-on-azure-hdinsight-spark-clusters"></a><span data-ttu-id="04264-103">Installare .NET per Apache Spark nei notebook di Jupyter nei cluster Azure HDInsight Spark</span><span class="sxs-lookup"><span data-stu-id="04264-103">Install .NET for Apache Spark on Jupyter notebooks on Azure HDInsight Spark clusters</span></span>

<span data-ttu-id="04264-104">Questo articolo illustra come installare .NET per Apache Spark in notebook di Jupyter in Azure HDInsight Spark cluster.</span><span class="sxs-lookup"><span data-stu-id="04264-104">This article teaches you how to install .NET for Apache Spark on Jupyter notebooks on Azure HDInsight Spark clusters.</span></span> <span data-ttu-id="04264-105">È possibile distribuire .NET per Apache Spark nei cluster Azure HDInsight tramite una combinazione della riga di comando e della portale di Azure (per altre informazioni, vedere [How to Deploy an .NET for Apache Spark Application to Azure HDInsight](../tutorials/hdinsight-deployment.md)), ma i notebook forniscono un'esperienza interattiva e iterativa.</span><span class="sxs-lookup"><span data-stu-id="04264-105">You can deploy .NET for Apache Spark on Azure HDInsight clusters through a combination of the command line and the Azure portal (for more information, see [how to deploy a .NET for Apache Spark application to Azure HDInsight](../tutorials/hdinsight-deployment.md)), but notebooks provide a more interactive and iterative experience.</span></span>

<span data-ttu-id="04264-106">I cluster HDInsight di Azure sono già dotati di notebook di Jupyter, quindi è sufficiente configurare i notebook di Jupyter per eseguire .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="04264-106">Azure HDInsight clusters already come with Jupyter notebooks, so all you have to do is configure the Jupyter notebooks to run .NET for Apache Spark.</span></span> <span data-ttu-id="04264-107">Per usare .NET per Apache Spark nei notebook di Jupyter, è necessario un REPL C# per eseguire il codice C# riga per riga e mantenere lo stato di esecuzione quando necessario.</span><span class="sxs-lookup"><span data-stu-id="04264-107">To use .NET for Apache Spark in your Jupyter notebooks, a C# REPL is needed to execute your C# code line-by-line and to preserve execution state when necessary.</span></span> <span data-ttu-id="04264-108">[Try .NET](https://github.com/dotnet/try) è stato integrato come repl .NET ufficiale.</span><span class="sxs-lookup"><span data-stu-id="04264-108">[Try .NET](https://github.com/dotnet/try) has been integrated as the official .NET REPL.</span></span>

<span data-ttu-id="04264-109">Per abilitare .NET per Apache Spark tramite l'esperienza Jupyter Notebooks, è necessario seguire alcuni passaggi manuali tramite [Ambari](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-manage-ambari) e inviare [azioni script](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux) nel cluster HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="04264-109">To enable .NET for Apache Spark through the Jupyter Notebooks experience, you need to follow a few manual steps through [Ambari](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-manage-ambari) and submit [script actions](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux) on the HDInsight Spark cluster.</span></span>

> [!NOTE]
> <span data-ttu-id="04264-110">Questa funzionalità è *sperimentale* e non è supportata dal team di HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="04264-110">This feature is *experimental* and is not supported by the HDInsight Spark team.</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a><span data-ttu-id="04264-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="04264-111">Prerequisites</span></span>

<span data-ttu-id="04264-112">Se non ne è già presente uno, creare un cluster [Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-jupyter-spark-sql-use-portal#create-an-apache-spark-cluster-in-hdinsight) .</span><span class="sxs-lookup"><span data-stu-id="04264-112">If you don't already have one, create an [Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-jupyter-spark-sql-use-portal#create-an-apache-spark-cluster-in-hdinsight) cluster.</span></span>

1. <span data-ttu-id="04264-113">Visitare il [portale di Azure](https://portal.azure.com) e selezionare **+ Crea una risorsa**.</span><span class="sxs-lookup"><span data-stu-id="04264-113">Visit the [Azure portal](https://portal.azure.com) and select **+ Create a Resource**.</span></span>

1. <span data-ttu-id="04264-114">Creare una nuova risorsa cluster di Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="04264-114">Create a new Azure HDInsight cluster resource.</span></span> <span data-ttu-id="04264-115">Selezionare **Spark 2,4** e **HDI 4,0** durante la creazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="04264-115">Select **Spark 2.4** and **HDI 4.0** during cluster creation.</span></span>

## <a name="install-net-for-apache-spark"></a><span data-ttu-id="04264-116">Installare .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="04264-116">Install .NET for Apache Spark</span></span>

<span data-ttu-id="04264-117">Nella portale di Azure selezionare il **cluster HDInsight Spark** creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="04264-117">In the Azure portal, select the **HDInsight Spark cluster** you created in the previous step.</span></span>

### <a name="stop-the-livy-server"></a><span data-ttu-id="04264-118">Arrestare il server Livio</span><span class="sxs-lookup"><span data-stu-id="04264-118">Stop the Livy server</span></span>

1. <span data-ttu-id="04264-119">Dal portale selezionare **Panoramica**, quindi selezionare **Ambari Home**.</span><span class="sxs-lookup"><span data-stu-id="04264-119">From the portal, select **Overview**, and then select **Ambari home**.</span></span> <span data-ttu-id="04264-120">Se richiesto, immettere le credenziali di accesso per il cluster.</span><span class="sxs-lookup"><span data-stu-id="04264-120">If prompted, enter the login credentials for the cluster.</span></span>

   ![Interrompi server Livio](./media/hdinsight-notebook-installation/select-ambari.png)

2. <span data-ttu-id="04264-122">Selezionare **Spark2** nel menu di spostamento a sinistra e selezionare **Livio per il server Spark2**.</span><span class="sxs-lookup"><span data-stu-id="04264-122">Select **Spark2** from the left navigation menu, and select **LIVY FOR SPARK2 SERVER**.</span></span>

   ![Interrompi server Livio](./media/hdinsight-notebook-installation/select-livyserver.png)

3. <span data-ttu-id="04264-124">Seleziona **hn0... host**.</span><span class="sxs-lookup"><span data-stu-id="04264-124">Select **hn0... host**.</span></span>

   ![Interrompi server Livio](./media/hdinsight-notebook-installation/select-host.png)

4. <span data-ttu-id="04264-126">Selezionare i puntini di sospensione accanto a **Livio per il server Spark2** e selezionare **Arresta**.</span><span class="sxs-lookup"><span data-stu-id="04264-126">Select the ellipsis next to **Livy for Spark2 Server** and select **Stop**.</span></span> <span data-ttu-id="04264-127">Quando richiesto, selezionare **OK** per continuare.</span><span class="sxs-lookup"><span data-stu-id="04264-127">When prompted, select **OK** to proceed.</span></span>

   <span data-ttu-id="04264-128">Arrestare Livio per il server Spark2.</span><span class="sxs-lookup"><span data-stu-id="04264-128">Stop Livy for Spark2 Server.</span></span>
   <span data-ttu-id="04264-129">![Interrompi server Livio](./media/hdinsight-notebook-installation/stop-server.png)</span><span class="sxs-lookup"><span data-stu-id="04264-129">![Stop Livy Server](./media/hdinsight-notebook-installation/stop-server.png)</span></span>

5. <span data-ttu-id="04264-130">Ripetere i passaggi precedenti per **HN1... host**.</span><span class="sxs-lookup"><span data-stu-id="04264-130">Repeat the previous steps for **hn1... host**.</span></span>

### <a name="submit-an-hdinsight-script-action"></a><span data-ttu-id="04264-131">Inviare un'azione di script HDInsight</span><span class="sxs-lookup"><span data-stu-id="04264-131">Submit an HDInsight script action</span></span>

1. <span data-ttu-id="04264-132">`install-interactive-notebook.sh`È uno script che installa .NET per Apache Spark e apporta modifiche a Apache Livio e sparkmagic.</span><span class="sxs-lookup"><span data-stu-id="04264-132">The `install-interactive-notebook.sh` is a script that installs .NET for Apache Spark and makes changes to Apache Livy and sparkmagic.</span></span> <span data-ttu-id="04264-133">Prima di inviare un'azione script a HDInsight, è necessario creare e caricare `install-interactive-notebook.sh` .</span><span class="sxs-lookup"><span data-stu-id="04264-133">Before you submit a script action to HDInsight, you need to create and upload `install-interactive-notebook.sh`.</span></span>

   <span data-ttu-id="04264-134">Creare un nuovo file denominato **Install-Interactive-notebook.sh** nel computer locale e incollare il contenuto del [contenuto di install-Interactive-notebook.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/HDI-Spark/Notebooks/install-interactive-notebook.sh).</span><span class="sxs-lookup"><span data-stu-id="04264-134">Create a new file named **install-interactive-notebook.sh** in your local computer and paste the contents of [install-interactive-notebook.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/HDI-Spark/Notebooks/install-interactive-notebook.sh).</span></span>

   <span data-ttu-id="04264-135">Caricare lo script in un [URI](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux#understand-script-actions) accessibile dal cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="04264-135">Upload the script to a [URI](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux#understand-script-actions) that's accessible from the HDInsight cluster.</span></span> <span data-ttu-id="04264-136">Ad esempio, `https://<my storage account>.blob.core.windows.net/<my container>/<some dir>/install-interactive-notebook.sh`</span><span class="sxs-lookup"><span data-stu-id="04264-136">For example, `https://<my storage account>.blob.core.windows.net/<my container>/<some dir>/install-interactive-notebook.sh`.</span></span>

2. <span data-ttu-id="04264-137">Eseguire `install-interactive-notebook.sh` nel cluster usando [azioni script di HDInsight](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span><span class="sxs-lookup"><span data-stu-id="04264-137">Run `install-interactive-notebook.sh` on the cluster using [HDInsight Script Actions](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span></span>

   <span data-ttu-id="04264-138">Tornare al cluster HDI nell'portale di Azure e selezionare **azioni script** dalle opzioni a sinistra.</span><span class="sxs-lookup"><span data-stu-id="04264-138">Return to your HDI cluster in the Azure portal, and select **Script actions** from the options on the left.</span></span> <span data-ttu-id="04264-139">Si invia un'azione script per distribuire .NET per Apache Spark REPL nel cluster HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="04264-139">You submit one script action to deploy the .NET for Apache Spark REPL on your HDInsight Spark cluster.</span></span> <span data-ttu-id="04264-140">Usare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="04264-140">Use the following settings:</span></span>

   |<span data-ttu-id="04264-141">Proprietà</span><span class="sxs-lookup"><span data-stu-id="04264-141">Property</span></span>  |<span data-ttu-id="04264-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04264-142">Description</span></span>  |
   |---------|---------|
   | <span data-ttu-id="04264-143">Tipo di script</span><span class="sxs-lookup"><span data-stu-id="04264-143">Script type</span></span> | <span data-ttu-id="04264-144">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="04264-144">Custom</span></span> |
   | <span data-ttu-id="04264-145">Name</span><span class="sxs-lookup"><span data-stu-id="04264-145">Name</span></span> | <span data-ttu-id="04264-146">*Installare .NET per Apache Spark esperienza interattiva del notebook*</span><span class="sxs-lookup"><span data-stu-id="04264-146">*Install .NET for Apache Spark Interactive Notebook Experience*</span></span> |
   | <span data-ttu-id="04264-147">URI script Bash</span><span class="sxs-lookup"><span data-stu-id="04264-147">Bash script URI</span></span> | <span data-ttu-id="04264-148">URI in cui è stato caricato `install-interactive-notebook.sh`.</span><span class="sxs-lookup"><span data-stu-id="04264-148">The URI to which you uploaded `install-interactive-notebook.sh`.</span></span> |
   | <span data-ttu-id="04264-149">Tipo/i di nodo</span><span class="sxs-lookup"><span data-stu-id="04264-149">Node type(s)</span></span>| <span data-ttu-id="04264-150">Head e worker</span><span class="sxs-lookup"><span data-stu-id="04264-150">Head and Worker</span></span> |
   | <span data-ttu-id="04264-151">Parametri</span><span class="sxs-lookup"><span data-stu-id="04264-151">Parameters</span></span> | <span data-ttu-id="04264-152">.NET per Apache Spark versione.</span><span class="sxs-lookup"><span data-stu-id="04264-152">.NET for Apache Spark version.</span></span> <span data-ttu-id="04264-153">È possibile controllare [.NET per Apache Spark versioni](https://github.com/dotnet/spark/releases).</span><span class="sxs-lookup"><span data-stu-id="04264-153">You can check [.NET for Apache Spark releases](https://github.com/dotnet/spark/releases).</span></span> <span data-ttu-id="04264-154">Ad esempio, se si vuole installare Sparkdotnet versione 0.6.0, sarà `0.6.0` .</span><span class="sxs-lookup"><span data-stu-id="04264-154">For example, if you want to install Sparkdotnet version 0.6.0 then it would be `0.6.0`.</span></span>

   <span data-ttu-id="04264-155">Passare al passaggio successivo quando vengono visualizzati segni di spunta verdi accanto allo stato dell'azione script.</span><span class="sxs-lookup"><span data-stu-id="04264-155">Move to the next step when green checkmarks appear next to the status of the script action.</span></span>

### <a name="start-the-livy-server"></a><span data-ttu-id="04264-156">Avviare il server Livio</span><span class="sxs-lookup"><span data-stu-id="04264-156">Start the Livy server</span></span>

<span data-ttu-id="04264-157">Seguire le istruzioni riportate nella sezione [arrestare il server Livio](#stop-the-livy-server) per **avviare** (anziché **arrestare**) il Livio per il server Spark2 per gli host **hn0** e **HN1**.</span><span class="sxs-lookup"><span data-stu-id="04264-157">Follow the instructions in the [Stop Livy server](#stop-the-livy-server) section to **Start** (rather than **Stop**) the Livy for Spark2 Server for hosts **hn0** and **hn1**.</span></span>

### <a name="set-up-spark-default-configurations"></a><span data-ttu-id="04264-158">Configurare le configurazioni predefinite di Spark</span><span class="sxs-lookup"><span data-stu-id="04264-158">Set up Spark default configurations</span></span>

1. <span data-ttu-id="04264-159">Dal portale selezionare **Panoramica**, quindi selezionare **Ambari Home**.</span><span class="sxs-lookup"><span data-stu-id="04264-159">From the portal, select **Overview**, and then select **Ambari home**.</span></span> <span data-ttu-id="04264-160">Se richiesto, immettere le credenziali di accesso del cluster.</span><span class="sxs-lookup"><span data-stu-id="04264-160">If prompted, enter the cluster login credentials for the cluster.</span></span>

2. <span data-ttu-id="04264-161">Selezionare **Spark2** e **configs**.</span><span class="sxs-lookup"><span data-stu-id="04264-161">Select **Spark2** and **CONFIGS**.</span></span> <span data-ttu-id="04264-162">Quindi selezionare **Custom spark2-defaults**.</span><span class="sxs-lookup"><span data-stu-id="04264-162">Then, select **Custom spark2-defaults**.</span></span>

   ![Imposta configurazioni](./media/hdinsight-notebook-installation/spark-configs.png)

3. <span data-ttu-id="04264-164">Selezionare **Aggiungi proprietà** per aggiungere le impostazioni predefinite di Spark.</span><span class="sxs-lookup"><span data-stu-id="04264-164">Select **Add Property...** to add Spark default settings.</span></span>

   ![Aggiungi proprietà](./media/hdinsight-notebook-installation/add-property.png)

   <span data-ttu-id="04264-166">Sono disponibili tre singole proprietà.</span><span class="sxs-lookup"><span data-stu-id="04264-166">There are three individual properties.</span></span> <span data-ttu-id="04264-167">Aggiungerli uno alla volta usando il tipo di proprietà **Text** in modalità di aggiunta di una singola proprietà.</span><span class="sxs-lookup"><span data-stu-id="04264-167">Add them one at a time using the **TEXT** property type in Single property add mode.</span></span> <span data-ttu-id="04264-168">Verificare che non siano presenti spazi aggiuntivi prima o dopo una qualsiasi delle chiavi o dei valori.</span><span class="sxs-lookup"><span data-stu-id="04264-168">Check that you don't have any extra spaces before or after any of the keys/values.</span></span>

   * <span data-ttu-id="04264-169">**Proprietà 1**</span><span class="sxs-lookup"><span data-stu-id="04264-169">**Property 1**</span></span>
       * <span data-ttu-id="04264-170">Chiave&ensp;&ensp;`spark.dotnet.shell.command`</span><span class="sxs-lookup"><span data-stu-id="04264-170">Key:&ensp;&ensp;`spark.dotnet.shell.command`</span></span>
       * <span data-ttu-id="04264-171">Valore: `/usr/share/dotnet-tools/dotnet-try,kernel-server,--default-kernel,csharp`</span><span class="sxs-lookup"><span data-stu-id="04264-171">Value: `/usr/share/dotnet-tools/dotnet-try,kernel-server,--default-kernel,csharp`</span></span>

   * <span data-ttu-id="04264-172">**Proprietà 2** Usare la versione di .NET per Apache Spark inclusa nell'azione script precedente.</span><span class="sxs-lookup"><span data-stu-id="04264-172">**Property 2** Use the version of .NET for Apache Spark which you had included in the previous script action.</span></span>
       * <span data-ttu-id="04264-173">Chiave&ensp;&ensp;`spark.dotnet.packages`</span><span class="sxs-lookup"><span data-stu-id="04264-173">Key:&ensp;&ensp;`spark.dotnet.packages`</span></span>
       * <span data-ttu-id="04264-174">Valore: `["nuget: Microsoft.Spark, 0.6.0", "nuget: Microsoft.Spark.Extensions.Delta, 0.6.0"]`</span><span class="sxs-lookup"><span data-stu-id="04264-174">Value: `["nuget: Microsoft.Spark, 0.6.0", "nuget: Microsoft.Spark.Extensions.Delta, 0.6.0"]`</span></span>

   * <span data-ttu-id="04264-175">**Proprietà 3**</span><span class="sxs-lookup"><span data-stu-id="04264-175">**Property 3**</span></span>
       * <span data-ttu-id="04264-176">Chiave&ensp;&ensp;`spark.dotnet.interpreter`</span><span class="sxs-lookup"><span data-stu-id="04264-176">Key:&ensp;&ensp;`spark.dotnet.interpreter`</span></span>
       * <span data-ttu-id="04264-177">Valore: `try`</span><span class="sxs-lookup"><span data-stu-id="04264-177">Value: `try`</span></span>

   <span data-ttu-id="04264-178">Nell'immagine seguente, ad esempio, viene acquisita l'impostazione per l'aggiunta della proprietà 1:</span><span class="sxs-lookup"><span data-stu-id="04264-178">For example, the following image captures the setting for adding property 1:</span></span>

   ![Imposta configurazioni](./media/hdinsight-notebook-installation/add-sparkconfig.png)

   <span data-ttu-id="04264-180">Dopo aver aggiunto le tre proprietà, selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="04264-180">After adding the three properties, select **SAVE**.</span></span> <span data-ttu-id="04264-181">Se viene visualizzata una schermata di avviso relativa alle raccomandazioni di configurazione, selezionare **continua comunque**.</span><span class="sxs-lookup"><span data-stu-id="04264-181">If you see a warning screen of config recommendations, select **PROCEED ANYWAY**.</span></span>

4. <span data-ttu-id="04264-182">Riavviare i componenti interessati.</span><span class="sxs-lookup"><span data-stu-id="04264-182">Restart affected components.</span></span>

   <span data-ttu-id="04264-183">Dopo aver aggiunto le nuove proprietà, è necessario riavviare i componenti interessati dalle modifiche.</span><span class="sxs-lookup"><span data-stu-id="04264-183">After adding the new properties, you need to restart components that were affected by the changes.</span></span> <span data-ttu-id="04264-184">Nella parte superiore selezionare **Riavvia**, quindi **riavviare tutti gli interessati** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="04264-184">At the top, select **RESTART**, and then **Restart All Affected** from the drop-down.</span></span>

   ![Imposta configurazioni](./media/hdinsight-notebook-installation/restart-affected.png)

   <span data-ttu-id="04264-186">Quando richiesto, selezionare **Confirm REstart all** per continuare, quindi fare clic su **OK** per terminare.</span><span class="sxs-lookup"><span data-stu-id="04264-186">When prompted, select **CONFIRM RESTART ALL** to continue, then click **OK** to finish.</span></span>

## <a name="submit-jobs-through-a-jupyter-notebook"></a><span data-ttu-id="04264-187">Inviare processi tramite un notebook di Jupyter</span><span class="sxs-lookup"><span data-stu-id="04264-187">Submit jobs through a Jupyter notebook</span></span>

<span data-ttu-id="04264-188">Dopo aver completato i passaggi precedenti, è ora possibile inviare .NET per i processi di Apache Spark tramite notebook di Jupyter.</span><span class="sxs-lookup"><span data-stu-id="04264-188">After finishing the previous steps, you can now submit your .NET for Apache Spark jobs through Jupyter notebooks.</span></span>

1. <span data-ttu-id="04264-189">Creare una nuova .NET per Apache Spark notebook.</span><span class="sxs-lookup"><span data-stu-id="04264-189">Create a new .NET for Apache Spark notebook.</span></span> <span data-ttu-id="04264-190">Avviare un notebook di Jupyter dal cluster HDI nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="04264-190">Launch a Jupyter notebook from your HDI cluster in the Azure portal.</span></span>

   ![Avvia Jupyter Notebook](./media/hdinsight-notebook-installation/launch-notebook.png)

   <span data-ttu-id="04264-192">Quindi, selezionare **nuovo**  >  **.NET Spark (C#)** per creare un notebook.</span><span class="sxs-lookup"><span data-stu-id="04264-192">Then, select **New** > **.NET Spark (C#)** to create a notebook.</span></span>

   ![Notebook Jupyter](./media/hdinsight-notebook-installation/create-sparkdotnet-notebook.png)

2. <span data-ttu-id="04264-194">Inviare processi con .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="04264-194">Submit jobs using .NET for Apache Spark.</span></span>

   <span data-ttu-id="04264-195">Usare il frammento di codice seguente per creare un dataframe:</span><span class="sxs-lookup"><span data-stu-id="04264-195">Use the following code snippet to create a DataFrame:</span></span>

   ```csharp
   var df = spark.Range(0,5);
   df.Show();
   ```

   ![Invia processo Spark](./media/hdinsight-notebook-installation/create-df.png)

   <span data-ttu-id="04264-197">Usare il frammento di codice seguente per registrare una funzione definita dall'utente (UDF) e usare la funzione definita dall'utente con dataframe:</span><span class="sxs-lookup"><span data-stu-id="04264-197">Use the following code snippet to register a user-defined function (UDF) and use the UDF with DataFrames:</span></span>

   ```csharp
   var myawesomeudf = Udf<int, string>((id) => $"hello {id}");
   df.Select(myawesomeudf(df["id"])).Show();
   ```

   ![Invia processo Spark](./media/hdinsight-notebook-installation/run-udf.png)

## <a name="next-steps"></a><span data-ttu-id="04264-199">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="04264-199">Next steps</span></span>

* [<span data-ttu-id="04264-200">Distribuire un'applicazione .NET per Apache Spark in Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="04264-200">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="04264-201">Documentazione di HDInsight</span><span class="sxs-lookup"><span data-stu-id="04264-201">HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)

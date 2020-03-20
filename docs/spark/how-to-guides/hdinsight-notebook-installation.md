---
title: Installare .NET per Apache Spark nei blocchi appunti Jupyter nei cluster Spark di Azure HDInsightInstall .NET for Apache Spark on Jupyter notebooks on Azure HDInsight Spark clusters
description: Informazioni su come installare .NET per Apache Spark nei blocchi appunti Jupyter di Azure HDInsight.Learn how to install .NET for Apache Spark on Azure HDInsight's Jupyter Notebooks.
ms.date: 03/13/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 32047efcde093a3752bdd59baa88896d1547b93e
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546750"
---
# <a name="install-net-for-apache-spark-on-jupyter-notebooks-on-azure-hdinsight-spark-clusters"></a>Installare .NET per Apache Spark nei blocchi appunti Jupyter nei cluster Spark di Azure HDInsightInstall .NET for Apache Spark on Jupyter notebooks on Azure HDInsight Spark clusters

Questo articolo illustra come installare .NET per Apache Spark nei blocchi appunti Jupyter nei cluster Spark di Azure HDInsight.This article teaches you how to install .NET for Apache Spark on Jupyter notebooks on Azure HDInsight Spark clusters. È possibile distribuire .NET per Apache Spark nei cluster di Azure HDInsight tramite una combinazione della riga di comando e del portale di Azure (per altre informazioni, vedere [come distribuire un'applicazione .NET per Apache Spark in Azure HDInsight),](../tutorials/hdinsight-deployment.md)ma i notebook offrono un'esperienza più interattiva e iterativa.

I cluster di Azure HDInsight sono già dotati di blocchi appunti Jupyter, pertanto è consigliabile configurare i blocchi appunti Jupyter per l'esecuzione di .NET per Apache Spark.Azure HDInsight clusters already have with Jupyter notebooks, so all you have to do is configure the Jupyter notebooks to run .NET for Apache Spark. Per usare .NET per Apache Spark nei blocchi appunti Jupyter, è necessario un REPL di C'è necessario per eseguire il codice C 'NET riga per riga e per mantenere lo stato di esecuzione quando necessario. [Try .NET](https://github.com/dotnet/try) è stato integrato come REPL ufficiale .NET.

Per abilitare .NET per Apache Spark tramite l'esperienza Jupyter Notebooks, è necessario seguire alcuni passaggi manuali tramite [Ambari](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-manage-ambari) e inviare [azioni script](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux) nel cluster HDInsight Spark.

> [!NOTE]
> Questa funzionalità è *sperimentale* e non è supportata dal team di HDInsight Spark.This feature is experimental and is not supported by the HDInsight Spark team.

## <a name="prerequisites"></a>Prerequisites

Se non ne hai già uno, crea un cluster [Spark di Azure HDInsight.If](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-jupyter-spark-sql-use-portal#create-an-hdinsight-spark-cluster) you don't already have one, create an Azure HDInsight Spark cluster.

1. Visitare il [portale di Azure](https://portal.azure.com) e selezionare Crea una **risorsa**.

1. Creare una nuova risorsa cluster di Azure HDInsight.Create a new Azure HDInsight cluster resource. Selezionare **Spark 2.4** e **HDI 4.0** durante la creazione del cluster.

## <a name="install-net-for-apache-spark"></a>Installare .NET per Apache Spark

Nel portale di Azure selezionare il **cluster HDInsight Spark** creato nel passaggio precedente.

### <a name="stop-the-livy-server"></a>Arrestare il server Livy

1. Dal portale selezionare **Panoramica**, quindi **fare clic sulla home page di Ambari**. Se richiesto, immettere le credenziali di accesso per il cluster.

   ![Arresta Livy Server](./media/hdinsight-notebook-installation/select-ambari.png)

2. Selezionare **Spark2** dal menu di navigazione a sinistra e selezionare **LIVY FOR SPARK2 SERVER**.

   ![Arresta Livy Server](./media/hdinsight-notebook-installation/select-livyserver.png)

3. Selezionare **hn0... l'host**.

   ![Arresta Livy Server](./media/hdinsight-notebook-installation/select-host.png)

4. Selezionare i lipsiani accanto a **Livy per Spark2 Server** e selezionare **Arresta**. Quando richiesto, selezionare **OK** per procedere.

   Arrestare Livy per Spark2 Server.
   ![Arresta Livy Server](./media/hdinsight-notebook-installation/stop-server.png)

5. Ripetere i passaggi precedenti per **hn1... l'host**.

### <a name="submit-an-hdinsight-script-action"></a>Inviare un'azione di script HDInsightSubmit an HDInsight script action

1. Il `install-interactive-notebook.sh` è uno script che installa .NET per Apache Spark e apporta modifiche a Apache Livy e sparkmagic. Prima di inviare un'azione script a HDInsight, è necessario creare e caricare `install-interactive-notebook.sh`.

   Creare un nuovo file denominato **install-interactive-notebook.sh** nel computer locale e incollare il contenuto di [install-interactive-notebook.sh contenuto](https://raw.githubusercontent.com/dotnet/spark/master/deployment/HDI-Spark/Notebooks/install-interactive-notebook.sh).

   Caricare lo script in un URI accessibile dal cluster HDInsight.Upload the script to a [URI](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux#understand-script-actions) that's accessible from the HDInsight cluster. Ad esempio: `https://<my storage account>.blob.core.windows.net/<my container>/<some dir>/install-interactive-notebook.sh`.

2. Eseguire `install-interactive-notebook.sh` nel cluster usando [azioni script di HDInsight](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).

   Tornare al cluster HDI nel portale di Azure e selezionare **Azioni script** dalle opzioni a sinistra. Si invia un'azione di script per distribuire .NET per Apache Spark REPL nel cluster HDInsight Spark. Usare le seguenti impostazioni:

   |Proprietà  |Descrizione  |
   |---------|---------|
   | Tipo di script | Personalizzato |
   | Nome | *Installare .NET per L'esperienza notebook interattiva di Apache Spark* |
   | URI script Bash | URI in cui è stato caricato `install-interactive-notebook.sh`. |
   | Tipo/i di nodo| Testa e lavoratore |
   | Parametri | .NET per la versione Apache Spark. È possibile controllare .NET per le versioni di [Apache Spark](https://github.com/dotnet/spark/releases). Ad esempio, se si desidera installare Sparkdotnet versione 0.6.0, sarà `0.6.0`.

   Passare al passaggio successivo quando accanto allo stato dell'azione di script vengono visualizzati dei segni di spunta verdi.

### <a name="start-the-livy-server"></a>Avviare il server Livy

Seguire le istruzioni nella sezione [Stop Livy server](#stop-the-livy-server) per **avviare** (anziché **arrestare**) Il server Livy for Spark2 Server per gli host **hn0** e **hn1**.

### <a name="set-up-spark-default-configurations"></a>Configurare le configurazioni predefinite di Spark

1. Dal portale selezionare **Panoramica**, quindi **fare clic sulla home page di Ambari**. Se richiesto, immettere le credenziali di accesso del cluster.

2. Selezionare **Spark2** e **CONFIGS**. Selezionare quindi **Custom spark2-defaults**.

   ![Imposta configurazioni](./media/hdinsight-notebook-installation/spark-configs.png)

3. Selezionare Aggiungi proprietà... per aggiungere le impostazioni predefinite Spark.Select **Add Property...** to add Spark default settings.

   ![Aggiungi proprietà](./media/hdinsight-notebook-installation/add-property.png)

   Ci sono tre proprietà individuali. Aggiungerli uno alla volta utilizzando il tipo di proprietà TESTO in modalità di aggiunta di proprietà Single.Add them one at a time using the **TEXT** property type in Single property add mode. Verificare che non siano presenti spazi aggiuntivi prima o dopo una delle chiavi/valori.

   * **Proprietà 1**
       * Chiave:&ensp;&ensp;`spark.dotnet.shell.command`
       * Valore: `/usr/share/dotnet-tools/dotnet-try,kernel-server,--default-kernel,csharp`

   * **Proprietà 2** Utilizzare la versione di .NET per Apache Spark inclusa nell'azione script precedente.
       * Chiave:&ensp;&ensp;`spark.dotnet.packages`
       * Valore: `["nuget: Microsoft.Spark, 0.6.0", "nuget: Microsoft.Spark.Extensions.Delta, 0.6.0"]`

   * **Proprietà 3**
       * Chiave:&ensp;&ensp;`spark.dotnet.interpreter`
       * Valore: `try`

   Ad esempio, l'immagine seguente acquisisce l'impostazione per l'aggiunta della proprietà 1:For example, the following image captures the setting for adding property 1:

   ![Imposta configurazioni](./media/hdinsight-notebook-installation/add-sparkconfig.png)

   Dopo aver aggiunto le tre proprietà, selezionare **SALVA**. Se viene visualizzata una schermata di avviso dei suggerimenti di configurazione, selezionare **PROCEED ANYWAY**.

4. Riavviare i componenti interessati.

   Dopo aver aggiunto le nuove proprietà, è necessario riavviare i componenti interessati dalle modifiche. Nella parte superiore selezionare **RESTART**, quindi **Riavvia tutto interessato** dall'elenco a discesa.

   ![Imposta configurazioni](./media/hdinsight-notebook-installation/restart-affected.png)

   Quando richiesto, selezionare **CONFIRM RESTART ALL** per continuare, quindi fare clic su **OK** per terminare.

## <a name="submit-jobs-through-a-jupyter-notebook"></a>Inviare processi tramite un blocco appunti di Jupyter

Dopo aver completato i passaggi precedenti, è ora possibile inviare i processi .NET per Apache Spark tramite notebook Jupyter.

1. Creare un nuovo blocco appunti .NET per Apache Spark. Avviare un blocco appunti Jupyter dal cluster HDI nel portale di Azure.Launch a Jupyter notebook from your HDI cluster in the Azure portal.

   ![Lancia Jupyter Notebook](./media/hdinsight-notebook-installation/launch-notebook.png)

   Selezionare quindi **Nuovo** > **.NET Spark (Cè)** per creare un blocco appunti.

   ![Notebook Jupyter](./media/hdinsight-notebook-installation/create-sparkdotnet-notebook.png)

2. Inviare processi utilizzando .NET per Apache Spark.

   Usare il frammento di codice seguente per creare un oggetto DataFrame:Use the following code snippet to create a DataFrame:

   ```csharp
   var df = spark.Range(0,5);
   df.Show();
   ```

   ![Invia processo Spark](./media/hdinsight-notebook-installation/create-df.png)

   Use the following code snippet to register a user-defined function (UDF) and use the UDF with DataFrames:

   ```csharp
   var myawesomeudf = Udf<int, string>((id) => $"hello {id}");
   df.Select(myawesomeudf(df["id"])).Show();
   ```

   ![Invia processo Spark](./media/hdinsight-notebook-installation/run-udf.png)

## <a name="next-steps"></a>Passaggi successivi

* [Distribuire un'applicazione .NET per Apache Spark in Azure HDInsight](../tutorials/hdinsight-deployment.md)
* [Documentazione di HDInsightHDInsight Documentation](https://docs.microsoft.com/azure/hdinsight/)

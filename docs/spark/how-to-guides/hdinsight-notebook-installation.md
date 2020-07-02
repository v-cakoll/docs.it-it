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
# <a name="install-net-for-apache-spark-on-jupyter-notebooks-on-azure-hdinsight-spark-clusters"></a>Installare .NET per Apache Spark nei notebook di Jupyter nei cluster Azure HDInsight Spark

Questo articolo illustra come installare .NET per Apache Spark in notebook di Jupyter in Azure HDInsight Spark cluster. È possibile distribuire .NET per Apache Spark nei cluster Azure HDInsight tramite una combinazione della riga di comando e della portale di Azure (per altre informazioni, vedere [How to Deploy an .NET for Apache Spark Application to Azure HDInsight](../tutorials/hdinsight-deployment.md)), ma i notebook forniscono un'esperienza interattiva e iterativa.

I cluster HDInsight di Azure sono già dotati di notebook di Jupyter, quindi è sufficiente configurare i notebook di Jupyter per eseguire .NET per Apache Spark. Per usare .NET per Apache Spark nei notebook di Jupyter, è necessario un REPL C# per eseguire il codice C# riga per riga e mantenere lo stato di esecuzione quando necessario. [Try .NET](https://github.com/dotnet/try) è stato integrato come repl .NET ufficiale.

Per abilitare .NET per Apache Spark tramite l'esperienza Jupyter Notebooks, è necessario seguire alcuni passaggi manuali tramite [Ambari](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-manage-ambari) e inviare [azioni script](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux) nel cluster HDInsight Spark.

> [!NOTE]
> Questa funzionalità è *sperimentale* e non è supportata dal team di HDInsight Spark.

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a>Prerequisiti

Se non ne è già presente uno, creare un cluster [Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-jupyter-spark-sql-use-portal#create-an-apache-spark-cluster-in-hdinsight) .

1. Visitare il [portale di Azure](https://portal.azure.com) e selezionare **+ Crea una risorsa**.

1. Creare una nuova risorsa cluster di Azure HDInsight. Selezionare **Spark 2,4** e **HDI 4,0** durante la creazione del cluster.

## <a name="install-net-for-apache-spark"></a>Installare .NET per Apache Spark

Nella portale di Azure selezionare il **cluster HDInsight Spark** creato nel passaggio precedente.

### <a name="stop-the-livy-server"></a>Arrestare il server Livio

1. Dal portale selezionare **Panoramica**, quindi selezionare **Ambari Home**. Se richiesto, immettere le credenziali di accesso per il cluster.

   ![Interrompi server Livio](./media/hdinsight-notebook-installation/select-ambari.png)

2. Selezionare **Spark2** nel menu di spostamento a sinistra e selezionare **Livio per il server Spark2**.

   ![Interrompi server Livio](./media/hdinsight-notebook-installation/select-livyserver.png)

3. Seleziona **hn0... host**.

   ![Interrompi server Livio](./media/hdinsight-notebook-installation/select-host.png)

4. Selezionare i puntini di sospensione accanto a **Livio per il server Spark2** e selezionare **Arresta**. Quando richiesto, selezionare **OK** per continuare.

   Arrestare Livio per il server Spark2.
   ![Interrompi server Livio](./media/hdinsight-notebook-installation/stop-server.png)

5. Ripetere i passaggi precedenti per **HN1... host**.

### <a name="submit-an-hdinsight-script-action"></a>Inviare un'azione di script HDInsight

1. `install-interactive-notebook.sh`È uno script che installa .NET per Apache Spark e apporta modifiche a Apache Livio e sparkmagic. Prima di inviare un'azione script a HDInsight, è necessario creare e caricare `install-interactive-notebook.sh` .

   Creare un nuovo file denominato **Install-Interactive-notebook.sh** nel computer locale e incollare il contenuto del [contenuto di install-Interactive-notebook.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/HDI-Spark/Notebooks/install-interactive-notebook.sh).

   Caricare lo script in un [URI](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux#understand-script-actions) accessibile dal cluster HDInsight. Ad esempio, `https://<my storage account>.blob.core.windows.net/<my container>/<some dir>/install-interactive-notebook.sh`

2. Eseguire `install-interactive-notebook.sh` nel cluster usando [azioni script di HDInsight](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).

   Tornare al cluster HDI nell'portale di Azure e selezionare **azioni script** dalle opzioni a sinistra. Si invia un'azione script per distribuire .NET per Apache Spark REPL nel cluster HDInsight Spark. Usare le seguenti impostazioni:

   |Proprietà  |Descrizione  |
   |---------|---------|
   | Tipo di script | Personalizzato |
   | Name | *Installare .NET per Apache Spark esperienza interattiva del notebook* |
   | URI script Bash | URI in cui è stato caricato `install-interactive-notebook.sh`. |
   | Tipo/i di nodo| Head e worker |
   | Parametri | .NET per Apache Spark versione. È possibile controllare [.NET per Apache Spark versioni](https://github.com/dotnet/spark/releases). Ad esempio, se si vuole installare Sparkdotnet versione 0.6.0, sarà `0.6.0` .

   Passare al passaggio successivo quando vengono visualizzati segni di spunta verdi accanto allo stato dell'azione script.

### <a name="start-the-livy-server"></a>Avviare il server Livio

Seguire le istruzioni riportate nella sezione [arrestare il server Livio](#stop-the-livy-server) per **avviare** (anziché **arrestare**) il Livio per il server Spark2 per gli host **hn0** e **HN1**.

### <a name="set-up-spark-default-configurations"></a>Configurare le configurazioni predefinite di Spark

1. Dal portale selezionare **Panoramica**, quindi selezionare **Ambari Home**. Se richiesto, immettere le credenziali di accesso del cluster.

2. Selezionare **Spark2** e **configs**. Quindi selezionare **Custom spark2-defaults**.

   ![Imposta configurazioni](./media/hdinsight-notebook-installation/spark-configs.png)

3. Selezionare **Aggiungi proprietà** per aggiungere le impostazioni predefinite di Spark.

   ![Aggiungi proprietà](./media/hdinsight-notebook-installation/add-property.png)

   Sono disponibili tre singole proprietà. Aggiungerli uno alla volta usando il tipo di proprietà **Text** in modalità di aggiunta di una singola proprietà. Verificare che non siano presenti spazi aggiuntivi prima o dopo una qualsiasi delle chiavi o dei valori.

   * **Proprietà 1**
       * Chiave&ensp;&ensp;`spark.dotnet.shell.command`
       * Valore: `/usr/share/dotnet-tools/dotnet-try,kernel-server,--default-kernel,csharp`

   * **Proprietà 2** Usare la versione di .NET per Apache Spark inclusa nell'azione script precedente.
       * Chiave&ensp;&ensp;`spark.dotnet.packages`
       * Valore: `["nuget: Microsoft.Spark, 0.6.0", "nuget: Microsoft.Spark.Extensions.Delta, 0.6.0"]`

   * **Proprietà 3**
       * Chiave&ensp;&ensp;`spark.dotnet.interpreter`
       * Valore: `try`

   Nell'immagine seguente, ad esempio, viene acquisita l'impostazione per l'aggiunta della proprietà 1:

   ![Imposta configurazioni](./media/hdinsight-notebook-installation/add-sparkconfig.png)

   Dopo aver aggiunto le tre proprietà, selezionare **Salva**. Se viene visualizzata una schermata di avviso relativa alle raccomandazioni di configurazione, selezionare **continua comunque**.

4. Riavviare i componenti interessati.

   Dopo aver aggiunto le nuove proprietà, è necessario riavviare i componenti interessati dalle modifiche. Nella parte superiore selezionare **Riavvia**, quindi **riavviare tutti gli interessati** dall'elenco a discesa.

   ![Imposta configurazioni](./media/hdinsight-notebook-installation/restart-affected.png)

   Quando richiesto, selezionare **Confirm REstart all** per continuare, quindi fare clic su **OK** per terminare.

## <a name="submit-jobs-through-a-jupyter-notebook"></a>Inviare processi tramite un notebook di Jupyter

Dopo aver completato i passaggi precedenti, è ora possibile inviare .NET per i processi di Apache Spark tramite notebook di Jupyter.

1. Creare una nuova .NET per Apache Spark notebook. Avviare un notebook di Jupyter dal cluster HDI nel portale di Azure.

   ![Avvia Jupyter Notebook](./media/hdinsight-notebook-installation/launch-notebook.png)

   Quindi, selezionare **nuovo**  >  **.NET Spark (C#)** per creare un notebook.

   ![Notebook Jupyter](./media/hdinsight-notebook-installation/create-sparkdotnet-notebook.png)

2. Inviare processi con .NET per Apache Spark.

   Usare il frammento di codice seguente per creare un dataframe:

   ```csharp
   var df = spark.Range(0,5);
   df.Show();
   ```

   ![Invia processo Spark](./media/hdinsight-notebook-installation/create-df.png)

   Usare il frammento di codice seguente per registrare una funzione definita dall'utente (UDF) e usare la funzione definita dall'utente con dataframe:

   ```csharp
   var myawesomeudf = Udf<int, string>((id) => $"hello {id}");
   df.Select(myawesomeudf(df["id"])).Show();
   ```

   ![Invia processo Spark](./media/hdinsight-notebook-installation/run-udf.png)

## <a name="next-steps"></a>Passaggi successivi

* [Distribuire un'applicazione .NET per Apache Spark in Azure HDInsight](../tutorials/hdinsight-deployment.md)
* [Documentazione di HDInsight](https://docs.microsoft.com/azure/hdinsight/)

---
title: Distribuire un'applicazione .NET per Apache Spark in Azure HDInsight
description: Informazioni su come distribuire un'applicazione .NET per Apache Spark in HDInsight.
ms.date: 01/23/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 77b57463375c36444532bdd383ec4b3bfe3ab056
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504172"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a>Esercitazione: distribuire un'applicazione .NET per Apache Spark in Azure HDInsight

Questa esercitazione illustra come distribuire .NET per Apache Spark app nel cloud tramite un cluster Azure HDInsight. HDInsight semplifica la creazione e la configurazione di un cluster Spark in Azure poiché i cluster Spark in HDInsight sono compatibili con archiviazione di Azure e Azure Data Lake Storage.

In questa esercitazione si imparerà a:

> [!div class="checklist"]
>
> * Accedere agli account di archiviazione usando Azure Storage Explorer.
> * Creare un cluster HDInsight di Azure.
> * Pubblicare .NET per Apache Spark app.
> * Creare ed eseguire un'azione di script HDInsight.
> * Eseguire un'app .NET per Apache Spark in un cluster HDInsight.

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, eseguire le attività seguenti:

* Se non si ha una sottoscrizione di Azure, creare un [account gratuito](https://azure.microsoft.com/free/).
* Accedere al [portale di Azure](https://portal.azure.com/).
* Installare Azure Storage Explorer nel computer [Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409), [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409)o [MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409) .
* Completare l'esercitazione [su .NET per Apache Spark-introduzione in 10 minuti](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) .

## <a name="access-your-storage-accounts"></a>Accedere agli account di archiviazione

1. Aprire Azure Storage Explorer.

2. Selezionare **Aggiungi account** nel menu a sinistra e accedere al proprio account Azure.

    ![Accedere all'account Azure da Storage Explorer](./media/hdinsight-deployment/signin-azure-storage-explorer.png)

   Dopo aver eseguito l'accesso, verranno visualizzati tutti gli account di archiviazione disponibili e tutte le risorse caricate negli account di archiviazione.

## <a name="create-an-hdinsight-cluster"></a>Creazione di un cluster HDInsight

> [!IMPORTANT]
> La fatturazione per i cluster HDInsight viene rivalutata al minuto, anche se non vengono usate. Assicurarsi di eliminare il cluster dopo aver finito di usarlo. Per ulteriori informazioni, vedere la sezione [Pulisci risorse in](#clean-up-resources) questa esercitazione.

1. Visitare il [portale di Azure](https://portal.azure.com).

2. Selezionare **+ Crea una risorsa**. Selezionare quindi **HDInsight** dalla categoria **Analytics** .

    ![Creare una risorsa HDInsight da portale di Azure](./media/hdinsight-deployment/create-hdinsight-resource.png)

3. In **Informazioni di base** specificare i valori seguenti:

    |Proprietà  |Descrizione  |
    |---------|---------|
    |Sottoscrizione  | Dall'elenco a discesa scegliere una delle sottoscrizioni di Azure attive. |
    |Gruppo di risorse | Specificare se si vuole creare un nuovo gruppo di risorse o usarne uno esistente. Un gruppo di risorse è un contenitore con risorse correlate per una soluzione Azure. |
    |Nome del cluster | Assegnare un nome al cluster HDInsight Spark.|
    |Location   | Selezionare una posizione per il gruppo di risorse. Il modello usa questa posizione per la creazione del cluster e per l'archiviazione del cluster predefinita. |
    |Tipo di cluster| Selezionare **Spark** come tipo di cluster.|
    |Versione del cluster|Questo campo verrà automaticamente popolato con la versione predefinita dopo che è stato selezionato il tipo di cluster. Selezionare una versione 2,3 o 2,4 di Spark.|
    |Nome utente dell'account di accesso del cluster| Immettere il nome utente dell'account di accesso del cluster.  Il nome predefinito è *admin*. |
    |Password di accesso al cluster| Immettere una password di accesso. |
    |Nome utente Secure Shell (SSH)| Immettere il nome utente SSH. Per impostazione predefinita, questo account condivide la stessa password dell'account *Nome utente dell'account di accesso del cluster*. |

4. Selezionare **Avanti: archiviazione > >** per passare alla pagina **archiviazione** . In **Archiviazione** specificare i valori seguenti:

    |Proprietà  |Descrizione  |
    |---------|---------|
    |Tipo di archiviazione primario|Usare il valore predefinito **Archiviazione di Azure**.|
    |Metodo di selezione|Usare il valore predefinito **Selezionare dall'elenco**.|
    |Account di archiviazione primario|Scegliere la sottoscrizione e uno degli account di archiviazione attivi all'interno di tale sottoscrizione.|
    |Contenitore|Questo contenitore è il contenitore BLOB specifico nell'account di archiviazione in cui il cluster Cerca i file per l'esecuzione dell'app nel cloud. È possibile assegnargli qualsiasi nome disponibile.|

5. In **Rivedi e crea** selezionare **Crea**. La creazione del cluster richiede circa 20 minuti. Il cluster deve essere creato prima di continuare con il passaggio successivo.

## <a name="publish-your-app"></a>Pubblicare l'app

Successivamente, pubblicare il *mySparkApp* creato in [.NET per Apache Spark-introduzione in 10 minuti](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) , che consente al cluster Spark di accedere a tutti i file necessari per eseguire l'app.

1. Eseguire i comandi seguenti per pubblicare il *mySparkApp*:

   **In Windows:**

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

   **In Linux:**

   ```bash
   cd mySparkApp
   foo@bar:~/path/to/app$ dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. Eseguire le attività seguenti per comprimere i file dell'app pubblicata in modo che sia possibile caricarli facilmente nel cluster HDInsight.

   **In Windows:**

   Passare a *mySparkApp/bin/Release/netcoreapp 3.0/Ubuntu. 16.04-x64*. Quindi, fare clic con il pulsante destro del mouse su cartella di **pubblicazione** e selezionare **Invia a > cartella compressa**. Assegnare alla nuova cartella il nome **Publish. zip**.

   **In Linux eseguire il comando seguente:**

   ```bash
   zip -r publish.zip
   ```

## <a name="upload-files-to-azure"></a>Caricare file in Azure

Usare quindi il Azure Storage Explorer per caricare i cinque file seguenti nel contenitore BLOB scelto per l'archiviazione del cluster:

* Microsoft. Spark. Worker
* install-worker.sh
* Publish. zip
* Microsoft-Spark-2.3. x-0.3.0. jar
* input. txt.

1. Aprire Azure Storage Explorer e passare all'account di archiviazione dal menu a sinistra. Eseguire il drill-down nel contenitore BLOB per il cluster in **contenitori BLOB** nell'account di archiviazione.

2. *Microsoft. Spark. Worker* consente di Apache Spark eseguire l'app, ad esempio qualsiasi funzione definita dall'utente (UDF) che è stata scritta. Scaricare [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases/download/v0.3.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.3.0.tar.gz). Selezionare quindi **carica** in Azure Storage Explorer per caricare il ruolo di lavoro.

   ![Caricare file in Azure Storage Explorer](./media/hdinsight-deployment/upload-files-to-storage.png)

3. *Install-Worker.sh* è uno script che consente di copiare .net per Apache Spark file dipendenti nei nodi del cluster.

   Creare un nuovo file denominato **Install-Worker.sh** nel computer locale e incollare il [contenuto di install-Worker.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) disponibile in GitHub. Quindi, caricare *Install-Worker.sh* nel contenitore BLOB.

4. Il cluster richiede il file Publish. zip che contiene i file pubblicati dell'app. Passare alla cartella pubblicata, **mySparkApp/bin/Release/netcoreapp 3.0/Ubuntu. 16.04-x64**e individuare **Publish. zip**. Caricare quindi *Publish. zip* nel contenitore BLOB.

5. Il cluster necessita del codice dell'applicazione che è stato incluso in un file jar. Passare alla cartella pubblicata, **mySparkApp/bin/Release/netcoreapp 3.0/Ubuntu. 16.04-x64**e individuare **Microsoft-Spark-2.3. x-0.3.0. jar**. Caricare quindi il file jar nel contenitore BLOB.

   Potrebbero essere presenti più file con estensione jar (per le versioni 2.3. x e 2.4. x di Spark). È necessario scegliere il file con estensione jar che corrisponde alla versione di Spark scelta durante la creazione del cluster. Ad esempio, scegliere *Microsoft-Spark-2.3. x-0.3.0. jar* se si sceglie Spark 2.3.2 durante la creazione del cluster.

6. Il cluster necessita dell'input per l'app. Passare alla directory **mySparkApp** e individuare **input. txt**. Caricare il file di input nella directory **User/sshuser** nel contenitore BLOB. Ci si connette al cluster tramite SSH e questa cartella è la posizione in cui il cluster cerca l'input. Il file *input. txt* è l'unico file caricato in una directory specifica.

## <a name="run-the-hdinsight-script-action"></a>Eseguire l'azione di script HDInsight

Quando il cluster è in esecuzione e i file sono stati caricati in Azure, si esegue lo script **Install-Worker.sh** nel cluster.

1. Passare al cluster HDInsight Spark in portale di Azure, quindi selezionare **azioni script**.

2. Selezionare **+ Invia nuovo** e specificare i valori seguenti:

   |Proprietà  |Descrizione  |
   |---------|---------|
   | Tipo di script |Personalizzato|
   | Name | Installare il ruolo di lavoro|
   | URI script Bash |https://mystorageaccount.blob.core.windows.net/mycontainer/install-worker.sh </br> Per confermare questo URI, fare clic con il pulsante destro del mouse su install-worker.sh in Azure Storage Explorer e scegliere Proprietà. |
   | Tipo/i di nodo| Worker|
   | Parametri | azure </br> wasbs://mycontainer@myStorageAccount.blob.core.windows.net/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz </br> /usr/local/bin

3. Selezionare **Crea** per inviare lo script.

## <a name="run-your-app"></a>Eseguire l'app

1. Passare al cluster HDInsight Spark in portale di Azure, quindi selezionare **SSH + login cluster**.

2. Copiare le informazioni di accesso SSH e incollare l'account di accesso in un terminale. Accedere al cluster usando la password impostata durante la creazione del cluster. Verranno visualizzati messaggi di benvenuto in Ubuntu e Spark.

3. Usare il comando **Spark-Submit** per eseguire l'app nel cluster HDInsight. Ricordarsi di **sostituire e** **mystorageaccount** nello script di esempio con i nomi effettivi del contenitore BLOB e dell'account di archiviazione.

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

   Quando l'app viene eseguita, viene visualizzata la stessa tabella di conteggio delle parole dall'esecuzione locale della Guida introduttiva scritta nella console. Congratulazioni, è stata eseguita la prima applicazione .NET per Apache Spark nel cloud.

## <a name="clean-up-resources"></a>Pulire le risorse

HDInsight Salva i dati in archiviazione di Azure, in modo da poter eliminare in modo sicuro un cluster quando non è in uso. Vengono addebitati i costi anche per i cluster HDInsight che non sono in uso. Poiché i costi per il cluster sono decisamente superiori a quelli per l'archiviazione, economicamente ha senso eliminare i cluster quando non vengono usati.

È anche possibile selezionare il nome del gruppo di risorse per aprire la pagina del gruppo di risorse e quindi selezionare **Elimina gruppo di risorse**. Eliminando il gruppo di risorse, si elimina sia il cluster HDInsight Spark che l'account di archiviazione predefinito.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata distribuita un'applicazione .NET per Apache Spark in Azure HDInsight. Per altre informazioni su HDInsight, continuare con la documentazione di Azure HDInsight.

> [!div class="nextstepaction"]
> [Documentazione di Azure HDInsight](https://docs.microsoft.com/azure/hdinsight/)

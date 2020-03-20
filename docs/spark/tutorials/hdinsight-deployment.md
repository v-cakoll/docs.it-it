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
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a>Esercitazione: Distribuire un'applicazione .NET per Apache Spark in Azure HDInsightTutorial: Deploy a .NET for Apache Spark application to Azure HDInsight

Questa esercitazione illustra come distribuire l'app .NET per Apache Spark nel cloud tramite un cluster Azure HDInsight.This tutorial teaches you how to deploy your .NET for Apache Spark app to the cloud through an Azure HDInsight cluster. HDInsight makes it easier to create and configure a Spark cluster in Azure since Spark clusters in HDInsight are compatible with Azure Storage and Azure Data Lake Storage.

In questa esercitazione verranno illustrate le procedure per:

> [!div class="checklist"]
>
> * Accedere agli account di archiviazione usando Azure Storage Explorer.Access your storage accounts using Azure Storage Explorer.
> * Creare un cluster di Azure HDInsight.Create an Azure HDInsight cluster.
> * Pubblica l'app .NET per Apache Spark.
> * Creare ed eseguire un'azione di script HDInsight.Create and run an HDInsight script action.
> * Eseguire un'app .NET per Apache Spark in un cluster HDInsight.Run a .NET for Apache Spark app on an HDInsight cluster.

## <a name="prerequisites"></a>Prerequisites

Prima di iniziare, eseguire le attività seguenti:

* Se non si dispone di una sottoscrizione di Azure, creare un [account gratuito.](https://azure.microsoft.com/free/)
* Accedere al [portale](https://portal.azure.com/)di Azure .
* Installare Azure Storage Explorer nel computer [Windows,](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409) [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409)o [MacOS.](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409)
* Completare [.NET per Apache Spark - Introduzione](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) nell'esercitazione di 10 minuti.

## <a name="access-your-storage-accounts"></a>Accedere agli account di archiviazioneAccess your storage accounts

1. Aprire Azure Storage Explorer.

2. Selezionare Aggiungi account nel menu a sinistra e accedere all'account Azure.Select **Add Account** on the left menu, and sign in to your Azure account.

    ![Accedere all'account di Azure da Esplora risorse](./media/hdinsight-deployment/signin-azure-storage-explorer.png)

   Dopo l'accesso, verranno visualizzati tutti gli account di archiviazione di cui si dispone e tutte le risorse caricate negli account di archiviazione.

## <a name="create-an-hdinsight-cluster"></a>Creazione di un cluster HDInsight

> [!IMPORTANT]
> La fatturazione per i cluster HDInsight viene rivalutata proporzionalmente al minuto, anche se non vengono usati. Assicurarsi di eliminare il cluster dopo aver finito di usarlo. Per altre informazioni, vedere la sezione [Pulire le risorse](#clean-up-resources) di questa esercitazione.

1. Visitare il [portale di Azure](https://portal.azure.com).

2. Selezionare **: Crea una risorsa**. Selezionare **quindi HDInsight** dalla categoria Analisi.Then, select HDInsight from the **Analytics** category.

    ![Creare una risorsa HDInsight dal portale di AzureCreate HDInsight resource from Azure portal](./media/hdinsight-deployment/create-hdinsight-resource.png)

3. In **Informazioni di base** specificare i valori seguenti:

    |Proprietà  |Descrizione  |
    |---------|---------|
    |Subscription  | Nell'elenco a discesa scegliere una delle sottoscrizioni di Azure attive. |
    |Resource group | Specificare se si vuole creare un nuovo gruppo di risorse o usarne uno esistente. Un gruppo di risorse è un contenitore con risorse correlate per una soluzione Azure. |
    |Nome cluster | Assegnare un nome al cluster HDInsight Spark.|
    |Location   | Selezionare una posizione per il gruppo di risorse. Il modello usa questa posizione per la creazione del cluster e per l'archiviazione del cluster predefinita. |
    |Tipo di cluster| Selezionare **Spark** come tipo di cluster.|
    |Versione del cluster|Questo campo verrà compilato automaticamente con la versione predefinita una volta selezionato il tipo di cluster. Selezionare una versione 2.3 o 2.4 di Spark.|
    |Nome utente dell'account di accesso del cluster| Immettere il nome utente dell'account di accesso del cluster.  Il nome predefinito è *admin*. |
    |Password di accesso al cluster| Immettere una password di accesso. |
    |Nome utente Secure Shell (SSH)| Immettere il nome utente SSH. Per impostazione predefinita, questo account condivide la stessa password dell'account *Nome utente dell'account di accesso del cluster*. |

4. Selezionare Avanti: Archiviazione >>per continuare con la pagina **Archiviazione.Select** **Next: Storage >>** to continue to the Storage page. In **Archiviazione** specificare i valori seguenti:

    |Proprietà  |Descrizione  |
    |---------|---------|
    |Tipo di archiviazione primario|Usare il valore predefinito **Archiviazione di Azure**.|
    |Metodo di selezione|Usare il valore predefinito **Selezionare dall'elenco**.|
    |Account di archiviazione primario|Scegliere la sottoscrizione e uno degli account di archiviazione attivi all'interno di tale sottoscrizione.|
    |Contenitore|Questo contenitore è il contenitore BLOB specifico nell'account di archiviazione in cui il cluster cerca i file per eseguire l'app nel cloud. È possibile assegnare qualsiasi nome disponibile.|

5. In **Rivedi e crea** selezionare **Crea**. La creazione del cluster richiede circa 20 minuti. Il cluster deve essere creato prima di poter continuare con il passaggio successivo.

## <a name="publish-your-app"></a>Pubblicare l'app

Successivamente, si pubblica *mySparkApp* creata in [.NET per Apache Spark - Introduzione](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) nell'esercitazione di 10 minuti, che consente al cluster Spark di accedere a tutti i file necessari per eseguire l'app.

1. Eseguire i seguenti comandi per pubblicare *mySparkApp*:

   **In Windows:**

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

   **Su Linux:**

   ```bash
   cd mySparkApp
   foo@bar:~/path/to/app$ dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. Eseguire le attività seguenti per comprimere i file dell'app pubblicati in modo da poterli caricare facilmente nel cluster HDInsight.Do the following tasks to zip your published app files so that you can easily upload them to your HDInsight cluster.

   **In Windows:**

   Passare a *mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64*. Quindi, fare clic con il pulsante destro del mouse su **Pubblica** cartella e selezionare **Invia a > cartella compressa (compressa).** Assegnare alla nuova cartella il nome **publish.zip**.

   **In Linux, eseguire il comando seguente:**

   ```bash
   zip -r publish.zip
   ```

## <a name="upload-files-to-azure"></a>Caricare file in AzureUpload files to Azure

Successivamente, si usa Azure Storage Explorer per caricare i cinque file seguenti nel contenitore BLOB scelto per l'archiviazione del cluster:Next, you use the Azure Storage Explorer to upload the following five files to the blob container you chose for your cluster's storage:

* Microsoft.Spark.Worker
* install-worker.sh
* publish.zip
* microsoft-spark-2.3.x-0.3.0.jar
* input.txt.

1. Aprire Esplora archivi di Azure e passare all'account di archiviazione dal menu a sinistra. Eseguire il drill-down nel contenitore BLOB per il cluster in **Contenitori BLOB** nell'account di archiviazione.

2. *Microsoft.Spark.Worker* consente a Apache Spark di eseguire l'app, ad esempio qualsiasi funzione definita dall'utente (UDF) che è stata scritta. Scaricare [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.3.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.3.0.tar.gz). Selezionare quindi **Carica** in Azure Storage Explorer per caricare il worker.

   ![Caricare file in Azure Storage Explorer](./media/hdinsight-deployment/upload-files-to-storage.png)

3. Il *install-worker.sh* è uno script che consente di copiare .NET per i file dipendenti da Apache Spark nei nodi del cluster.

   Creare un nuovo file denominato **install-worker.sh** computer locale e incollare il contenuto del install-worker.sh disponibile in GitHub.Create a new file named install-worker.sh your local computer, and paste [the install-worker.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) located on GitHub. Caricare quindi *install-worker.sh* nel contenitore BLOB.

4. Il cluster richiede il file publish.zip che contiene i file pubblicati dell'app. Passare alla cartella pubblicata, **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, e individuare **publish.zip**. Quindi caricare *publish.zip* nel contenitore BLOB.

5. Il cluster necessita del codice dell'applicazione incluso in un file jar. Passare alla cartella pubblicata, **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, e individuare **microsoft-spark-2.3.x-0.3.0.jar**. Quindi, caricare il file jar nel contenitore BLOB.

   Potrebbero essere presenti più file JAR (per le versioni 2.3.x e 2.4.x di Spark). È necessario scegliere il file JAR che corrisponde alla versione di Spark scelta durante la creazione del cluster. Ad esempio, scegliere *microsoft-spark-2.3.x-0.3.0.jar* se si sceglie Spark 2.3.2 durante la creazione del cluster.

6. Il cluster richiede l'input per l'app. Passare alla directory **mySparkApp** e individuare **input.txt**. Caricare il file di input nella directory **user/sshuser** nel contenitore BLOB. Ci si connetterà al cluster tramite ssh e questa cartella è dove il cluster cerca il suo input. Il file *input.txt* è l'unico file caricato in una directory specifica.

## <a name="run-the-hdinsight-script-action"></a>Eseguire l'azione script HDInsightRun the HDInsight script action

Dopo che il cluster è in esecuzione e aver caricato i file in Azure, eseguire lo script **di install-worker.sh** nel cluster.

1. Passare al cluster HDInsight Spark nel portale di Azure e quindi selezionare **Azioni script**.

2. Selezionare **Invia nuovo** e specificare i seguenti valori:

   |Proprietà  |Descrizione  |
   |---------|---------|
   | Tipo di script |Personalizzato|
   | Nome | Installa lavoratore|
   | URI script Bash |https://mystorageaccount.blob.core.windows.net/mycontainer/install-worker.sh </br> Per confermare questo URI, fare clic con il pulsante destro del mouse su install-worker.sh in Esplora archivi di Azure e selezionare Proprietà.To confirm this URI, right-click on install-worker.sh in Azure Storage Explorer and select Properties. |
   | Tipo/i di nodo| Worker|
   | Parametri | azure </br> wasbs://mycontainer@myStorageAccount.blob.core.windows.net/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz </br> /usr/locale/bin

3. Selezionare **Crea** per inviare lo script.

## <a name="run-your-app"></a>Eseguire l'app

1. Passare al cluster HDInsight Spark nel portale di Azure e quindi selezionare **SSH e accesso al cluster.**

2. Copiare le informazioni di accesso ssh e incollare il login in un terminale. Accedere al cluster utilizzando la password impostata durante la creazione del cluster. Dovresti vedere messaggi che ti accolgano a Ubuntu e Spark.

3. Usare il comando spark-submit per eseguire l'app nel cluster HDInsight.Use the **spark-submit** command to run your app on your HDInsight cluster. Ricordarsi di sostituire **mycontainer** e **mystorageaccount** nello script di esempio con i nomi effettivi del contenitore BLOB e dell'account di archiviazione.

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

   Quando l'app viene eseguita, viene visualizzata la stessa tabella di conteggio delle parole dell'esecuzione locale introduttiva scritta nella console. Congratulazioni, hai eseguito la tua prima applicazione .NET per Apache Spark nel cloud!

## <a name="clean-up-resources"></a>Pulire le risorse

HDInsight salva i dati in Archiviazione di Azure, in modo da poter eliminare in modo sicuro un cluster quando non è in uso. Vengono addebitati i costi anche per i cluster HDInsight che non sono in uso. Poiché i costi per il cluster sono decisamente superiori a quelli per l'archiviazione, economicamente ha senso eliminare i cluster quando non vengono usati.

È anche possibile selezionare il nome del gruppo di risorse per aprire la pagina del gruppo di risorse e quindi selezionare **Elimina gruppo di risorse**. Eliminando il gruppo di risorse, si elimina sia il cluster HDInsight Spark che l'account di archiviazione predefinito.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata distribuita un'applicazione .NET per Apache Spark in Azure HDInsight. Per altre informazioni su HDInsight, continuare con la documentazione di Azure HDInsight.

> [!div class="nextstepaction"]
> [Azure HDInsight Documentation](https://docs.microsoft.com/azure/hdinsight/)

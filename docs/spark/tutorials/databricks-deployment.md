---
title: Distribuire un'applicazione .NET per Apache Spark in Databricks
description: Informazioni su come distribuire un'applicazione .NET per Apache Spark in Databricks.
ms.date: 01/23/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c5308530831fa288bf637849c1342f51769c3ad4
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503957"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-databricks"></a>Esercitazione: distribuire un'applicazione .NET per Apache Spark a databricks

Questa esercitazione illustra come distribuire un'app nel cloud tramite Azure Databricks, una piattaforma di analisi basata su Apache Spark con installazione con un clic, flussi di lavoro semplificati e un'area di lavoro interattiva che consente la collaborazione.

In questa esercitazione si imparerà a:

> [!div class="checklist"]
>
> - Creare un'area di lavoro di Azure Databricks.
> - Pubblicare .NET per Apache Spark app.
> - Creare un processo Spark e un cluster Spark.
> - Eseguire l'app nel cluster Spark.

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, eseguire le attività seguenti:

* Se non si ha un account Azure, creare un [account gratuito](https://azure.microsoft.com/free/).
* Accedere al [portale di Azure](https://portal.azure.com/).
* Completare l'esercitazione [su .NET per Apache Spark-introduzione in 10 minuti](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) .

## <a name="create-an-azure-databricks-workspace"></a>Creare un'area di lavoro di Azure Databricks

> [!Note]
> Questa esercitazione non può essere eseguita usando una **sottoscrizione di valutazione gratuita di Azure**.
> Se l'utente ha un account gratuito, andare al proprio profilo e modificare la sottoscrizione a **con pagamento in base al consumo**. Per altre informazioni, vedere [Account gratuito di Azure](https://azure.microsoft.com/free/). Quindi [rimuovere il limite di spesa](https://docs.microsoft.com/azure/billing/billing-spending-limit#why-you-might-want-to-remove-the-spending-limit) e [richiedere un aumento della quota](https://docs.microsoft.com/azure/azure-supportability/resource-manager-core-quotas-request) per le vCPU nell'area dell'utente. Quando si crea l'area di lavoro Azure Databricks, è possibile selezionare il piano tariffario **Versione di valutazione (Premium - Unità Databricks gratuite per 14 giorni)** per concedere l'accesso gratuito Premium per 14 giorni dell'area di lavoro alle Unità Databricks di Azure.

In questa sezione viene creata un'area di lavoro di Azure Databricks usando il portale di Azure.

1. Nel portale di Azure selezionare **Crea una risorsa** > **Analisi** > **Azure Databricks**.

   ![Creare una risorsa Azure Databricks in portale di Azure](./media/databricks-deployment/create-databricks-resource.png)

2. Nella pagina **Servizio Azure Databricks** specificare i valori per creare un'area di lavoro di Databricks.

    |Proprietà  |Descrizione  |
    |---------|---------|
    |**Nome area di lavoro**     | Specificare un nome per l'area di lavoro di Databricks.        |
    |**Sottoscrizione**     | Selezionare la sottoscrizione di Azure nell'elenco a discesa.        |
    |**Gruppo di risorse**     | Specificare se si vuole creare un nuovo gruppo di risorse o usarne uno esistente. Un gruppo di risorse è un contenitore con risorse correlate per una soluzione Azure. Per altre informazioni, vedere [Panoramica di Gestione risorse di Microsoft Azure](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview). |
    |**Posizione**     | Selezionare l'area preferita. Per informazioni sulle aree disponibili, vedere [servizi di Azure disponibili in base all'area](https://azure.microsoft.com/regions/services/).        |
    |**Piano tariffario**     |  Scegliere tra **Standard**, **Premium** e **Versione di valutazione**. Per altre informazioni su questi piani tariffari, vedere la [pagina dei prezzi di Databricks](https://azure.microsoft.com/pricing/details/databricks/).       |
    |**Rete virtuale**     |   No       |

3. Selezionare **Crea**. La creazione dell'area di lavoro richiede alcuni minuti, durante i quali è possibile visualizzare lo stato della distribuzione in **Notifiche**.

## <a name="install-azure-databricks-tools"></a>Installare gli strumenti di Azure Databricks

È possibile usare l'interfaccia della riga di comando di **databricks** per connettersi a Azure Databricks cluster e caricarvi file dal computer locale. I cluster databricks accedono ai file tramite DBFS (file System databricks).

1. L'interfaccia della riga di comando di databricks richiede Python 3,6 o versione successiva. Se Python è già installato, è possibile ignorare questo passaggio.

   **Per Windows:**

   [Scaricare Python per Windows](https://www.python.org/ftp/python/3.7.4/python-3.7.4.exe)

   **Per Linux:** Python è preinstallato nella maggior parte delle distribuzioni di Linux. Eseguire il comando seguente per visualizzare la versione installata:

   ```bash
   python3 --version
   ```

2. Usare PIP per installare l'interfaccia della riga di comando di databricks. Python 3,4 e versioni successive includono PIP per impostazione predefinita. Usare PIP3 per Python 3. Eseguire il comando seguente:

   ```bash
   pip3 install databricks-cli
   ```

3. Dopo aver installato l'interfaccia della riga di comando di databricks, aprire un nuovo prompt dei comandi ed eseguire il comando `databricks`. Se viene visualizzato un **errore di comando interno o esterno**, verificare che sia stato aperto un nuovo prompt dei comandi.

## <a name="set-up-azure-databricks"></a>Configurare Azure Databricks

Ora che è stata installata l'interfaccia della riga di comando di databricks, è necessario configurare i dettagli di autenticazione.

1. Eseguire il comando dell'interfaccia della riga di comando di databricks `databricks configure --token`.

2. Dopo aver eseguito il comando configure, viene richiesto di immettere un host. L'URL dell'host usa il formato **https://< \Location >. azuredatabricks. NET**. Se, ad esempio, è stato selezionato **eastus2** durante la creazione del servizio Azure Databricks, l'host verrebbe **https://eastus2.azuredatabricks.net** .

3. Dopo l'immissione dell'host, viene richiesto di immettere un token. Nella portale di Azure selezionare **Avvia area di lavoro** per avviare l'area di lavoro Azure Databricks.

   ![Avvia Azure Databricks area di lavoro](./media/databricks-deployment/launch-databricks-workspace.png)

4. Nella home page dell'area di lavoro selezionare **impostazioni utente**.

   ![Impostazioni utente nell'area di lavoro Azure Databricks](./media/databricks-deployment/databricks-user-settings.png)

5. Nella pagina impostazioni utente è possibile generare un nuovo token. Copiare il token generato e incollarlo di nuovo nel prompt dei comandi.

   ![Genera un nuovo token di accesso nell'area di lavoro Azure Databricks](./media/databricks-deployment/generate-token.png)

A questo punto dovrebbe essere possibile accedere a tutti i cluster di Azure Databricks creati e caricare i file in DBFS.

## <a name="download-worker-dependencies"></a>Scarica dipendenze di lavoro

1. Microsoft. Spark. Worker consente di Apache Spark eseguire l'app, ad esempio qualsiasi funzione definita dall'utente (UDF) che è stata scritta. Scaricare [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz).

2. *Install-Worker.sh* è uno script che consente di copiare .net per Apache Spark file dipendenti nei nodi del cluster.

   Creare un nuovo file denominato **Install-Worker.sh** nel computer locale e incollare il contenuto di [Install-Worker.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) disponibile in GitHub.

3. *DB-init.sh* è uno script che consente di installare le dipendenze nel cluster Spark di databricks.

   Creare un nuovo file denominato **DB-init.sh** nel computer locale e incollare il contenuto di [DB-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) disponibile in GitHub.

   Nel file appena creato impostare la variabile `DOTNET_SPARK_RELEASE` su `https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz`. Lasciare invariato il resto del file *DB-init.sh* .

> [!Note]
> Se si usa Windows, verificare che le terminazioni di riga negli script *Install-Worker.sh* e *DB-init.sh* siano di tipo UNIX (LF). È possibile modificare le terminazioni riga tramite editor di testo come blocco note + + e Atom.

## <a name="publish-your-app"></a>Pubblicare l'app

Successivamente, pubblicare il *mySparkApp* creato in [.NET per Apache Spark-introduzione in 10 minuti](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) esercitazione per assicurarsi che il cluster Spark possa accedere a tutti i file necessari per eseguire l'app.

1. Eseguire i comandi seguenti per pubblicare il *mySparkApp*:

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. Eseguire le attività seguenti per comprimere i file dell'app pubblicata in modo che sia possibile caricarli facilmente nel cluster di databricks Spark.

   **In Windows:**

   Passare a mySparkApp/bin/Release/netcoreapp 3.0/Ubuntu. 16.04-x64. Quindi, fare clic con il pulsante destro del mouse su cartella di **pubblicazione** e selezionare **Invia a > cartella compressa**. Assegnare alla nuova cartella il nome **Publish. zip**.

   **In Linux eseguire il comando seguente:**

   ```bash
   zip -r publish.zip .
   ```

## <a name="upload-files"></a>Caricare file

In questa sezione vengono caricati diversi file in DBFS in modo che il cluster disponga di tutti gli elementi necessari per eseguire l'app nel cloud. Ogni volta che si carica un file in DBFS, assicurarsi di trovarsi nella directory in cui si trova il file nel computer.

1. Eseguire i comandi seguenti per caricare *DB-init.sh*, *Install-Worker.sh*e *Microsoft. Spark. Worker* in DBFS:

   ```console
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   databricks fs cp Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz dbfs:/spark-dotnet/   Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz
   ```

2. Eseguire i comandi seguenti per caricare i file rimanenti che il cluster dovrà eseguire l'app: la cartella di pubblicazione compresso, *input. txt*e *Microsoft-Spark-2.4. x-0.3.0. jar*.

   ```console
   cd mySparkApp
   databricks fs cp input.txt dbfs:/input.txt

   cd mySparkApp\bin\Release\netcoreapp3.0\ubuntu.16.04-x64 directory
   databricks fs cp mySparkApp.zip dbfs:/spark-dotnet/publish.zip
   databricks fs cp microsoft-spark-2.4.x-0.6.0.jar dbfs:/spark-dotnet/microsoft-spark-2.4.x-0.6.0.jar
   ```

## <a name="create-a-job"></a>Creare un processo

L'app viene eseguita in Azure Databricks tramite un processo che esegue **Spark-Submit**, che è il comando usato per eseguire .net per Apache Spark processi.

1. Nell'area di lavoro Azure Databricks selezionare l'icona **processi** , quindi **+ Crea processo**.

   ![Creare un processo di Azure Databricks](./media/databricks-deployment/create-job.png)

2. Scegliere un titolo per il processo e quindi selezionare **Configura Spark-Submit**.

   ![Configurare Spark-Submit per un processo databricks](./media/databricks-deployment/configure-spark-submit.png)

3. Incollare i parametri seguenti nella configurazione del processo. Selezionare quindi **conferma**.

   ```
   ["--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/spark-dotnet/microsoft-spark-2.4.x-0.6.0.jar","/dbfs/spark-dotnet/publish.zip","mySparkApp"]
   ```

## <a name="create-a-cluster"></a>Creare un cluster

1. Passare al processo e selezionare **modifica** per configurare il cluster del processo.

2. Impostare il cluster su **Spark 2.4.1**. Selezionare quindi **Opzioni avanzate** > **script init**. Impostare percorso script init come `dbfs:/spark-dotnet/db-init.sh`.

   ![Configurare il cluster Spark in Azure Databricks](./media/databricks-deployment/cluster-config.png)

3. Selezionare **conferma** per confermare le impostazioni del cluster.

## <a name="run-your-app"></a>Eseguire l'app

1. Passare al processo e selezionare **Esegui adesso** per eseguire il processo nel cluster Spark appena configurato.

2. La creazione del cluster del processo richiede alcuni minuti. Una volta creato, il processo verrà inviato ed è possibile visualizzare l'output.

3. Selezionare **cluster** dal menu a sinistra e quindi il nome e l'esecuzione del processo.

4. Selezionare **log driver** per visualizzare l'output del processo. Al termine dell'esecuzione dell'app, nella console di output standard viene visualizzata la stessa tabella di conteggio delle parole dell'esecuzione locale di Getting Started.

   ![Tabella di output del processo Azure Databricks](./media/databricks-deployment/table-output.png)

   Congratulazioni, è stata eseguita la prima applicazione .NET per Apache Spark nel cloud.

## <a name="clean-up-resources"></a>Pulire le risorse

Se l'area di lavoro databricks non è più necessaria, è possibile eliminare la risorsa Azure Databricks nel portale di Azure. È anche possibile selezionare il nome del gruppo di risorse per aprire la pagina del gruppo di risorse e quindi selezionare **Elimina gruppo di risorse**.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata distribuita un'applicazione .NET per Apache Spark in Databricks. Per altre informazioni su Databricks, passare alla documentazione di Azure Databricks.

> [!div class="nextstepaction"]
> [Documentazione di Azure Databricks](https://docs.microsoft.com/azure/azure-databricks/)

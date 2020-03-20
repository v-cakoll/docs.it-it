---
title: Distribuire un'applicazione .NET per Apache Spark in Databricks
description: Informazioni su come distribuire un'applicazione .NET per Apache Spark in Databricks.
ms.date: 01/23/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c5308530831fa288bf637849c1342f51769c3ad4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "77503957"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-databricks"></a>Esercitazione: Distribuire un'applicazione .NET per Apache Spark in DatabricksTutorial: Deploy a .NET for Apache Spark application to Databricks

Questa esercitazione illustra come distribuire l'app nel cloud tramite Azure Databricks, una piattaforma di analisi basata su Apache Spark con configurazione con un clic, flussi di lavoro semplificati e area di lavoro interattiva che consente la collaborazione.

In questa esercitazione verranno illustrate le procedure per:

> [!div class="checklist"]
>
> - Creare un'area di lavoro di Azure Databricks.
> - Pubblica l'app .NET per Apache Spark.
> - Creare un processo Spark e un cluster Spark.Create a Spark job and Spark cluster.
> - Eseguire l'app nel cluster Spark.

## <a name="prerequisites"></a>Prerequisites

Prima di iniziare, eseguire le attività seguenti:

* Se non si dispone di un account Azure, creare un [account gratuito.](https://azure.microsoft.com/free/)
* Accedere al [portale](https://portal.azure.com/)di Azure .
* Completare [.NET per Apache Spark - Introduzione](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) nell'esercitazione di 10 minuti.

## <a name="create-an-azure-databricks-workspace"></a>Creare un'area di lavoro di Azure Databricks

> [!Note]
> Questa esercitazione non può essere eseguita usando una **sottoscrizione di valutazione gratuita di Azure**.
> Se l'utente ha un account gratuito, andare al proprio profilo e modificare la sottoscrizione a **con pagamento in base al consumo**. Per altre informazioni, vedere [Account gratuito di Azure](https://azure.microsoft.com/free/). Quindi [rimuovere il limite di spesa](https://docs.microsoft.com/azure/billing/billing-spending-limit#why-you-might-want-to-remove-the-spending-limit) e [richiedere un aumento della quota](https://docs.microsoft.com/azure/azure-supportability/resource-manager-core-quotas-request) per le vCPU nell'area dell'utente. Quando si crea l'area di lavoro Azure Databricks, è possibile selezionare il piano tariffario **Versione di valutazione (Premium - Unità Databricks gratuite per 14 giorni)** per concedere l'accesso gratuito Premium per 14 giorni dell'area di lavoro alle Unità Databricks di Azure.

In questa sezione viene creata un'area di lavoro di Azure Databricks usando il portale di Azure.

1. Nel portale di Azure selezionare **Crea una risorsa** > Analytics Azure Databricks.In the Azure portal, select Create a resource**Analytics** > **Azure Databricks.**

   ![Creare una risorsa di Azure Databricks nel portale di AzureCreate an Azure Databricks resource in Azure portal](./media/databricks-deployment/create-databricks-resource.png)

2. Nella pagina **Servizio Azure Databricks** specificare i valori per creare un'area di lavoro di Databricks.

    |Proprietà  |Descrizione  |
    |---------|---------|
    |**Nome dell'area di lavoro**     | Specificare un nome per l'area di lavoro di Databricks.        |
    |**Sottoscrizione**     | Selezionare la sottoscrizione di Azure nell'elenco a discesa.        |
    |**Gruppo di risorse**     | Specificare se si vuole creare un nuovo gruppo di risorse o usarne uno esistente. Un gruppo di risorse è un contenitore con risorse correlate per una soluzione Azure. Per altre informazioni, vedere [Panoramica di Gestione risorse di Microsoft Azure](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview). |
    |**Percorso**     | Selezionare l'area preferita. Per informazioni sulle aree disponibili, vedere Servizi di [Azure disponibili per area.](https://azure.microsoft.com/regions/services/)        |
    |**Livello di determinazione dei prezzi**     |  Scegliere tra **Standard**, **Premium** e **Versione di valutazione**. Per altre informazioni su questi piani tariffari, vedere la [pagina dei prezzi di Databricks](https://azure.microsoft.com/pricing/details/databricks/).       |
    |**Rete virtuale**     |   No       |

3. Selezionare **Crea**. La creazione dell'area di lavoro richiede alcuni minuti, durante i quali è possibile visualizzare lo stato della distribuzione in **Notifiche**.

## <a name="install-azure-databricks-tools"></a>Installare gli strumenti di Azure DatabricksInstall Azure Databricks tools

È possibile usare l'interfaccia della riga di **comando Databricks** per connettersi ai cluster di Azure Databricks e caricarli dal computer locale. I cluster Databricks accedono ai file tramite DBFS (Databricks File System).

1. Databricks CLI richiede Python 3.6 o superiore. Se Python è già installato, è possibile ignorare questo passaggio.

   **Per Windows:**

   [Scarica Python per Windows](https://www.python.org/ftp/python/3.7.4/python-3.7.4.exe)

   **Per Linux:** Python viene preinstallato sulla maggior parte delle distribuzioni Linux. Eseguire il comando seguente per vedere quale versione è stata installata:

   ```bash
   python3 --version
   ```

2. Utilizzare pip per installare la CLI Databricks. Python 3.4 e versioni successive includono pip per impostazione predefinita. Utilizzare pip3 per Python 3. Eseguire il comando seguente:

   ```bash
   pip3 install databricks-cli
   ```

3. Dopo aver installato l'interfaccia della riga di comando di `databricks`Databricks, aprire un nuovo prompt dei comandi ed eseguire il comando . Se si riceve un **'databricks' non viene riconosciuto come un errore**di comando interno o esterno , assicurarsi di aver aperto un nuovo prompt dei comandi.

## <a name="set-up-azure-databricks"></a>Configurare Azure DatabricksSet up Azure Databricks

Ora che è installata l'interfaccia della riga di comando Databricks, è necessario impostare i dettagli di autenticazione.

1. Eseguire il comando `databricks configure --token`CLI Databricks .

2. Dopo aver eseguito il comando di configurazione, viene richiesto di immettere un host. L'URL dell'host utilizza il formato: **https://<-Location>.azuredatabricks.net .** Ad esempio, se è stato selezionato **eastus2** durante la **https://eastus2.azuredatabricks.net**creazione del servizio Azure Databricks, l'host sarà .

3. Dopo aver inserito l'host, viene richiesto di immettere un token. Nel portale di Azure selezionare **Avvia area di lavoro** per avviare l'area di lavoro di Azure Databricks.In the Azure portal, select Launch Workspace to launch your Azure Databricks workspace.

   ![Avviare l'area di lavoro di Azure Databricks](./media/databricks-deployment/launch-databricks-workspace.png)

4. Nella home page dell'area di lavoro selezionare **Impostazioni utente**.

   ![Impostazioni utente nell'area di lavoro di Azure DatabricksUser settings in Azure Databricks workspace](./media/databricks-deployment/databricks-user-settings.png)

5. Nella pagina Impostazioni utente è possibile generare un nuovo token. Copiare il token generato e incollarlo nuovamente nel prompt dei comandi.

   ![Generare un nuovo token di accesso nell'area di lavoro di Azure DatabricksGenerate new access token in Azure Databricks workspace](./media/databricks-deployment/generate-token.png)

A questo punto dovrebbe essere possibile accedere a tutti i cluster di Azure Databricks creati e caricati file in DBFS.

## <a name="download-worker-dependencies"></a>Scarica dipendenze del worker

1. Microsoft.Spark.Worker consente a Apache Spark di eseguire l'app, ad esempio qualsiasi funzione definita dall'utente (UDF) che è stata scritta. Scaricare [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz).

2. Il *install-worker.sh* è uno script che consente di copiare .NET per i file dipendenti da Apache Spark nei nodi del cluster.

   Creare un nuovo file denominato install-worker.sh nel computer locale e incollare il contenuto della install-worker.sh disponibile in GitHub.Create a new file named **to** your local computer, and paste [the install-worker.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) located on GitHub.

3. Il *db-init.sh* è uno script che installa le dipendenze nel cluster Databricks Spark.The the db-init.sh is a script that installs dependencies onto your Databricks Spark cluster.

   Creare un nuovo file denominato db-init.sh nel computer locale e incollare il contenuto del db-init.sh disponibile in GitHub.Create a new file named **db-init.sh** on your local computer, and paste [the db-init.sh contents](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) located on GitHub.

   Nel file appena creato, `DOTNET_SPARK_RELEASE` impostare `https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz`la variabile su . Lasciare il resto del *file db-init.sh* così com'è.

> [!Note]
> Se si utilizza Windows, verificare che le terminazioni di riga negli *script install-worker.sh* e *db-init.sh* siano in stile Unix (LF). È possibile modificare le terminazioni di riga tramite editor di testo come Blocco note e Atom.

## <a name="publish-your-app"></a>Pubblicare l'app

Successivamente, si pubblica *mySparkApp* creata in [.NET per Apache Spark - Introduzione](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) nell'esercitazione di 10 minuti per assicurarsi che il cluster Spark abbia accesso a tutti i file necessari per eseguire l'app.

1. Eseguire i seguenti comandi per pubblicare *mySparkApp*:

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. Eseguire le attività seguenti per comprimere i file dell'app pubblicati in modo da poterli caricare facilmente nel cluster Databricks Spark.

   **In Windows:**

   Passare a mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64. Quindi, fare clic con il pulsante destro del mouse su **Pubblica** cartella e selezionare **Invia a > cartella compressa (compressa).** Assegnare alla nuova cartella il nome **publish.zip**.

   **In Linux, eseguire il comando seguente:**

   ```bash
   zip -r publish.zip .
   ```

## <a name="upload-files"></a>Caricare file

In questa sezione vengono caricati diversi file in DBFS in modo che il cluster disponga di tutto il necessario per eseguire l'app nel cloud. Ogni volta che si carica un file in DBFS, assicurarsi di trovarsi nella directory in cui si trova il file nel computer.

1. Eseguire i comandi seguenti per caricare i *comandi db-init.sh*, *install-worker.sh*e *Microsoft.Spark.Worker* in DBFS:

   ```console
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   databricks fs cp Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz dbfs:/spark-dotnet/   Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz
   ```

2. Eseguire i comandi seguenti per caricare i file rimanenti necessari al cluster per eseguire l'app: la cartella di pubblicazione compressa, *input.txt*e *microsoft-spark-2.4.x-0.3.0.jar*.

   ```console
   cd mySparkApp
   databricks fs cp input.txt dbfs:/input.txt

   cd mySparkApp\bin\Release\netcoreapp3.0\ubuntu.16.04-x64 directory
   databricks fs cp mySparkApp.zip dbfs:/spark-dotnet/publish.zip
   databricks fs cp microsoft-spark-2.4.x-0.6.0.jar dbfs:/spark-dotnet/microsoft-spark-2.4.x-0.6.0.jar
   ```

## <a name="create-a-job"></a>Creare un processo

L'app viene eseguita in Azure Databricks tramite un processo che esegue **spark-submit,** ovvero il comando usato per eseguire .NET per i processi Apache Spark.

1. Nell'area di lavoro di Azure Databricks selezionare l'icona **Processi** e quindi **Crea processo**.

   ![Creare un processo di Azure DatabricksCreate an Azure Databricks job](./media/databricks-deployment/create-job.png)

2. Scegliere un titolo per il processo e quindi **selezionare Configura invio spark**.

   ![Configurare l'invio di spark per il processo Databricks](./media/databricks-deployment/configure-spark-submit.png)

3. Incollare i seguenti parametri nella configurazione del processo. Selezionare **quindi Conferma**.

   ```
   ["--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/spark-dotnet/microsoft-spark-2.4.x-0.6.0.jar","/dbfs/spark-dotnet/publish.zip","mySparkApp"]
   ```

## <a name="create-a-cluster"></a>Creare un cluster

1. Passare al processo e selezionare **Modifica** per configurare il cluster del processo.

2. Impostare il cluster su **Spark 2.4.1**. Quindi, selezionare **Opzioni avanzate Init** > **Scripts**. Impostare Percorso script `dbfs:/spark-dotnet/db-init.sh`Init come .

   ![Configurare il cluster spark in Azure DatabricksConfigure spark cluster in Azure Databricks](./media/databricks-deployment/cluster-config.png)

3. Selezionare **Conferma** per confermare le impostazioni del cluster.

## <a name="run-your-app"></a>Eseguire l'app

1. Passare al processo e selezionare **Esegui ora** per eseguire il processo nel cluster Spark appena configurato.

2. La creazione del cluster del processo richiede alcuni minuti. Una volta creato, il lavoro verrà inviato ed è possibile visualizzare l'output.

3. Selezionare **Cluster** dal menu a sinistra, quindi il nome e l'esecuzione del processo.

4. Selezionare **Registri driver** per visualizzare l'output del processo. Al termine dell'esecuzione dell'app, viene visualizzata la stessa tabella di conteggio delle parole dell'esecuzione locale avviata scritta nella console di output standard.

   ![Tabella di output del processo di Azure DatabricksAzure Databricks job output table](./media/databricks-deployment/table-output.png)

   Congratulazioni, hai eseguito la tua prima applicazione .NET per Apache Spark nel cloud!

## <a name="clean-up-resources"></a>Pulire le risorse

Se l'area di lavoro Databricks non è più necessaria, è possibile eliminare la risorsa Azure Databricks nel portale di Azure.If you no longer need the Databricks workspace, you can delete your Azure Databricks resource in the Azure portal. È anche possibile selezionare il nome del gruppo di risorse per aprire la pagina del gruppo di risorse e quindi selezionare **Elimina gruppo di risorse**.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata distribuita un'applicazione .NET per Apache Spark in Databricks. Per altre informazioni su Databricks, passare alla documentazione di Azure Databricks.

> [!div class="nextstepaction"]
> [Documentazione di Azure Databricks](https://docs.microsoft.com/azure/azure-databricks/)

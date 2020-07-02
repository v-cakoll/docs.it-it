---
title: Inviare un .NET per Apache Spark processo a databricks
description: Informazioni su come inviare un .NET per Apache Spark processo a databricks con Spark-Submit e set jar.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: bebd170a689d8ae56aa6c55486d70354da2437ea
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617769"
---
# <a name="submit-a-net-for-apache-spark-job-to-databricks"></a>Inviare un .NET per Apache Spark processo a databricks

È possibile eseguire .NET per Apache Spark processi nei cluster databricks, ma non è disponibile per l'utente. Esistono due modi per distribuire .NET per Apache Spark processo a databricks: `spark-submit` e impostare jar.

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="deploy-using-spark-submit"></a>Eseguire la distribuzione con Spark-Submit

È possibile usare il comando [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) per inviare .net per Apache Spark processi a databricks. `spark-submit`consente l'invio solo a un cluster che viene creato su richiesta.

1. Passare all'area di lavoro databricks e creare un processo. Scegliere un titolo per il processo e quindi selezionare **Configura Spark-Submit**. Incollare i parametri seguenti nella configurazione del processo, quindi selezionare **conferma**.

    ```
    ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
    ```

    > [!NOTE]
    > Aggiornare il contenuto del parametro precedente in base ai file e alla configurazione specifici. Ad esempio, fare riferimento alla versione del file jar Microsoft. Spark caricato in DBFS e usare il nome appropriato dell'app e il file zip dell'app pubblicata.

2. Passare al processo e selezionare **modifica** per configurare il cluster del processo. Impostare la versione di Databricks Runtime in base alla versione di Apache Spark che si desidera utilizzare nella distribuzione. Selezionare quindi **Opzioni avanzate > script init**e impostare percorso script init come `dbfs:/spark-dotnet/db-init.sh` . Selezionare **conferma** per confermare le impostazioni del cluster.

3. Passare al processo e selezionare **Esegui adesso** per eseguire il processo nel cluster Spark appena configurato. Sono necessari alcuni minuti per la creazione del cluster del processo. Una volta creato, il processo verrà inviato. È possibile visualizzare l'output selezionando **cluster** dal menu a sinistra dell'area di lavoro databricks e quindi selezionando **log driver**.

## <a name="deploy-using-set-jar"></a>Eseguire la distribuzione usando set jar

In alternativa, è possibile usare [set jar](https://docs.microsoft.com/azure/databricks/jobs#--create-a-job) nell'area di lavoro di databricks per inviare .net per Apache Spark processi a databricks. *Set jar* consente l'invio di processi a un cluster attivo esistente.

### <a name="one-time-setup"></a>Installazione singola

1. Passare al cluster databricks e selezionare **processi** dal menu a sinistra, quindi **impostare jar**.

2. Caricare l'oggetto appropriato `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` .

3. Modificare i parametri seguenti in modo da includere il nome corretto per il file eseguibile pubblicato al posto di `<your-app-name>` :

    ```
    Main Class: org.apache.spark.deploy.dotnet.DotnetRunner
    Arguments /dbfs/apps/<your-app-name>.zip <your-app-name>
    ```

4. Configurare il cluster in modo che punti a un cluster esistente per cui è già stato impostato lo script init.

### <a name="publish-and-run-your-app"></a>Pubblicare ed eseguire l'app

1. Assicurarsi di aver pubblicato l'app e che il codice dell'applicazione non usi `SparkSession.Stop()` .

2. Usare l'interfaccia della riga di comando di [databricks](https://docs.microsoft.com/azure/databricks/dev-tools/databricks-cli) per caricare l'applicazione nel cluster databricks. Ad esempio, usare il comando seguente per caricare l'app pubblicata nel cluster:

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
    ```

3. Se nell'app sono presenti funzioni definite dall'utente, gli assembly di app, ad esempio le dll che contengono funzioni definite dall'utente e le relative dipendenze, devono essere posizionati nella directory di lavoro di ogni *Microsoft. Spark. Worker*.

    Caricare gli assembly dell'applicazione nel cluster databricks:

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <assembly>.dll dbfs:/apps/dependencies
    ```

    Rimuovere il commento e modificare la sezione relativa alle dipendenze dell'app in [DB-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) in modo che punti al percorso delle dipendenze dell'app. Caricare quindi il *DB-init.sh* aggiornato nel cluster:

    ```console
    cd <path-to-db-init-and-install-worker>
    databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
    ```

4. Passare a **databricks cluster > Jobs > [nome processo] > Esegui ora** per eseguire il processo.

## <a name="next-steps"></a>Passaggi successivi

* [Introduzione a .NET per Apache Spark](../tutorials/get-started.md)
* [Distribuire un'applicazione .NET per Apache Spark in Databricks](../tutorials/databricks-deployment.md)
* [Documentazione di Azure Databricks](https://docs.microsoft.com/azure/azure-databricks/)

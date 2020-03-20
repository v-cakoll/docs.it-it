---
title: Inviare un processo .NET for Apache Spark a Databricks
description: Informazioni su come inviare un processo .NET for Apache Spark a Databricks usando spark-submit e Set Jar.
ms.date: 12/05/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 65976f9095ecef66e0538c398492033c612c1430
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187603"
---
# <a name="submit-a-net-for-apache-spark-job-to-databricks"></a>Inviare un processo .NET for Apache Spark a Databricks

Esistono due modi per distribuire il processo .NET per Apache Spark in Databricks: `spark-submit` e Set Jar.

## <a name="deploy-using-spark-submit"></a>Eseguire la distribuzione tramite spark-submit

È possibile utilizzare il comando spark-submit per inviare i processi .NET for Apache Spark a Databricks.You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Databricks. `spark-submit`consente l'invio solo a un cluster che viene creato su richiesta.

1. Passare all'area di lavoro Databricks e creare un processo. Scegliere un titolo per il processo e quindi **selezionare Configura invio spark**. Incollare i seguenti parametri nella configurazione del processo, quindi selezionare **Conferma**.

    ```
    ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
    ```

    > [!NOTE]
    > Aggiornare il contenuto del parametro precedente in base ai file e alla configurazione specifici. Ad esempio, fai riferimento alla versione del file jar di Microsoft.Spark caricato in DBFS e usa il nome appropriato dell'app e del file zip dell'app pubblicato.

2. Passare al processo e selezionare **Modifica** per configurare il cluster del processo. Impostare la versione di Runtime di Databricks in base alla versione di Apache Spark che si desidera utilizzare nella distribuzione. Selezionare **quindi Opzioni avanzate > Script Init** `dbfs:/spark-dotnet/db-init.sh`e impostare Init Script Path come . Selezionare **Conferma** per confermare le impostazioni del cluster.

3. Passare al processo e selezionare **Esegui ora** per eseguire il processo nel cluster Spark appena configurato. La creazione del cluster del processo richiede alcuni minuti. Una volta creato, il tuo lavoro verrà inviato. È possibile visualizzare l'output selezionando **Cluster** dal menu a sinistra dell'area di lavoro Databricks, quindi selezionare **Driver Logs**.

## <a name="deploy-using-set-jar"></a>Eseguire la distribuzione con Set JarDeploy using Set Jar

In alternativa, è possibile utilizzare [Imposta Jar](https://docs.microsoft.com/azure/databricks/jobs#--create-a-job) nell'area di lavoro Databricks per inviare i processi .NET per Apache Spark a Databricks. *Set Jar* consente l'invio di processi a un cluster attivo esistente.

### <a name="one-time-setup"></a>Installazione singola

1. Passare al cluster Databricks e selezionare **Processi** dal menu a sinistra, seguito da **Imposta JAR**.

2. Caricare il `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar`file .

3. Modificare i seguenti parametri per includere il nome corretto `<your-app-name>`per l'eseguibile pubblicato al posto di :

    ```
    Main Class: org.apache.spark.deploy.dotnet.DotnetRunner
    Arguments /dbfs/apps/<your-app-name>.zip <your-app-name>
    ```

4. Configurare il cluster in modo che punti a un cluster esistente per il quale è già stato impostato lo script init.

### <a name="publish-and-run-your-app"></a>Pubblicare ed eseguire l'app

1. Assicurarsi di aver pubblicato l'app e `SparkSession.Stop()`che il codice dell'applicazione non utilizzi .

2. Usare [l'interfaccia della riga](https://docs.microsoft.com/azure/databricks/dev-tools/databricks-cli) di comando di Databricks per caricare l'applicazione nel cluster Databricks.Use Databricks CLI to upload your application to your Databricks cluster. Ad esempio, usa il comando seguente per caricare l'app pubblicata nel cluster:

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
    ```

3. Se nell'app sono presenti funzioni definite dall'utente, gli assembly dell'app, ad esempio le DLL che contengono funzioni definite dall'utente insieme alle relative dipendenze, devono essere inseriti nella directory di lavoro di ogni *Microsoft.Spark.Worker*.

    Caricare gli assiemi dell'applicazione nel cluster Databricks:

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <assembly>.dll dbfs:/apps/dependencies
    ```

    Rimuovere il commento e modificare la sezione delle dipendenze dell'app in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) in modo che punti al percorso delle dipendenze dell'app. Quindi, caricare il db-init.sh aggiornato nel cluster:Then, upload the updated *db-init.sh* to your cluster:

    ```console
    cd <path-to-db-init-and-install-worker>
    databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
    ```

4. Passare al **cluster Databricks > processi > [nome processo] > Esegui ora** per eseguire il processo.

## <a name="next-steps"></a>Passaggi successivi

* [Introduzione a .NET per Apache Spark](../tutorials/get-started.md)
* [Distribuire un'applicazione .NET per Apache Spark in Databricks](../tutorials/databricks-deployment.md)
* [Documentazione di Azure Databricks](https://docs.microsoft.com/azure/azure-databricks/)

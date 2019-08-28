---
title: Distribuire un'applicazione .NET per Apache Spark in Databricks
description: Informazioni su come distribuire un'applicazione .NET per Apache Spark in Databricks.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: ca9e93a413622c84325ca9fc8bac17268b990c5a
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "69576968"
---
# <a name="deploy-a-net-for-apache-spark-application-to-databricks"></a>Distribuire un'applicazione .NET per Apache Spark in Databricks

Questa esercitazione illustra come distribuire un'applicazione .NET per Apache Spark in Databricks.

In questa esercitazione si imparerà a:

> [!div class="checklist"]
> * Preparare Microsoft.Spark.Worker
> * Pubblicare l'app Spark .NET
> * Distribuire l'app in Databricks
> * Eseguire l'app

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, eseguire le operazioni seguenti:

* Scaricare l'[interfaccia della riga di comando di Databricks](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).
* Scaricare [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) nel computer locale. Si tratta di uno script helper che verrà usato in seguito per copiare i file dipendenti di .NET per Apache Spark nei nodi di lavoro del cluster Spark.

## <a name="prepare-worker-dependencies"></a>Preparare le dipendenze dei nodi di lavoro

**Microsoft. Spark.Worker** è un componente back-end che risiede nei singoli nodi di lavoro del cluster Spark. Quando si vuole eseguire una funzione definita dall'utente C#, Spark deve comprendere come avviare CLR .NET per eseguire la funzione definita dall'utente. **Microsoft. Spark.Worker** offre una raccolta di classi per Spark che consentono di abilitare questa funzionalità.

1. Selezionare una versione netcoreapp Linux di [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) da distribuire nel cluster.

   Ad esempio, se si vuole usare `.NET for Apache Spark v0.1.0` con `netcoreapp2.1`, scaricare [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).

2. Caricare `Microsoft.Spark.Worker.<release>.tar.gz` e [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) in un file system distribuito (ad esempio, DBFS) a cui può accedere il cluster.

## <a name="prepare-your-net-for-apache-spark-app"></a>Preparare .NET per l'app Apache Spark

1. Per creare l'app, seguire l'esercitazione [Introduzione](get-started.md).

2. Pubblicare l'app Spark .NET come indipendente.

   In Linux è possibile eseguire il comando seguente.

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. Produrre `<your app>.zip` per i file pubblicati.

   In Linux è possibile eseguire il comando seguente con `zip`.

   ```bash
   zip -r <your app>.zip .
   ```

4. Caricare il file seguente in un file system distribuito (ad esempio, DBFS) a cui può accedere il cluster:

   * `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Questo file jar è incluso nel pacchetto NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) e viene posizionato nella directory di output di compilazione dell'app.
   * `<your app>.zip`
   * I file (come i file di dipendenza o i dati comuni accessibili a ogni ruolo di lavoro) o gli assembly (ad esempio le DLL che contengono funzioni definite dall'utente o librerie da cui dipende l'app), vengono inseriti nella directory di lavoro di ogni executor.

## <a name="deploy-to-databricks"></a>Distribuire in Databricks

[Databricks](https://databricks.com) è una piattaforma che offre funzionalità di elaborazione di Big Data basate sul cloud con Apache Spark.

> [!Note] 
> [Azure Databricks](https://azure.microsoft.com/services/databricks/) e [AWS Databricks](https://databricks.com/aws) sono basati su Linux. Per questo motivo, se si è interessati a distribuire l'app in Databricks, assicurarsi che l'app sia compatibile con .NET Standard e che venga usato il [compilatore .NET Core](https://dotnet.microsoft.com/download) per compilare l'app.

Databricks consente di inviare app .NET per Apache Spark a un cluster attivo esistente o di creare un nuovo cluster ogni volta che viene avviato un processo. A questo scopo, è necessario installare **Microsoft.Spark.Worker** prima di inviare un'app.NET per Apache Spark.

### <a name="deploy-microsoftsparkworker"></a>Distribuire Microsoft.Spark.Worker

Questo passaggio è necessario solo una volta per un cluster.

1. Scaricare [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) e [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) nel computer locale.

2. Modificare **db-init.sh** in modo che punti alla versione di **Microsoft.Spark.Worker** che si vuole scaricare e installare nel cluster.

3. Installare l'[interfaccia della riga di comando di Databricks](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).

4. [Configurare i dettagli dell'autenticazione](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) per l'interfaccia della riga di comando di Databricks.

5. Caricare i file nel cluster Databricks con il comando seguente:

   ```bash
   cd <path-to-db-init-and-install-worker>
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   ```

6. Passare all'area di lavoro di Databricks. Selezionare **Clusters** (Cluster) dal menu a sinistra e quindi selezionare **Create Cluster** (Crea cluster).

7. Dopo aver configurato il cluster in modo appropriato, **impostare lo script** di inizializzazione e creare il cluster.

   ![Immagine dell'azione script](./media/databricks-deployment/deployment-databricks-init-script.png)

## <a name="run-your-app"></a>Eseguire l'app 

È possibile usare `set JAR` o `spark-submit` per inviare il processo a Databricks.

### <a name="use-set-jar"></a>Usare Set JAR (Imposta JAR)

[Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) (Imposta JAR) consente di inviare un processo a un cluster attivo esistente.

#### <a name="one-time-setup"></a>Installazione singola

1. Passare al cluster Databricks e selezionare **Jobs** (Processi) dal menu a sinistra. Selezionare quindi **Set JAR** (Imposta JAR).

2. Caricare il file `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` appropriato.

3. Impostare i parametri in modo appropriato.

   ```
   Main Class: org.apache.spark.deploy.DotnetRunner
   Arguments /dbfs/apps/<your-app-name>.zip <your-app-main-class>
   ```
 
4. Configurare il **cluster** in modo che punti al cluster esistente per cui è stato creato lo **script** di inizializzazione nella sezione precedente.

#### <a name="publish-and-run-your-app"></a>Pubblicare ed eseguire l'app

1. Usare l'[interfaccia della riga di comando di Databricks](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) per caricare l'applicazione nel cluster Databricks.

      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
      ```

2. Questo passaggio è necessario solo se gli assembly dell'app, ad esempio le DLL che contengono funzioni definite dall'utente e le relative dipendenze, devono essere posizionati nella directory di lavoro di ogni **Microsoft.Spark.Worker**.

   - Caricare gli assembly dell'applicazione nel cluster Databricks
      
      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <assembly>.dll dbfs:/apps/dependencies
      ```

   - Rimuovere il commento e modificare la sezione relativa alle dipendenze dell'app in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) per puntare al percorso delle dipendenze dell'app ed eseguire il caricamento nel cluster Databricks.
   
      ```bash
      cd <path-to-db-init-and-install-worker>
      databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
      ```
   
   - Riavviare il cluster.

3. Passare al cluster Databricks nell'area di lavoro di Databricks. In **Jobs** (Processi) selezionare il processo e quindi selezionare **Run Now** (Esegui adesso) per eseguire il processo.

### <a name="use-spark-submit"></a>Usare spark-submit

Il comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) consente di inviare un processo a un nuovo cluster.

1. [Creare un processo](https://docs.databricks.com/user-guide/jobs.html) e selezionare **Configure spark-submit** (Configura spark-submit).

2. Configurare `spark-submit` con i parametri seguenti:

      ```bash
      ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
      ```

3. Passare al cluster Databricks nell'area di lavoro di Databricks. In **Jobs** (Processi) selezionare il processo e quindi selezionare **Run Now** (Esegui adesso) per eseguire il processo.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata distribuita un'applicazione .NET per Apache Spark in Databricks. Per altre informazioni su Databricks, passare alla documentazione di Azure Databricks.

> [!div class="nextstepaction"]
> [Documentazione di Azure Databricks](https://docs.microsoft.com/azure/azure-databricks/)

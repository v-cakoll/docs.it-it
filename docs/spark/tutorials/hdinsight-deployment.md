---
title: Distribuire un'applicazione .NET per Apache Spark in Azure HDInsight
description: Informazioni su come distribuire un'applicazione .NET per Apache Spark in HDInsight.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 81d1af1fd4e3329c4a289eea388edf8af57d7c4e
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70243942"
---
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a>Distribuire un'applicazione .NET per Apache Spark in Azure HDInsight

Questa esercitazione illustra come distribuire un'applicazione .NET per Apache Spark in Azure HDInsight.

In questa esercitazione si imparerà a:

> [!div class="checklist"]
> * Preparare Microsoft.Spark.Worker
> * Pubblicare l'app Spark .NET
> * Distribuire l'app in Azure HDInsight
> * Eseguire l'app

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, eseguire le operazioni seguenti:

* Scaricare [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).
* Scaricare [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) nel computer locale. Si tratta di uno script helper che verrà usato in seguito per copiare i file dipendenti di .NET per Apache Spark nei nodi di lavoro del cluster Spark.

## <a name="prepare-worker-dependencies"></a>Preparare le dipendenze dei nodi di lavoro

**Microsoft. Spark.Worker** è un componente back-end che risiede nei singoli nodi di lavoro del cluster Spark. Quando si vuole eseguire una funzione definita dall'utente C#, Spark deve comprendere come avviare CLR .NET per eseguire la funzione definita dall'utente. **Microsoft. Spark.Worker** offre una raccolta di classi per Spark che consentono di abilitare questa funzionalità.

1. Selezionare una versione netcoreapp Linux di [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) da distribuire nel cluster.

   Ad esempio, se si vuole usare `.NET for Apache Spark v0.1.0` con `netcoreapp2.1`, scaricare [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).

2. Caricare `Microsoft.Spark.Worker.<release>.tar.gz` e [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) in un file system distribuito (ad esempio, HDFS, WASB, ADLS) a cui può accedere il cluster.

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

4. Caricare il file seguente in un file system distribuito, ad esempio HDFS, WASB, ADLS, a cui può accedere il cluster:

   * `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Questo file jar è incluso nel pacchetto NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) e viene posizionato nella directory di output di compilazione dell'app.
   * `<your app>.zip`
   * I file (come i file di dipendenza o i dati comuni accessibili a ogni ruolo di lavoro) o gli assembly (ad esempio le DLL che contengono funzioni definite dall'utente o librerie da cui dipende `app`), vengono inseriti nella directory di lavoro di ogni executor.

## <a name="deploy-to-azure-hdinsight-spark"></a>Distribuire in Azure HDInsight Spark

[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) è l'implementazione Microsoft di Apache Spark nel cloud che consente agli utenti di avviare e configurare cluster Spark in Azure. È possibile usare cluster HDInsight Spark per elaborare i dati archiviati in [Archiviazione di Azure](https://azure.microsoft.com/services/storage/) o in [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).

> [!NOTE]
> Azure HDInsight Spark è basato su Linux. Se si è interessati a distribuire l'app in Azure HDInsight Spark, assicurarsi che l'app sia compatibile con .NET Standard e che venga usato il [compilatore .NET Core](https://dotnet.microsoft.com/download) per compilare l'app.

### <a name="deploy-microsoftsparkworker"></a>Distribuire Microsoft.Spark.Worker

Questo passaggio è necessario solo una volta per il cluster.

Eseguire `install-worker.sh` nel cluster usando [azioni script di HDInsight](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).

|Impostazione|Valore|
|-------|-----|
|Tipo di script|Personalizzato|
|NOME|Installare Microsoft.Spark.Worker|
|URI script Bash|URI in cui è stato caricato `install-worker.sh`. Ad esempio, `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`.|
|Tipi di nodo|Lavoro|
|Parametri|Parametri per `install-worker.sh`. Ad esempio, se `install-worker.sh` viene caricato in Azure Data Lake Gen2, sarà `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.|

![Immagine dell'azione script](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a>Eseguire l'app

È possibile inviare il processo ad Azure HDInsight usando `spark-submit` o Apache Livy.

### <a name="use-spark-submit"></a>Usare spark-submit

È possibile usare il comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) per inviare processi .NET per Apache Spark ad Azure HDInsight.
 
1. `ssh` in uno dei nodi head del cluster.

1. Esegui `spark-submit`:

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a>Usare Apache Livy

È possibile usare [Apache Livy](https://livy.incubator.apache.org/), l'API REST di Apache Spark, per inviare i processi .NET per Apache Spark a un cluster Azure HDInsight Spark. Per altre informazioni, vedere [Processi remoti con Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).

In Linux è possibile eseguire il comando seguente con `curl`:

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.dotnet.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata distribuita un'applicazione .NET per Apache Spark in Azure HDInsight. Per altre informazioni su HDInsight, continuare con la documentazione di Azure HDInsight.

> [!div class="nextstepaction"]
> [Documentazione di Azure HDInsight](https://docs.microsoft.com/azure/hdinsight/)

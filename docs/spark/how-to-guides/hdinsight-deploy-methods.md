---
title: Inviare un processo .NET per Apache Spark ad Azure HDInsightSubmit a .NET for Apache Spark job to Azure HDInsight
description: Informazioni su come inviare un processo .NET for Apache Spark ad Azure HDInsight usando spark-submit e Apache Livy.
ms.date: 11/19/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 83359f7f613b500a4ce121ce1612cda0ad1191ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79185791"
---
# <a name="submit-a-net-for-apache-spark-job-to-azure-hdinsight"></a>Inviare un processo .NET per Apache Spark ad Azure HDInsightSubmit a .NET for Apache Spark job to Azure HDInsight

Esistono due modi per distribuire il processo .NET per Apache Spark in HDInsight: `spark-submit` e Apache Livy.

## <a name="deploy-using-spark-submit"></a>Eseguire la distribuzione tramite spark-submit

È possibile usare il comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) per inviare processi .NET per Apache Spark ad Azure HDInsight.

1. Passare al cluster HDInsight Spark nel portale di Azure e quindi selezionare **SSH e accesso al cluster.**

2. Copiare le informazioni di accesso ssh e incollare il login in un terminale. Accedere al cluster utilizzando la password impostata durante la creazione del cluster. Dovresti vedere messaggi che ti accolgano a Ubuntu e Spark.

3. Usare il comando spark-submit per eseguire l'app nel cluster HDInsight.Use the **spark-submit** command to run your app on your HDInsight cluster. Ricordarsi di sostituire **mycontainer** e **mystorageaccount** nello script di esempio con i nomi effettivi del contenitore BLOB e dell'account di archiviazione. Inoltre, assicurarsi `microsoft-spark-2.3.x-0.6.0.jar` di sostituire con il file jar appropriato che si sta utilizzando per la distribuzione. `2.3.x`rappresenta la versione di Apache `0.6.0` Spark e rappresenta la versione di [.NET per Apache Spark worker.](https://github.com/dotnet/spark/releases)

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

## <a name="deploy-using-apache-livy"></a>Distribuire utilizzando Apache Livy

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

* [Introduzione a .NET per Apache Spark](../tutorials/get-started.md)
* [Distribuire un'applicazione .NET per Apache Spark in Azure HDInsight](../tutorials/hdinsight-deployment.md)
* [Documentazione di HDInsightHDInsight Documentation](https://docs.microsoft.com/azure/hdinsight/)

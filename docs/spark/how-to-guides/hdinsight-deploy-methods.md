---
title: Inviare un processo .NET per Apache Spark processo ad Azure HDInsight
description: Informazioni su come inviare un .NET per Apache Spark processo ad Azure HDInsight usando Spark-Submit e Apache Livio.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 50611b1f62934a446e5b80a8c53698efe23cd1fc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617691"
---
# <a name="submit-a-net-for-apache-spark-job-to-azure-hdinsight"></a>Inviare un processo .NET per Apache Spark processo ad Azure HDInsight

Esistono due modi per distribuire .NET per Apache Spark processo in HDInsight: `spark-submit` e Apache Livio.

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="deploy-using-spark-submit"></a>Eseguire la distribuzione con Spark-Submit

È possibile usare il comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) per inviare processi .NET per Apache Spark ad Azure HDInsight.

1. Passare al cluster HDInsight Spark in portale di Azure, quindi selezionare **SSH + login cluster**.

2. Copiare le informazioni di accesso SSH e incollare l'account di accesso in un terminale. Accedere al cluster usando la password impostata durante la creazione del cluster. Verranno visualizzati messaggi di benvenuto in Ubuntu e Spark.

3. Usare il comando **Spark-Submit** per eseguire l'app nel cluster HDInsight. Ricordarsi di **sostituire e** **mystorageaccount** nello script di esempio con i nomi effettivi del contenitore BLOB e dell'account di archiviazione. Inoltre, assicurarsi di sostituire `microsoft-spark-2.3.x-0.6.0.jar` con il file jar appropriato che si sta usando per la distribuzione. `2.3.x`rappresenta la versione di Apache Spark e `0.6.0` rappresenta la versione di [.net per Apache Spark Worker](https://github.com/dotnet/spark/releases).

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

## <a name="deploy-using-apache-livy"></a>Eseguire la distribuzione usando Apache Livio

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
* [Documentazione di HDInsight](https://docs.microsoft.com/azure/hdinsight/)

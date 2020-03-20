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
# <a name="submit-a-net-for-apache-spark-job-to-azure-hdinsight"></a><span data-ttu-id="cb17b-103">Inviare un processo .NET per Apache Spark ad Azure HDInsightSubmit a .NET for Apache Spark job to Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="cb17b-103">Submit a .NET for Apache Spark job to Azure HDInsight</span></span>

<span data-ttu-id="cb17b-104">Esistono due modi per distribuire il processo .NET per Apache Spark in HDInsight: `spark-submit` e Apache Livy.</span><span class="sxs-lookup"><span data-stu-id="cb17b-104">There are two ways to deploy your .NET for Apache Spark job to HDInsight: `spark-submit` and Apache Livy.</span></span>

## <a name="deploy-using-spark-submit"></a><span data-ttu-id="cb17b-105">Eseguire la distribuzione tramite spark-submit</span><span class="sxs-lookup"><span data-stu-id="cb17b-105">Deploy using spark-submit</span></span>

<span data-ttu-id="cb17b-106">È possibile usare il comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) per inviare processi .NET per Apache Spark ad Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="cb17b-106">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>

1. <span data-ttu-id="cb17b-107">Passare al cluster HDInsight Spark nel portale di Azure e quindi selezionare **SSH e accesso al cluster.**</span><span class="sxs-lookup"><span data-stu-id="cb17b-107">Navigate to your HDInsight Spark cluster in Azure portal, and then select **SSH + Cluster login**.</span></span>

2. <span data-ttu-id="cb17b-108">Copiare le informazioni di accesso ssh e incollare il login in un terminale.</span><span class="sxs-lookup"><span data-stu-id="cb17b-108">Copy the ssh login information and paste the login into a terminal.</span></span> <span data-ttu-id="cb17b-109">Accedere al cluster utilizzando la password impostata durante la creazione del cluster.</span><span class="sxs-lookup"><span data-stu-id="cb17b-109">Sign in to your cluster using the password you set during cluster creation.</span></span> <span data-ttu-id="cb17b-110">Dovresti vedere messaggi che ti accolgano a Ubuntu e Spark.</span><span class="sxs-lookup"><span data-stu-id="cb17b-110">You should see messages welcoming you to Ubuntu and Spark.</span></span>

3. <span data-ttu-id="cb17b-111">Usare il comando spark-submit per eseguire l'app nel cluster HDInsight.Use the **spark-submit** command to run your app on your HDInsight cluster.</span><span class="sxs-lookup"><span data-stu-id="cb17b-111">Use the **spark-submit** command to run your app on your HDInsight cluster.</span></span> <span data-ttu-id="cb17b-112">Ricordarsi di sostituire **mycontainer** e **mystorageaccount** nello script di esempio con i nomi effettivi del contenitore BLOB e dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cb17b-112">Remember to replace **mycontainer** and **mystorageaccount** in the example script with the actual names of your blob container and storage account.</span></span> <span data-ttu-id="cb17b-113">Inoltre, assicurarsi `microsoft-spark-2.3.x-0.6.0.jar` di sostituire con il file jar appropriato che si sta utilizzando per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cb17b-113">Also, be sure to replace `microsoft-spark-2.3.x-0.6.0.jar` with the appropriate jar file you're using for deployment.</span></span> <span data-ttu-id="cb17b-114">`2.3.x`rappresenta la versione di Apache `0.6.0` Spark e rappresenta la versione di [.NET per Apache Spark worker.](https://github.com/dotnet/spark/releases)</span><span class="sxs-lookup"><span data-stu-id="cb17b-114">`2.3.x` represents the version of Apache Spark, and `0.6.0` represents the version of the [.NET for Apache Spark worker](https://github.com/dotnet/spark/releases).</span></span>

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

## <a name="deploy-using-apache-livy"></a><span data-ttu-id="cb17b-115">Distribuire utilizzando Apache Livy</span><span class="sxs-lookup"><span data-stu-id="cb17b-115">Deploy using Apache Livy</span></span>

<span data-ttu-id="cb17b-116">È possibile usare [Apache Livy](https://livy.incubator.apache.org/), l'API REST di Apache Spark, per inviare i processi .NET per Apache Spark a un cluster Azure HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="cb17b-116">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="cb17b-117">Per altre informazioni, vedere [Processi remoti con Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span><span class="sxs-lookup"><span data-stu-id="cb17b-117">For more information, see [Remote jobs with Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="cb17b-118">In Linux è possibile eseguire il comando seguente con `curl`:</span><span class="sxs-lookup"><span data-stu-id="cb17b-118">You can run the following command on Linux using `curl`:</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="cb17b-119">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cb17b-119">Next steps</span></span>

* [<span data-ttu-id="cb17b-120">Introduzione a .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="cb17b-120">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="cb17b-121">Distribuire un'applicazione .NET per Apache Spark in Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="cb17b-121">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="cb17b-122">Documentazione di HDInsightHDInsight Documentation</span><span class="sxs-lookup"><span data-stu-id="cb17b-122">HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)

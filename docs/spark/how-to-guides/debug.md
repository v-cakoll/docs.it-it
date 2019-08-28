---
title: Eseguire il debug di un'applicazione .NET per Apache Spark in Windows
description: Informazioni su come eseguire il debug di un'applicazione .NET per Apache Spark in Windows.
ms.date: 08/15/2019
ms.topic: how-to
ms.custom: mvc
ms.openlocfilehash: 08142bd45c475ddd131053213ebdea5f843fa736
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69667669"
---
# <a name="debug-a-net-for-apache-spark-application"></a><span data-ttu-id="49033-103">Eseguire il debug di un'applicazione .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="49033-103">Debug a .NET for Apache Spark application</span></span>

<span data-ttu-id="49033-104">Questa procedura indica i comandi necessari per eseguire il debug di un'applicazione .NET per Apache Spark e di codice Scala in Windows.</span><span class="sxs-lookup"><span data-stu-id="49033-104">This how-to provides the commands you need to run to debug your .NET for Apache Spark application and Scala code on Windows.</span></span>

## <a name="debug-your-application"></a><span data-ttu-id="49033-105">Eseguire il debug dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="49033-105">Debug your application</span></span>

<span data-ttu-id="49033-106">Aprire una nuova finestra del prompt dei comandi ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="49033-106">Open a new command prompt window, run the following:</span></span>

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

<span data-ttu-id="49033-107">Quando si esegue il comando viene visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="49033-107">When you run the command, you see the following output:</span></span>

```
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

<span data-ttu-id="49033-108">In questa modalità di debug, `DotnetRunner` non avvia l'applicazione .NET, ma resta in attesa della connessione.</span><span class="sxs-lookup"><span data-stu-id="49033-108">In this debug mode, `DotnetRunner` does not launch the .NET application, but it waits for it to connect.</span></span> <span data-ttu-id="49033-109">Lasciare aperta questa finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="49033-109">Leave this command prompt window open.</span></span>

<span data-ttu-id="49033-110">A questo punto è possibile eseguire l'applicazione .NET con qualsiasi debugger per eseguirne il debug.</span><span class="sxs-lookup"><span data-stu-id="49033-110">Now you can run your .NET application with any debugger to debug your application.</span></span>

## <a name="debug-scala-code"></a><span data-ttu-id="49033-111">Debug del codice Scala</span><span class="sxs-lookup"><span data-stu-id="49033-111">Debug Scala code</span></span>

<span data-ttu-id="49033-112">Se è necessario eseguire il debug del codice sul lato Scala, come `DotnetRunner` o `DotnetBackendHandler`, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="49033-112">If you need to debug the Scala side code, such as `DotnetRunner` or `DotnetBackendHandler`, run the following command:</span></span>

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

<span data-ttu-id="49033-113">Dopo aver eseguito il comando, collegare un debugger al processo in esecuzione usando [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span><span class="sxs-lookup"><span data-stu-id="49033-113">After you run the command, attach a debugger to the running process using [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span></span>

## <a name="next-steps"></a><span data-ttu-id="49033-114">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="49033-114">Next steps</span></span>

* [<span data-ttu-id="49033-115">Introduzione a .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="49033-115">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="49033-116">Distribuire un'applicazione .NET per Apache Spark in Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="49033-116">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="49033-117">Distribuire un'applicazione .NET per Apache Spark in Databricks</span><span class="sxs-lookup"><span data-stu-id="49033-117">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="49033-118">Distribuire un'applicazione .NET per Apache Spark in Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="49033-118">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>](../tutorials/amazon-emr-spark-deployment.md)
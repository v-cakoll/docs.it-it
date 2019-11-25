---
title: Eseguire il debug di un'applicazione .NET per Apache Spark in Windows
description: Informazioni su come eseguire il debug di un'applicazione .NET per Apache Spark in Windows.
ms.date: 08/15/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 098c7519fe99ef04773c5e4b81685ca0f06f1272
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281523"
---
# <a name="debug-a-net-for-apache-spark-application"></a><span data-ttu-id="b953f-103">Eseguire il debug di un'applicazione .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="b953f-103">Debug a .NET for Apache Spark application</span></span>

<span data-ttu-id="b953f-104">Questa procedura indica i comandi necessari per eseguire il debug di un'applicazione .NET per Apache Spark e di codice Scala in Windows.</span><span class="sxs-lookup"><span data-stu-id="b953f-104">This how-to provides the commands you need to run to debug your .NET for Apache Spark application and Scala code on Windows.</span></span>

## <a name="debug-your-application"></a><span data-ttu-id="b953f-105">Eseguire il debug dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="b953f-105">Debug your application</span></span>

<span data-ttu-id="b953f-106">Aprire una nuova finestra del prompt dei comandi ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b953f-106">Open a new command prompt window, run the following:</span></span>

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

<span data-ttu-id="b953f-107">Quando si esegue il comando viene visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="b953f-107">When you run the command, you see the following output:</span></span>

```console
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

<span data-ttu-id="b953f-108">In questa modalità di debug, `DotnetRunner` non avvia l'applicazione .NET, ma resta in attesa della connessione.</span><span class="sxs-lookup"><span data-stu-id="b953f-108">In this debug mode, `DotnetRunner` does not launch the .NET application, but it waits for it to connect.</span></span> <span data-ttu-id="b953f-109">Lasciare aperta questa finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="b953f-109">Leave this command prompt window open.</span></span>

<span data-ttu-id="b953f-110">A questo punto è possibile eseguire l'applicazione .NET con qualsiasi debugger per eseguirne il debug.</span><span class="sxs-lookup"><span data-stu-id="b953f-110">Now you can run your .NET application with any debugger to debug your application.</span></span>

## <a name="debug-scala-code"></a><span data-ttu-id="b953f-111">Debug del codice Scala</span><span class="sxs-lookup"><span data-stu-id="b953f-111">Debug Scala code</span></span>

<span data-ttu-id="b953f-112">Se è necessario eseguire il debug del codice sul lato Scala, come `DotnetRunner` o `DotnetBackendHandler`, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b953f-112">If you need to debug the Scala side code, such as `DotnetRunner` or `DotnetBackendHandler`, run the following command:</span></span>

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

<span data-ttu-id="b953f-113">Dopo aver eseguito il comando, collegare un debugger al processo in esecuzione usando [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span><span class="sxs-lookup"><span data-stu-id="b953f-113">After you run the command, attach a debugger to the running process using [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b953f-114">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b953f-114">Next steps</span></span>

* [<span data-ttu-id="b953f-115">Introduzione a .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="b953f-115">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="b953f-116">Distribuire un'applicazione .NET per Apache Spark in Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="b953f-116">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="b953f-117">Distribuire un'applicazione .NET per Apache Spark in Databricks</span><span class="sxs-lookup"><span data-stu-id="b953f-117">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="b953f-118">Distribuire un'applicazione .NET per Apache Spark in Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="b953f-118">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>](../tutorials/amazon-emr-spark-deployment.md)

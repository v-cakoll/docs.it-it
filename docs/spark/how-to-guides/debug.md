---
title: Eseguire il debug di un'applicazione .NET per Apache Spark in Windows
description: Informazioni su come eseguire il debug di un'applicazione .NET per Apache Spark in Windows.
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: dac6aed1f7faba7f07b722a6dac0da930ab9ec66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79185813"
---
# <a name="debug-a-net-for-apache-spark-application"></a><span data-ttu-id="4715e-103">Eseguire il debug di un'applicazione .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="4715e-103">Debug a .NET for Apache Spark application</span></span>

<span data-ttu-id="4715e-104">Questa procedura illustra i passaggi per eseguire il debug di .NET per l'applicazione Apache Spark in Windows.This how-to provides the steps to debug your .NET for Apache Spark application on Windows.</span><span class="sxs-lookup"><span data-stu-id="4715e-104">This how-to provides the steps to debug your .NET for Apache Spark application on Windows.</span></span>

## <a name="debug-your-application"></a><span data-ttu-id="4715e-105">Eseguire il debug dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="4715e-105">Debug your application</span></span>

<span data-ttu-id="4715e-106">Aprire una nuova finestra del prompt dei comandi ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4715e-106">Open a new command prompt window and run the following command:</span></span>

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

<span data-ttu-id="4715e-107">Quando si esegue il comando viene visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="4715e-107">When you run the command, you see the following output:</span></span>

```console
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

<span data-ttu-id="4715e-108">In modalità di debug, DotnetRunner non avvia l'applicazione .NET, ma attende l'avvio dell'app .NET.</span><span class="sxs-lookup"><span data-stu-id="4715e-108">In debug mode, DotnetRunner does not launch the .NET application, but instead waits for you to start the .NET app.</span></span> <span data-ttu-id="4715e-109">Lasciare aperta questa finestra del prompt dei comandi e avviare l'applicazione .NET tramite il debugger C' per eseguire il debug dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4715e-109">Leave this command prompt window open and start your .NET application through C# debugger to debug your application.</span></span> <span data-ttu-id="4715e-110">Avviare l'applicazione .NET con un debugger di C, ([Visual Studio Debugger per Windows/macOS](https://visualstudio.microsoft.com/vs/) o Estensione del debugger [C'è nel codice](https://code.visualstudio.com/Docs/editor/debugging)di Visual Studio ) per eseguire il debug dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4715e-110">Start your .NET application with a C# debugger ([Visual Studio Debugger for Windows/macOS](https://visualstudio.microsoft.com/vs/) or [C# Debugger Extension in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)) to debug your application.</span></span>

## <a name="debug-a-user-defined-function-udf"></a><span data-ttu-id="4715e-111">Eseguire il debug di una funzione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="4715e-111">Debug a user-defined function (UDF)</span></span>

> [!NOTE]
> <span data-ttu-id="4715e-112">Le funzioni definite dall'utente sono supportate solo in Windows con Visual Studio Debugger.User-defined functions are supported only on Windows with Visual Studio Debugger.</span><span class="sxs-lookup"><span data-stu-id="4715e-112">User-defined functions are supported only on Windows with Visual Studio Debugger.</span></span>

<span data-ttu-id="4715e-113">Prima `spark-submit`dell'esecuzione , impostare la seguente variabile di ambiente:</span><span class="sxs-lookup"><span data-stu-id="4715e-113">Before running `spark-submit`, set the following environment variable:</span></span>

```bat
set DOTNET_WORKER_DEBUG=1
```

<span data-ttu-id="4715e-114">Quando si esegue l'applicazione `Choose Just-In-Time Debugger` Spark, verrà visualizzata una finestra.</span><span class="sxs-lookup"><span data-stu-id="4715e-114">When you run your Spark application, a `Choose Just-In-Time Debugger` window will pop up.</span></span> <span data-ttu-id="4715e-115">Scegliere un debugger di Visual Studio.Choose a Visual Studio debugger.</span><span class="sxs-lookup"><span data-stu-id="4715e-115">Choose a Visual Studio debugger.</span></span>

<span data-ttu-id="4715e-116">Il debugger si interrompo nel seguente percorso in [TaskRunner.cs:](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52)</span><span class="sxs-lookup"><span data-stu-id="4715e-116">The debugger will break at the following location in [TaskRunner.cs](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52):</span></span>

```csharp
if (EnvironmentUtils.GetEnvironmentVariableAsBool("DOTNET_WORKER_DEBUG"))
{
    Debugger.Launch(); // <-- The debugger will break here.
}
```

<span data-ttu-id="4715e-117">Passare al file *con estensione cs* che contiene la funzione definita dall'utente che si intende eseguire il debug e [impostare un punto di interruzione](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="4715e-117">Navigate to the *.cs* file that contains the UDF that you plan to debug, and [set a breakpoint](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints?view=vs-2019).</span></span> <span data-ttu-id="4715e-118">Il punto `The breakpoint will not currently be hit` di interruzione indica perché il worker non ha ancora caricato l'assembly che contiene la funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4715e-118">The breakpoint will say `The breakpoint will not currently be hit` because the worker hasn't loaded the assembly that contains UDF yet.</span></span>

<span data-ttu-id="4715e-119">Hit `F5` per continuare l'applicazione e il punto di interruzione verrà raggiunto alla fine.</span><span class="sxs-lookup"><span data-stu-id="4715e-119">Hit `F5` to continue your application and the breakpoint will eventually be hit.</span></span>

> [!NOTE]
> <span data-ttu-id="4715e-120">Viene visualizzata la finestra Scegli debugger Just-In-Time per ogni attività.</span><span class="sxs-lookup"><span data-stu-id="4715e-120">The Choose Just-In-Time Debugger window pops up for each task.</span></span> <span data-ttu-id="4715e-121">Per evitare un numero eccessivo di popup, impostare il numero di esecutori su un numero basso.</span><span class="sxs-lookup"><span data-stu-id="4715e-121">To avoid excessive pop-ups, set the number of executors to a low number.</span></span> <span data-ttu-id="4715e-122">Ad esempio, è possibile utilizzare l'opzione **--master local[1]** per spark-submit per impostare il numero di attività su 1, che avvia una singola istanza del debugger.</span><span class="sxs-lookup"><span data-stu-id="4715e-122">For example, you can use the **--master local[1]** option for spark-submit to set the number of tasks to 1, which launches a single debugger instance.</span></span>

## <a name="debug-scala-code"></a><span data-ttu-id="4715e-123">Debug del codice Scala</span><span class="sxs-lookup"><span data-stu-id="4715e-123">Debug Scala code</span></span>

<span data-ttu-id="4715e-124">Se è necessario eseguire il debug`DotnetRunner` `DotnetBackendHandler`del codice lato Scala ( , , e così via), è possibile utilizzare il comando seguente e collegare un debugger al processo in esecuzione utilizzando [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html):</span><span class="sxs-lookup"><span data-stu-id="4715e-124">If you need to debug the Scala-side code (`DotnetRunner`, `DotnetBackendHandler`, etc.), you can use the following command and attach a debugger to the running process using [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html):</span></span>

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

<span data-ttu-id="4715e-125">Dopo aver eseguito il comando, collegare un debugger al processo in esecuzione usando [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span><span class="sxs-lookup"><span data-stu-id="4715e-125">After you run the command, attach a debugger to the running process using [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4715e-126">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4715e-126">Next steps</span></span>

* [<span data-ttu-id="4715e-127">Introduzione a .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="4715e-127">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="4715e-128">Distribuire un'applicazione .NET per Apache Spark in Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="4715e-128">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="4715e-129">Distribuire un'applicazione .NET per Apache Spark in Databricks</span><span class="sxs-lookup"><span data-stu-id="4715e-129">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="4715e-130">Distribuire un'applicazione .NET per Apache Spark in Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="4715e-130">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>](../tutorials/amazon-emr-spark-deployment.md)

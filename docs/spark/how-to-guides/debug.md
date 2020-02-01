---
title: Eseguire il debug di un'applicazione .NET per Apache Spark in Windows
description: Informazioni su come eseguire il debug di un'applicazione .NET per Apache Spark in Windows.
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 25f5291c47dc1cdf2668cb077fae7439e330cc1c
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76919930"
---
# <a name="debug-a-net-for-apache-spark-application"></a>Eseguire il debug di un'applicazione .NET per Apache Spark

Questa procedura consente di eseguire il debug di .NET per Apache Spark applicazione in Windows.

## <a name="debug-your-application"></a>Eseguire il debug dell'applicazione

Aprire una nuova finestra del prompt dei comandi ed eseguire il comando seguente:

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

Quando si esegue il comando viene visualizzato l'output seguente:

```console
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

In modalità di debug, DotnetRunner non avvia l'applicazione .NET, ma attende che venga avviata l'app .NET. Lasciare aperta questa finestra del prompt dei comandi e avviare l'applicazione C# .NET tramite il debugger per eseguire il debug dell'applicazione. Avviare l'applicazione .NET con un C# debugger ([debugger di Visual Studio per Windows/MacOS](https://visualstudio.microsoft.com/vs/) o [ C# estensione del debugger in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)) per eseguire il debug dell'applicazione.

## <a name="debug-a-user-defined-function-udf"></a>Eseguire il debug di una funzione definita dall'utente (UDF)

> [!NOTE]
> Le funzioni definite dall'utente sono supportate solo in Windows con il debugger di Visual Studio.

Prima di eseguire `spark-submit`, impostare la variabile di ambiente seguente:

```bat
set DOTNET_WORKER_DEBUG=1
```

Quando si esegue l'applicazione Spark, viene visualizzata una finestra `Choose Just-In-Time Debugger`. Scegliere un debugger di Visual Studio.

Il debugger si interrompe nel percorso seguente in [TaskRunner.cs](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52):

```csharp
if (EnvironmentUtils.GetEnvironmentVariableAsBool("DOTNET_WORKER_DEBUG"))
{
    Debugger.Launch(); // <-- The debugger will break here.
}
```

Passare al file con *estensione cs* che contiene la funzione definita dall'utente di cui si intende eseguire il debug e [impostare un](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints?view=vs-2019)punto di interruzione. Il punto di interruzione indicherà `The breakpoint will not currently be hit` perché il ruolo di lavoro non ha ancora caricato l'assembly che contiene UDF.

Premere `F5` per continuare con l'applicazione e il punto di interruzione verrà raggiunto.

> [!NOTE] 
> Viene visualizzata la finestra Scegli debugger JIT per ogni attività. Per evitare un numero eccessivo di popup, impostare il numero di esecutori su un numero basso. Ad esempio, è possibile usare l'opzione **--Master local [1]** per Spark-Submit per impostare il numero di attività su 1, che avvia una singola istanza del debugger.

## <a name="debug-scala-code"></a>Debug del codice Scala

Se è necessario eseguire il debug del codice sul lato scala (`DotnetRunner`, `DotnetBackendHandler`e così via), è possibile usare il comando seguente e aggiungere un debugger al processo in esecuzione usando [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html):

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

Dopo aver eseguito il comando, collegare un debugger al processo in esecuzione usando [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).

## <a name="next-steps"></a>Passaggi successivi

* [Introduzione a .NET per Apache Spark](../tutorials/get-started.md)
* [Distribuire un'applicazione .NET per Apache Spark in Azure HDInsight](../tutorials/hdinsight-deployment.md)
* [Distribuire un'applicazione .NET per Apache Spark in Databricks](../tutorials/databricks-deployment.md)
* [Distribuire un'applicazione .NET per Apache Spark in Amazon EMR Spark](../tutorials/amazon-emr-spark-deployment.md)

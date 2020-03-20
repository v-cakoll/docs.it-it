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
# <a name="debug-a-net-for-apache-spark-application"></a>Eseguire il debug di un'applicazione .NET per Apache Spark

Questa procedura illustra i passaggi per eseguire il debug di .NET per l'applicazione Apache Spark in Windows.This how-to provides the steps to debug your .NET for Apache Spark application on Windows.

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

In modalità di debug, DotnetRunner non avvia l'applicazione .NET, ma attende l'avvio dell'app .NET. Lasciare aperta questa finestra del prompt dei comandi e avviare l'applicazione .NET tramite il debugger C' per eseguire il debug dell'applicazione. Avviare l'applicazione .NET con un debugger di C, ([Visual Studio Debugger per Windows/macOS](https://visualstudio.microsoft.com/vs/) o Estensione del debugger [C'è nel codice](https://code.visualstudio.com/Docs/editor/debugging)di Visual Studio ) per eseguire il debug dell'applicazione.

## <a name="debug-a-user-defined-function-udf"></a>Eseguire il debug di una funzione definita dall'utente

> [!NOTE]
> Le funzioni definite dall'utente sono supportate solo in Windows con Visual Studio Debugger.User-defined functions are supported only on Windows with Visual Studio Debugger.

Prima `spark-submit`dell'esecuzione , impostare la seguente variabile di ambiente:

```bat
set DOTNET_WORKER_DEBUG=1
```

Quando si esegue l'applicazione `Choose Just-In-Time Debugger` Spark, verrà visualizzata una finestra. Scegliere un debugger di Visual Studio.Choose a Visual Studio debugger.

Il debugger si interrompo nel seguente percorso in [TaskRunner.cs:](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52)

```csharp
if (EnvironmentUtils.GetEnvironmentVariableAsBool("DOTNET_WORKER_DEBUG"))
{
    Debugger.Launch(); // <-- The debugger will break here.
}
```

Passare al file *con estensione cs* che contiene la funzione definita dall'utente che si intende eseguire il debug e [impostare un punto di interruzione](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints?view=vs-2019). Il punto `The breakpoint will not currently be hit` di interruzione indica perché il worker non ha ancora caricato l'assembly che contiene la funzione definita dall'utente.

Hit `F5` per continuare l'applicazione e il punto di interruzione verrà raggiunto alla fine.

> [!NOTE]
> Viene visualizzata la finestra Scegli debugger Just-In-Time per ogni attività. Per evitare un numero eccessivo di popup, impostare il numero di esecutori su un numero basso. Ad esempio, è possibile utilizzare l'opzione **--master local[1]** per spark-submit per impostare il numero di attività su 1, che avvia una singola istanza del debugger.

## <a name="debug-scala-code"></a>Debug del codice Scala

Se è necessario eseguire il debug`DotnetRunner` `DotnetBackendHandler`del codice lato Scala ( , , e così via), è possibile utilizzare il comando seguente e collegare un debugger al processo in esecuzione utilizzando [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html):

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

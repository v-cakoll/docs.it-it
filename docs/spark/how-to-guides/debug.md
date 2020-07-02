---
title: Eseguire il debug di un'applicazione .NET per Apache Spark in Windows
description: Informazioni su come eseguire il debug di un'applicazione .NET per Apache Spark in Windows.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 9209d5bdec6dd85f6d21a502fb07204effef1934
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617756"
---
# <a name="debug-a-net-for-apache-spark-application"></a>Eseguire il debug di un'applicazione .NET per Apache Spark

Questa procedura consente di eseguire il debug di .NET per Apache Spark applicazione in Windows.

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

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

In modalità di debug, DotnetRunner non avvia l'applicazione .NET, ma attende che venga avviata l'app .NET. Lasciare aperta questa finestra del prompt dei comandi e avviare l'applicazione .NET tramite il debugger C# per eseguire il debug dell'applicazione. Per eseguire il debug dell'applicazione, avviare l'applicazione .NET con un debugger C# ([debugger di Visual Studio per Windows/MacOS](https://visualstudio.microsoft.com/vs/) o [estensione del debugger c# in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)).

## <a name="debug-a-user-defined-function-udf"></a>Eseguire il debug di una funzione definita dall'utente (UDF)

> [!NOTE]
> Le funzioni definite dall'utente sono supportate solo in Windows con il debugger di Visual Studio.

Prima `spark-submit` di eseguire, impostare la variabile di ambiente seguente:

```bat
set DOTNET_WORKER_DEBUG=1
```

Quando si esegue l'applicazione Spark, `Choose Just-In-Time Debugger` viene visualizzata una finestra. Scegliere un debugger di Visual Studio.

Il debugger si interrompe nel percorso seguente in [TaskRunner.cs](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52):

```csharp
if (EnvironmentUtils.GetEnvironmentVariableAsBool("DOTNET_WORKER_DEBUG"))
{
    Debugger.Launch(); // <-- The debugger will break here.
}
```

Passare al file con *estensione cs* che contiene la funzione definita dall'utente di cui si intende eseguire il debug e [impostare un](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints?view=vs-2019)punto di interruzione. Il punto di interruzione dirà `The breakpoint will not currently be hit` perché il ruolo di lavoro non ha caricato l'assembly che contiene ancora UDF.

Premere `F5` per continuare l'applicazione e il punto di interruzione verrà raggiunto.

> [!NOTE]
> Viene visualizzata la finestra Scegli debugger JIT per ogni attività. Per evitare un numero eccessivo di popup, impostare il numero di esecutori su un numero basso. Ad esempio, è possibile usare l'opzione **--Master local [1]** per Spark-Submit per impostare il numero di attività su 1, che avvia una singola istanza del debugger.

## <a name="debug-scala-code"></a>Debug del codice Scala

Se è necessario eseguire il debug del codice sul lato scala ( `DotnetRunner` , e `DotnetBackendHandler` così via), è possibile usare il comando seguente e aggiungere un debugger al processo in esecuzione usando [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html):

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

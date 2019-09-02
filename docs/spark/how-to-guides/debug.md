---
title: Eseguire il debug di un'applicazione .NET per Apache Spark in Windows
description: Informazioni su come eseguire il debug di un'applicazione .NET per Apache Spark in Windows.
ms.date: 08/15/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: dcaca96f6eb871c15a37adc18190b073c63c8e93
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70206152"
---
# <a name="debug-a-net-for-apache-spark-application"></a>Eseguire il debug di un'applicazione .NET per Apache Spark

Questa procedura indica i comandi necessari per eseguire il debug di un'applicazione .NET per Apache Spark e di codice Scala in Windows.

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

```
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

In questa modalità di debug, `DotnetRunner` non avvia l'applicazione .NET, ma resta in attesa della connessione. Lasciare aperta questa finestra del prompt dei comandi.

A questo punto è possibile eseguire l'applicazione .NET con qualsiasi debugger per eseguirne il debug.

## <a name="debug-scala-code"></a>Debug del codice Scala

Se è necessario eseguire il debug del codice sul lato Scala, come `DotnetRunner` o `DotnetBackendHandler`, eseguire il comando seguente:

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

---
title: Che cos'è .NET per Apache Spark?
description: Informazioni su .NET per Apache Spark, un framework gratuito, open source e multipiattaforma per analisi di Big Data che consente di usare Spark ovunque si scriva codice .NET.
author: mamccrea
ms.topic: overview
ms.date: 10/15/2019
ms.openlocfilehash: 12fccd478cedaccf455043feb3afa7b12221bf0e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73458197"
---
# <a name="what-is-net-for-apache-spark"></a>Che cos'è .NET per Apache Spark?

[Apache Spark](what-is-spark.md) è un motore di elaborazione distribuito generico per l'analisi su set di dati di grandi dimensioni, in genere terabyte o petabyte di dati. Con .NET per Apache Spark, il supporto gratuito, open source e multipiattaforma .NET per il popolare framework di analisi dei Big Data open source, è ora possibile aggiungere la potenza di Apache Spark alle applicazioni Big Data utilizzando linguaggi già conosciuti.

## <a name="why-choose-net-for-apache-spark"></a>Perché scegliere .NET per Apache Spark?

.NET per Apache Spark consente agli sviluppatori di esperienza .NET o basi di codice per partecipare al mondo dell'analisi dei Big Data. .NET per Apache Spark offre API ad alte prestazioni per l'utilizzo di Spark da C e F. Con C# e F# è possibile accedere a:

* DataFrame e SparkSQL per l'utilizzo di dati strutturati.
* Spark Structured Streaming per l'utilizzo di dati di streaming.
* Spark SQL per la scrittura di query con sintassi SQL.
* Integrazione di Machine Learning per una formazione e una stima più veloci, ovvero usare .NET per Apache Spark insieme [a ML.NET](https://dot.net/ml)).

.NET per Apache Spark è conforme a .NET Standard, una specifica formale delle API .NET comuni tra le implementazioni di .NET. Questo significa che è possibile usare .NET per Apache Spark ovunque si scriva codice .NET, potendo così riutilizzare tutte le conoscenze, le competenze, il codice e le librerie già disponibili come sviluppatori .NET.

.NET per Apache Spark viene eseguito in Windows, Linux e macOS con .NET Core. Viene eseguito anche in Windows con .NET Framework. È possibile distribuire le applicazioni a tutti i principali provider di servizi cloud, tra cui Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks e Databricks su AWS.

## <a name="net-for-apache-spark-architecture"></a>.NET per l'architettura Apache Spark

L'associazione del linguaggio C / F a Spark viene scritta in un nuovo livello di interoperabilità Spark che offre una maggiore estendibilità. Questo nuovo livello di interoperabilità Spark è stato scritto utilizzando le procedure consigliate per l'estensione del linguaggio e ottimizza per l'interoperabilità e le prestazioni. A lungo termine, questa estendibilità può essere utilizzata per aggiungere il supporto per altre lingue in Spark.

> [!div class="mx-imgBorder"]
> ![.NET per l'architettura Apache Spark](media/dotnet-spark-architecture.png)

Per informazioni sul supporto dell'interoperabilità per le estensioni del linguaggio [Spark, vedere la proposta](https://issues.apache.org/jira/browse/SPARK-26257).

## <a name="net-for-apache-spark-performance"></a>.NET per prestazioni di Apache Spark

Rispetto a Python e Scala che utilizzano il [benchmark TPC-H](http://www.tpc.org/tpch/), .NET per Apache Spark funziona bene nella maggior parte dei casi ed è 2 volte più veloce di Python quando le prestazioni delle funzioni definite dall'utente sono critiche. C'è uno sforzo continuo per migliorare e valutare le prestazioni.

Per eseguire il benchmarking, vedere i benchmark disponibili in [.NET per Apache Spark GitHub](https://github.com/dotnet/spark/tree/master/benchmark).

## <a name="net-for-apache-spark-roadmap"></a>Guida di orientamento a .NET for Apache Spark

Scopri i piani a breve e lungo termine dalla roadmap ufficiale [di .NET for Apache Spark](https://github.com/dotnet/spark/blob/master/ROADMAP.md).

## <a name="net-foundation"></a>.NET Foundation

Il progetto .NET per Apache Spark fa parte di [.NET Foundation.](https://www.dotnetfoundation.org/)

## <a name="contributions"></a>Contributi

Il team di .NET per Apache Spark incoraggia i contributi, sia sotto forma di registrazione di problemi che di richieste pull in GitHub. Per prima cosa, cercare un [problema esistente](https://github.com/dotnet/spark/issues). Se non si riesce a trovare un problema esistente, [aprire un nuovo problema](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).

## <a name="next-steps"></a>Passaggi successivi

Prova .NET per Apache Spark.
> [!div class="nextstepaction"]
> [Esercitazione: Introduzione a .NET per Apache SparkTutorial: Get started with .NET for Apache Spark](./tutorials/get-started.md)

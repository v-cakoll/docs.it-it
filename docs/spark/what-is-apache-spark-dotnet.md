---
title: Che cos'è .NET per Apache Spark?
description: Informazioni su .NET per Apache Spark, un framework gratuito, open source e multipiattaforma per analisi di Big Data che consente di usare Spark ovunque si scriva codice .NET.
author: mamccrea
ms.topic: overview
ms.date: 10/15/2019
ms.openlocfilehash: c31b50a20ac08bcde077e1e85ee915435a99fc28
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395867"
---
# <a name="what-is-net-for-apache-spark"></a>Che cos'è .NET per Apache Spark?

[Apache Spark](what-is-spark.md) è un motore di elaborazione distribuito per utilizzo generico per l'analisi su set di dati di grandi dimensioni, in genere terabyte o petabyte di dati. Con .NET per Apache Spark, il supporto .NET gratuito, open source e multipiattaforma per il diffuso Framework open source Big Data Analytics, è ora possibile aggiungere la potenza di Apache Spark alle applicazioni Big Data usando i linguaggi che già conosci.

## <a name="why-choose-net-for-apache-spark"></a>Perché scegliere .NET per Apache Spark?

.NET per Apache Spark consente agli sviluppatori con esperienza .NET o codebase di partecipare al mondo di Big Data Analytics. .NET per Apache Spark fornisce API ad alte prestazioni per l'uso C# di F#Spark da e. Con C# e F# è possibile accedere a:

* Dataframe e SparkSQL per l'uso di dati strutturati
* Streaming strutturato Spark per l'uso di dati di streaming
* Spark SQL per la scrittura di query con la sintassi SQL
* Integrazione di machine learning per la formazione e la stima più veloci (ad esempio, usare .NET per Apache Spark insieme a [ml.NET](http://dot.net/ml))

.NET per Apache Spark è conforme a .NET Standard, una specifica formale delle API .NET comuni tra le implementazioni di .NET. Questo significa che è possibile usare .NET per Apache Spark ovunque si scriva codice .NET, potendo così riutilizzare tutte le conoscenze, le competenze, il codice e le librerie già disponibili come sviluppatori .NET.

.NET per Apache Spark viene eseguito in Windows, Linux e macOS con .NET Core. Viene eseguito anche in Windows con .NET Framework. È possibile distribuire le applicazioni a tutti i principali provider di servizi cloud, tra cui Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks e Databricks su AWS.

## <a name="net-for-apache-spark-architecture"></a>.NET per architettura Apache Spark

Il C#binding F# della lingua/per Spark viene scritto in un nuovo livello di interoperabilità Spark che offre un'estensibilità più semplice. Questo nuovo livello di interoperabilità Spark è stato scritto usando le procedure consigliate per l'estensione del linguaggio e ottimizza per l'interoperabilità e le prestazioni. A lungo termine, questa estensibilità può essere usata per aggiungere il supporto per altri linguaggi in Spark.

> [!div class="mx-imgBorder"]
> ![.NET per l'architettura Apache Spark @ no__t-1

È possibile ottenere informazioni sul supporto di interoperabilità per [le estensioni del](https://issues.apache.org/jira/browse/SPARK-26257)linguaggio Spark dalla proposta.

## <a name="net-for-apache-spark-performance"></a>.NET per prestazioni Apache Spark

Quando viene confrontato con Python e scala usando il [benchmark TPC-H](http://www.tpc.org/tpch/), .net for Apache Spark viene eseguito correttamente nella maggior parte dei casi e 2x è più veloce di Python quando le prestazioni delle funzioni definite dall'utente sono critiche. È possibile migliorare le prestazioni e migliorare le prestazioni del benchmark. 

Per eseguire il benchmarking, vedere i benchmark disponibili in [.NET per Apache Spark GitHub](https://github.com/dotnet/spark/tree/master/benchmark).

## <a name="net-for-apache-spark-roadmap"></a>Guida di orientamento a .NET per Apache Spark

Per informazioni sui piani a breve e a lungo termine, vedere la pagina [relativa a .NET ufficiale per Apache Spark roadmap](https://github.com/dotnet/spark/blob/master/ROADMAP.md).

## <a name="net-foundation"></a>.NET Foundation

Il progetto .NET per Apache Spark fa parte di [.NET Foundation.](https://www.dotnetfoundation.org/)

## <a name="contributions"></a>Contributi

Il team di .NET per Apache Spark incoraggia i contributi, sia sotto forma di registrazione di problemi che di richieste pull in GitHub. Per prima cosa, cercare un [problema esistente](https://github.com/dotnet/spark/issues). Se non si riesce a trovare un problema esistente, [aprire un nuovo problema](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).

## <a name="next-steps"></a>Passaggi successivi

Provare .NET per Apache Spark.
> [!div class="nextstepaction"]
> [Esercitazione: Introduzione a .NET per Apache Spark](./tutorials/get-started.md)

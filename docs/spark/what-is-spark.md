---
title: Che cos'è Apache Spark?
description: Informazioni sugli scenari Apache Spark e Big Data.
ms.date: 10/15/2019
ms.topic: conceptual
ms.custom: mvc
ms.openlocfilehash: ccf41f08df3c68a039210320f14219e6b6229a64
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72396236"
---
# <a name="what-is-apache-spark"></a>Che cos'è Apache Spark?

[Apache Spark](https://spark.apache.org/) è un Framework di elaborazione parallela open source che supporta l'elaborazione in memoria per migliorare le prestazioni delle applicazioni che analizzano Big Data. Le soluzioni per Big data sono progettate per gestire dati troppo grandi o complessi per i database tradizionali. Spark elabora grandi quantità di dati in memoria, il che è molto più veloce rispetto alle alternative basate su disco. 

## <a name="common-big-data-scenarios"></a>Scenari comuni di Big Data

È possibile prendere in considerazione un'architettura Big Data se è necessario archiviare ed elaborare grandi volumi di dati, trasformare i dati non strutturati o elaborare dati di streaming. Spark è un motore di elaborazione distribuito per utilizzo generico che può essere usato per diversi scenari di Big Data. 

### <a name="extract-transform-and-load-etl"></a>Estrarre, trasformare e caricare (ETL)

L' [estrazione, la trasformazione e il caricamento (ETL)](/azure/architecture/data-guide/relational-data/etl) è il processo di raccolta dei dati da una o più origini, modifica dei dati e trasferimento dei dati in un nuovo archivio dati. Esistono diversi modi per trasformare i dati, tra cui:

* Filtro
* Ordinamento
* Aggregazione
* Uso di join
* Pulizia
* Deduplicazione
* Convalida

### <a name="real-time-data-stream-processing"></a>Elaborazione del flusso di dati in tempo reale

I dati in streaming o in tempo reale sono dati in movimento. I dati di telemetria dei dispositivi, i log e i clickstream sono tutti esempi di dati di streaming. I dati in tempo reale possono essere elaborati per fornire informazioni utili, ad esempio l'analisi geospaziale, il monitoraggio remoto e il rilevamento delle anomalie. Analogamente ai dati relazionali, è possibile filtrare, aggregare e preparare i dati di streaming prima di trasferire i dati in un sink di output. Apache Spark supporta l' [elaborazione di flussi di dati in tempo reale](/azure/architecture/data-guide/big-data/real-time-processing) tramite [Spark streaming](https://spark.apache.org/streaming/). 

### <a name="batch-processing"></a>Elaborazione batch

L' [elaborazione batch](/azure/architecture/data-guide/big-data/batch-processing) è l'elaborazione di Big Data inattivi. È possibile filtrare, aggregare e preparare set di impostazioni di grandi dimensioni utilizzando processi con esecuzione prolungata in parallelo.

### <a name="machine-learning-through-mllib"></a>Apprendimento automatico tramite MLlib

Machine Learning viene usato per i problemi analitici avanzati. Il computer può usare i dati esistenti per prevedere o prevedere comportamenti, risultati e tendenze futuri. La libreria di Machine Learning di Apache Spark, [MLlib](https://spark.apache.org/mllib/), contiene diverse utilità e algoritmi di machine learning.

### <a name="graph-processing-through-graphx"></a>Elaborazione di grafi tramite GraphX

Un grafico è una raccolta di nodi collegati da bordi. È possibile utilizzare un database Graph se si dispone di dati gerarchica o di dati con relazioni interconnesse. È possibile elaborare questi dati usando l'API [graphx](https://spark.apache.org/graphx/) di Apache Spark.

### <a name="sql-and-structured-data-processing-with-spark-sql"></a>Elaborazione di dati strutturati e SQL con Spark SQL

Se si lavora con dati strutturati (formattati), è possibile usare le query SQL nell'applicazione Spark usando [Spark SQL](https://spark.apache.org/sql/).

## <a name="apache-spark-architecture"></a>Architettura Apache Spark

Apache Spark, che utilizza l'architettura master/di lavoro, dispone di tre componenti principali: driver, Executor e gestione cluster.

![Architettura Apache Spark](media/spark-architecture.png)

### <a name="driver"></a>Driver

Il driver è costituito dal programma, ad C# esempio un'app console e una sessione di Spark. La sessione Spark prende il programma e lo divide in attività più piccole gestite dagli esecutori.

### <a name="executors"></a>Esecutori

Ogni Executor, o nodo di lavoro, riceve un'attività dal driver ed esegue tale attività. Gli executor si trovano in un'entità nota come cluster.

### <a name="cluster-manager"></a>Gestione cluster

Gestione cluster comunica con il driver e gli Executor per:

- Gestisci allocazione risorse
- Gestisci divisione programmi
- Gestire l'esecuzione del programma

## <a name="language-support"></a>Supporto delle lingue

Apache Spark supporta i linguaggi di programmazione seguenti:

- Scala
- Python
- Java
- SQL
- V
- .NET

## <a name="spark-apis"></a>API Spark

Apache Spark supporta le API seguenti:

- [API Spark scala](https://spark.apache.org/docs/2.2.0/api/scala/index.html)
- [API Java Spark](https://spark.apache.org/docs/2.2.0/api/java/index.html)
- [API Python Spark](https://spark.apache.org/docs/2.2.0/api/python/index.html)
- [API R Spark](https://spark.apache.org/docs/2.2.0/api/R/index.html)
- Funzioni predefinite di [Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html)

## <a name="next-steps"></a>Passaggi successivi

Informazioni su come usare Apache Spark nell'applicazione .NET. Con .NET per Apache Spark, gli sviluppatori con esperienza .NET e la logica di business possono scrivere C# Big data F#query in e.
> [!div class="nextstepaction"]
> [Informazioni su .NET per Apache Spark](what-is-apache-spark-dotnet.md)

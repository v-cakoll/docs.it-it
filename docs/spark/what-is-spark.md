---
title: Che cos'è Apache Spark?
description: Scopri di più sugli scenari di Apache Spark e Big Data.
ms.date: 10/15/2019
ms.topic: conceptual
ms.custom: mvc
ms.openlocfilehash: 653f355d09a045feabb3dee0f5737cb691cf2dc4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73458171"
---
# <a name="what-is-apache-spark"></a>Che cos'è Apache Spark?

[Apache Spark](https://spark.apache.org/) è un framework di elaborazione parallela open source che supporta l'elaborazione in memoria per migliorare le prestazioni delle applicazioni che analizzano i Big Data. Le soluzioni Big Data sono progettate per gestire dati troppo grandi o complessi per i database tradizionali. Spark elabora grandi quantità di dati in memoria, il che è molto più veloce rispetto alle alternative basate su disco.

## <a name="common-big-data-scenarios"></a>Scenari comuni di Big Data

È possibile prendere in considerazione un'architettura Big Data se è necessario archiviare ed elaborare grandi volumi di dati, trasformare dati non strutturati o elaborare i dati in streaming. Spark è un motore di elaborazione distribuito generico che può essere utilizzato per diversi scenari di Big Data.Spark is a general-purpose distributed processing engine that can be used for several Big Data scenarios.

### <a name="extract-transform-and-load-etl"></a>ETL (Extract, Transform, and Load)

[Estrai, trasforma e carica (ETL)](/azure/architecture/data-guide/relational-data/etl) è il processo di raccolta di dati da una o più origini, la modifica dei dati e lo spostamento dei dati in un nuovo archivio dati. Esistono diversi modi per trasformare i dati, tra cui:There are several ways to transform data, including:

* Filtri
* Ordinamento
* Aggregazione
* Aggiunta
* Pulizia
* Deduplicazione
* Convalida in corso.

### <a name="real-time-data-stream-processing"></a>Elaborazione del flusso di dati in tempo reale

Lo streaming, o dati in tempo reale, sono dati in movimento. La telemetria da dispositivi IoT, weblog e clickstream sono tutti esempi di dati di streaming. I dati in tempo reale possono essere elaborati per fornire informazioni utili, come l'analisi geospaziale, il monitoraggio remoto e il rilevamento delle anomalie. Analogamente ai dati relazionali, è possibile filtrare, aggregare e preparare i dati in streaming prima di spostare i dati in un sink di output. Apache Spark supporta [l'elaborazione](/azure/architecture/data-guide/big-data/real-time-processing) del flusso di dati in tempo reale tramite [Spark Streaming](https://spark.apache.org/streaming/).

### <a name="batch-processing"></a>Elaborazione batch

[L'elaborazione batch](/azure/architecture/data-guide/big-data/batch-processing) è l'elaborazione dei Big Data inattivi. È possibile filtrare, aggregare e preparare set di dati di grandi dimensioni usando processi a esecuzione prolungata in parallelo.

### <a name="machine-learning-through-mllib"></a>Apprendimento automatico tramite MLlib

L'apprendimento automatico viene utilizzato per problemi analitici avanzati. Il computer può utilizzare i dati esistenti per prevedere o prevedere comportamenti, risultati e tendenze futuri. La libreria di apprendimento automatico di Apache Spark, [MLlib](https://spark.apache.org/mllib/), contiene diversi algoritmi e utilità di apprendimento automatico.

### <a name="graph-processing-through-graphx"></a>Elaborazione grafica tramite GraphX

Un grafico è una raccolta di nodi collegati da bordi. È possibile utilizzare un database grafico se si dispone di dati gerarchici o di dati con relazioni interconnesse. È possibile elaborare questi dati utilizzando l'API GraphX di Apache Spark.You can process this data using Apache Spark's [GraphX](https://spark.apache.org/graphx/) API.

### <a name="sql-and-structured-data-processing-with-spark-sql"></a>Elaborazione di dati SQL e strutturati con Spark SQL

Se si utilizzano dati strutturati (formattati), è possibile utilizzare query SQL nell'applicazione Spark utilizzando [Spark SQL](https://spark.apache.org/sql/).

## <a name="apache-spark-architecture"></a>Architettura Apache Spark

Apache Spark, che utilizza l'architettura master/worker, include tre componenti principali: il driver, gli esecutori e il gestore cluster.

![Architettura Apache Spark](media/spark-architecture.png)

### <a name="driver"></a>Driver

Il driver è costituito da un programma, ad esempio un'app console di C, e una sessione Spark.The driver consists of your program, like a C' console app, and a Spark session. La sessione Spark prende il programma e lo divide in attività più piccole gestite dagli esecutori.

### <a name="executors"></a>Executors

Ogni esecutore, o nodo di lavoro, riceve un'attività dal driver ed esegue tale attività. Gli esecutori risiedono in un'entità nota come cluster.

### <a name="cluster-manager"></a>Gestione cluster

Il gestore cluster comunica con il driver e gli esecutori per:

* Gestire l'allocazione delle risorse
* Gestire la divisione dei programmi
* Gestire l'esecuzione del programma

## <a name="language-support"></a>Lingue supportate

Apache Spark supporta i seguenti linguaggi di programmazione:

* Scala
* Python
* Java
* SQL
* R
* .NET

## <a name="spark-apis"></a>API Spark

Apache Spark supporta le seguenti API:

* [Spark Scala API](https://spark.apache.org/docs/2.2.0/api/scala/index.html)
* [Spark Java API](https://spark.apache.org/docs/2.2.0/api/java/index.html)
* [Spark Python API](https://spark.apache.org/docs/2.2.0/api/python/index.html)
* [Spark R API](https://spark.apache.org/docs/2.2.0/api/R/index.html)
* [Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html), funzioni incorporate

## <a name="next-steps"></a>Passaggi successivi

Informazioni su come usare Apache Spark nell'applicazione .NET. Con .NET per Apache Spark, gli sviluppatori con esperienza .NET e logica di business possono scrivere query Di Big Data in C e F.
> [!div class="nextstepaction"]
> [Che cos'è .NET per Apache Spark](what-is-apache-spark-dotnet.md)

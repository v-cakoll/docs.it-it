---
title: Librerie del framework
description: Informazioni sul modo in cui le librerie offrono implementazioni per molti tipi generali e specifici dell'app, algoritmi e funzionalità di utilità.
author: richlander
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: 7b77b6c1-8367-4602-bff3-91e4c05ac643
ms.openlocfilehash: d4444b6d080afa92a4e7fd9f30c5f9358f02f0ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159234"
---
# <a name="framework-libraries"></a>Librerie del framework

.NET ha un ampio set standard di librerie di classi, definite librerie di classi di base (set di base) o librerie di classi di framework (set completo). Le librerie offrono implementazioni per molti tipi generali e specifici dell'app, algoritmi e funzionalità di utilità. Le librerie commerciali e delle community sono basati sulle librerie di classi di framework e offrono librerie disponibili sul mercato facili da usare per un ampio set di attività di elaborazione.

Con ogni implementazione di .NET viene offerto un sottoinsieme di queste librerie. Le API delle librerie di classi base sono incluse in qualsiasi implementazione di .NET, poiché sono richieste dagli sviluppatori e necessarie all'esecuzione delle librerie comunemente diffuse. Le librerie specifiche delle app di livello superiore alle librerie di classi base, ad esempio ASP.NET, non saranno disponibili in tutte le implementazioni .NET.

## <a name="base-class-libraries"></a>Librerie di classi base

Le librerie di classi base offrono i tipi fondamentali e le funzionalità di utilità e sono la base per tutte le altre librerie di classi .NET. Hanno lo scopo di offrire implementazioni molto generali senza eccezioni ai carichi di lavoro. Le prestazioni sono sempre un fattore importante, poiché le app potrebbero preferire criteri specifici, ad esempio bassa latenza o velocità elevata oppure memoria minima o basso utilizzo della CPU. Queste librerie in genere sono destinate ad alte prestazioni e rappresentano un compromesso operativo tra i vari livelli di esecuzione. Per la maggior parte delle app, la loro implementazione ha dato risultati abbastanza positivi.

## <a name="primitive-types"></a>Tipi primitivi

.NET include un set di tipi primitivi, che vengono usati in tutti i programmi (a diversi livelli). Questi tipi contengono dati, ad esempio numeri, stringhe, byte e oggetti arbitrari. Il linguaggio C# include parole chiave per questi tipi. Un set di esempio di questi tipi è elencato di seguito, con le parole chiave del linguaggio C# corrispondenti.

* <xref:System.Object?displayProperty=nameWithType> ([object](../csharp/language-reference/builtin-types/reference-types.md#the-object-type)): classe di base principale nel sistema di tipo CLR. È la radice della gerarchia dei tipi.
* <xref:System.Int16?displayProperty=nameWithType> ([short](../csharp/language-reference/builtin-types/integral-numeric-types.md)): tipo intero con segno a 16 bit. È anche disponibile il tipo <xref:System.UInt16> senza segno.
* <xref:System.Int32?displayProperty=nameWithType> ([int](../csharp/language-reference/builtin-types/integral-numeric-types.md)): tipo intero con segno a 32 bit. È anche disponibile il tipo [UInt32](../csharp/language-reference/builtin-types/integral-numeric-types.md) senza segno.
* <xref:System.Single?displayProperty=nameWithType> ([float](../csharp/language-reference/builtin-types/floating-point-numeric-types.md)): tipo a virgola mobile a 32 bit.
* <xref:System.Decimal?displayProperty=nameWithType> ([decimal](../csharp/language-reference/builtin-types/floating-point-numeric-types.md)): tipo decimale a 128 bit.
* <xref:System.Byte?displayProperty=nameWithType> ([byte](../csharp/language-reference/builtin-types/integral-numeric-types.md)): tipo intero senza segno a 8 bit che rappresenta un byte di memoria.
* <xref:System.Boolean?displayProperty=nameWithType>([bool](../csharp/language-reference/builtin-types/bool.md)) - Tipo `true` `false`booleano che rappresenta o .
* <xref:System.Char?displayProperty=nameWithType> ([char](../csharp/language-reference/builtin-types/char.md)): tipo numerico a 16 bit che rappresenta un carattere Unicode.
* <xref:System.String?displayProperty=nameWithType> ([string](../csharp/language-reference/builtin-types/reference-types.md#the-string-type)): rappresenta una serie di caratteri. Diverso dal tipo `char[]`, ma consente l'indicizzazione in ogni singolo `char` di `string`.

## <a name="data-structures"></a>strutture di dati

.NET include un insieme di strutture di dati che sono alla base di quasi tutte le applicazioni .NET. Si tratta principalmente di raccolte, ma sono inclusi anche altri tipi.

* <xref:System.Array>: rappresenta una matrice di oggetti fortemente tipizzati accessibile con l'indice. Per struttura, ha una dimensione fissa.
* <xref:System.Collections.Generic.List%601>: rappresenta un elenco di oggetti fortemente tipizzati accessibile per indice. Viene ridimensionato automaticamente secondo le necessità.
* <xref:System.Collections.Generic.Dictionary%602>: rappresenta una raccolta di valori indicizzati da una chiave. I valori sono accessibili tramite chiave. Viene ridimensionato automaticamente secondo le necessità.
* <xref:System.Uri>: fornisce una rappresentazione in forma di oggetto di un identificatore URI (uniform resource identifier) e un pratico accesso alle parti dell'URI.
* <xref:System.DateTime>: rappresenta un istante di tempo, in genere espresso come data e ora del giorno.

## <a name="utility-apis"></a>API di utilità

.NET include un set di API di utilità che offre funzionalità per molte attività importanti.

* <xref:System.Net.Http.HttpClient>: un'API per inviare richieste HTTP e ricevere risposte HTTP da una risorsa identificata da un URI.
* <xref:System.Xml.Linq.XDocument>: un'API per il caricamento e l'esecuzione di query su documenti XML con LINQ.
* <xref:System.IO.StreamReader> : Un'API per la lettura dei file.
* <xref:System.IO.StreamWriter> : Un'API per la scrittura dei file.

## <a name="app-model-apis"></a>API dei modelli per App

Ci sono molti modelli per app, offerti da diverse società, che possono essere usati con .NET.

* [ASP.NET](https://www.asp.net): offre un framework Web per la creazione di siti Web e servizi. Supportato in Windows, Linux e macOS (dipende dalla versione ASP.NET).

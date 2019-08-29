---
title: Esecuzione di operazioni aritmetiche con date e ore
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET Framework], arithmetic operations
- dates [.NET Framework], arithmetic operations
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], comparing
- DateTime structure, arithmetic operations
- DateTimeOffset structure, arithmetic operations
ms.assetid: 87c7ddf2-f15e-48af-8602-b3642237e6d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01314c160fc531f5c97a1369c8444dce7f590d53
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106606"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Esecuzione di operazioni aritmetiche con date e ore

Sebbene entrambe le <xref:System.DateTime> <xref:System.DateTimeOffset> strutture e forniscano membri che eseguono operazioni aritmetiche sui rispettivi valori, i risultati delle operazioni aritmetiche sono molto diversi. In questo argomento vengono esaminate tali differenze, in relazione ai gradi di riconoscimento del fuso orario nei dati di data e ora e viene illustrato come eseguire operazioni complete di riconoscimento del fuso orario utilizzando i dati di data e ora.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Confronti e operazioni aritmetiche con valori DateTime

La <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> proprietà consente di <xref:System.DateTimeKind> assegnare un valore alla data e all'ora per indicare se rappresenta l'ora locale, l'ora UTC (Coordinated Universal Time) o l'ora in un fuso orario non specificato. Queste informazioni limitate sul fuso orario vengono tuttavia ignorate durante il confronto o l'esecuzione di operazioni <xref:System.DateTimeKind> aritmetiche di data e ora sui valori. Questa condizione è illustrata nell'esempio seguente, in cui si confronta l'ora locale corrente con l'ora UTC corrente.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

Il <xref:System.DateTime.CompareTo%28System.DateTime%29> metodo indica che l'ora locale è precedente a (o minore di) l'ora UTC e l'operazione di sottrazione indica che la differenza tra l'ora UTC e l'ora locale per un sistema negli Stati Uniti Pacifico (Stati Uniti) è sette ore. Ma poiché questi due valori indicano rappresentazioni diverse di un singolo momento, è chiaro in questo caso che l'intervallo di tempo è completamente attribuibile all'offset del fuso orario locale rispetto all'ora UTC.

Più in generale, <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> la proprietà non influisce sui risultati restituiti <xref:System.DateTime.Kind> dai metodi di confronto e aritmetici (come indica il confronto tra due identici momenti), anche se può influire sull'interpretazione di tali risultati. Ad esempio:

- Il risultato di qualsiasi operazione aritmetica eseguita su due valori di data e <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> ora le cui <xref:System.DateTimeKind> proprietà corrispondono entrambe all'intervallo di tempo effettivo tra i due valori. Analogamente, il confronto di due valori di data e ora di questo tipo riflette esattamente la relazione tra le ore.

- Risultato di qualsiasi operazione aritmetica o di confronto eseguita su due valori di data e <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> ora le cui <xref:System.DateTimeKind> proprietà sono uguali o su due valori di data <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> e ora con valori di proprietà diversi riflettono la differenza nel tempo di clock tra i due valori.

- Le operazioni aritmetiche o di confronto sui valori locali di data e ora non considerano se un particolare valore è ambiguo o non valido e non tengono conto dell'effetto di eventuali regole di regolazione risultanti dalla transizione del fuso orario locale a o dall'ora legale.

- Qualsiasi operazione che confronta o calcola la differenza tra ora UTC e ora locale include un intervallo di tempo uguale all'offset del fuso orario locale rispetto all'ora UTC nel risultato.

- Qualsiasi operazione che confronta o calcola la differenza tra un'ora non specificata e l'ora UTC o l'ora locale riflette l'ora dell'orologio. Le differenze di fuso orario non vengono considerate e il risultato non riflette l'applicazione delle regole di regolazione del fuso orario.

- Qualsiasi operazione che confronta o calcola la differenza tra due ore non specificate può includere un intervallo sconosciuto che riflette la differenza di orario in due fusi orari diversi.

Esistono molti scenari in cui le differenze di fuso orario non influiscono sui calcoli di data e ora (per una descrizione di alcuni di questi, vedere [scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)) o in cui il contesto dei dati di data e ora definisce il significato delle operazioni aritmetiche o di confronto.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Confronti e operazioni aritmetiche con i valori DateTimeOffset

Un <xref:System.DateTimeOffset> valore include non solo una data e un'ora, ma anche un offset che definisce in modo univoco tale data e ora rispetto all'ora UTC. In questo modo è possibile definire l'uguaglianza in modo diverso <xref:System.DateTimeOffset> rispetto ai valori. Mentre <xref:System.DateTime> i valori sono uguali se hanno lo stesso valore di data e ora <xref:System.DateTimeOffset> , i valori sono uguali se si riferiscono entrambi allo stesso momento. In questo modo <xref:System.DateTimeOffset> un valore risulta più accurato e meno necessario per l'interpretazione quando viene usato nei confronti e nella maggior parte delle operazioni aritmetiche che determinano l'intervallo tra due date e ore. Nell'esempio seguente, che è l' <xref:System.DateTimeOffset> equivalente dell'esempio precedente in cui vengono confrontati <xref:System.DateTimeOffset> i valori locali e UTC, viene illustrata questa differenza di comportamento.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

In questo esempio, il <xref:System.DateTimeOffset.CompareTo%2A> metodo indica che l'ora locale corrente e l'ora UTC corrente sono uguali e la sottrazione di <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> valori indica che la differenza tra i due orari è <xref:System.TimeSpan.Zero?displayProperty=nameWithType>.

La limitazione principale dell'uso <xref:System.DateTimeOffset> dei valori nell'aritmetica di data e ora <xref:System.DateTimeOffset> è che anche se i valori hanno una certa consapevolezza del fuso orario, non sono completamente compatibili con il fuso orario. Anche se <xref:System.DateTimeOffset> l'offset del valore riflette l'offset di un fuso orario rispetto all' <xref:System.DateTimeOffset> ora UTC quando a una variabile viene assegnato per la prima volta un valore, questo viene dissociato dal fuso orario successivamente. Poiché non è più associato direttamente a un'ora identificabile, l'aggiunta e la sottrazione degli intervalli di data e ora non considerano le regole di regolazione del fuso orario.

A titolo esemplificativo, la transizione all'ora legale negli Stati Uniti, ora solare fuso centrale, avviene alle 2.00 del 9 marzo 2008. Ciò significa che l'aggiunta di un intervallo di due ore e mezzo all'1.30 del 9 marzo 2008 nel fuso orario standard centrale deve generare una data e un'ora equivalente alle 5.00 del 9 marzo 2008. Tuttavia, come mostrato nell'esempio seguente, il risultato dell'addizione è 4.00 del 9 marzo 2008. Si noti che il risultato di questa operazione rappresenta il momento corretto, sebbene non sia l'ora nel fuso orario che interessa (ovvero, non presenta l'offset previsto per il fuso orario).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Operazioni aritmetiche con ore in fusi orari

La <xref:System.TimeZoneInfo> classe include un numero di metodi di conversione che applicano automaticamente le regolazioni quando convertono gli orari da un fuso orario a un altro. tra cui:

- I <xref:System.TimeZoneInfo.ConvertTime%2A> metodi <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> e, che convertono gli orari tra due fusi orari.

- I <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> metodi <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> e, che convertono l'ora in un determinato fuso orario in ora UTC, o convertono l'ora UTC all'ora in un determinato fuso orario.

Per informazioni dettagliate, vedere [conversione degli orari tra fusi](../../../docs/standard/datetime/converting-between-time-zones.md)orari.

La <xref:System.TimeZoneInfo.ConvertTimeToUtc(System.DateTime)> classe non fornisce metodi che applicano automaticamente regole di regolazione quando si eseguono operazioni aritmetiche di data e ora. Tuttavia, è possibile convertire l'ora in un fuso orario in ora UTC, eseguendo l'operazione aritmetica, e quindi convertirla di nuovo da ora UTC a ora nel fuso orario. Per informazioni dettagliate, vedere [Procedura: Usare fusi orari nell'aritmetica](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)di data e ora.

Ad esempio, il codice seguente è simile al codice precedente che ha aggiunto due ore e mezzo alle 2.00 del 9 marzo 2008. Tuttavia, perché il codice converte un'ora solare nel fuso orario centrale in ora UTC prima di eseguire un'operazione aritmetica con data e ora e quindi converte di nuovo il risultato da ora UTC in ora solare nel fuso orario centrale, l'ora risultante riflette la transizione dell'ora solare nel fuso orario centrale all'ora legale.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
- [Procedura: Usare fusi orari nell'aritmetica di data e ora](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)

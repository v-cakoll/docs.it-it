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
ms.openlocfilehash: c212397f99bd09195f298d7d704c879705b14f02
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281544"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Esecuzione di operazioni aritmetiche con date e ore

Sebbene entrambe le <xref:System.DateTime> strutture e <xref:System.DateTimeOffset> forniscano membri che eseguono operazioni aritmetiche sui rispettivi valori, i risultati delle operazioni aritmetiche sono molto diversi. In questo argomento vengono esaminate tali differenze, in relazione ai gradi di riconoscimento del fuso orario nei dati di data e ora e viene illustrato come eseguire operazioni complete di riconoscimento del fuso orario utilizzando i dati di data e ora.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Confronti e operazioni aritmetiche con valori DateTime

La <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> proprietà consente di <xref:System.DateTimeKind> assegnare un valore alla data e all'ora per indicare se rappresenta l'ora locale, l'ora UTC (Coordinated Universal Time) o l'ora in un fuso orario non specificato. Queste informazioni limitate sul fuso orario vengono tuttavia ignorate durante il confronto o l'esecuzione di operazioni aritmetiche di data e ora sui <xref:System.DateTimeKind> valori. Questa condizione è illustrata nell'esempio seguente, in cui si confronta l'ora locale corrente con l'ora UTC corrente.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

Tramite il metodo <xref:System.DateTime.CompareTo%28System.DateTime%29> viene indicato che l'ora locale è più indietro rispetto all'ora UTC e tramite l'operazione di sottrazione viene indicata che la differenza tra l'ora UTC e l'ora locale per un sistema nel fuso orario standard del Pacifico (Stati Uniti) è di sette ore. Tuttavia, poiché questi due valori forniscono rappresentazioni diverse di un singolo momento, è chiaro in questo caso che l'intervallo di tempo è completamente attribuibile all'offset del fuso orario locale rispetto all'ora UTC.

Più in generale, la <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> proprietà non influisce sui risultati restituiti dai <xref:System.DateTime.Kind> metodi di confronto e aritmetici (come indica il confronto tra due identici momenti), anche se può influire sull'interpretazione di tali risultati. Ad esempio:

- Il risultato di qualsiasi operazione aritmetica eseguita su due valori di data e ora le cui <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> proprietà corrispondono entrambe <xref:System.DateTimeKind> all'intervallo di tempo effettivo tra i due valori. Analogamente, il confronto di due valori di data e ora di questo tipo riflette esattamente la relazione tra le ore.

- Risultato di qualsiasi operazione aritmetica o di confronto eseguita su due valori di data e ora le cui <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> proprietà sono uguali <xref:System.DateTimeKind> o su due valori di data e ora con <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> valori di proprietà diversi riflettono la differenza nel tempo di clock tra i due valori.

- Le operazioni aritmetiche o di confronto sui valori locali di data e ora non considerano se un particolare valore è ambiguo o non valido e non tengono conto dell'effetto di eventuali regole di regolazione risultanti dalla transizione del fuso orario locale a o dall'ora legale.

- Qualsiasi operazione che confronta o calcola la differenza tra ora UTC e ora locale include un intervallo di tempo uguale all'offset del fuso orario locale rispetto all'ora UTC nel risultato.

- Qualsiasi operazione che confronta o calcola la differenza tra un'ora non specificata e l'ora UTC o l'ora locale riflette l'ora dell'orologio. Le differenze di fuso orario non vengono considerate e il risultato non riflette l'applicazione delle regole di regolazione del fuso orario.

- Qualsiasi operazione che confronta o calcola la differenza tra due ore non specificate può includere un intervallo sconosciuto che riflette la differenza di orario in due fusi orari diversi.

Esistono molti scenari in cui le differenze di fuso orario non influiscono sui calcoli di data e ora (per una descrizione di alcuni di questi, vedere [scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo](choosing-between-datetime.md)) o in cui il contesto dei dati di data e ora definisce il significato delle operazioni aritmetiche o di confronto.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Confronti e operazioni aritmetiche con i valori DateTimeOffset

Un <xref:System.DateTimeOffset> valore include non solo una data e un'ora, ma anche un offset che definisce in modo univoco tale data e ora rispetto all'ora UTC. In questo modo è possibile definire l'uguaglianza in modo diverso rispetto ai <xref:System.DateTimeOffset> valori. Mentre i <xref:System.DateTime> valori sono uguali se hanno lo stesso valore di data e ora, <xref:System.DateTimeOffset> i valori sono uguali se si riferiscono entrambi allo stesso momento. In questo modo un <xref:System.DateTimeOffset> valore risulta più accurato e meno necessario per l'interpretazione quando viene usato nei confronti e nella maggior parte delle operazioni aritmetiche che determinano l'intervallo tra due date e ore. Nell'esempio seguente, che è l' <xref:System.DateTimeOffset> equivalente dell'esempio precedente in cui vengono confrontati <xref:System.DateTimeOffset> i valori locali e UTC, viene illustrata questa differenza di comportamento.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

In questo esempio, il <xref:System.DateTimeOffset.CompareTo%2A> metodo indica che l'ora locale corrente e l'ora UTC corrente sono uguali e la sottrazione di <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> valori indica che la differenza tra i due orari è <xref:System.TimeSpan.Zero?displayProperty=nameWithType> .

La limitazione principale dell'uso dei <xref:System.DateTimeOffset> valori nell'aritmetica di data e ora è che anche se <xref:System.DateTimeOffset> i valori hanno una certa consapevolezza del fuso orario, non sono completamente compatibili con il fuso orario. Anche se l' <xref:System.DateTimeOffset> offset del valore riflette l'offset di un fuso orario rispetto all'ora UTC quando a una <xref:System.DateTimeOffset> variabile viene assegnato per la prima volta un valore, questo viene dissociato dal fuso orario successivamente. Poiché non è più associato direttamente a un'ora identificabile, l'aggiunta e la sottrazione degli intervalli di data e ora non considerano le regole di regolazione del fuso orario.

Per illustrare, la transizione all'ora legale nel fuso orario standard degli Stati Uniti si verifica alle ore 2:00. del 9 marzo 2008. Ciò significa che l'aggiunta di un intervallo di due ore e mezzo all'1.30 del 9 marzo 2008 nel fuso orario standard centrale deve generare una data e un'ora equivalente alle 5.00 del 9 marzo 2008. Tuttavia, come mostrato nell'esempio seguente, il risultato dell'addizione è 4.00 del 9 marzo 2008. Si noti che il risultato di questa operazione rappresenta il momento corretto, sebbene non sia l'ora nel fuso orario a cui si è interessati (ovvero, non ha la differenza di fuso orario prevista).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Operazioni aritmetiche con ore in fusi orari

La <xref:System.TimeZoneInfo> classe include un numero di metodi di conversione che applicano automaticamente le regolazioni quando convertono gli orari da un fuso orario a un altro. tra cui:

- I <xref:System.TimeZoneInfo.ConvertTime%2A> <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> metodi e, che convertono gli orari tra due fusi orari.

- I <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> metodi e, che convertono l'ora in un determinato fuso orario in ora UTC, o convertono l'ora UTC all'ora in un determinato fuso orario.

Per informazioni dettagliate, vedere [conversione degli orari tra fusi](converting-between-time-zones.md)orari.

La <xref:System.TimeZoneInfo> classe non fornisce metodi che applicano automaticamente regole di regolazione quando si eseguono operazioni aritmetiche di data e ora. Tuttavia, è possibile convertire l'ora in un fuso orario in ora UTC, eseguendo l'operazione aritmetica, e quindi convertirla di nuovo da ora UTC a ora nel fuso orario. Per informazioni dettagliate, vedere [procedura: usare fusi orari nell'aritmetica di data e ora](use-time-zones-in-arithmetic.md).

Ad esempio, il codice seguente è simile al codice precedente che ha aggiunto due ore e mezzo alle 2.00 del 9 marzo 2008. Tuttavia, perché il codice converte un'ora solare nel fuso orario centrale in ora UTC prima di eseguire un'operazione aritmetica con data e ora e quindi converte di nuovo il risultato da ora UTC in ora solare nel fuso orario centrale, l'ora risultante riflette la transizione dell'ora solare nel fuso orario centrale all'ora legale.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](index.md)
- [Procedura: utilizzare fusi orari nell'aritmetica di data e ora](use-time-zones-in-arithmetic.md)

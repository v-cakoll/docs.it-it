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
ms.openlocfilehash: 0db0331620da8337930bfacf5d1bbd9913647afa
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344180"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Esecuzione di operazioni aritmetiche con date e ore

Anche se <xref:System.DateTime> sia <xref:System.DateTimeOffset> la strutture e forniscono membri che eseguono operazioni aritmetiche sui loro valori, i risultati delle operazioni aritmetiche sono molto diversi. In questo argomento vengono esaminate queste differenze, vengono correlate ai gradi di riconoscimento del fuso orario nei dati di data e ora e viene illustrato come eseguire operazioni completamente in grado di riconoscere il fuso orario usando dati di data e ora.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Confronti e operazioni aritmetiche con valori DateTimeComparisons and arithmetic operations with DateTime values

La <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> proprietà <xref:System.DateTimeKind> consente di assegnare un valore alla data e all'ora per indicare se rappresenta l'ora locale, l'ora UTC (Coordinated Universal Time) o l'ora in un fuso orario non specificato. Tuttavia, queste informazioni limitate sul fuso orario vengono <xref:System.DateTimeKind> ignorate quando si confrontano o si eseguono operazioni aritmetiche di data e ora sui valori. Questa condizione è illustrata nell'esempio seguente, in cui si confronta l'ora locale corrente con l'ora UTC corrente.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

Tramite il metodo <xref:System.DateTime.CompareTo%28System.DateTime%29> viene indicato che l'ora locale è più indietro rispetto all'ora UTC e tramite l'operazione di sottrazione viene indicata che la differenza tra l'ora UTC e l'ora locale per un sistema nel fuso orario standard del Pacifico (Stati Uniti) è di sette ore. Ma poiché questi due valori forniscono rappresentazioni diverse di un singolo punto nel tempo, è chiaro in questo caso che l'intervallo di tempo è completamente attribuibile all'offset del fuso orario locale dall'ora UTC.

Più in <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> generale, la proprietà non <xref:System.DateTime.Kind> influisce sui risultati restituiti dai metodi di confronto e aritmetici (come indica il confronto di due punti identici nel tempo), anche se può influenzare l'interpretazione di tali risultati. Ad esempio:

- Il risultato di qualsiasi operazione aritmetica <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> eseguita <xref:System.DateTimeKind> su due valori di data e ora le cui proprietà sono uguali riflette l'intervallo di tempo effettivo tra i due valori. Analogamente, il confronto di due valori di data e ora di questo tipo riflette esattamente la relazione tra le ore.

- Il risultato di qualsiasi operazione aritmetica o <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> di confronto <xref:System.DateTimeKind> eseguita su due valori <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> di data e ora le cui proprietà sono uguali o su due valori di data e ora con valori di proprietà diversi riflette la differenza nell'ora dell'orologio tra i due valori.

- Le operazioni aritmetiche o di confronto sui valori locali di data e ora non considerano se un particolare valore è ambiguo o non valido e non tengono conto dell'effetto di eventuali regole di regolazione risultanti dalla transizione del fuso orario locale a o dall'ora legale.

- Qualsiasi operazione che confronta o calcola la differenza tra ora UTC e ora locale include un intervallo di tempo uguale all'offset del fuso orario locale rispetto all'ora UTC nel risultato.

- Qualsiasi operazione che confronta o calcola la differenza tra un'ora non specificata e l'ora UTC o l'ora locale riflette l'ora dell'orologio. Le differenze di fuso orario non vengono considerate e il risultato non riflette l'applicazione delle regole di regolazione del fuso orario.

- Qualsiasi operazione che confronta o calcola la differenza tra due ore non specificate può includere un intervallo sconosciuto che riflette la differenza di orario in due fusi orari diversi.

Esistono molti scenari in cui le differenze di fuso orario non influiscono sui calcoli di data e ora (per una descrizione di alcuni di questi, vedere [Scelta tra DateTime, DateTimeOffset, TimeSpan, e Time-oneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)) o in cui il contesto dei dati di data e ora definisce il significato delle operazioni di confronto o aritmetiche.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Confronti e operazioni aritmetiche con valori DateTimeOffset

Un <xref:System.DateTimeOffset> valore include non solo una data e un'ora, ma anche un offset che definisce in modo non ambiguo tale data e ora rispetto all'ora UTC. In questo modo è possibile definire l'uguaglianza in modo leggermente diverso rispetto ai <xref:System.DateTimeOffset> valori. Mentre <xref:System.DateTime> i valori sono uguali se hanno <xref:System.DateTimeOffset> lo stesso valore di data e ora, i valori sono uguali se entrambi fanno riferimento allo stesso punto nel tempo. Questo rende <xref:System.DateTimeOffset> un valore più preciso e meno bisognoso di interpretazione quando viene utilizzato nei confronti e nella maggior parte delle operazioni aritmetiche che determinano l'intervallo tra due date e ore. Nell'esempio seguente, <xref:System.DateTimeOffset> che è l'equivalente dell'esempio precedente che ha confrontato i valori locali e UTC, <xref:System.DateTimeOffset> viene illustrata questa differenza nel comportamento.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

In questo esempio, il <xref:System.DateTimeOffset.CompareTo%2A> metodo indica che l'ora locale corrente e <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> l'ora UTC corrente sono uguali <xref:System.TimeSpan.Zero?displayProperty=nameWithType>e la sottrazione di valori indica che la differenza tra le due volte è .

La limitazione <xref:System.DateTimeOffset> principale dell'utilizzo di valori <xref:System.DateTimeOffset> nell'aritmetica di data e ora è che, sebbene i valori abbiano una certa consapevolezza del fuso orario, non sono completamente in grado di riconoscere il fuso orario. Anche <xref:System.DateTimeOffset> se l'offset del valore riflette l'offset <xref:System.DateTimeOffset> di un fuso orario dall'ora UTC quando a una variabile viene assegnato per la prima volta un valore, viene dissociato dal fuso orario successivo. Poiché non è più associato direttamente a un'ora identificabile, l'aggiunta e la sottrazione degli intervalli di data e ora non considerano le regole di regolazione del fuso orario.

Per illustrare, la transizione all'ora legale nel fuso orario standard centrale degli Stati Uniti si verifica alle 2:00. del 9 marzo 2008. Ciò significa che l'aggiunta di un intervallo di due ore e mezzo all'1.30 del 9 marzo 2008 nel fuso orario standard centrale deve generare una data e un'ora equivalente alle 5.00 del 9 marzo 2008. Tuttavia, come mostrato nell'esempio seguente, il risultato dell'addizione è 4.00 del 9 marzo 2008. Si noti che il risultato di questa operazione rappresenta il punto nel tempo corretto, anche se non è l'ora nel fuso orario in cui siamo interessati (vale a dire, non ha l'offset del fuso orario previsto).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Operazioni aritmetiche con orari nei fusi orari

La <xref:System.TimeZoneInfo> classe include una serie di metodi di conversione che applicano automaticamente le regolazioni quando convertono gli orari da un fuso orario a un altro. tra cui:

- I <xref:System.TimeZoneInfo.ConvertTime%2A> <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> metodi e, che convertono gli orari tra due fusi orari qualsiasi.

- I <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> metodi e , che convertono l'ora in un particolare fuso orario in UTC, o convertono l'ora UTC nell'ora di un particolare fuso orario.

Per informazioni dettagliate, vedere [Conversione degli orari tra fusi orari.](../../../docs/standard/datetime/converting-between-time-zones.md)

La <xref:System.TimeZoneInfo> classe non fornisce metodi che applicano automaticamente le regole di regolazione quando si eseguono operazioni aritmetiche su data e ora. Tuttavia, è possibile convertire l'ora in un fuso orario in ora UTC, eseguendo l'operazione aritmetica, e quindi convertirla di nuovo da ora UTC a ora nel fuso orario. Per informazioni dettagliate, vedere [Procedura: Utilizzare fusi orari nell'aritmetica](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)di data e ora .

Ad esempio, il codice seguente è simile al codice precedente che ha aggiunto due ore e mezzo alle 2.00 del 9 marzo 2008. Tuttavia, perché il codice converte un'ora solare nel fuso orario centrale in ora UTC prima di eseguire un'operazione aritmetica con data e ora e quindi converte di nuovo il risultato da ora UTC in ora solare nel fuso orario centrale, l'ora risultante riflette la transizione dell'ora solare nel fuso orario centrale all'ora legale.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
- [Procedura: Utilizzare i fusi orari nell'aritmetica di data e oraHow to: Use time zones in date and time arithmetic](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)

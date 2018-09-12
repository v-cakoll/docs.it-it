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
ms.openlocfilehash: c2a50823b812541786cf1bebfd6b1262ce2e9314
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44708426"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Esecuzione di operazioni aritmetiche con date e ore

Sebbene sia la <xref:System.DateTime> e il <xref:System.DateTimeOffset> strutture forniscano membri che eseguono operazioni aritmetiche sui relativi valori, i risultati delle operazioni aritmetiche sono molto diversi. In questo argomento vengono esaminate tali differenze, relazione alla presenza di fuso orario nei dati di data e ora e descrive come eseguire completamente operazioni compatibili con fuso orario usando i dati di data e ora.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Confronti e operazioni aritmetiche con i valori DateTime

Il <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> proprietà consente a un <xref:System.DateTimeKind> valore da assegnare alla data e ora per indicare se rappresenta l'ora locale, Coordinated Universal Time (UTC) o l'ora in un fuso orario non specificato. Tuttavia, queste informazioni limitate fuso orario viene ignorate durante il confronto o l'esecuzione di data e ora aritmetica su <xref:System.DateTimeKind> valori. Questa condizione è illustrata nell'esempio seguente, in cui si confronta l'ora locale corrente con l'ora UTC corrente.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

Il <xref:System.DateTime.CompareTo%28System.DateTime%29> metodo segnala che l'ora locale è precedente a (o minore di), l'ora UTC e l'operazione di sottrazione indica che la differenza tra ora UTC e l'ora locale per un sistema in Stati Uniti Pacifico (Stati Uniti) è sette ore. Ma poiché questi due valori indicano rappresentazioni diverse di un singolo momento, è chiaro in questo caso che l'intervallo di tempo è completamente attribuibile all'offset del fuso orario locale rispetto all'ora UTC.

Più in generale, il <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> proprietà influisce sui risultati restituiti da <xref:System.DateTime.Kind> metodi di confronto e aritmetici (come indica il confronto tra due identici momenti), anche se può influire sull'interpretazione dei risultati. Ad esempio:

* Il risultato di qualsiasi operazione aritmetica eseguita su due valori di data e ora la cui proprietà <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> le proprietà sono uguali <xref:System.DateTimeKind> riflette l'intervallo di tempo effettivo tra i due valori. Analogamente, il confronto di due valori di data e ora di questo tipo riflette esattamente la relazione tra le ore.

* Il risultato di qualsiasi operazione aritmetica o di confronto eseguita su due valori di data e ora la cui proprietà <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> le proprietà sono uguali <xref:System.DateTimeKind> oppure su due valori di data e ora con diversi <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> i valori delle proprietà riflette la differenza di orario tra i due valori.

* Le operazioni aritmetiche o di confronto sui valori locali di data e ora non considerano se un particolare valore è ambiguo o non valido e non tengono conto dell'effetto di eventuali regole di regolazione risultanti dalla transizione del fuso orario locale a o dall'ora legale.

* Qualsiasi operazione che confronta o calcola la differenza tra ora UTC e ora locale include un intervallo di tempo uguale all'offset del fuso orario locale rispetto all'ora UTC nel risultato.

* Qualsiasi operazione che confronta o calcola la differenza tra un'ora non specificata e l'ora UTC o l'ora locale riflette l'ora dell'orologio. Le differenze di fuso orario non vengono considerate e il risultato non riflette l'applicazione delle regole di regolazione del fuso orario.

* Qualsiasi operazione che confronta o calcola la differenza tra due ore non specificate può includere un intervallo sconosciuto che riflette la differenza di orario in due fusi orari diversi.

Esistono molti scenari nel fuso orario in cui le differenze non influiscono sui calcoli di data e ora (per una discussione su alcune di queste, vedere [scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)) o in cui il contesto di data e ora di dati definiscono il significato delle operazioni di confronto o aritmetici.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Confronti e operazioni aritmetiche con i valori DateTimeOffset

Oggetto <xref:System.DateTimeOffset> valore include non solo una data e ora, ma anche un offset che definisce in modo univoco tale data e ora rispetto all'ora UTC. In questo modo è possibile definire l'uguaglianza in modo diverso rispetto a <xref:System.DateTimeOffset> valori. Considerando <xref:System.DateTime> i valori sono uguali se hanno la stessa data e ora, <xref:System.DateTimeOffset> valori sono uguali se entrambe si riferiscono allo stesso punto nel tempo. In questo modo un <xref:System.DateTimeOffset> valore più preciso e meno soggetto a interpretazione quando utilizzata nei confronti e nella maggior parte delle operazioni aritmetiche che determinano l'intervallo tra due date e ore. L'esempio seguente, che è il <xref:System.DateTimeOffset> equivalente all'esempio precedente che confrontato locali e UTC <xref:System.DateTimeOffset> valori, viene illustrata questa differenza nel comportamento.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

In questo esempio, il <xref:System.DateTimeOffset.CompareTo%2A> metodo indica che l'ora locale corrente e l'ora UTC corrente sono uguali e la sottrazione del <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> valori indica che la differenza tra i due orari è <xref:System.TimeSpan.Zero?displayProperty=nameWithType>.

La limitazione principale dell'utilizzo <xref:System.DateTimeOffset> valori di data e ora aritmetico è che sebbene <xref:System.DateTimeOffset> valori hanno fuso orario, non sono completamente fuso orario. Anche se il <xref:System.DateTimeOffset> riflette l'offset del valore di offset del fuso orario rispetto all'ora UTC quando un <xref:System.DateTimeOffset> variabile viene assegnato un valore, l'associazione viene il fuso orario successivamente. Poiché non è più associato direttamente a un'ora identificabile, l'aggiunta e la sottrazione degli intervalli di data e ora non considerano le regole di regolazione del fuso orario.

A titolo esemplificativo, la transizione all'ora legale negli Stati Uniti, ora solare fuso centrale, avviene alle 2.00 del 9 marzo 2008. Ciò significa che l'aggiunta di un intervallo di due ore e mezzo all'1.30 del 9 marzo 2008 nel fuso orario standard centrale deve generare una data e un'ora equivalente alle 5.00 del 9 marzo 2008. Tuttavia, come mostrato nell'esempio seguente, il risultato dell'addizione è 4.00 del 9 marzo 2008. Si noti che il risultato di questa operazione rappresenta il momento corretto, sebbene non sia l'ora nel fuso orario che interessa (ovvero, non presenta l'offset previsto per il fuso orario).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Operazioni aritmetiche con ore in fusi orari

Il <xref:System.TimeZoneInfo> classe include una serie di metodi di conversione applicate automaticamente le regolazioni quando si convertono le ore da un fuso orario a un altro. tra cui:

* Il <xref:System.TimeZoneInfo.ConvertTime%2A> e <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> metodi che convertono le ore tra due fusi orari.

* Il <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> e <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> metodi, che convertono l'ora in un determinato fuso orario in ora UTC o convertono l'ora UTC nell'ora di un determinato fuso orario.

Per informazioni dettagliate, vedere [conversione degli orari tra fusi orari](../../../docs/standard/datetime/converting-between-time-zones.md).

Il <xref:System.TimeZoneInfo.ConvertTimeToUtc(System.DateTime)> classe non fornisce metodi che applicano automaticamente regole di regolazione quando si esegue Data e ora aritmetico. Tuttavia, è possibile convertire l'ora in un fuso orario in ora UTC, eseguendo l'operazione aritmetica, e quindi convertirla di nuovo da ora UTC a ora nel fuso orario. Per informazioni dettagliate, vedere [procedura: usare fusi orari nella data e ora aritmetico](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md).

Ad esempio, il codice seguente è simile al codice precedente che ha aggiunto due ore e mezzo alle 2.00 del 9 marzo 2008. Tuttavia, perché il codice converte un'ora solare nel fuso orario centrale in ora UTC prima di eseguire un'operazione aritmetica con data e ora e quindi converte di nuovo il risultato da ora UTC in ora solare nel fuso orario centrale, l'ora risultante riflette la transizione dell'ora solare nel fuso orario centrale all'ora legale.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>Vedere anche

* [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
* [Procedura: Usare fusi orari nell'aritmetica di data e ora](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)

---
title: Esecuzione di operazioni aritmetiche con date e ore
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: edad8fc6643b90afc8327b574e19b178270829b3
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Esecuzione di operazioni aritmetiche con date e ore

Sebbene sia il <xref:System.DateTime> e <xref:System.DateTimeOffset> strutture forniscano membri che eseguono operazioni aritmetiche sui relativi valori, i risultati di operazioni aritmetiche sono molto diversi. In questo argomento vengono esaminate tali differenze, messe in relazione ai livelli di compatibilità del fuso orario nei dati di data e ora e viene descritto come eseguire completamente le operazioni di compatibile con fuso orario utilizzando i dati di data e ora.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Confronti e operazioni aritmetiche con i valori DateTime

Il <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> proprietà consente a un <xref:System.DateTimeKind> valore da assegnare alla data e ora per indicare se rappresenta l'ora locale, Coordinated Universal Time (UTC) o l'ora in un fuso orario non specificato. Tuttavia, queste informazioni limitate fuso orario viene ignorate durante il confronto o l'esecuzione di data e ora operazioni aritmetica sul <xref:System.DateTimeKind> valori. Questa condizione è illustrata nell'esempio seguente, in cui si confronta l'ora locale corrente con l'ora UTC corrente.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

Il <xref:System.DateTime.CompareTo%28System.DateTime%29> metodo segnala che è precedente all'ora locale (o minore di), l'ora UTC e l'operazione di sottrazione indica che la differenza tra l'ora UTC e l'ora locale per un sistema negli Stati Uniti Pacifico (Stati Uniti) è sette ore. Ma poiché questi due valori indicano rappresentazioni diverse di un singolo momento, è chiaro in questo caso che l'intervallo di tempo è completamente attribuibile all'offset del fuso orario locale rispetto all'ora UTC.

Più in generale, il <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> proprietà non influisce sui risultati restituiti da <xref:System.DateTime.Kind> aritmetiche e confronto di metodi (come indica il confronto di due punti identico nel tempo), anche se può influire sull'interpretazione di tali risultati. Ad esempio:

* Il risultato di qualsiasi operazione aritmetica eseguita su due valori di data e ora la cui proprietà <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> proprietà sono uguali a <xref:System.DateTimeKind> riflette l'intervallo di tempo effettivo tra i due valori. Analogamente, il confronto di due valori di data e ora di questo tipo riflette esattamente la relazione tra le ore.

* Il risultato di qualsiasi operazione di confronto o aritmetica eseguita su due valori di data e ora la cui proprietà <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> proprietà sono uguali a <xref:System.DateTimeKind> o due valori di data e ora con diversi <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> i valori delle proprietà corrisponde alla differenza di orario tra i due valori.

* Le operazioni aritmetiche o di confronto sui valori locali di data e ora non considerano se un particolare valore è ambiguo o non valido e non tengono conto dell'effetto di eventuali regole di regolazione risultanti dalla transizione del fuso orario locale a o dall'ora legale.

* Qualsiasi operazione che confronta o calcola la differenza tra ora UTC e ora locale include un intervallo di tempo uguale all'offset del fuso orario locale rispetto all'ora UTC nel risultato.

* Qualsiasi operazione che confronta o calcola la differenza tra un'ora non specificata e l'ora UTC o l'ora locale riflette l'ora dell'orologio. Le differenze di fuso orario non vengono considerate e il risultato non riflette l'applicazione delle regole di regolazione del fuso orario.

* Qualsiasi operazione che confronta o calcola la differenza tra due ore non specificate può includere un intervallo sconosciuto che riflette la differenza di orario in due fusi orari diversi.

Esistono molti scenari di fuso orario differenze non influiscono sui calcoli di data e ora (per una discussione su alcuni di questi, vedere [scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)) o in cui il contesto Data e ora di dati definiscono il significato delle operazioni di confronto o aritmetici.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Confronti e operazioni aritmetiche con valori di DateTimeOffset

Oggetto <xref:System.DateTimeOffset> valore include non solo una data e ora, ma anche un offset che definisce in modo univoco tale data e ora rispetto all'ora UTC. In questo modo è possibile definire l'uguaglianza in modo diverso rispetto a <xref:System.DateTimeOffset> valori. Mentre <xref:System.DateTime> i valori sono uguali se hanno la stessa data e ora, <xref:System.DateTimeOffset> i valori sono uguali se entrambe si riferiscono allo stesso punto nel tempo. In questo modo un <xref:System.DateTimeOffset> valore più preciso e meno soggetto a interpretazione quando viene utilizzato nei confronti e nella maggior parte delle operazioni aritmetiche che determinano l'intervallo tra due date e ore. Nell'esempio seguente, che è il <xref:System.DateTimeOffset> equivalente all'esempio precedente che confrontato locale e l'ora UTC <xref:System.DateTimeOffset> valori, viene illustrata questa differenza nel comportamento.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

In questo esempio, il <xref:System.DateTimeOffset.CompareTo%2A> metodo indica che l'ora locale corrente e l'ora UTC corrente sono uguali e la sottrazione di <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> valori indica che la differenza tra due orari è <xref:System.TimeSpan.Zero?displayProperty=nameWithType>.

La limitazione principale dell'utilizzo <xref:System.DateTimeOffset> valori di data e ora aritmetico è che sebbene <xref:System.DateTimeOffset> valori presentano alcune informazioni sul fuso orario, non sono completamente consapevoli di fuso orario. Sebbene il <xref:System.DateTimeOffset> riflette l'offset del valore di offset del fuso orario dall'ora UTC quando un <xref:System.DateTimeOffset> variabile viene assegnato un valore, l'associazione viene il fuso orario successivo. Poiché non è più associato direttamente a un'ora identificabile, l'aggiunta e la sottrazione degli intervalli di data e ora non considerano le regole di regolazione del fuso orario.

A titolo esemplificativo, la transizione all'ora legale negli Stati Uniti, ora solare fuso centrale, avviene alle 2.00 del 9 marzo 2008. Ciò significa che l'aggiunta di un intervallo di due ore e mezzo all'1.30 del 9 marzo 2008 nel fuso orario standard centrale deve generare una data e un'ora equivalente alle 5.00 del 9 marzo 2008. Tuttavia, come mostrato nell'esempio seguente, il risultato dell'addizione è 4.00 del 9 marzo 2008. Si noti che il risultato di questa operazione rappresenta il momento corretto, sebbene non sia l'ora nel fuso orario che interessa (ovvero, non presenta l'offset previsto per il fuso orario).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Operazioni aritmetiche con fusi orari

La <xref:System.TimeZoneInfo> classe include una serie di metodi di conversione che applicano automaticamente rettifiche quando convertono le ore da un fuso orario a un altro. tra cui:

* Il <xref:System.TimeZoneInfo.ConvertTime%2A> e <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> metodi che convertono le ore tra due fusi orari.

* Il <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> e <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> metodi che convertono l'ora in un particolare fuso orario in formato UTC, o convertono nell'ora in un particolare fuso orario UTC.

Per informazioni dettagliate, vedere [conversione degli orari tra fusi orari](../../../docs/standard/datetime/converting-between-time-zones.md).

La <xref:System.TimeZoneInfo.ConvertTimeToUtc(System.DateTime)> classe non fornisce metodi che applicano automaticamente le regole di rettifica quando si eseguono data e ora aritmetico. Tuttavia, è possibile convertire l'ora in un fuso orario in ora UTC, eseguendo l'operazione aritmetica, e quindi convertirla di nuovo da ora UTC a ora nel fuso orario. Per informazioni dettagliate, vedere [procedura: utilizzare fusi orari nella data e ora aritmetico](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md).

Ad esempio, il codice seguente è simile al codice precedente che ha aggiunto due ore e mezzo alle 2.00 del 9 marzo 2008. Tuttavia, perché il codice converte un'ora solare nel fuso orario centrale in ora UTC prima di eseguire un'operazione aritmetica con data e ora e quindi converte di nuovo il risultato da ora UTC in ora solare nel fuso orario centrale, l'ora risultante riflette la transizione dell'ora solare nel fuso orario centrale all'ora legale.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>Vedere anche

[Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
[procedura: utilizzare fusi orari nella data e ora aritmetico](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)

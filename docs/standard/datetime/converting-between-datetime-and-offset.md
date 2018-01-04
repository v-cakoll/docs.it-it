---
title: Conversione tra DateTime e DateTimeOffset
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
- DateTime structure, converting
- time zones [.NET Framework], conversions
- UTC times, converting
- DateTimeOffset structure, converting
- converting DateTimeOffset and DateTime values
- dates [.NET Framework], converting
- converting times
- Date data type, converting
- local time conversions
ms.assetid: b605ff97-0c45-4c24-833f-4c6a3e8be64c
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2055df26618664ee130be417599f4ec46e439444
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Conversione tra DateTime e DateTimeOffset

Sebbene il <xref:System.DateTimeOffset> struttura offre un maggiore livello di compatibilità del fuso orario rispetto al <xref:System.DateTime> struttura <xref:System.DateTime> parametri vengono utilizzati più comunemente nelle chiamate al metodo. Per questo motivo, la capacità di conversione <xref:System.DateTimeOffset> valori <xref:System.DateTime> valori e viceversa è particolarmente importante. In questo argomento viene illustrato come eseguire queste conversioni in modo che mantiene le informazioni di fuso orario possibili.

> [!NOTE]
> Sia il <xref:System.DateTime> e <xref:System.DateTimeOffset> tipi presentano alcune limitazioni per la rappresentazione in fusi orari. Con il relativo <xref:System.DateTime.Kind%2A> proprietà <xref:System.DateTime> è in grado di riflettere solo Coordinated Universal Time (UTC) e fuso orario locale del sistema. <xref:System.DateTimeOffset>riflette l'offset dall'ora UTC di un'ora, ma non riflette il fuso orario effettivo che offset che appartiene. Per informazioni dettagliate sul supporto per i fusi orari e i valori di ora, vedere [scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Conversioni da DateTime a DateTimeOffset

Il <xref:System.DateTimeOffset> struttura fornisce due modalità equivalenti per eseguire <xref:System.DateTime> a <xref:System.DateTimeOffset> conversione adatte per la maggior parte delle conversioni:

* Il <xref:System.DateTimeOffset.%23ctor%2A> costruttore, che crea un nuovo <xref:System.DateTimeOffset> oggetto basato su un <xref:System.DateTime> valore.

* L'operatore di conversione implicita, che consente di assegnare un <xref:System.DateTime> valore un <xref:System.DateTimeOffset> oggetto.

Per l'ora UTC e locali <xref:System.DateTime> valori, il <xref:System.DateTimeOffset.Offset%2A> proprietà dell'oggetto risultante <xref:System.DateTimeOffset> valore riflette esattamente la differenza di fuso ora UTC o locale. Ad esempio, il codice seguente converte un'ora UTC equivalente <xref:System.DateTimeOffset> valore.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

In questo caso, l'offset della variabile `utcTime2` è 00:00. Analogamente, il codice seguente converte un'ora locale equivalente <xref:System.DateTimeOffset> valore.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Tuttavia, per <xref:System.DateTime> i cui valori <xref:System.DateTime.Kind%2A> proprietà <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, questi due metodi di conversione producano un <xref:System.DateTimeOffset> valore il cui offset è quella del fuso orario locale. Ciò viene illustrato nell'esempio seguente che viene eseguito nel fuso orario Ora solare del Pacifico (Stati Uniti).

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Se il <xref:System.DateTime> valore riflette la data e ora in modo diverso il fuso orario locale o UTC, è possibile convertirla in un <xref:System.DateTimeOffset> valore e conservare informazioni sul fuso orario chiamando il metodo di overload <xref:System.DateTimeOffset.%23ctor%2A> costruttore. Ad esempio, nell'esempio seguente crea un <xref:System.DateTimeOffset> oggetto che riflette l'ora solare.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

Il secondo parametro di questo overload del costruttore, un <xref:System.TimeSpan> oggetto che rappresenta l'offset dell'ora rispetto a UTC, deve essere recuperato chiamando il <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> metodo del fuso orario corrispondente dell'ora. L'unico parametro del metodo è il <xref:System.DateTime> valore che rappresenta la data e ora da convertire. Se il fuso orario supporta l'ora legale, questo parametro consente al metodo di determinare l'offset adatto per la data e l'ora specifici.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Conversioni da DateTimeOffset a DateTime

Il <xref:System.DateTimeOffset.DateTime%2A> proprietà viene in genere utilizzata per eseguire <xref:System.DateTimeOffset> a <xref:System.DateTime> conversione. Tuttavia, viene restituito un <xref:System.DateTime> il cui valore <xref:System.DateTime.Kind%2A> proprietà <xref:System.DateTimeKind.Unspecified>, come illustrato nell'esempio seguente.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Ciò significa che tutte le informazioni sul <xref:System.DateTimeOffset> relazione tra il valore in formato UTC viene persa durante la conversione quando il <xref:System.DateTimeOffset.DateTime%2A> viene utilizzata la proprietà. Ciò influisce sul <xref:System.DateTimeOffset> valori che corrispondono all'ora UTC o all'ora locale del sistema perché il <xref:System.DateTimeOffset.DateTime%2A> struttura riflette solo questi due fusi orari nella relativa <xref:System.DateTime.Kind%2A> proprietà.

Per mantenere le informazioni di fuso orario possibile durante la conversione di un <xref:System.DateTimeOffset> per un <xref:System.DateTime> valore, è possibile utilizzare il <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> e <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> proprietà.

### <a name="converting-a-utc-time"></a>Conversione di un'ora UTC

Per indicare che un oggetto convertito <xref:System.DateTimeOffset.DateTime%2A> valore è l'ora UTC, è possibile recuperare il valore di <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> proprietà. Si differenzia dal <xref:System.DateTimeOffset.DateTime%2A> proprietà in due modi:

* Restituisce un <xref:System.DateTime> il cui valore <xref:System.DateTime.Kind%2A> proprietà <xref:System.DateTimeKind.Utc>.

* Se il <xref:System.DateTimeOffset.Offset%2A> valore della proprietà non è uguale <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, l'ora viene convertita nell'ora UTC.

> [!NOTE]
> Se l'applicazione richiede che convertito <xref:System.DateTime> valori identificano in modo non ambiguo un singolo punto nel tempo, è consigliabile utilizzare il <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> proprietà gestire tutto <xref:System.DateTimeOffset> a <xref:System.DateTime> conversioni.

Il codice seguente usa il <xref:System.DateTimeOffset.UtcDateTime%2A> proprietà per convertire un <xref:System.DateTimeOffset> valore il cui offset è uguale a <xref:System.TimeSpan.Zero?displayProperty=nameWithType> per un <xref:System.DateTime> valore.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

Il codice seguente usa il <xref:System.DateTimeOffset.UtcDateTime%2A> proprietà per eseguire una conversione del fuso orario sia una conversione del tipo in un <xref:System.DateTimeOffset> valore.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Conversione di un'ora locale

Per indicare che un <xref:System.DateTimeOffset> valore rappresenta l'ora locale, è possibile passare il <xref:System.DateTime> valore restituito dal <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> proprietà per il `static` (`Shared` in Visual Basic) <xref:System.DateTime.SpecifyKind%2A> metodo. Il metodo restituisce la data e ora passate come primo parametro, ma imposta il <xref:System.DateTime.Kind%2A> proprietà sul valore specificato dal secondo parametro. Il codice seguente usa il <xref:System.DateTime.SpecifyKind%2A> metodo durante la conversione di un <xref:System.DateTimeOffset> valore il cui offset corrisponde a quella del fuso orario locale.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

È inoltre possibile utilizzare il <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> proprietà per convertire un <xref:System.DateTimeOffset> valore a una variabile locale <xref:System.DateTime> valore. Il <xref:System.DateTime.Kind%2A> proprietà dell'oggetto restituito <xref:System.DateTime> valore <xref:System.DateTimeKind.Local>. Il codice seguente usa il <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> proprietà durante la conversione di un <xref:System.DateTimeOffset> valore il cui offset corrisponde a quella del fuso orario locale. 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

Quando si recupera un <xref:System.DateTime> valore utilizzando il <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> proprietà, la proprietà `get` converte innanzitutto una funzione di accesso di <xref:System.DateTimeOffset> valore in formato UTC, quindi converte in ora locale chiamando il <xref:System.DateTimeOffset.ToLocalTime%2A> (metodo). Ciò significa che è possibile recuperare un valore di <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> proprietà per eseguire una conversione del fuso orario nello stesso momento di eseguire una conversione del tipo. Nell'esecuzione della conversione vengono anche applicate le regole di rettifica del fuso orario. Il codice seguente viene illustrato l'utilizzo del <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> proprietà per eseguire un tipo e una conversione del fuso orario.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Un metodo di conversione generico

L'esempio seguente definisce un metodo denominato `ConvertFromDateTimeOffset` che converte <xref:System.DateTimeOffset> valori <xref:System.DateTime> valori. In base all'offset, determina se il <xref:System.DateTimeOffset> valore è un'ora UTC, un'ora locale o un secondo momento e che definisce la data restituita e del valore di ora <xref:System.DateTime.Kind%2A> proprietà conseguenza.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

Nell'esempio seguente viene chiamato il `ConvertFromDateTimeOffset` metodo per la conversione <xref:System.DateTimeOffset> valori che rappresentano un'ora UTC, un'ora locale e un'ora negli Stati Uniti. un'ora solare fuso centrale degli Stati Uniti.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Questo codice si basa su due presupposti che, a seconda dell'applicazione e dell'origine dei valori di data e ora, potrebbero non essere sempre validi:

* Si presuppone che una data e ora valore il cui offset è <xref:System.TimeSpan.Zero?displayProperty=nameWithType> rappresenta l'ora UTC. Infatti UTC non rappresenta un'ora in un particolare fuso orario, ma l'ora in relazione alla quale vengono normalizzati i fusi orari di tutto il mondo. Fusi orari possono anche presentare un offset di <xref:System.TimeSpan.Zero>.

* Il presupposto è che valori di data e ora il cui offset è uguale a quelli del fuso orario locale rappresentino il fuso orario locale. Poiché l'associazione dei valori di data e ora al fuso orario originale è annullata, potrebbe non essere questo il caso; la data e l'ora potrebbero essere state originate in un altro fuso orario con lo stesso offset.

## <a name="see-also"></a>Vedere anche

[Date, ore e fusi orari](../../../docs/standard/datetime/index.md)

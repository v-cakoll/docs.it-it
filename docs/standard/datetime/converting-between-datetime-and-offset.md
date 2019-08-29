---
title: Conversione tra DateTime e DateTimeOffset
ms.date: 04/10/2017
ms.technology: dotnet-standard
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb91ed8edd0c5cd3cb1d051157596f311718195d
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107069"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Conversione tra DateTime e DateTimeOffset

Sebbene la <xref:System.DateTimeOffset> struttura fornisca un maggiore grado di riconoscimento del fuso orario rispetto <xref:System.DateTime> alla struttura <xref:System.DateTime> , i parametri vengono usati più comunemente nelle chiamate al metodo. Per questo motivo la possibilità di convertire <xref:System.DateTimeOffset> i valori in <xref:System.DateTime> valori e viceversa è particolarmente importante. In questo argomento viene illustrato come eseguire queste conversioni in modo da mantenere il maggior quantità possibile di informazioni sul fuso orario.

> [!NOTE]
> Entrambi i <xref:System.DateTime> <xref:System.DateTimeOffset> tipi e presentano alcune limitazioni quando rappresentano le ore nei fusi orari. Con la <xref:System.DateTime.Kind%2A> relativa proprietà <xref:System.DateTime> , è in grado di riflettere solo l'ora UTC (Coordinated Universal Time) e il fuso orario locale del sistema. <xref:System.DateTimeOffset>riflette l'offset dell'ora rispetto all'ora UTC, ma non riflette il fuso orario effettivo a cui appartiene l'offset. Per informazioni dettagliate sui valori temporali e il supporto per i fusi orari, vedere [scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Conversioni da DateTime a DateTimeOffset

La <xref:System.DateTimeOffset> struttura fornisce due modi equivalenti per <xref:System.DateTime> <xref:System.DateTimeOffset> eseguire la conversione, adatti per la maggior parte delle conversioni:

- Il <xref:System.DateTimeOffset.%23ctor%2A> costruttore, che crea un nuovo <xref:System.DateTimeOffset> oggetto in base a <xref:System.DateTime> un valore.

- Operatore di conversione implicito, che consente di assegnare un <xref:System.DateTime> valore a un <xref:System.DateTimeOffset> oggetto.

Per i valori UTC <xref:System.DateTime> e locali, <xref:System.DateTimeOffset.Offset%2A> la proprietà del valore <xref:System.DateTimeOffset> risultante riflette accuratamente l'offset dell'ora UTC o del fuso orario locale. Il codice seguente, ad esempio, converte un'ora UTC nel valore <xref:System.DateTimeOffset> equivalente.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

In questo caso, l'offset della variabile `utcTime2` è 00:00. Analogamente, il codice seguente converte un'ora locale nel valore <xref:System.DateTimeOffset> equivalente.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Tuttavia, per <xref:System.DateTime> i valori <xref:System.DateTime.Kind%2A> la cui <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>proprietà è, questi due metodi di <xref:System.DateTimeOffset> conversione producono un valore il cui offset è quello del fuso orario locale. Ciò viene illustrato nell'esempio seguente che viene eseguito nel fuso orario Ora solare del Pacifico (Stati Uniti).

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Se il <xref:System.DateTime> valore riflette la data e l'ora in un elemento diverso dal fuso orario locale o dall'ora UTC, è possibile convertirlo in un <xref:System.DateTimeOffset> valore e mantenere le informazioni sul fuso orario <xref:System.DateTimeOffset.%23ctor%2A> chiamando il costruttore di overload. Nell'esempio seguente viene creata un'istanza di un <xref:System.DateTimeOffset> oggetto che riflette l'ora solare fuso centrale.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

Il secondo parametro per questo overload del costruttore, <xref:System.TimeSpan> un oggetto che rappresenta l'offset dell'ora rispetto all'ora UTC, deve essere recuperato <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> chiamando il metodo del fuso orario corrispondente all'ora. L'unico parametro del metodo è il <xref:System.DateTime> valore che rappresenta la data e l'ora da convertire. Se il fuso orario supporta l'ora legale, questo parametro consente al metodo di determinare l'offset adatto per la data e l'ora specifici.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Conversioni da DateTimeOffset a DateTime

La <xref:System.DateTimeOffset.DateTime%2A> proprietà è più comunemente utilizzata per <xref:System.DateTime> eseguire <xref:System.DateTimeOffset> la conversione. Tuttavia, restituisce un <xref:System.DateTime> valore la cui <xref:System.DateTime.Kind%2A> proprietà è <xref:System.DateTimeKind.Unspecified>, come illustrato nell'esempio seguente.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Ciò significa che tutte le informazioni sulla <xref:System.DateTimeOffset> relazione del valore con l'ora UTC vengono perse dalla conversione <xref:System.DateTimeOffset.DateTime%2A> quando si utilizza la proprietà. Ciò influiscono <xref:System.DateTimeOffset> sui valori che corrispondono all'ora UTC o all'ora locale del sistema perché <xref:System.DateTimeOffset.DateTime%2A> la struttura riflette solo i <xref:System.DateTime.Kind%2A> due fusi orari nella proprietà.

Per conservare il maggior quantità possibile di informazioni sul fuso orario quando <xref:System.DateTimeOffset> si converte <xref:System.DateTime> un oggetto in un valore, <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> è <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> possibile usare le proprietà e.

### <a name="converting-a-utc-time"></a>Conversione di un'ora UTC

Per indicare che un valore <xref:System.DateTimeOffset.DateTime%2A> convertito è l'ora UTC, è possibile recuperare il valore <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> della proprietà. Si differenzia dalla <xref:System.DateTimeOffset.DateTime%2A> proprietà in due modi:

- Restituisce un valore <xref:System.DateTime> la cui <xref:System.DateTime.Kind%2A> proprietà è <xref:System.DateTimeKind.Utc>.

- Se il <xref:System.DateTimeOffset.Offset%2A> valore della proprietà non è <xref:System.TimeSpan.Zero?displayProperty=nameWithType>uguale, l'ora viene convertita in ora UTC.

> [!NOTE]
> Se l'applicazione richiede che i <xref:System.DateTime> valori convertiti identifichino senza ambiguità un singolo momento, è consigliabile usare la <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> <xref:System.DateTime> proprietà per gestire tutte <xref:System.DateTimeOffset> le conversioni.

Il codice seguente usa la <xref:System.DateTimeOffset.UtcDateTime%2A> proprietà per convertire un <xref:System.DateTimeOffset> <xref:System.TimeSpan.Zero?displayProperty=nameWithType> valore il cui offset è uguale a <xref:System.DateTime> un valore.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

Il codice seguente usa la <xref:System.DateTimeOffset.UtcDateTime%2A> proprietà per eseguire una conversione del fuso orario e una conversione di tipi su <xref:System.DateTimeOffset> un valore.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Conversione di un'ora locale

Per indicare che un <xref:System.DateTimeOffset> valore rappresenta l'ora locale, è possibile passare il <xref:System.DateTime> valore restituito `static` dalla <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> proprietà al metodo (`Shared` in Visual Basic) <xref:System.DateTime.SpecifyKind%2A> . Il metodo restituisce la data e l'ora passate come primo parametro, ma imposta la <xref:System.DateTime.Kind%2A> proprietà sul valore specificato dal secondo parametro. Il codice seguente usa il <xref:System.DateTime.SpecifyKind%2A> metodo durante la conversione <xref:System.DateTimeOffset> di un valore il cui offset corrisponde a quello del fuso orario locale.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

È anche possibile usare la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> proprietà per convertire un <xref:System.DateTimeOffset> valore in un valore <xref:System.DateTime> locale. La <xref:System.DateTime.Kind%2A> proprietà del valore restituito <xref:System.DateTime> è <xref:System.DateTimeKind.Local>. Nel codice seguente viene utilizzata <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> la proprietà quando si <xref:System.DateTimeOffset> converte un valore il cui offset corrisponde a quello del fuso orario locale. 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

Quando si recupera un <xref:System.DateTime> valore utilizzando la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> proprietà, la funzione di `get` accesso della proprietà converte <xref:System.DateTimeOffset> innanzitutto il valore in formato UTC, quindi lo converte nell'ora locale <xref:System.DateTimeOffset.ToLocalTime%2A> chiamando il metodo. Ciò significa che è possibile recuperare un valore dalla <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> proprietà per eseguire una conversione del fuso orario nello stesso momento in cui si esegue una conversione di tipi. Nell'esecuzione della conversione vengono anche applicate le regole di rettifica del fuso orario. Il codice seguente illustra l'uso della <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> proprietà per eseguire sia un tipo sia una conversione del fuso orario.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Metodo di conversione per utilizzo generico

Nell'esempio seguente viene definito un metodo `ConvertFromDateTimeOffset` denominato che <xref:System.DateTimeOffset> converte i <xref:System.DateTime> valori in valori. In base all'offset, determina se il <xref:System.DateTimeOffset> valore è un'ora UTC, un'ora locale o un'altra ora e definisce di conseguenza la proprietà del valore di <xref:System.DateTime.Kind%2A> data e ora restituito.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

Nell'esempio seguente viene chiamato `ConvertFromDateTimeOffset` il metodo per <xref:System.DateTimeOffset> convertire i valori che rappresentano un'ora UTC, un'ora locale e un'ora negli Stati Uniti un'ora solare fuso centrale degli Stati Uniti.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Questo codice si basa su due presupposti che, a seconda dell'applicazione e dell'origine dei valori di data e ora, potrebbero non essere sempre validi:

- Si presuppone che un valore di data e ora il cui <xref:System.TimeSpan.Zero?displayProperty=nameWithType> offset sia rappresentato dall'ora UTC. Infatti UTC non rappresenta un'ora in un particolare fuso orario, ma l'ora in relazione alla quale vengono normalizzati i fusi orari di tutto il mondo. I fusi orari possono anche avere un offset <xref:System.TimeSpan.Zero>di.

- Il presupposto è che valori di data e ora il cui offset è uguale a quelli del fuso orario locale rappresentino il fuso orario locale. Poiché l'associazione dei valori di data e ora al fuso orario originale è annullata, potrebbe non essere questo il caso; la data e l'ora potrebbero essere state originate in un altro fuso orario con lo stesso offset.

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)

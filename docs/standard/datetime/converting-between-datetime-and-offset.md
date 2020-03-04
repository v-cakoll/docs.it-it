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
ms.openlocfilehash: 5c19296f75e9e002e88263c5e5efa9917e185ebc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156036"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Conversione tra DateTime e DateTimeOffset

Sebbene la struttura di <xref:System.DateTimeOffset> offra un livello maggiore di riconoscimento del fuso orario rispetto alla struttura <xref:System.DateTime>, i parametri <xref:System.DateTime> vengono usati più comunemente nelle chiamate al metodo. Per questo motivo la possibilità di convertire valori <xref:System.DateTimeOffset> in valori <xref:System.DateTime> e viceversa è particolarmente importante. In questo argomento viene illustrato come eseguire queste conversioni in modo da mantenere il maggior quantità possibile di informazioni sul fuso orario.

> [!NOTE]
> Sia la <xref:System.DateTime> che i tipi di <xref:System.DateTimeOffset> presentano alcune limitazioni quando rappresentano i tempi nei fusi orari. Con la relativa proprietà <xref:System.DateTime.Kind%2A>, <xref:System.DateTime> è in grado di riflettere solo l'ora UTC (Coordinated Universal Time) e il fuso orario locale del sistema. <xref:System.DateTimeOffset> riflette l'offset dell'ora rispetto all'ora UTC, ma non riflette il fuso orario effettivo a cui appartiene l'offset. Per informazioni dettagliate sui valori temporali e il supporto per i fusi orari, vedere [scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Conversioni da DateTime a DateTimeOffset

La struttura <xref:System.DateTimeOffset> offre due modi equivalenti per eseguire <xref:System.DateTime> alla conversione <xref:System.DateTimeOffset> adatta per la maggior parte delle conversioni:

- Il costruttore <xref:System.DateTimeOffset.%23ctor%2A>, che crea un nuovo oggetto <xref:System.DateTimeOffset> in base a un valore di <xref:System.DateTime>.

- Operatore di conversione implicito, che consente di assegnare un valore <xref:System.DateTime> a un oggetto <xref:System.DateTimeOffset>.

Per i valori UTC e locali <xref:System.DateTime> la proprietà <xref:System.DateTimeOffset.Offset%2A> del valore di <xref:System.DateTimeOffset> risultante riflette accuratamente l'offset UTC o il fuso orario locale. Il codice seguente, ad esempio, converte un'ora UTC nell'equivalente <xref:System.DateTimeOffset> valore.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

In questo caso, l'offset della variabile `utcTime2` è 00:00. Analogamente, il codice seguente converte un'ora locale nell'equivalente <xref:System.DateTimeOffset> valore.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Tuttavia, per <xref:System.DateTime> valori la cui proprietà <xref:System.DateTime.Kind%2A> è <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, questi due metodi di conversione producono un valore <xref:System.DateTimeOffset> il cui offset è quello del fuso orario locale. Ciò viene illustrato nell'esempio seguente che viene eseguito nel fuso orario standard del Pacifico (Stati Uniti).

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Se il valore <xref:System.DateTime> riflette la data e l'ora in un valore diverso dal fuso orario locale o UTC, è possibile convertirlo in un valore <xref:System.DateTimeOffset> e mantenere le informazioni sul fuso orario chiamando il costruttore di <xref:System.DateTimeOffset.%23ctor%2A> di overload. Nell'esempio seguente viene creata un'istanza di un oggetto <xref:System.DateTimeOffset> che riflette l'ora solare fuso centrale.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

Il secondo parametro per questo overload del costruttore, un <xref:System.TimeSpan> oggetto che rappresenta l'offset dell'ora rispetto all'ora UTC, deve essere recuperato chiamando il metodo <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> del fuso orario corrispondente all'ora. L'unico parametro del metodo è il valore <xref:System.DateTime> che rappresenta la data e l'ora da convertire. Se il fuso orario supporta l'ora legale, questo parametro consente al metodo di determinare l'offset adatto per la data e l'ora specifici.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Conversioni da DateTimeOffset a DateTime

La proprietà <xref:System.DateTimeOffset.DateTime%2A> viene comunemente utilizzata per eseguire <xref:System.DateTimeOffset> per <xref:System.DateTime> la conversione. Tuttavia, restituisce un valore <xref:System.DateTime> la cui proprietà <xref:System.DateTime.Kind%2A> è <xref:System.DateTimeKind.Unspecified>, come illustrato nell'esempio seguente.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Ciò significa che qualsiasi informazione sulla relazione del valore di <xref:System.DateTimeOffset> con l'ora UTC viene persa durante la conversione quando viene usata la proprietà <xref:System.DateTimeOffset.DateTime%2A>. Questa operazione interessa <xref:System.DateTimeOffset> valori che corrispondono all'ora UTC o all'ora locale del sistema perché la struttura <xref:System.DateTimeOffset.DateTime%2A> riflette solo i due fusi orari nella proprietà <xref:System.DateTime.Kind%2A>.

Per conservare il maggior quantità possibile di informazioni sul fuso orario quando si converte un <xref:System.DateTimeOffset> in un valore <xref:System.DateTime>, è possibile usare le proprietà <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> e <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType>.

### <a name="converting-a-utc-time"></a>Conversione di un'ora UTC

Per indicare che un valore <xref:System.DateTimeOffset.DateTime%2A> convertito è l'ora UTC, è possibile recuperare il valore della proprietà <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType>. Si differenzia dalla proprietà <xref:System.DateTimeOffset.DateTime%2A> in due modi:

- Restituisce un valore <xref:System.DateTime> la cui proprietà <xref:System.DateTime.Kind%2A> è <xref:System.DateTimeKind.Utc>.

- Se il valore della proprietà <xref:System.DateTimeOffset.Offset%2A> non è uguale <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, l'ora viene convertita in ora UTC.

> [!NOTE]
> Se l'applicazione richiede che i valori <xref:System.DateTime> convertiti identifichino senza ambiguità un singolo momento, è consigliabile usare la proprietà <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> per gestire tutti i <xref:System.DateTimeOffset> <xref:System.DateTime> le conversioni.

Il codice seguente usa la proprietà <xref:System.DateTimeOffset.UtcDateTime%2A> per convertire un valore <xref:System.DateTimeOffset> il cui offset è uguale <xref:System.TimeSpan.Zero?displayProperty=nameWithType> a un valore <xref:System.DateTime>.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

Il codice seguente usa la proprietà <xref:System.DateTimeOffset.UtcDateTime%2A> per eseguire una conversione del fuso orario e una conversione di tipi su un valore <xref:System.DateTimeOffset>.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Conversione di un'ora locale

Per indicare che un valore di <xref:System.DateTimeOffset> rappresenta l'ora locale, è possibile passare il valore <xref:System.DateTime> restituito dalla proprietà <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> al metodo di`Shared` `static` (Visual Basic nel <xref:System.DateTime.SpecifyKind%2A>). Il metodo restituisce la data e l'ora passate come primo parametro, ma imposta la proprietà <xref:System.DateTime.Kind%2A> sul valore specificato dal secondo parametro. Il codice seguente usa il metodo <xref:System.DateTime.SpecifyKind%2A> durante la conversione di un valore <xref:System.DateTimeOffset> il cui offset corrisponde a quello del fuso orario locale.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

È anche possibile usare la proprietà <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> per convertire un valore <xref:System.DateTimeOffset> in un valore <xref:System.DateTime> locale. Viene <xref:System.DateTimeKind.Local>la proprietà <xref:System.DateTime.Kind%2A> del valore <xref:System.DateTime> restituito. Nel codice seguente viene utilizzata la proprietà <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> durante la conversione di un valore <xref:System.DateTimeOffset> il cui offset corrisponde a quello del fuso orario locale.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

Quando si recupera un valore di <xref:System.DateTime> usando la proprietà <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType>, la funzione di accesso `get` della proprietà converte prima di tutto il valore <xref:System.DateTimeOffset> in formato UTC, quindi lo converte nell'ora locale chiamando il metodo <xref:System.DateTimeOffset.ToLocalTime%2A>. Ciò significa che è possibile recuperare un valore dalla proprietà <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> per eseguire una conversione del fuso orario nello stesso momento in cui si esegue una conversione di tipi. Nell'esecuzione della conversione vengono anche applicate le regole di rettifica del fuso orario. Il codice seguente illustra l'uso della proprietà <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> per eseguire sia un tipo sia una conversione del fuso orario.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Metodo di conversione per utilizzo generico

Nell'esempio seguente viene definito un metodo denominato `ConvertFromDateTimeOffset` che converte i valori di <xref:System.DateTimeOffset> in valori di <xref:System.DateTime>. In base all'offset, determina se il valore <xref:System.DateTimeOffset> è un'ora UTC, un'ora locale o un'altra ora e definisce di conseguenza la proprietà <xref:System.DateTime.Kind%2A> del valore di data e ora restituito.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

Nell'esempio seguente viene chiamato il metodo `ConvertFromDateTimeOffset` per convertire i valori <xref:System.DateTimeOffset> che rappresentano un'ora UTC, un'ora locale e un'ora nel fuso orario standard degli Stati Uniti Centrali.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Questo codice si basa su due presupposti che, a seconda dell'applicazione e dell'origine dei valori di data e ora, potrebbero non essere sempre validi:

- Si presuppone che un valore di data e ora il cui offset è <xref:System.TimeSpan.Zero?displayProperty=nameWithType> rappresenti l'ora UTC. Infatti UTC non rappresenta un'ora in un particolare fuso orario, ma l'ora in relazione alla quale vengono normalizzati i fusi orari di tutto il mondo. I fusi orari possono anche avere un offset di <xref:System.TimeSpan.Zero>.

- Il presupposto è che valori di data e ora il cui offset è uguale a quelli del fuso orario locale rappresentino il fuso orario locale. Poiché l'associazione dei valori di data e ora al fuso orario originale è annullata, potrebbe non essere questo il caso; la data e l'ora potrebbero essere state originate in un altro fuso orario con lo stesso offset.

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)

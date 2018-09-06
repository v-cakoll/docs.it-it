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
ms.openlocfilehash: 830e3e6e98be2eaaff2af6c0bdac650732833ab7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864421"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Conversione tra DateTime e DateTimeOffset

Anche se il <xref:System.DateTimeOffset> struttura fornisce un livello di compatibilità del fuso orario rispetto a maggiore il <xref:System.DateTime> struttura, <xref:System.DateTime> parametri vengono utilizzati più comunemente nelle chiamate al metodo. Per questo motivo, la capacità di convertire <xref:System.DateTimeOffset> valori <xref:System.DateTime> valori e viceversa è particolarmente importante. Questo argomento illustra come eseguire queste conversioni in modo tale da mantenere quante più informazioni possibili fuso orario.

> [!NOTE]
> Sia la <xref:System.DateTime> e il <xref:System.DateTimeOffset> tipi presentano alcune limitazioni in caso di rappresentazione delle ore nei fusi orari. Con relativo <xref:System.DateTime.Kind%2A> proprietà, <xref:System.DateTime> è in grado di riflettere solo Coordinated Universal Time (UTC) e fuso orario locale del sistema. <xref:System.DateTimeOffset> riflette l'offset di un'ora rispetto all'ora UTC, ma non riflette il fuso orario effettivo a cui tale offset appartiene. Per informazioni dettagliate sui valori di ora e il supporto per i fusi orari, vedere [scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Conversioni da DateTime a DateTimeOffset

Il <xref:System.DateTimeOffset> struttura fornisce due modalità equivalenti per eseguire <xref:System.DateTime> a <xref:System.DateTimeOffset> conversione adatti per la maggior parte delle conversioni:

* Il <xref:System.DateTimeOffset.%23ctor%2A> costruttore che crea una nuova <xref:System.DateTimeOffset> oggetto in base un <xref:System.DateTime> valore.

* L'operatore di conversione implicita, che consente di assegnare un <xref:System.DateTime> valore per un <xref:System.DateTimeOffset> oggetto.

Per ora UTC e locali <xref:System.DateTime> valori, il <xref:System.DateTimeOffset.Offset%2A> proprietà dell'oggetto risultante <xref:System.DateTimeOffset> valore rifletta accuratamente la differenza di fuso orario locale o UTC. Ad esempio, il codice seguente converte un'ora UTC equivalente <xref:System.DateTimeOffset> valore.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

In questo caso, l'offset della variabile `utcTime2` è 00:00. Analogamente, il codice seguente converte un'ora locale equivalente <xref:System.DateTimeOffset> valore.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Tuttavia, affinché <xref:System.DateTime> valori la cui proprietà <xref:System.DateTime.Kind%2A> proprietà è <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, questi due metodi di conversione producono un <xref:System.DateTimeOffset> valore il cui offset è quello del fuso orario locale. Ciò viene illustrato nell'esempio seguente che viene eseguito nel fuso orario Ora solare del Pacifico (Stati Uniti).

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Se il <xref:System.DateTime> valore riflette la data e ora in modo diverso dal fuso orario locale o UTC, è possibile convertirlo in un <xref:System.DateTimeOffset> valore e mantenere le informazioni sul fuso orario chiamando il metodo di overload <xref:System.DateTimeOffset.%23ctor%2A> costruttore. Ad esempio, nell'esempio seguente crea un <xref:System.DateTimeOffset> oggetto che riflette l'ora solare fuso centrale.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

Il secondo parametro per questo overload del costruttore, un <xref:System.TimeSpan> oggetto che rappresenta l'offset dell'ora rispetto all'ora UTC, deve essere recuperato chiamando il <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> metodo del fuso orario corrispondente dell'ora. L'unico parametro del metodo è il <xref:System.DateTime> valore che rappresenta la data e ora da convertire. Se il fuso orario supporta l'ora legale, questo parametro consente al metodo di determinare l'offset adatto per la data e l'ora specifici.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Conversioni da DateTimeOffset a DateTime

Il <xref:System.DateTimeOffset.DateTime%2A> proprietà viene in genere usata per eseguire <xref:System.DateTimeOffset> a <xref:System.DateTime> conversione. Tuttavia, viene restituito un <xref:System.DateTime> valore la cui proprietà <xref:System.DateTime.Kind%2A> è di proprietà <xref:System.DateTimeKind.Unspecified>, come illustrato nell'esempio seguente.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Ciò significa che tutte le informazioni sul <xref:System.DateTimeOffset> relazione tra il valore in formato UTC viene persa durante la conversione quando il <xref:System.DateTimeOffset.DateTime%2A> proprietà viene utilizzata. Questa impostazione influisce sulle <xref:System.DateTimeOffset> i valori che corrispondono all'ora UTC o all'ora locale del sistema perché la <xref:System.DateTimeOffset.DateTime%2A> struttura riflette solo questi due fusi orari in relativo <xref:System.DateTime.Kind%2A> proprietà.

Per mantenere quante più informazioni possibili fuso orario durante la conversione di un <xref:System.DateTimeOffset> per un <xref:System.DateTime> valore, è possibile utilizzare il <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> e <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> proprietà.

### <a name="converting-a-utc-time"></a>Conversione di un'ora UTC

Per indicare che un oggetto convertito <xref:System.DateTimeOffset.DateTime%2A> valore è l'ora UTC, è possibile recuperare il valore della <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> proprietà. Si differenzia dal <xref:System.DateTimeOffset.DateTime%2A> proprietà in due modi:

* Restituisce un <xref:System.DateTime> valore la cui proprietà <xref:System.DateTime.Kind%2A> è di proprietà <xref:System.DateTimeKind.Utc>.

* Se il <xref:System.DateTimeOffset.Offset%2A> valore della proprietà non è uguale <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, converte l'ora in formato UTC.

> [!NOTE]
> Se l'applicazione richiede che convertito <xref:System.DateTime> valori identificano in modo non ambiguo un singolo punto nel tempo, è consigliabile usare il <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> proprietà gestire tutto <xref:System.DateTimeOffset> a <xref:System.DateTime> conversioni.

Il codice seguente usa il <xref:System.DateTimeOffset.UtcDateTime%2A> proprietà per convertire un <xref:System.DateTimeOffset> valore il cui offset equivale <xref:System.TimeSpan.Zero?displayProperty=nameWithType> a un <xref:System.DateTime> valore.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

Il codice seguente usa il <xref:System.DateTimeOffset.UtcDateTime%2A> proprietà per eseguire una conversione del fuso orario e una conversione del tipo in un <xref:System.DateTimeOffset> valore.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Conversione dell'ora locale

Per indicare che un <xref:System.DateTimeOffset> valore rappresenta l'ora locale, è possibile passare il <xref:System.DateTime> valore restituito dal <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> proprietà per il `static` (`Shared` in Visual Basic) <xref:System.DateTime.SpecifyKind%2A> (metodo). Il metodo restituisce la data e ora passate come primo parametro, ma imposta il <xref:System.DateTime.Kind%2A> proprietà sul valore specificato dal secondo parametro. Il codice seguente usa il <xref:System.DateTime.SpecifyKind%2A> metodo quando si converte un <xref:System.DateTimeOffset> valore il cui offset corrisponde a quello del fuso orario locale.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

È anche possibile usare la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> proprietà per convertire un <xref:System.DateTimeOffset> valore a una variabile locale <xref:System.DateTime> valore. Il <xref:System.DateTime.Kind%2A> proprietà dell'oggetto restituito <xref:System.DateTime> valore <xref:System.DateTimeKind.Local>. Il codice seguente usa il <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> proprietà durante la conversione di un <xref:System.DateTimeOffset> valore il cui offset corrisponde a quello del fuso orario locale. 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

Quando si recupera un <xref:System.DateTime> valore usando la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> proprietà, la proprietà `get` della funzione di accesso vengono innanzitutto convertiti il <xref:System.DateTimeOffset> valore in formato UTC, quindi lo converte in ora locale chiamando il <xref:System.DateTimeOffset.ToLocalTime%2A> (metodo). Ciò significa che è possibile recuperare un valore compreso il <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> proprietà per eseguire una conversione del fuso orario allo stesso tempo eseguire una conversione del tipo. Nell'esecuzione della conversione vengono anche applicate le regole di rettifica del fuso orario. Il codice seguente illustra l'uso del <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> proprietà per eseguire una conversione del fuso orario e un tipo.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Un metodo di conversione per utilizzo generico

L'esempio seguente definisce un metodo denominato `ConvertFromDateTimeOffset` che converte <xref:System.DateTimeOffset> valori <xref:System.DateTime> valori. In base all'offset, determina se il <xref:System.DateTimeOffset> valore è un'ora UTC, un'ora locale o un'altra occasione e definisce la data restituita e del valore di ora <xref:System.DateTime.Kind%2A> proprietà conseguenza.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

Nell'esempio seguente viene chiamato il `ConvertFromDateTimeOffset` metodo per convertire <xref:System.DateTimeOffset> valori che rappresentano un'ora UTC, un'ora locale e un'ora negli Stati Uniti un'ora solare fuso centrale degli Stati Uniti.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Questo codice si basa su due presupposti che, a seconda dell'applicazione e dell'origine dei valori di data e ora, potrebbero non essere sempre validi:

* Si presuppone che una data e ora valore il cui offset è <xref:System.TimeSpan.Zero?displayProperty=nameWithType> rappresenta l'ora UTC. Infatti UTC non rappresenta un'ora in un particolare fuso orario, ma l'ora in relazione alla quale vengono normalizzati i fusi orari di tutto il mondo. Fusi orari possono presentare anche un offset di <xref:System.TimeSpan.Zero>.

* Il presupposto è che valori di data e ora il cui offset è uguale a quelli del fuso orario locale rappresentino il fuso orario locale. Poiché l'associazione dei valori di data e ora al fuso orario originale è annullata, potrebbe non essere questo il caso; la data e l'ora potrebbero essere state originate in un altro fuso orario con lo stesso offset.

## <a name="see-also"></a>Vedere anche

* [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)

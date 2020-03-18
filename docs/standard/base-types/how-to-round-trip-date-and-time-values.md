---
title: 'Procedura: Eseguire il round trip dei valori di data e ora'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- round-trip date and time values
- dates [.NET Framework], round-trip values
- time zones [.NET Framework], round-trip date and time values
- time [.NET Framework], round-trip values
- formatting strings [.NET Framework], round-trip values
ms.assetid: b609b277-edc6-4c74-b03e-ea73324ecbdb
ms.openlocfilehash: 2e3a58ffe8332e0afec62461f6897d673e1da09f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73132002"
---
# <a name="how-to-round-trip-date-and-time-values"></a>Procedura: Eseguire il round trip dei valori di data e ora

In molte applicazioni un valore di data e ora deve identificare una data e un'ora singole in modo non ambiguo. Questo argomento illustra come salvare e ripristinare un valore <xref:System.DateTime>, un valore <xref:System.DateTimeOffset> e un valore di data e ora con informazioni sul fuso orario, in modo che il valore ripristinato identifichi la stessa ora del valore salvato.

### <a name="to-round-trip-a-datetime-value"></a>Per eseguire il round trip di un valore DateTime

1. Convertire il valore <xref:System.DateTime> nella relativa rappresentazione di stringa chiamando il metodo <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> con l'identificatore di formato "o".

2. Salvare la rappresentazione di stringa del valore <xref:System.DateTime> in un file o passarla attraverso un processo, un dominio dell'applicazione o un limite della macchina.

3. Recuperare la stringa che rappresenta il valore <xref:System.DateTime>.

4. Chiamare il metodo <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> e passare <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> come valore del parametro `styles`.

L'esempio seguente illustra come eseguire il round trip di un valore <xref:System.DateTime>.

[!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
[!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]

Quando si esegue il round trip di un valore <xref:System.DateTime>, questa tecnica consente di mantenere correttamente l'ora per tutte le ore locali e UTC. Ad esempio, se un valore locale <xref:System.DateTime> viene salvato in un sistema nel fuso orario standard del Pacifico (Stati Uniti) e viene ripristinato in un sistema nel fuso orario standard degli Stati Uniti Centrali, la data e l'ora ripristinate saranno due ore avanti rispetto all'ora originale, la quale riflette la differenza di tempo tra i due fusi orari. Tuttavia, questa tecnica non è sempre accurata per le ore non specificate. Tutti i valori <xref:System.DateTime> la cui proprietà <xref:System.DateTime.Kind%2A> è <xref:System.DateTimeKind.Unspecified> vengono trattati come valori di ora locale. Se ciò non avvenisse, <xref:System.DateTime> non potrebbe identificare il punto nel tempo corretto. La soluzione alternativa per questa limitazione consiste nell'associare un valore di data e ora al proprio fuso orario per l'operazione di salvataggio e ripristino.

### <a name="to-round-trip-a-datetimeoffset-value"></a>Per eseguire il round trip di un valore DateTimeOffset

1. Convertire il valore <xref:System.DateTimeOffset> nella relativa rappresentazione di stringa chiamando il metodo <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> con l'identificatore di formato "o".

2. Salvare la rappresentazione di stringa del valore <xref:System.DateTimeOffset> in un file o passarla attraverso un processo, un dominio dell'applicazione o un limite della macchina.

3. Recuperare la stringa che rappresenta il valore <xref:System.DateTimeOffset>.

4. Chiamare il metodo <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> e passare <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> come valore del parametro `styles`.

L'esempio seguente illustra come eseguire il round trip di un valore <xref:System.DateTimeOffset>.

[!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
[!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]

Questa tecnica consente sempre di identificare in modo non ambiguo il valore <xref:System.DateTimeOffset> come singolo punto nel tempo. Il valore può quindi essere convertito nell'ora UTC (Coordinated Universal Time) chiamando il metodo <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> oppure può essere convertito nell'ora di un particolare fuso orario chiamando il metodo <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> o <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>. La limitazione principale di questa tecnica è che le operazioni aritmetiche con data e ora, quando eseguite su un valore <xref:System.DateTimeOffset> che rappresenta l'ora di un particolare fuso orario, possono restituire risultati non precisi per quel fuso orario. Ciò si verifica perché quando viene creata un'istanza di un valore <xref:System.DateTimeOffset>, viene rimossa l'associazione del valore dal relativo fuso orario. Di conseguenza, le regole di rettifica del fuso orario non possono più essere applicate quando si eseguono i calcoli di data e ora. È possibile risolvere questo problema mediante la definizione di un tipo personalizzato che includa sia un valore di data e ora sia il fuso orario ad esso associato.

### <a name="to-round-trip-a-date-and-time-value-with-its-time-zone"></a>Per il round trip a un valore di data e ora con il proprio fuso orario

1. Definire una classe o una struttura con due campi. Il primo campo è un oggetto <xref:System.DateTime> o <xref:System.DateTimeOffset> e il secondo è un oggetto <xref:System.TimeZoneInfo>. L'esempio seguente è una versione semplificata di tale tipo.

    [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
    [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]

2. Contrassegnare la classe con l'attributo <xref:System.SerializableAttribute>.

3. Serializzare l'oggetto usando il metodo <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>.

4. Ripristinare l'oggetto usando il metodo <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A>.

5. Eseguire il cast (in C#) o la conversione (in Visual Basic) dell'oggetto deserializzato in un oggetto del tipo appropriato.

L'esempio seguente illustra come eseguire un round trip di un oggetto che archivia informazioni relative sia a data e ora che al fuso orario.

[!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
[!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]

Questa tecnica riflette sempre senza ambiguità il punto nel tempo corretto prima e dopo il salvataggio e il ripristino, a condizione che l'implementazione dell'oggetto combinato di data e ora e fuso orario non consenta al valore di data di perdere la sincronizzazione con il valore di fuso orario.

## <a name="compiling-the-code"></a>Compilazione del codice

Gli esempi presentano i requisiti seguenti:

- Gli spazi dei nomi seguenti devono essere importati con istruzioni `using` di C# o istruzioni `Imports` di Visual Basic:

  - <xref:System> (solo C#).

  - <xref:System.Globalization?displayProperty=nameWithType>.

  - <xref:System.IO?displayProperty=nameWithType>.

  - <xref:System.Runtime.Serialization?displayProperty=nameWithType>.

  - <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.

- Ogni esempio di codice, ad eccezione della classe `DateInTimeZone`, deve essere incluso in una classe o un modulo di Visual Basic, ne deve essere eseguito il wrapping nei metodi e deve essere chiamato dal metodo `Main`.

## <a name="see-also"></a>Vedere anche

- [Esecuzione di operazioni di formattazione](../../../docs/standard/base-types/performing-formatting-operations.md)
- [Scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)
- [Stringhe di formato di data e ora standard](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)

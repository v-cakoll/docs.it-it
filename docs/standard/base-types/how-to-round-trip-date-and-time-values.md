---
title: 'Procedura: Valori di data e ora round trip'
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
ms.openlocfilehash: 60483a6e29c65fc0c5803e8084053d53d9fc3c37
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290448"
---
# <a name="how-to-round-trip-date-and-time-values"></a>Procedura: Valori di data e ora round trip

In molte applicazioni un valore di data e ora deve identificare una data e un'ora singole in modo non ambiguo. In questo articolo viene illustrato come salvare e ripristinare un valore <xref:System.DateTime> , un valore <xref:System.DateTimeOffset> e un valore di data e ora con le informazioni sul fuso orario, in modo che il valore ripristinato identifichi la stessa ora del valore salvato.

## <a name="round-trip-a-datetime-value"></a>Round trip di un valore DateTime

1. Convertire il valore <xref:System.DateTime> nella relativa rappresentazione di stringa chiamando il metodo <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> con l'identificatore di formato "o".

2. Salvare la rappresentazione di stringa del valore <xref:System.DateTime> in un file o passarla attraverso un processo, un dominio dell'applicazione o un limite della macchina.

3. Recuperare la stringa che rappresenta il valore <xref:System.DateTime>.

4. Chiamare il metodo <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> e passare <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> come valore del parametro `styles`.

L'esempio seguente illustra come eseguire il round trip di un valore <xref:System.DateTime>.

[!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
[!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]

Quando si esegue il round trip di un valore <xref:System.DateTime>, questa tecnica consente di mantenere correttamente l'ora per tutte le ore locali e UTC. Ad esempio, se un valore locale <xref:System.DateTime> viene salvato in un sistema nel fuso orario standard del Pacifico (Stati Uniti) e viene ripristinato in un sistema nel fuso orario standard degli Stati Uniti Centrali, la data e l'ora ripristinate saranno due ore avanti rispetto all'ora originale, la quale riflette la differenza di tempo tra i due fusi orari. Tuttavia, questa tecnica non è sempre accurata per le ore non specificate. Tutti i valori <xref:System.DateTime> la cui proprietà <xref:System.DateTime.Kind%2A> è <xref:System.DateTimeKind.Unspecified> vengono trattati come valori di ora locale. Se non è un'ora locale, il <xref:System.DateTime> non identifica correttamente il punto nel tempo corretto. La soluzione alternativa per questa limitazione consiste nell'associare un valore di data e ora al proprio fuso orario per l'operazione di salvataggio e ripristino.

## <a name="round-trip-a-datetimeoffset-value"></a>Round trip di un valore DateTimeOffset

1. Convertire il valore <xref:System.DateTimeOffset> nella relativa rappresentazione di stringa chiamando il metodo <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> con l'identificatore di formato "o".

2. Salvare la rappresentazione di stringa del valore <xref:System.DateTimeOffset> in un file o passarla attraverso un processo, un dominio dell'applicazione o un limite della macchina.

3. Recuperare la stringa che rappresenta il valore <xref:System.DateTimeOffset>.

4. Chiamare il metodo <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> e passare <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> come valore del parametro `styles`.

L'esempio seguente illustra come eseguire il round trip di un valore <xref:System.DateTimeOffset>.

[!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
[!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]

Questa tecnica consente sempre di identificare in modo non ambiguo il valore <xref:System.DateTimeOffset> come singolo punto nel tempo. Il valore può quindi essere convertito nell'ora UTC (Coordinated Universal Time) chiamando il metodo <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> oppure può essere convertito nell'ora di un particolare fuso orario chiamando il metodo <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> o <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>. La limitazione principale di questa tecnica è che le operazioni aritmetiche con data e ora, quando eseguite su un valore <xref:System.DateTimeOffset> che rappresenta l'ora di un particolare fuso orario, possono restituire risultati non precisi per quel fuso orario. Ciò si verifica perché quando viene creata un'istanza di un valore <xref:System.DateTimeOffset>, viene rimossa l'associazione del valore dal relativo fuso orario. Di conseguenza, le regole di rettifica del fuso orario non possono più essere applicate quando si eseguono i calcoli di data e ora. È possibile risolvere questo problema mediante la definizione di un tipo personalizzato che includa sia un valore di data e ora sia il fuso orario ad esso associato.

## <a name="round-trip-a-date-and-time-value-with-its-time-zone"></a>Round trip di un valore di data e ora con il fuso orario

1. Definire una classe o una struttura con due campi. Il primo campo è un oggetto <xref:System.DateTime> o <xref:System.DateTimeOffset> e il secondo è un oggetto <xref:System.TimeZoneInfo>. L'esempio seguente è una versione semplificata di tale tipo.

    [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
    [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]

2. Contrassegnare la classe con l'attributo <xref:System.SerializableAttribute>.

3. Serializzare l'oggetto usando il metodo <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>.

4. Ripristinare l'oggetto usando il metodo <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A>.

5. Eseguire il cast (in C#) o la conversione (in Visual Basic) dell'oggetto deserializzato in un oggetto del tipo appropriato.

Nell'esempio seguente viene illustrato come eseguire il round trip di un oggetto che archivia sia il fuso orario sia le informazioni di data e ora.

[!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
[!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]

Questa tecnica riflette sempre senza ambiguità il punto nel tempo corretto prima e dopo il salvataggio e il ripristino, a condizione che l'implementazione dell'oggetto combinato di data e ora e fuso orario non consenta al valore di data di perdere la sincronizzazione con il valore di fuso orario.

## <a name="compile-the-code"></a>Compilare il codice

Per questi esempi è necessario quanto segue:

- Gli spazi dei nomi seguenti vengono importati con le `using` direttive o Visual Basic C# `Imports` :

  - <xref:System>(Solo C#)

  - <xref:System.Globalization?displayProperty=nameWithType>

  - <xref:System.IO?displayProperty=nameWithType>

  - <xref:System.Runtime.Serialization?displayProperty=nameWithType>

  - <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>

- Ogni esempio di codice, ad eccezione della `DateInTimeZone` classe, deve essere incluso in una classe o in un modulo Visual Basic, sottoposto a incapsulamento nei metodi e chiamato dal `Main` metodo.

## <a name="see-also"></a>Vedere anche

- [Scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo](../datetime/choosing-between-datetime.md)
- [Stringhe di formato di data e ora standard](standard-date-and-time-format-strings.md)

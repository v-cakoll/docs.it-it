---
title: 'Procedura: Eseguire il round trip dei valori di data e ora'
ms.custom: 
ms.date: 03/30/2017
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
- round-trip date and time values
- dates [.NET Framework], round-trip values
- time zones [.NET Framework], round-trip date and time values
- time [.NET Framework], round-trip values
- formatting strings [.NET Framework], round-trip values
ms.assetid: b609b277-edc6-4c74-b03e-ea73324ecbdb
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 515a29e279cfa8fc100e0612fc19df7abc6a3b36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-round-trip-date-and-time-values"></a>Procedura: Eseguire il round trip dei valori di data e ora
In molte applicazioni un valore di data e ora deve identificare una data e un'ora singole in modo non ambiguo. In questo argomento viene illustrato come salvare e ripristinare un <xref:System.DateTime> valore, un <xref:System.DateTimeOffset> informazioni area valore e un valore di data e ora con il tempo in modo che il valore ripristinato identifichi alla stessa ora il valore salvato.  
  
### <a name="to-round-trip-a-datetime-value"></a>Per eseguire il round trip di un valore DateTime  
  
1.  Convertire il <xref:System.DateTime> valore nella relativa rappresentazione di stringa chiamando il <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> metodo con l'identificatore di formato "o".  
  
2.  Rappresentazione di stringa di salvare il <xref:System.DateTime> valore in un file o passarla a un processo, dominio di applicazione o all'esterno del computer.  
  
3.  Recuperare la stringa che rappresenta il <xref:System.DateTime> valore.  
  
4.  Chiamare il <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> (metodo) e passare <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> come valore della `styles` parametro.  
  
 Nell'esempio seguente viene illustrato come round trip un <xref:System.DateTime> valore.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
 [!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]  
  
 Quando eseguire un round trip un <xref:System.DateTime> valore, questa tecnica consente di mantenere correttamente l'ora per tutte le volte locale e universale. Ad esempio, se una variabile locale <xref:System.DateTime> valore viene salvato in un sistema negli Stati Uniti. ora solare pacifico e viene ripristinato in un sistema con fuso orario ora solare centrale, la data e l'ora ripristinate saranno due ore avanti rispetto all'orario originale. Ciò riflette la differenza tra i due fusi orari. Tuttavia, questa tecnica non è sempre accurata per le ore non specificate. Tutti <xref:System.DateTime> i cui valori <xref:System.DateTime.Kind%2A> proprietà <xref:System.DateTimeKind.Unspecified> vengono trattati come se fossero orari locali. Se non è il caso, il <xref:System.DateTime> non identificherà correttamente al momento corretto nel tempo. La soluzione alternativa per questa limitazione consiste nell'associare un valore di data e ora al proprio fuso orario per l'operazione di salvataggio e ripristino.  
  
### <a name="to-round-trip-a-datetimeoffset-value"></a>Per eseguire il round trip di un valore DateTimeOffset  
  
1.  Convertire il <xref:System.DateTimeOffset> valore nella relativa rappresentazione di stringa chiamando il <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> metodo con l'identificatore di formato "o".  
  
2.  Rappresentazione di stringa di salvare il <xref:System.DateTimeOffset> valore in un file o passarla a un processo, dominio di applicazione o all'esterno del computer.  
  
3.  Recuperare la stringa che rappresenta il <xref:System.DateTimeOffset> valore.  
  
4.  Chiamare il <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> (metodo) e passare <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> come valore della `styles` parametro.  
  
 Nell'esempio seguente viene illustrato come round trip un <xref:System.DateTimeOffset> valore.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
 [!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]  
  
 Questa tecnica identifica sempre senza ambiguità un <xref:System.DateTimeOffset> valore come un singolo punto nel tempo. Il valore può quindi essere convertito nell'ora Coordinated Universal Time (UTC) chiamando il <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> metodo oppure può essere convertito nell'ora di un particolare fuso orario chiamando il <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> o <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> metodo. La limitazione principale di questa tecnica è la data e ora aritmetici, durante l'esecuzione su un <xref:System.DateTimeOffset> valore che rappresenta l'ora di un particolare fuso orario, potrebbe produrre risultati non precisi per tale fuso orario. Infatti, quando un <xref:System.DateTimeOffset> viene creata un'istanza di valore, viene dissociato dal proprio fuso orario. Di conseguenza, le regole di rettifica del fuso orario non possono più essere applicate quando si eseguono i calcoli di data e ora. È possibile risolvere questo problema mediante la definizione di un tipo personalizzato che includa sia un valore di data e ora sia il fuso orario ad esso associato.  
  
### <a name="to-round-trip-a-date-and-time-value-with-its-time-zone"></a>Per il round trip a un valore di data e ora al proprio fuso orario  
  
1.  Definire una classe o una struttura con due campi. Il primo campo è un <xref:System.DateTime> o <xref:System.DateTimeOffset> oggetto e il secondo è un <xref:System.TimeZoneInfo> oggetto. L'esempio seguente è una versione semplificata di tale tipo.  
  
     [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
     [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]  
  
2.  Contrassegnare la classe con il <xref:System.SerializableAttribute> attributo.  
  
3.  Serializzare l'oggetto utilizzando il <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> metodo.  
  
4.  Ripristinare l'oggetto utilizzando il <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> metodo.  
  
5.  Eseguire il cast (in c#) o convertire (in Visual Basic) l'oggetto deserializzato in un oggetto del tipo appropriato.  
  
 Nell'esempio seguente viene illustrata la modalità di andata e ritorno di un oggetto che archivia informazioni di data e ora e fuso orario.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
 [!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]  
  
 Questa tecnica deve riflettere sempre senza ambiguità il momento esatto di tempo sia prima e dopo che viene salvato e ripristinato, fornito che l'implementazione dell'oggetto data e ora e fuso orario combinato non consente il valore della data risultare non sincronizzati con il valore del fuso orario.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi presentano i requisiti seguenti:  
  
-   L'importazione di spazi dei nomi seguenti con c# `using` istruzioni o [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` istruzioni:  
  
    -   <xref:System>(Solo c#).  
  
    -   <xref:System.Globalization?displayProperty=nameWithType>.  
  
    -   <xref:System.IO?displayProperty=nameWithType>.  
  
    -   <xref:System.Runtime.Serialization?displayProperty=nameWithType>.  
  
    -   <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.  
  
-   Un riferimento a System.Core.dll.  
  
-   Ogni esempio di codice, tranne il `DateInTimeZone` (classe), deve essere incluso in una classe o un modulo di Visual Basic, incapsulato nei metodi e chiamata dal `Main` metodo.  
  
## <a name="see-also"></a>Vedere anche  
 [Esecuzione di operazioni di formattazione](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [Scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)  
 [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)

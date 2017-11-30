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
# <a name="how-to-round-trip-date-and-time-values"></a><span data-ttu-id="90582-102">Procedura: Eseguire il round trip dei valori di data e ora</span><span class="sxs-lookup"><span data-stu-id="90582-102">How to: Round-trip Date and Time Values</span></span>
<span data-ttu-id="90582-103">In molte applicazioni un valore di data e ora deve identificare una data e un'ora singole in modo non ambiguo.</span><span class="sxs-lookup"><span data-stu-id="90582-103">In many applications, a date and time value is intended to unambiguously identify a single point in time.</span></span> <span data-ttu-id="90582-104">In questo argomento viene illustrato come salvare e ripristinare un <xref:System.DateTime> valore, un <xref:System.DateTimeOffset> informazioni area valore e un valore di data e ora con il tempo in modo che il valore ripristinato identifichi alla stessa ora il valore salvato.</span><span class="sxs-lookup"><span data-stu-id="90582-104">This topic shows how to save and restore a <xref:System.DateTime> value, a <xref:System.DateTimeOffset> value, and a date and time value with time zone information so that the restored value identifies the same time as the saved value.</span></span>  
  
### <a name="to-round-trip-a-datetime-value"></a><span data-ttu-id="90582-105">Per eseguire il round trip di un valore DateTime</span><span class="sxs-lookup"><span data-stu-id="90582-105">To round-trip a DateTime value</span></span>  
  
1.  <span data-ttu-id="90582-106">Convertire il <xref:System.DateTime> valore nella relativa rappresentazione di stringa chiamando il <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> metodo con l'identificatore di formato "o".</span><span class="sxs-lookup"><span data-stu-id="90582-106">Convert the <xref:System.DateTime> value to its string representation by calling the <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>  
  
2.  <span data-ttu-id="90582-107">Rappresentazione di stringa di salvare il <xref:System.DateTime> valore in un file o passarla a un processo, dominio di applicazione o all'esterno del computer.</span><span class="sxs-lookup"><span data-stu-id="90582-107">Save the string representation of the <xref:System.DateTime> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>  
  
3.  <span data-ttu-id="90582-108">Recuperare la stringa che rappresenta il <xref:System.DateTime> valore.</span><span class="sxs-lookup"><span data-stu-id="90582-108">Retrieve the string that represents the <xref:System.DateTime> value.</span></span>  
  
4.  <span data-ttu-id="90582-109">Chiamare il <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> (metodo) e passare <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> come valore della `styles` parametro.</span><span class="sxs-lookup"><span data-stu-id="90582-109">Call the <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>  
  
 <span data-ttu-id="90582-110">Nell'esempio seguente viene illustrato come round trip un <xref:System.DateTime> valore.</span><span class="sxs-lookup"><span data-stu-id="90582-110">The following example illustrates how to round-trip a <xref:System.DateTime> value.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
 [!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]  
  
 <span data-ttu-id="90582-111">Quando eseguire un round trip un <xref:System.DateTime> valore, questa tecnica consente di mantenere correttamente l'ora per tutte le volte locale e universale.</span><span class="sxs-lookup"><span data-stu-id="90582-111">When round-tripping a <xref:System.DateTime> value, this technique successfully preserves the time for all local and universal times.</span></span> <span data-ttu-id="90582-112">Ad esempio, se una variabile locale <xref:System.DateTime> valore viene salvato in un sistema negli Stati Uniti. ora solare pacifico e viene ripristinato in un sistema con fuso orario ora solare centrale, la data e l'ora ripristinate saranno due ore avanti rispetto all'orario originale. Ciò riflette la differenza tra i due fusi orari.</span><span class="sxs-lookup"><span data-stu-id="90582-112">For example, if a local <xref:System.DateTime> value is saved on a system in the U.S. Pacific Standard Time zone and is restored on a system in the U.S. Central Standard Time zone, the restored date and time will be two hours later than the original time, which reflects the time difference between the two time zones.</span></span> <span data-ttu-id="90582-113">Tuttavia, questa tecnica non è sempre accurata per le ore non specificate.</span><span class="sxs-lookup"><span data-stu-id="90582-113">However, this technique is not necessarily accurate for unspecified times.</span></span> <span data-ttu-id="90582-114">Tutti <xref:System.DateTime> i cui valori <xref:System.DateTime.Kind%2A> proprietà <xref:System.DateTimeKind.Unspecified> vengono trattati come se fossero orari locali.</span><span class="sxs-lookup"><span data-stu-id="90582-114">All <xref:System.DateTime> values whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Unspecified> are treated as if they are local times.</span></span> <span data-ttu-id="90582-115">Se non è il caso, il <xref:System.DateTime> non identificherà correttamente al momento corretto nel tempo.</span><span class="sxs-lookup"><span data-stu-id="90582-115">If this is not the case, the <xref:System.DateTime> will not successfully identify the correct point in time.</span></span> <span data-ttu-id="90582-116">La soluzione alternativa per questa limitazione consiste nell'associare un valore di data e ora al proprio fuso orario per l'operazione di salvataggio e ripristino.</span><span class="sxs-lookup"><span data-stu-id="90582-116">The workaround for this limitation is to tightly couple a date and time value with its time zone for the save and restore operation.</span></span>  
  
### <a name="to-round-trip-a-datetimeoffset-value"></a><span data-ttu-id="90582-117">Per eseguire il round trip di un valore DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="90582-117">To round-trip a DateTimeOffset value</span></span>  
  
1.  <span data-ttu-id="90582-118">Convertire il <xref:System.DateTimeOffset> valore nella relativa rappresentazione di stringa chiamando il <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> metodo con l'identificatore di formato "o".</span><span class="sxs-lookup"><span data-stu-id="90582-118">Convert the <xref:System.DateTimeOffset> value to its string representation by calling the <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>  
  
2.  <span data-ttu-id="90582-119">Rappresentazione di stringa di salvare il <xref:System.DateTimeOffset> valore in un file o passarla a un processo, dominio di applicazione o all'esterno del computer.</span><span class="sxs-lookup"><span data-stu-id="90582-119">Save the string representation of the <xref:System.DateTimeOffset> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>  
  
3.  <span data-ttu-id="90582-120">Recuperare la stringa che rappresenta il <xref:System.DateTimeOffset> valore.</span><span class="sxs-lookup"><span data-stu-id="90582-120">Retrieve the string that represents the <xref:System.DateTimeOffset> value.</span></span>  
  
4.  <span data-ttu-id="90582-121">Chiamare il <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> (metodo) e passare <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> come valore della `styles` parametro.</span><span class="sxs-lookup"><span data-stu-id="90582-121">Call the <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>  
  
 <span data-ttu-id="90582-122">Nell'esempio seguente viene illustrato come round trip un <xref:System.DateTimeOffset> valore.</span><span class="sxs-lookup"><span data-stu-id="90582-122">The following example illustrates how to round-trip a <xref:System.DateTimeOffset> value.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
 [!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]  
  
 <span data-ttu-id="90582-123">Questa tecnica identifica sempre senza ambiguità un <xref:System.DateTimeOffset> valore come un singolo punto nel tempo.</span><span class="sxs-lookup"><span data-stu-id="90582-123">This technique always unambiguously identifies a <xref:System.DateTimeOffset> value as a single point in time.</span></span> <span data-ttu-id="90582-124">Il valore può quindi essere convertito nell'ora Coordinated Universal Time (UTC) chiamando il <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> metodo oppure può essere convertito nell'ora di un particolare fuso orario chiamando il <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> o <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="90582-124">The value can then be converted to Coordinated Universal Time (UTC) by calling the <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> method, or it can be converted to the time in a particular time zone by calling the <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> or <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="90582-125">La limitazione principale di questa tecnica è la data e ora aritmetici, durante l'esecuzione su un <xref:System.DateTimeOffset> valore che rappresenta l'ora di un particolare fuso orario, potrebbe produrre risultati non precisi per tale fuso orario.</span><span class="sxs-lookup"><span data-stu-id="90582-125">The major limitation of this technique is that date and time arithmetic, when performed on a <xref:System.DateTimeOffset> value that represents the time in a particular time zone, may not produce accurate results for that time zone.</span></span> <span data-ttu-id="90582-126">Infatti, quando un <xref:System.DateTimeOffset> viene creata un'istanza di valore, viene dissociato dal proprio fuso orario.</span><span class="sxs-lookup"><span data-stu-id="90582-126">This is because when a <xref:System.DateTimeOffset> value is instantiated, it is disassociated from its time zone.</span></span> <span data-ttu-id="90582-127">Di conseguenza, le regole di rettifica del fuso orario non possono più essere applicate quando si eseguono i calcoli di data e ora.</span><span class="sxs-lookup"><span data-stu-id="90582-127">Therefore, that time zone's adjustment rules can no longer be applied when you perform date and time calculations.</span></span> <span data-ttu-id="90582-128">È possibile risolvere questo problema mediante la definizione di un tipo personalizzato che includa sia un valore di data e ora sia il fuso orario ad esso associato.</span><span class="sxs-lookup"><span data-stu-id="90582-128">You can work around this problem by defining a custom type that includes both a date and time value and its accompanying time zone.</span></span>  
  
### <a name="to-round-trip-a-date-and-time-value-with-its-time-zone"></a><span data-ttu-id="90582-129">Per il round trip a un valore di data e ora al proprio fuso orario</span><span class="sxs-lookup"><span data-stu-id="90582-129">To round-trip a date and time value with its time zone</span></span>  
  
1.  <span data-ttu-id="90582-130">Definire una classe o una struttura con due campi.</span><span class="sxs-lookup"><span data-stu-id="90582-130">Define a class or a structure with two fields.</span></span> <span data-ttu-id="90582-131">Il primo campo è un <xref:System.DateTime> o <xref:System.DateTimeOffset> oggetto e il secondo è un <xref:System.TimeZoneInfo> oggetto.</span><span class="sxs-lookup"><span data-stu-id="90582-131">The first field is either a <xref:System.DateTime> or a <xref:System.DateTimeOffset> object, and the second is a <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="90582-132">L'esempio seguente è una versione semplificata di tale tipo.</span><span class="sxs-lookup"><span data-stu-id="90582-132">The following example is a simple version of such a type.</span></span>  
  
     [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
     [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]  
  
2.  <span data-ttu-id="90582-133">Contrassegnare la classe con il <xref:System.SerializableAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="90582-133">Mark the class with the <xref:System.SerializableAttribute> attribute.</span></span>  
  
3.  <span data-ttu-id="90582-134">Serializzare l'oggetto utilizzando il <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="90582-134">Serialize the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> method.</span></span>  
  
4.  <span data-ttu-id="90582-135">Ripristinare l'oggetto utilizzando il <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="90582-135">Restore the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> method.</span></span>  
  
5.  <span data-ttu-id="90582-136">Eseguire il cast (in c#) o convertire (in Visual Basic) l'oggetto deserializzato in un oggetto del tipo appropriato.</span><span class="sxs-lookup"><span data-stu-id="90582-136">Cast (in C#) or convert (in Visual Basic) the deserialized object to an object of the appropriate type.</span></span>  
  
 <span data-ttu-id="90582-137">Nell'esempio seguente viene illustrata la modalità di andata e ritorno di un oggetto che archivia informazioni di data e ora e fuso orario.</span><span class="sxs-lookup"><span data-stu-id="90582-137">The following example illustrates how to round-trip an object that stores both date and time and time zone information.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
 [!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]  
  
 <span data-ttu-id="90582-138">Questa tecnica deve riflettere sempre senza ambiguità il momento esatto di tempo sia prima e dopo che viene salvato e ripristinato, fornito che l'implementazione dell'oggetto data e ora e fuso orario combinato non consente il valore della data risultare non sincronizzati con il valore del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="90582-138">This technique should always unambiguously reflect the correct point of time both before and after it is saved and restored, provided that the implementation of the combined date and time and time zone object does not allow the date value to become out of sync with the time zone value.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="90582-139">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="90582-139">Compiling the Code</span></span>  
 <span data-ttu-id="90582-140">Gli esempi presentano i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="90582-140">These examples require:</span></span>  
  
-   <span data-ttu-id="90582-141">L'importazione di spazi dei nomi seguenti con c# `using` istruzioni o [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="90582-141">That the following namespaces be imported with C# `using` statements or [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` statements:</span></span>  
  
    -   <span data-ttu-id="90582-142"><xref:System>(Solo c#).</span><span class="sxs-lookup"><span data-stu-id="90582-142"><xref:System> (C# only).</span></span>  
  
    -   <span data-ttu-id="90582-143"><xref:System.Globalization?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="90582-143"><xref:System.Globalization?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="90582-144"><xref:System.IO?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="90582-144"><xref:System.IO?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="90582-145"><xref:System.Runtime.Serialization?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="90582-145"><xref:System.Runtime.Serialization?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="90582-146"><xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="90582-146"><xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="90582-147">Un riferimento a System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="90582-147">A reference to System.Core.dll.</span></span>  
  
-   <span data-ttu-id="90582-148">Ogni esempio di codice, tranne il `DateInTimeZone` (classe), deve essere incluso in una classe o un modulo di Visual Basic, incapsulato nei metodi e chiamata dal `Main` metodo.</span><span class="sxs-lookup"><span data-stu-id="90582-148">Each code example, other than the `DateInTimeZone` class, should be included in a class or Visual Basic module, wrapped in methods, and called from the `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90582-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90582-149">See Also</span></span>  
 [<span data-ttu-id="90582-150">Esecuzione di operazioni di formattazione</span><span class="sxs-lookup"><span data-stu-id="90582-150">Performing Formatting Operations</span></span>](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [<span data-ttu-id="90582-151">Scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="90582-151">Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo</span></span>](../../../docs/standard/datetime/choosing-between-datetime.md)  
 [<span data-ttu-id="90582-152">Standard Date and Time Format Strings</span><span class="sxs-lookup"><span data-stu-id="90582-152">Standard Date and Time Format Strings</span></span>](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)

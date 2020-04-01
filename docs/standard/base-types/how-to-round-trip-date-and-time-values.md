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
ms.openlocfilehash: 4fc38b6b852f8a7b8f268fd9e8624bdf350744c8
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523812"
---
# <a name="how-to-round-trip-date-and-time-values"></a><span data-ttu-id="cd736-102">Procedura: Valori di data e ora round trip</span><span class="sxs-lookup"><span data-stu-id="cd736-102">How to: Round-trip Date and Time Values</span></span>

<span data-ttu-id="cd736-103">In molte applicazioni un valore di data e ora deve identificare una data e un'ora singole in modo non ambiguo.</span><span class="sxs-lookup"><span data-stu-id="cd736-103">In many applications, a date and time value is intended to unambiguously identify a single point in time.</span></span> <span data-ttu-id="cd736-104">Questo argomento illustra come salvare e ripristinare un valore <xref:System.DateTime>, un valore <xref:System.DateTimeOffset> e un valore di data e ora con informazioni sul fuso orario, in modo che il valore ripristinato identifichi la stessa ora del valore salvato.</span><span class="sxs-lookup"><span data-stu-id="cd736-104">This topic shows how to save and restore a <xref:System.DateTime> value, a <xref:System.DateTimeOffset> value, and a date and time value with time zone information so that the restored value identifies the same time as the saved value.</span></span>

## <a name="round-trip-a-datetime-value"></a><span data-ttu-id="cd736-105">Andata e ritorno un valore DateTime</span><span class="sxs-lookup"><span data-stu-id="cd736-105">Round-trip a DateTime value</span></span>

1. <span data-ttu-id="cd736-106">Convertire il valore <xref:System.DateTime> nella relativa rappresentazione di stringa chiamando il metodo <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> con l'identificatore di formato "o".</span><span class="sxs-lookup"><span data-stu-id="cd736-106">Convert the <xref:System.DateTime> value to its string representation by calling the <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>

2. <span data-ttu-id="cd736-107">Salvare la rappresentazione di stringa del valore <xref:System.DateTime> in un file o passarla attraverso un processo, un dominio dell'applicazione o un limite della macchina.</span><span class="sxs-lookup"><span data-stu-id="cd736-107">Save the string representation of the <xref:System.DateTime> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>

3. <span data-ttu-id="cd736-108">Recuperare la stringa che rappresenta il valore <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="cd736-108">Retrieve the string that represents the <xref:System.DateTime> value.</span></span>

4. <span data-ttu-id="cd736-109">Chiamare il metodo <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> e passare <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> come valore del parametro `styles`.</span><span class="sxs-lookup"><span data-stu-id="cd736-109">Call the <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>

<span data-ttu-id="cd736-110">L'esempio seguente illustra come eseguire il round trip di un valore <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="cd736-110">The following example illustrates how to round-trip a <xref:System.DateTime> value.</span></span>

[!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
[!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]

<span data-ttu-id="cd736-111">Quando si esegue il round trip di un valore <xref:System.DateTime>, questa tecnica consente di mantenere correttamente l'ora per tutte le ore locali e UTC.</span><span class="sxs-lookup"><span data-stu-id="cd736-111">When round-tripping a <xref:System.DateTime> value, this technique successfully preserves the time for all local and universal times.</span></span> <span data-ttu-id="cd736-112">Ad esempio, se un valore locale <xref:System.DateTime> viene salvato in un sistema nel fuso orario standard del Pacifico (Stati Uniti) e viene ripristinato in un sistema nel fuso orario standard degli Stati Uniti Centrali, la data e l'ora ripristinate saranno due ore avanti rispetto all'ora originale, la quale riflette la differenza di tempo tra i due fusi orari.</span><span class="sxs-lookup"><span data-stu-id="cd736-112">For example, if a local <xref:System.DateTime> value is saved on a system in the U.S. Pacific Standard Time zone and is restored on a system in the U.S. Central Standard Time zone, the restored date and time will be two hours later than the original time, which reflects the time difference between the two time zones.</span></span> <span data-ttu-id="cd736-113">Tuttavia, questa tecnica non è sempre accurata per le ore non specificate.</span><span class="sxs-lookup"><span data-stu-id="cd736-113">However, this technique is not necessarily accurate for unspecified times.</span></span> <span data-ttu-id="cd736-114">Tutti i valori <xref:System.DateTime> la cui proprietà <xref:System.DateTime.Kind%2A> è <xref:System.DateTimeKind.Unspecified> vengono trattati come valori di ora locale.</span><span class="sxs-lookup"><span data-stu-id="cd736-114">All <xref:System.DateTime> values whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Unspecified> are treated as if they are local times.</span></span> <span data-ttu-id="cd736-115">Se ciò non avvenisse, <xref:System.DateTime> non potrebbe identificare il punto nel tempo corretto.</span><span class="sxs-lookup"><span data-stu-id="cd736-115">If this is not the case, the <xref:System.DateTime> will not successfully identify the correct point in time.</span></span> <span data-ttu-id="cd736-116">La soluzione alternativa per questa limitazione consiste nell'associare un valore di data e ora al proprio fuso orario per l'operazione di salvataggio e ripristino.</span><span class="sxs-lookup"><span data-stu-id="cd736-116">The workaround for this limitation is to tightly couple a date and time value with its time zone for the save and restore operation.</span></span>

## <a name="round-trip-a-datetimeoffset-value"></a><span data-ttu-id="cd736-117">Round-trip un valore DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="cd736-117">Round-trip a DateTimeOffset value</span></span>

1. <span data-ttu-id="cd736-118">Convertire il valore <xref:System.DateTimeOffset> nella relativa rappresentazione di stringa chiamando il metodo <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> con l'identificatore di formato "o".</span><span class="sxs-lookup"><span data-stu-id="cd736-118">Convert the <xref:System.DateTimeOffset> value to its string representation by calling the <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>

2. <span data-ttu-id="cd736-119">Salvare la rappresentazione di stringa del valore <xref:System.DateTimeOffset> in un file o passarla attraverso un processo, un dominio dell'applicazione o un limite della macchina.</span><span class="sxs-lookup"><span data-stu-id="cd736-119">Save the string representation of the <xref:System.DateTimeOffset> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>

3. <span data-ttu-id="cd736-120">Recuperare la stringa che rappresenta il valore <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="cd736-120">Retrieve the string that represents the <xref:System.DateTimeOffset> value.</span></span>

4. <span data-ttu-id="cd736-121">Chiamare il metodo <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> e passare <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> come valore del parametro `styles`.</span><span class="sxs-lookup"><span data-stu-id="cd736-121">Call the <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>

<span data-ttu-id="cd736-122">L'esempio seguente illustra come eseguire il round trip di un valore <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="cd736-122">The following example illustrates how to round-trip a <xref:System.DateTimeOffset> value.</span></span>

[!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
[!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]

<span data-ttu-id="cd736-123">Questa tecnica consente sempre di identificare in modo non ambiguo il valore <xref:System.DateTimeOffset> come singolo punto nel tempo.</span><span class="sxs-lookup"><span data-stu-id="cd736-123">This technique always unambiguously identifies a <xref:System.DateTimeOffset> value as a single point in time.</span></span> <span data-ttu-id="cd736-124">Il valore può quindi essere convertito nell'ora UTC (Coordinated Universal Time) chiamando il metodo <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> oppure può essere convertito nell'ora di un particolare fuso orario chiamando il metodo <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> o <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cd736-124">The value can then be converted to Coordinated Universal Time (UTC) by calling the <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> method, or it can be converted to the time in a particular time zone by calling the <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> or <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="cd736-125">La limitazione principale di questa tecnica è che le operazioni aritmetiche con data e ora, quando eseguite su un valore <xref:System.DateTimeOffset> che rappresenta l'ora di un particolare fuso orario, possono restituire risultati non precisi per quel fuso orario.</span><span class="sxs-lookup"><span data-stu-id="cd736-125">The major limitation of this technique is that date and time arithmetic, when performed on a <xref:System.DateTimeOffset> value that represents the time in a particular time zone, may not produce accurate results for that time zone.</span></span> <span data-ttu-id="cd736-126">Ciò si verifica perché quando viene creata un'istanza di un valore <xref:System.DateTimeOffset>, viene rimossa l'associazione del valore dal relativo fuso orario.</span><span class="sxs-lookup"><span data-stu-id="cd736-126">This is because when a <xref:System.DateTimeOffset> value is instantiated, it is disassociated from its time zone.</span></span> <span data-ttu-id="cd736-127">Di conseguenza, le regole di rettifica del fuso orario non possono più essere applicate quando si eseguono i calcoli di data e ora.</span><span class="sxs-lookup"><span data-stu-id="cd736-127">Therefore, that time zone's adjustment rules can no longer be applied when you perform date and time calculations.</span></span> <span data-ttu-id="cd736-128">È possibile risolvere questo problema mediante la definizione di un tipo personalizzato che includa sia un valore di data e ora sia il fuso orario ad esso associato.</span><span class="sxs-lookup"><span data-stu-id="cd736-128">You can work around this problem by defining a custom type that includes both a date and time value and its accompanying time zone.</span></span>

## <a name="round-trip-a-date-and-time-value-with-its-time-zone"></a><span data-ttu-id="cd736-129">Il round trip di una data e di un'ora con il relativo fuso orario</span><span class="sxs-lookup"><span data-stu-id="cd736-129">Round-trip a date and time value with its time zone</span></span>

1. <span data-ttu-id="cd736-130">Definire una classe o una struttura con due campi.</span><span class="sxs-lookup"><span data-stu-id="cd736-130">Define a class or a structure with two fields.</span></span> <span data-ttu-id="cd736-131">Il primo campo è un oggetto <xref:System.DateTime> o <xref:System.DateTimeOffset> e il secondo è un oggetto <xref:System.TimeZoneInfo>.</span><span class="sxs-lookup"><span data-stu-id="cd736-131">The first field is either a <xref:System.DateTime> or a <xref:System.DateTimeOffset> object, and the second is a <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="cd736-132">L'esempio seguente è una versione semplificata di tale tipo.</span><span class="sxs-lookup"><span data-stu-id="cd736-132">The following example is a simple version of such a type.</span></span>

    [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
    [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]

2. <span data-ttu-id="cd736-133">Contrassegnare la classe con l'attributo <xref:System.SerializableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="cd736-133">Mark the class with the <xref:System.SerializableAttribute> attribute.</span></span>

3. <span data-ttu-id="cd736-134">Serializzare l'oggetto usando il metodo <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cd736-134">Serialize the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="cd736-135">Ripristinare l'oggetto usando il metodo <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A>.</span><span class="sxs-lookup"><span data-stu-id="cd736-135">Restore the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> method.</span></span>

5. <span data-ttu-id="cd736-136">Eseguire il cast (in C#) o la conversione (in Visual Basic) dell'oggetto deserializzato in un oggetto del tipo appropriato.</span><span class="sxs-lookup"><span data-stu-id="cd736-136">Cast (in C#) or convert (in Visual Basic) the deserialized object to an object of the appropriate type.</span></span>

<span data-ttu-id="cd736-137">L'esempio seguente illustra come eseguire un round trip di un oggetto che archivia informazioni relative sia a data e ora che al fuso orario.</span><span class="sxs-lookup"><span data-stu-id="cd736-137">The following example illustrates how to round-trip an object that stores both date and time and time zone information.</span></span>

[!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
[!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]

<span data-ttu-id="cd736-138">Questa tecnica riflette sempre senza ambiguità il punto nel tempo corretto prima e dopo il salvataggio e il ripristino, a condizione che l'implementazione dell'oggetto combinato di data e ora e fuso orario non consenta al valore di data di perdere la sincronizzazione con il valore di fuso orario.</span><span class="sxs-lookup"><span data-stu-id="cd736-138">This technique should always unambiguously reflect the correct point of time both before and after it is saved and restored, provided that the implementation of the combined date and time and time zone object does not allow the date value to become out of sync with the time zone value.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="cd736-139">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="cd736-139">Compile the code</span></span>

<span data-ttu-id="cd736-140">Questi esempi richiedono che:</span><span class="sxs-lookup"><span data-stu-id="cd736-140">These examples require that:</span></span>

- <span data-ttu-id="cd736-141">Gli spazi dei nomi seguenti `using` devono essere importati `Imports` con le direttive c'è o le istruzioni di Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="cd736-141">The following namespaces be imported with C# `using` directives or Visual Basic `Imports` statements:</span></span>

  - <span data-ttu-id="cd736-142"><xref:System>(Solo In C)</span><span class="sxs-lookup"><span data-stu-id="cd736-142"><xref:System> (C# only)</span></span>

  - <xref:System.Globalization?displayProperty=nameWithType>

  - <xref:System.IO?displayProperty=nameWithType>

  - <xref:System.Runtime.Serialization?displayProperty=nameWithType>

  - <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>

- <span data-ttu-id="cd736-143">Ogni esempio di codice, ad uso diverso dalla `DateInTimeZone` classe, deve essere incluso `Main` in una classe o in un modulo di Visual Basic, incluso nei metodi e chiamato dal metodo .</span><span class="sxs-lookup"><span data-stu-id="cd736-143">Each code example, other than the `DateInTimeZone` class, be included in a class or Visual Basic module, wrapped in methods, and called from the `Main` method.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd736-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd736-144">See also</span></span>

- [<span data-ttu-id="cd736-145">Scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="cd736-145">Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo</span></span>](../../../docs/standard/datetime/choosing-between-datetime.md)
- [<span data-ttu-id="cd736-146">Stringhe di formato di data e ora standard</span><span class="sxs-lookup"><span data-stu-id="cd736-146">Standard Date and Time Format Strings</span></span>](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)

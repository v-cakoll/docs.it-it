---
title: "Procedura: Usare fusi orari nell'aritmetica di data e ora"
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], adding and subtracting
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 053ca2d10deadf58d5bb8b4628fb5dee815d82c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026497"
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a><span data-ttu-id="7f6f1-102">Procedura: Usare fusi orari nell'aritmetica di data e ora</span><span class="sxs-lookup"><span data-stu-id="7f6f1-102">How to: Use time zones in date and time arithmetic</span></span>

<span data-ttu-id="7f6f1-103">In genere, quando si esegue Data e ora utilizzando aritmetica <xref:System.DateTime> o <xref:System.DateTimeOffset> valori, il risultato non riflette eventuali regole di rettifica del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-103">Ordinarily, when you perform date and time arithmetic using <xref:System.DateTime> or <xref:System.DateTimeOffset> values, the result does not reflect any time zone adjustment rules.</span></span> <span data-ttu-id="7f6f1-104">Questo vale anche quando il fuso orario del valore di data e ora è chiaramente identificabile (ad esempio, quando la <xref:System.DateTime.Kind%2A> è impostata su <xref:System.DateTimeKind.Local>).</span><span class="sxs-lookup"><span data-stu-id="7f6f1-104">This is true even when the time zone of the date and time value is clearly identifiable (for example, when the <xref:System.DateTime.Kind%2A> property is set to <xref:System.DateTimeKind.Local>).</span></span> <span data-ttu-id="7f6f1-105">In questo argomento viene illustrato come eseguire operazioni aritmetiche su valori di data e ora appartenenti a un determinato fuso orario.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-105">This topic shows how to perform arithmetic operations on date and time values that belong to a particular time zone.</span></span> <span data-ttu-id="7f6f1-106">I risultati delle operazioni aritmetiche rifletteranno le regole di rettifica del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-106">The results of the arithmetic operations will reflect the time zone's adjustment rules.</span></span>

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a><span data-ttu-id="7f6f1-107">Per applicare regole di rettifica ai calcoli aritmetici di data e ora</span><span class="sxs-lookup"><span data-stu-id="7f6f1-107">To apply adjustment rules to date and time arithmetic</span></span>

1. <span data-ttu-id="7f6f1-108">Implementare un metodo per vincolare un valore di data e ora al fuso orario al quale appartiene.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-108">Implement some method of closely coupling a date and time value with the time zone to which it belongs.</span></span> <span data-ttu-id="7f6f1-109">Ad esempio, dichiarare una struttura che include sia il valore di data e ora sia il fuso orario al quale appartiene.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-109">For example, declare a structure that includes both the date and time value and its time zone.</span></span> <span data-ttu-id="7f6f1-110">L'esempio seguente usa questo approccio per collegare un <xref:System.DateTime> valore al proprio fuso orario.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-110">The following example uses this approach to link a <xref:System.DateTime> value with its time zone.</span></span>

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. <span data-ttu-id="7f6f1-111">Convertire un'ora per ora Coordinated Universal Time (UTC) chiamando il <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> metodo o il <xref:System.TimeZoneInfo.ConvertTime%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="7f6f1-111">Convert a time to Coordinated Universal Time (UTC) by calling either the <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> method or the <xref:System.TimeZoneInfo.ConvertTime%2A> method.</span></span>

3. <span data-ttu-id="7f6f1-112">Eseguire l'operazione aritmetica sull'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-112">Perform the arithmetic operation on the UTC time.</span></span>

4. <span data-ttu-id="7f6f1-113">Convertire l'ora da UTC al fuso orario associato all'ora originale chiamando il <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> (metodo).</span><span class="sxs-lookup"><span data-stu-id="7f6f1-113">Convert the time from UTC to the original time's associated time zone by calling the <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span>

## <a name="example"></a><span data-ttu-id="7f6f1-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f6f1-114">Example</span></span>

<span data-ttu-id="7f6f1-115">L'esempio seguente aggiunge due ore e trenta minuti al 9 marzo 2008, alle 1.30</span><span class="sxs-lookup"><span data-stu-id="7f6f1-115">The following example adds two hours and thirty minutes to March 9, 2008, at 1:30 A.M.</span></span> <span data-ttu-id="7f6f1-116">ora solare fuso centrale (CST).</span><span class="sxs-lookup"><span data-stu-id="7f6f1-116">Central Standard Time.</span></span> <span data-ttu-id="7f6f1-117">La transizione del fuso orario all'ora legale si verifica trenta minuti dopo, alle 2.00</span><span class="sxs-lookup"><span data-stu-id="7f6f1-117">The time zone's transition to daylight saving time occurs thirty minutes later, at 2:00 A.M.</span></span> <span data-ttu-id="7f6f1-118">del 9 marzo 2008.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-118">on March 9, 2008.</span></span> <span data-ttu-id="7f6f1-119">Poiché nell'esempio vengono seguiti i quattro passaggi elencati nella sezione precedente, l'orario corretto risultante corrisponderà alle 5.00</span><span class="sxs-lookup"><span data-stu-id="7f6f1-119">Because the example follows the four steps listed in the previous section, it correctly reports the resulting time as 5:00 A.M.</span></span> <span data-ttu-id="7f6f1-120">del 9 marzo 2008.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-120">on March 9, 2008.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

<span data-ttu-id="7f6f1-121">Entrambe <xref:System.DateTime> e <xref:System.DateTimeOffset> valori sono dissociati da qualsiasi fuso orario al quale appartengono.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-121">Both <xref:System.DateTime> and <xref:System.DateTimeOffset> values are disassociated from any time zone to which they might belong.</span></span> <span data-ttu-id="7f6f1-122">Per eseguire operazioni aritmetiche di data ora con una modalità che applica automaticamente le regole di rettifica del fuso orario, il fuso orario di appartenenza di qualsiasi valore di data e ora deve essere immediatamente identificabile.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-122">To perform date and time arithmetic in a way that automatically applies a time zone's adjustment rules, the time zone to which any date and time value belongs must be immediately identifiable.</span></span> <span data-ttu-id="7f6f1-123">Ciò significa che una data e ora e il fuso orario associato devono essere strettamente collegati.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-123">This means that a date and time and its associated time zone must be tightly coupled.</span></span> <span data-ttu-id="7f6f1-124">Esistono diversi modi per ottenere questo risultato, tra cui i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f6f1-124">There are several ways to do this, which include the following:</span></span>

* <span data-ttu-id="7f6f1-125">Presupporre che tutti gli orari usati in un'applicazione appartengano a un determinato fuso orario.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-125">Assume that all times used in an application belong to a particular time zone.</span></span> <span data-ttu-id="7f6f1-126">Pur essendo appropriato in alcuni casi, questo approccio offre una flessibilità limitata e potenzialmente anche una portabilità limitata.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-126">Although appropriate in some cases, this approach offers limited flexibility and possibly limited portability.</span></span>

* <span data-ttu-id="7f6f1-127">Definire un tipo che vincoli in modo stretto una data e ora con il fuso orario associato, includendo entrambi come campi del tipo.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-127">Define a type that tightly couples a date and time with its associated time zone by including both as fields of the type.</span></span> <span data-ttu-id="7f6f1-128">Questo approccio viene usato nell'esempio di codice, che definisce una struttura per l'archiviazione della data e ora e del fuso orario in due campi membro.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-128">This approach is used in the code example, which defines a structure to store the date and time and the time zone in two member fields.</span></span>

<span data-ttu-id="7f6f1-129">Nell'esempio viene illustrato come eseguire operazioni aritmetiche su <xref:System.DateTime> valori in modo che le regole di regolazione fuso orario vengono applicate al risultato.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-129">The example illustrates how to perform arithmetic operations on <xref:System.DateTime> values so that time zone adjustment rules are applied to the result.</span></span> <span data-ttu-id="7f6f1-130">Tuttavia, <xref:System.DateTimeOffset> valori possono essere usati con la stessa semplicità.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-130">However, <xref:System.DateTimeOffset> values can be used just as easily.</span></span> <span data-ttu-id="7f6f1-131">Nell'esempio seguente viene illustrato come il codice nell'esempio originale potrebbe essere adattato per l'utilizzo <xref:System.DateTimeOffset> invece di <xref:System.DateTime> valori.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-131">The following example illustrates how the code in the original example might be adapted to use <xref:System.DateTimeOffset> instead of <xref:System.DateTime> values.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

<span data-ttu-id="7f6f1-132">Si noti che se questa aggiunta viene eseguita semplicemente il <xref:System.DateTimeOffset> valore senza prima convertirlo a UTC, il risultato riflette il momento esatto in tempo ma l'offset non riflette quello del fuso orario designato per quell'ora.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-132">Note that if this addition is simply performed on the <xref:System.DateTimeOffset> value without first converting it to UTC, the result reflects the correct point in time but its offset does not reflect that of the designated time zone for that time.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="7f6f1-133">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7f6f1-133">Compiling the code</span></span>

<span data-ttu-id="7f6f1-134">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f6f1-134">This example requires:</span></span>

* <span data-ttu-id="7f6f1-135">Aggiungere un riferimento a DLL al progetto.</span><span class="sxs-lookup"><span data-stu-id="7f6f1-135">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="7f6f1-136">Che il <xref:System> dello spazio dei nomi importati con il `using` istruzione (obbligatorio nel codice c#).</span><span class="sxs-lookup"><span data-stu-id="7f6f1-136">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="7f6f1-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f6f1-137">See also</span></span>

- [<span data-ttu-id="7f6f1-138">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="7f6f1-138">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="7f6f1-139">Esecuzione di operazioni aritmetiche con date e ore</span><span class="sxs-lookup"><span data-stu-id="7f6f1-139">Performing arithmetic operations with dates and times</span></span>](../../../docs/standard/datetime/performing-arithmetic-operations.md)

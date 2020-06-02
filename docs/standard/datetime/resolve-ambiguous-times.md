---
title: 'Procedura: risolvere orari ambigui'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
ms.openlocfilehash: ad69c0984a9d8c01ebd2198486cd0f6492a6116e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281505"
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="8bdb7-102">Procedura: risolvere orari ambigui</span><span class="sxs-lookup"><span data-stu-id="8bdb7-102">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="8bdb7-103">Un'ora ambigua è un'ora associata a più ore UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="8bdb7-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="8bdb7-104">Si verifica quando l'orologio viene riportato indietro, ad esempio durante la transizione dall'ora legale all'ora solare di un determinato fuso orario.</span><span class="sxs-lookup"><span data-stu-id="8bdb7-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="8bdb7-105">Quando si gestisce un'ora ambigua è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8bdb7-105">When handling an ambiguous time, you can do one of the following:</span></span>

- <span data-ttu-id="8bdb7-106">Fare una supposizione sulla modalità di associazione dell'ora all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="8bdb7-106">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="8bdb7-107">Si può, ad esempio, presupporre che un'ora ambigua sia sempre espressa nell'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="8bdb7-107">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

- <span data-ttu-id="8bdb7-108">Se l'ora ambigua è un elemento di dati immesso dall'utente, sarà l'utente a risolvere l'ambiguità.</span><span class="sxs-lookup"><span data-stu-id="8bdb7-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="8bdb7-109">In questo argomento viene illustrato come risolvere un'ora ambigua supponendo che rappresenti l'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="8bdb7-109">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="8bdb7-110">Per eseguire il mapping di un'ora ambigua all'ora solare del fuso orario</span><span class="sxs-lookup"><span data-stu-id="8bdb7-110">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="8bdb7-111">Chiamare il <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> metodo per determinare se l'ora è ambigua.</span><span class="sxs-lookup"><span data-stu-id="8bdb7-111">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="8bdb7-112">Se l'ora è ambigua, sottrarre l'ora dall' <xref:System.TimeSpan> oggetto restituito dalla proprietà del fuso orario <xref:System.TimeZoneInfo.BaseUtcOffset%2A> .</span><span class="sxs-lookup"><span data-stu-id="8bdb7-112">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="8bdb7-113">Chiamare il `static` `Shared` Metodo (in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> per impostare la proprietà del valore di data e ora UTC <xref:System.DateTime.Kind%2A> su <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="8bdb7-113">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="8bdb7-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="8bdb7-114">Example</span></span>

<span data-ttu-id="8bdb7-115">Nell'esempio seguente viene illustrato come convertire un'ora ambigua in ora UTC supponendo che rappresenti l'ora solare del fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="8bdb7-115">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="8bdb7-116">L'esempio è costituito da un metodo denominato `ResolveAmbiguousTime` che determina se il <xref:System.DateTime> valore passato è ambiguo.</span><span class="sxs-lookup"><span data-stu-id="8bdb7-116">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="8bdb7-117">Se il valore è ambiguo, il metodo restituisce un <xref:System.DateTime> valore che rappresenta l'ora UTC corrispondente.</span><span class="sxs-lookup"><span data-stu-id="8bdb7-117">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="8bdb7-118">Il metodo gestisce questa conversione sottraendo il valore della proprietà del fuso orario locale <xref:System.TimeZoneInfo.BaseUtcOffset%2A> dall'ora locale.</span><span class="sxs-lookup"><span data-stu-id="8bdb7-118">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="8bdb7-119">In genere, un'ora ambigua viene gestita chiamando il <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> metodo per recuperare una matrice di <xref:System.TimeSpan> oggetti che contengono i possibili offset UTC dell'ora ambigua.</span><span class="sxs-lookup"><span data-stu-id="8bdb7-119">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="8bdb7-120">Tuttavia, in questo esempio si presuppone che un'ora ambigua deve sempre essere mappata all'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="8bdb7-120">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="8bdb7-121">La <xref:System.TimeZoneInfo.BaseUtcOffset%2A> proprietà restituisce l'offset tra l'ora UTC e l'ora solare di un fuso orario.</span><span class="sxs-lookup"><span data-stu-id="8bdb7-121">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="8bdb7-122">In questo esempio, tutti i riferimenti al fuso orario locale vengono eseguiti tramite la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Proprietà. il fuso orario locale non viene mai assegnato a una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="8bdb7-122">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="8bdb7-123">Si tratta di una procedura consigliata perché una chiamata al <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> metodo invalida gli oggetti a cui è assegnato il fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="8bdb7-123">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="8bdb7-124">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8bdb7-124">Compiling the code</span></span>

<span data-ttu-id="8bdb7-125">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8bdb7-125">This example requires:</span></span>

- <span data-ttu-id="8bdb7-126">Che lo <xref:System> spazio dei nomi venga importato con l' `using` istruzione (obbligatoria nel codice C#).</span><span class="sxs-lookup"><span data-stu-id="8bdb7-126">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="8bdb7-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bdb7-127">See also</span></span>

- [<span data-ttu-id="8bdb7-128">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="8bdb7-128">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="8bdb7-129">Procedura: consentire agli utenti di risolvere orari ambigui</span><span class="sxs-lookup"><span data-stu-id="8bdb7-129">How to: Let users resolve ambiguous times</span></span>](let-users-resolve-ambiguous-times.md)

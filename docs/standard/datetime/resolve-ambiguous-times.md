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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb09b1f087e0a0f726d32d85e06cfb2a9ec741a8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863134"
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="1746b-102">Procedura: risolvere orari ambigui</span><span class="sxs-lookup"><span data-stu-id="1746b-102">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="1746b-103">Un'ora ambigua è un'ora associata a più ore UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="1746b-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="1746b-104">Si verifica quando l'orologio viene riportato indietro, ad esempio durante la transizione dall'ora legale all'ora solare di un determinato fuso orario.</span><span class="sxs-lookup"><span data-stu-id="1746b-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="1746b-105">Quando si gestisce un'ora ambigua è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1746b-105">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="1746b-106">Fare una supposizione sulla modalità di associazione dell'ora all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="1746b-106">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="1746b-107">Si può, ad esempio, presupporre che un'ora ambigua sia sempre espressa nell'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="1746b-107">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

* <span data-ttu-id="1746b-108">Se l'ora ambigua è un elemento di dati immesso dall'utente, sarà l'utente a risolvere l'ambiguità.</span><span class="sxs-lookup"><span data-stu-id="1746b-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="1746b-109">In questo argomento viene illustrato come risolvere un'ora ambigua presupponendo che rappresenti l'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="1746b-109">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="1746b-110">Per eseguire il mapping di un'ora ambigua all'ora solare del fuso orario</span><span class="sxs-lookup"><span data-stu-id="1746b-110">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="1746b-111">Chiamare il <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> metodo per determinare se l'ora è ambigua.</span><span class="sxs-lookup"><span data-stu-id="1746b-111">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="1746b-112">Se l'ora è ambigua, sottrarre l'ora dal <xref:System.TimeSpan> oggetto restituito da del fuso orario <xref:System.TimeZoneInfo.BaseUtcOffset%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="1746b-112">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="1746b-113">Chiamare il `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> per impostare l'ora UTC data e ora del valore <xref:System.DateTime.Kind%2A> proprietà <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1746b-113">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="1746b-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="1746b-114">Example</span></span>

<span data-ttu-id="1746b-115">Nell'esempio seguente viene illustrato come convertire un orario ambiguo in ora UTC, presupponendo che rappresenti l'ora solare del fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="1746b-115">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="1746b-116">L'esempio è costituito da un metodo denominato `ResolveAmbiguousTime` che determina se il <xref:System.DateTime> valore passato è ambiguo.</span><span class="sxs-lookup"><span data-stu-id="1746b-116">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="1746b-117">Se il valore è ambiguo, il metodo restituisce un <xref:System.DateTime> valore che rappresenta l'ora UTC corrispondente.</span><span class="sxs-lookup"><span data-stu-id="1746b-117">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="1746b-118">Il metodo gestisce questa conversione sottraendo il valore del fuso orario locale <xref:System.TimeZoneInfo.BaseUtcOffset%2A> proprietà dall'ora locale.</span><span class="sxs-lookup"><span data-stu-id="1746b-118">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="1746b-119">In genere, un'ora ambigua viene gestita chiamando il <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> metodo per recuperare una matrice di <xref:System.TimeSpan> oggetti contenenti UTC possibili dell'ora ambigua viene eseguito l'offset.</span><span class="sxs-lookup"><span data-stu-id="1746b-119">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="1746b-120">Tuttavia, in questo esempio si presuppone che un'ora ambigua deve sempre essere mappata all'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="1746b-120">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="1746b-121">Il <xref:System.TimeZoneInfo.BaseUtcOffset%2A> proprietà restituisce l'offset tra l'ora UTC e l'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="1746b-121">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="1746b-122">In questo esempio, tutti i riferimenti al fuso orario locale vengono effettuati tramite il <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> proprietà; l'ora locale zona non viene mai assegnata a una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="1746b-122">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="1746b-123">Si tratta di una procedura consigliata, perché una chiamata al <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> metodo invalida tutti gli oggetti cui è assegnato il fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="1746b-123">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="1746b-124">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="1746b-124">Compiling the code</span></span>

<span data-ttu-id="1746b-125">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1746b-125">This example requires:</span></span>

* <span data-ttu-id="1746b-126">Aggiungere un riferimento a DLL al progetto.</span><span class="sxs-lookup"><span data-stu-id="1746b-126">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="1746b-127">Che il <xref:System> dello spazio dei nomi importati con il `using` istruzione (obbligatorio nel codice c#).</span><span class="sxs-lookup"><span data-stu-id="1746b-127">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="1746b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1746b-128">See also</span></span>

* [<span data-ttu-id="1746b-129">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="1746b-129">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
* [<span data-ttu-id="1746b-130">Procedura: Consentire agli utenti di risolvere orari ambigui</span><span class="sxs-lookup"><span data-stu-id="1746b-130">How to: Let users resolve ambiguous times</span></span>](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)

---
title: 'Procedura: risolvere orari ambigui'
ms.custom: 
ms.date: 04/10/2017
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
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e3706747848dbcd29d4ed2e81d5b7447a127a653
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="d5d35-102">Procedura: risolvere orari ambigui</span><span class="sxs-lookup"><span data-stu-id="d5d35-102">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="d5d35-103">Un'ora ambigua è un'ora associata a più ore UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="d5d35-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="d5d35-104">Si verifica quando l'orologio viene riportato indietro, ad esempio durante la transizione dall'ora legale all'ora solare di un determinato fuso orario.</span><span class="sxs-lookup"><span data-stu-id="d5d35-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="d5d35-105">Quando si gestisce un'ora ambigua è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d5d35-105">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="d5d35-106">Fare una supposizione sulla modalità di associazione dell'ora all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="d5d35-106">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="d5d35-107">Si può, ad esempio, presupporre che un'ora ambigua sia sempre espressa nell'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="d5d35-107">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

* <span data-ttu-id="d5d35-108">Se l'ora ambigua è un elemento di dati immesso dall'utente, sarà l'utente a risolvere l'ambiguità.</span><span class="sxs-lookup"><span data-stu-id="d5d35-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="d5d35-109">In questo argomento viene illustrato come risolvere un'ora ambigua presupponendo che rappresenti l'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="d5d35-109">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="d5d35-110">Per eseguire il mapping di un'ora ambigua all'ora solare del fuso orario</span><span class="sxs-lookup"><span data-stu-id="d5d35-110">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="d5d35-111">Chiamare il <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> metodo per determinare se l'ora è ambigua.</span><span class="sxs-lookup"><span data-stu-id="d5d35-111">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="d5d35-112">Se l'ora è ambigua, sottrarre l'ora dal <xref:System.TimeSpan> oggetto restituito da del fuso orario <xref:System.TimeZoneInfo.BaseUtcOffset%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="d5d35-112">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="d5d35-113">Chiamare il `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> per impostare l'ora UTC data e ora del valore <xref:System.DateTime.Kind%2A> proprietà <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d5d35-113">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="d5d35-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="d5d35-114">Example</span></span>

<span data-ttu-id="d5d35-115">Nell'esempio seguente viene illustrato come convertire un'ora ambigua in UTC, presupponendo che rappresenti l'ora solare del fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="d5d35-115">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="d5d35-116">L'esempio è costituito da un metodo denominato `ResolveAmbiguousTime` che determina se il <xref:System.DateTime> valore passato è ambiguo.</span><span class="sxs-lookup"><span data-stu-id="d5d35-116">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="d5d35-117">Se il valore è ambiguo, il metodo restituisce un <xref:System.DateTime> valore che rappresenta l'ora UTC corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d5d35-117">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="d5d35-118">Il metodo gestisce questa conversione sottraendo il valore del fuso orario locale <xref:System.TimeZoneInfo.BaseUtcOffset%2A> proprietà dall'ora locale.</span><span class="sxs-lookup"><span data-stu-id="d5d35-118">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="d5d35-119">In genere, un'ora ambigua è gestita tramite la chiamata di <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> metodo per recuperare una matrice di <xref:System.TimeSpan> offset di oggetti che contengono UTC possibili dell'ora ambigua.</span><span class="sxs-lookup"><span data-stu-id="d5d35-119">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="d5d35-120">Tuttavia, in questo esempio si presuppone che un'ora ambigua deve sempre essere mappata all'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="d5d35-120">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="d5d35-121">Il <xref:System.TimeZoneInfo.BaseUtcOffset%2A> proprietà restituisce l'offset tra l'ora UTC e l'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="d5d35-121">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="d5d35-122">In questo esempio, tutti i riferimenti per il fuso orario locale vengono effettuati tramite il <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> proprietà; l'ora locale zona non viene mai assegnata a una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="d5d35-122">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="d5d35-123">Si tratta di una procedura consigliata, perché una chiamata al <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> metodo invalida tutti gli oggetti assegnati per il fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="d5d35-123">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="d5d35-124">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d5d35-124">Compiling the code</span></span>

<span data-ttu-id="d5d35-125">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d5d35-125">This example requires:</span></span>

* <span data-ttu-id="d5d35-126">Un riferimento a System.Core.dll essere aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="d5d35-126">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="d5d35-127">Che il <xref:System> dello spazio dei nomi importati con il `using` istruzione (richiesto nel codice c#).</span><span class="sxs-lookup"><span data-stu-id="d5d35-127">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="d5d35-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5d35-128">See also</span></span>

<span data-ttu-id="d5d35-129">[Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
[procedura: consentire agli utenti di risolvere orari ambigui](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)</span><span class="sxs-lookup"><span data-stu-id="d5d35-129">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Let users resolve ambiguous times](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)</span></span>

---
title: 'Procedura: consentire agli utenti di risolvere orari ambigui'
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91e80f44934092007f6f842f0694789d49321446
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863551"
---
# <a name="how-to-let-users-resolve-ambiguous-times"></a><span data-ttu-id="71c44-102">Procedura: consentire agli utenti di risolvere orari ambigui</span><span class="sxs-lookup"><span data-stu-id="71c44-102">How to: Let users resolve ambiguous times</span></span>

<span data-ttu-id="71c44-103">Un'ora ambigua è un'ora associata a più ore UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="71c44-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="71c44-104">Si verifica quando l'orologio viene riportato indietro, ad esempio durante la transizione dall'ora legale all'ora solare di un determinato fuso orario.</span><span class="sxs-lookup"><span data-stu-id="71c44-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="71c44-105">Quando si gestisce un'ora ambigua è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="71c44-105">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="71c44-106">Se l'ora ambigua è un elemento di dati immesso dall'utente, sarà l'utente a risolvere l'ambiguità.</span><span class="sxs-lookup"><span data-stu-id="71c44-106">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

* <span data-ttu-id="71c44-107">Fare una supposizione sulla modalità di associazione dell'ora all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="71c44-107">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="71c44-108">Si può, ad esempio, presupporre che un'ora ambigua sia sempre espressa nell'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="71c44-108">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

<span data-ttu-id="71c44-109">Questo argomento illustra come consentire agli utenti di risolvere orari ambigui.</span><span class="sxs-lookup"><span data-stu-id="71c44-109">This topic shows how to let a user resolve an ambiguous time.</span></span>

### <a name="to-let-a-user-resolve-an-ambiguous-time"></a><span data-ttu-id="71c44-110">Consentire a un utente di risolvere orari ambigui</span><span class="sxs-lookup"><span data-stu-id="71c44-110">To let a user resolve an ambiguous time</span></span>

1. <span data-ttu-id="71c44-111">Ottenere l'input di data e ora dall'utente.</span><span class="sxs-lookup"><span data-stu-id="71c44-111">Get the date and time input by the user.</span></span>

2. <span data-ttu-id="71c44-112">Chiamare il <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> metodo per determinare se l'ora è ambigua.</span><span class="sxs-lookup"><span data-stu-id="71c44-112">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

3. <span data-ttu-id="71c44-113">Se l'ora è ambigua, chiamare il <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> metodo per recuperare una matrice di <xref:System.TimeSpan> oggetti.</span><span class="sxs-lookup"><span data-stu-id="71c44-113">If the time is ambiguous, call the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects.</span></span> <span data-ttu-id="71c44-114">Ogni elemento nella matrice contiene un offset UTC a cui l'ora ambigua è possibile eseguire il mapping a.</span><span class="sxs-lookup"><span data-stu-id="71c44-114">Each element in the array contains a UTC offset that the ambiguous time can map to.</span></span>

4. <span data-ttu-id="71c44-115">Consentire all'utente di selezionare l'offset desiderato.</span><span class="sxs-lookup"><span data-stu-id="71c44-115">Let the user select the desired offset.</span></span>

5. <span data-ttu-id="71c44-116">Ottenere la data e l'ora UTC sottraendo dall'ora locale l'offset selezionato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="71c44-116">Get the UTC date and time by subtracting the offset selected by the user from the local time.</span></span>

6. <span data-ttu-id="71c44-117">Chiamare il `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> per impostare l'ora UTC data e ora del valore <xref:System.DateTime.Kind%2A> proprietà <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="71c44-117">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="71c44-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="71c44-118">Example</span></span>

<span data-ttu-id="71c44-119">Nell'esempio seguente si richiede all'utente di immettere una data e l'ora e, se è ambigua, si consente all'utente di selezionare l'ora UTC alla quale è associata l'ora ambigua.</span><span class="sxs-lookup"><span data-stu-id="71c44-119">The following example prompts the user to enter a date and time and, if it is ambiguous, lets the user select the UTC time that the ambiguous time maps to.</span></span>

[!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
[!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]

<span data-ttu-id="71c44-120">Il nucleo del codice di esempio Usa una matrice di <xref:System.TimeSpan> oggetti per indicare i possibili offset dell'ora ambigua dall'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="71c44-120">The core of the example code uses an array of <xref:System.TimeSpan> objects to indicate possible offsets of the ambiguous time from UTC.</span></span> <span data-ttu-id="71c44-121">Tuttavia, questi offset probabilmente non sono significativi per l'utente.</span><span class="sxs-lookup"><span data-stu-id="71c44-121">However, these offsets are unlikely to be meaningful to the user.</span></span> <span data-ttu-id="71c44-122">Per chiarire il significato degli offset, il codice indica anche se un offset rappresenta l'ora solare o l'ora legale del fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="71c44-122">To clarify the meaning of the offsets, the code also notes whether an offset represents the local time zone's standard time or its daylight saving time.</span></span> <span data-ttu-id="71c44-123">Il codice determina quale ora è standard e che ora è legale confrontando l'offset con il valore della <xref:System.TimeZoneInfo.BaseUtcOffset%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="71c44-123">The code determines which time is standard and which time is daylight by comparing the offset with the value of the <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span> <span data-ttu-id="71c44-124">Questa proprietà indica la differenza tra l'ora solare del fuso orario corrente e l'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="71c44-124">This property indicates the difference between the UTC and the time zone's standard time.</span></span>

<span data-ttu-id="71c44-125">In questo esempio, tutti i riferimenti al fuso orario locale vengono effettuati tramite il <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> proprietà; l'ora locale zona non viene mai assegnata a una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="71c44-125">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="71c44-126">Si tratta di una procedura consigliata, perché una chiamata al <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> metodo invalida tutti gli oggetti cui è assegnato il fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="71c44-126">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="71c44-127">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="71c44-127">Compiling the code</span></span>

<span data-ttu-id="71c44-128">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="71c44-128">This example requires:</span></span>

* <span data-ttu-id="71c44-129">Aggiungere un riferimento a DLL al progetto.</span><span class="sxs-lookup"><span data-stu-id="71c44-129">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="71c44-130">Che il <xref:System> dello spazio dei nomi importati con il `using` istruzione (obbligatorio nel codice c#).</span><span class="sxs-lookup"><span data-stu-id="71c44-130">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="71c44-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71c44-131">See also</span></span>

* [<span data-ttu-id="71c44-132">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="71c44-132">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
* [<span data-ttu-id="71c44-133">Procedura: Risolvere orari ambigui</span><span class="sxs-lookup"><span data-stu-id="71c44-133">How to: Resolve ambiguous times</span></span>](../../../docs/standard/datetime/resolve-ambiguous-times.md)

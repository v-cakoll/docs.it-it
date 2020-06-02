---
title: 'Procedura: consentire agli utenti di risolvere orari ambigui'
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
ms.openlocfilehash: ac723738d80a2f686a5fcaf279cec791b3c58619
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281583"
---
# <a name="how-to-let-users-resolve-ambiguous-times"></a><span data-ttu-id="86ed7-102">Procedura: consentire agli utenti di risolvere orari ambigui</span><span class="sxs-lookup"><span data-stu-id="86ed7-102">How to: Let users resolve ambiguous times</span></span>

<span data-ttu-id="86ed7-103">Un'ora ambigua è un'ora associata a più ore UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="86ed7-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="86ed7-104">Si verifica quando l'orologio viene riportato indietro, ad esempio durante la transizione dall'ora legale all'ora solare di un determinato fuso orario.</span><span class="sxs-lookup"><span data-stu-id="86ed7-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="86ed7-105">Quando si gestisce un'ora ambigua è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="86ed7-105">When handling an ambiguous time, you can do one of the following:</span></span>

- <span data-ttu-id="86ed7-106">Se l'ora ambigua è un elemento di dati immesso dall'utente, sarà l'utente a risolvere l'ambiguità.</span><span class="sxs-lookup"><span data-stu-id="86ed7-106">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

- <span data-ttu-id="86ed7-107">Fare una supposizione sulla modalità di associazione dell'ora all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="86ed7-107">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="86ed7-108">Si può, ad esempio, presupporre che un'ora ambigua sia sempre espressa nell'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="86ed7-108">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

<span data-ttu-id="86ed7-109">In questo argomento viene illustrato come consentire a un utente di risolvere un'ora ambigua.</span><span class="sxs-lookup"><span data-stu-id="86ed7-109">This topic shows how to let a user resolve an ambiguous time.</span></span>

### <a name="to-let-a-user-resolve-an-ambiguous-time"></a><span data-ttu-id="86ed7-110">Consentire a un utente di risolvere orari ambigui</span><span class="sxs-lookup"><span data-stu-id="86ed7-110">To let a user resolve an ambiguous time</span></span>

1. <span data-ttu-id="86ed7-111">Ottenere l'input di data e ora dall'utente.</span><span class="sxs-lookup"><span data-stu-id="86ed7-111">Get the date and time input by the user.</span></span>

2. <span data-ttu-id="86ed7-112">Chiamare il <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> metodo per determinare se l'ora è ambigua.</span><span class="sxs-lookup"><span data-stu-id="86ed7-112">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

3. <span data-ttu-id="86ed7-113">Se l'ora è ambigua, chiamare il <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> metodo per recuperare una matrice di <xref:System.TimeSpan> oggetti.</span><span class="sxs-lookup"><span data-stu-id="86ed7-113">If the time is ambiguous, call the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects.</span></span> <span data-ttu-id="86ed7-114">Ogni elemento nella matrice contiene un offset UTC a cui è possibile eseguire il mapping dell'ora ambigua.</span><span class="sxs-lookup"><span data-stu-id="86ed7-114">Each element in the array contains a UTC offset that the ambiguous time can map to.</span></span>

4. <span data-ttu-id="86ed7-115">Consentire all'utente di selezionare l'offset desiderato.</span><span class="sxs-lookup"><span data-stu-id="86ed7-115">Let the user select the desired offset.</span></span>

5. <span data-ttu-id="86ed7-116">Ottenere la data e l'ora UTC sottraendo dall'ora locale l'offset selezionato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="86ed7-116">Get the UTC date and time by subtracting the offset selected by the user from the local time.</span></span>

6. <span data-ttu-id="86ed7-117">Chiamare il `static` `Shared` Metodo (in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> per impostare la proprietà del valore di data e ora UTC <xref:System.DateTime.Kind%2A> su <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="86ed7-117">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="86ed7-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="86ed7-118">Example</span></span>

<span data-ttu-id="86ed7-119">Nell'esempio seguente si richiede all'utente di immettere una data e l'ora e, se è ambigua, si consente all'utente di selezionare l'ora UTC alla quale è associata l'ora ambigua.</span><span class="sxs-lookup"><span data-stu-id="86ed7-119">The following example prompts the user to enter a date and time and, if it is ambiguous, lets the user select the UTC time that the ambiguous time maps to.</span></span>

[!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
[!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]

<span data-ttu-id="86ed7-120">Il nucleo del codice di esempio usa una matrice di <xref:System.TimeSpan> oggetti per indicare possibili offset dell'ora ambigua dall'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="86ed7-120">The core of the example code uses an array of <xref:System.TimeSpan> objects to indicate possible offsets of the ambiguous time from UTC.</span></span> <span data-ttu-id="86ed7-121">Tuttavia, questi offset probabilmente non sono significativi per l'utente.</span><span class="sxs-lookup"><span data-stu-id="86ed7-121">However, these offsets are unlikely to be meaningful to the user.</span></span> <span data-ttu-id="86ed7-122">Per chiarire il significato degli offset, il codice indica anche se un offset rappresenta l'ora solare o l'ora legale del fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="86ed7-122">To clarify the meaning of the offsets, the code also notes whether an offset represents the local time zone's standard time or its daylight saving time.</span></span> <span data-ttu-id="86ed7-123">Il codice determina il tempo standard e l'ora legale confrontando l'offset con il valore della <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="86ed7-123">The code determines which time is standard and which time is daylight by comparing the offset with the value of the <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span> <span data-ttu-id="86ed7-124">Questa proprietà indica la differenza tra l'ora solare del fuso orario corrente e l'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="86ed7-124">This property indicates the difference between the UTC and the time zone's standard time.</span></span>

<span data-ttu-id="86ed7-125">In questo esempio, tutti i riferimenti al fuso orario locale vengono eseguiti tramite la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Proprietà. il fuso orario locale non viene mai assegnato a una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="86ed7-125">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="86ed7-126">Si tratta di una procedura consigliata perché una chiamata al <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> metodo invalida gli oggetti a cui è assegnato il fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="86ed7-126">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="86ed7-127">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="86ed7-127">Compiling the code</span></span>

<span data-ttu-id="86ed7-128">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="86ed7-128">This example requires:</span></span>

- <span data-ttu-id="86ed7-129">Che lo <xref:System> spazio dei nomi venga importato con l' `using` istruzione (obbligatoria nel codice C#).</span><span class="sxs-lookup"><span data-stu-id="86ed7-129">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="86ed7-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86ed7-130">See also</span></span>

- [<span data-ttu-id="86ed7-131">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="86ed7-131">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="86ed7-132">Procedura: risolvere orari ambigui</span><span class="sxs-lookup"><span data-stu-id="86ed7-132">How to: Resolve ambiguous times</span></span>](resolve-ambiguous-times.md)

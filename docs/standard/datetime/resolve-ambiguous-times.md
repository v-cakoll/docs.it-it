---
title: 'Procedura: Risolvere orari ambigui'
description: Come risolvere gli orari ambigui
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e86050c6-d16d-405e-8bba-7205945c9a81
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f4ab3b4bf3487e70be7e885e9b8a2281927eb30e
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="c5286-104">Procedura: Risolvere orari ambigui</span><span class="sxs-lookup"><span data-stu-id="c5286-104">How to: resolve ambiguous times</span></span>

<span data-ttu-id="c5286-105">Un'ora ambigua è un'ora associata a più ore UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="c5286-105">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="c5286-106">Si verifica quando l'orologio viene riportato indietro, ad esempio durante la transizione dall'ora legale all'ora solare di un determinato fuso orario.</span><span class="sxs-lookup"><span data-stu-id="c5286-106">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="c5286-107">Quando si gestisce un'ora ambigua è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5286-107">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="c5286-108">Fare una supposizione sulla modalità di associazione dell'ora all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="c5286-108">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="c5286-109">Si può, ad esempio, presupporre che un'ora ambigua sia sempre espressa nell'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="c5286-109">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

* <span data-ttu-id="c5286-110">Se l'ora ambigua è un elemento di dati immesso dall'utente, sarà l'utente a risolvere l'ambiguità.</span><span class="sxs-lookup"><span data-stu-id="c5286-110">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="c5286-111">In questo articolo viene illustrato come risolvere un'ora ambigua presupponendo che rappresenti l'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="c5286-111">This article shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

## <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="c5286-112">Per eseguire il mapping di un'ora ambigua all'ora solare del fuso orario</span><span class="sxs-lookup"><span data-stu-id="c5286-112">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="c5286-113">Chiamare il metodo[System.TimeZoneInfo.IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) o [System.TimeZoneInfo.IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) per determinare se l'ora è ambigua.</span><span class="sxs-lookup"><span data-stu-id="c5286-113">Call the [System.TimeZoneInfo.IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) or [System.TimeZoneInfo.IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="c5286-114">Se l'ora è ambigua, sottrarre l'ora dall'oggetto [TimeSpan](xref:System.TimeSpan) restituito dalla proprietà [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="c5286-114">If the time is ambiguous, subtract the time from the [TimeSpan](xref:System.TimeSpan) object returned by the time zone's [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property.</span></span>

3. <span data-ttu-id="c5286-115">Chiamare il metodo `static` (`Shared` in Visual Basic) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) per impostare la proprietà [Kind](xref:System.DateTime.Kind) del valore di data e ora UTC su [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span><span class="sxs-lookup"><span data-stu-id="c5286-115">Call the `static` (`Shared` in Visual Basic) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method to set the UTC date and time value's [Kind](xref:System.DateTime.Kind) property to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

## <a name="example"></a><span data-ttu-id="c5286-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5286-116">Example</span></span>

<span data-ttu-id="c5286-117">Nell'esempio seguente viene illustrato come convertire un valore [DateTime](xref:System.DateTime) ambiguo in ora UTC, presupponendo che rappresenti l'ora solare del fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="c5286-117">The following example illustrates how to convert an ambiguous [DateTime](xref:System.DateTime) to UTC by assuming that it represents the local time zone's standard time.</span></span> 

```csharp
private DateTime ResolveAmbiguousTime(DateTime ambiguousTime)
{
   // Time is not ambiguous
   if (! TimeZoneInfo.Local.IsAmbiguousTime(ambiguousTime))
   { 
      return ambiguousTime; 
   }
   // Time is ambiguous
   else
   {
      DateTime utcTime = DateTime.SpecifyKind(ambiguousTime - TimeZoneInfo.Local.BaseUtcOffset, 
                                              DateTimeKind.Utc);      
      Console.WriteLine("{0} local time corresponds to {1} {2}.", 
                        ambiguousTime, utcTime, utcTime.Kind.ToString());
      return utcTime;            
   }   
}
```

```vb
Private Function ResolveAmbiguousTime(ambiguousTime As Date) As Date
   ' Time is not ambiguous
   If Not TimeZoneInfo.Local.IsAmbiguousTime(ambiguousTime) Then 
      Return TimeZoneInfo.ConvertTimeToUtc(ambiguousTime) 
   ' Time is ambiguous
   Else
      Dim utcTime As Date = DateTime.SpecifyKind(ambiguousTime - TimeZoneInfo.Local.BaseUtcOffset, DateTimeKind.Utc)      
      Console.WriteLine("{0} local time corresponds to {1} {2}.", ambiguousTime, utcTime, utcTime.Kind.ToString())
      Return utcTime            
   End If   
End Function
```

<span data-ttu-id="c5286-118">L'esempio è costituito da un metodo denominato `ResolveAmbiguousTime` che determina se il valore [DateTime](xref:System.DateTime) passato è ambiguo.</span><span class="sxs-lookup"><span data-stu-id="c5286-118">The example consists of a method named `ResolveAmbiguousTime` that determines whether the [DateTime](xref:System.DateTime) value passed to it is ambiguous.</span></span> <span data-ttu-id="c5286-119">Se il valore è ambiguo, il metodo restituisce un valore [DateTime](xref:System.DateTime) che rappresenta l'ora UTC corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c5286-119">If the value is ambiguous, the method returns a [DateTime](xref:System.DateTime) value that represents the corresponding UTC time.</span></span> <span data-ttu-id="c5286-120">Il metodo gestisce questa conversione sottraendo il valore della proprietà [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) del fuso orario locale dall'ora locale.</span><span class="sxs-lookup"><span data-stu-id="c5286-120">The method handles this conversion by subtracting the value of the local time zone's [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property from the local time.</span></span> 

<span data-ttu-id="c5286-121">In genere, un'ora ambigua viene gestita chiamando il metodo [GetAmbiguousTimeOffsets](xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets(System.DateTime)) per recuperare una matrice di oggetti [TimeSpan](xref:System.TimeSpan) contenenti i possibili offset dall'ora UTC dell'ora ambigua.</span><span class="sxs-lookup"><span data-stu-id="c5286-121">Ordinarily, an ambiguous time is handled by calling the [GetAmbiguousTimeOffsets](xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets(System.DateTime)) method to retrieve an array of [TimeSpan](xref:System.TimeSpan) objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="c5286-122">Tuttavia, in questo esempio si presuppone che un'ora ambigua deve sempre essere mappata all'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="c5286-122">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="c5286-123">La proprietà [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) restituisce l'offset tra l'ora UTC e l'ora solare di un fuso orario.</span><span class="sxs-lookup"><span data-stu-id="c5286-123">The [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property returns the offset between UTC and a time zone's standard time.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5286-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5286-124">See Also</span></span>

[<span data-ttu-id="c5286-125">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="c5286-125">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="c5286-126">Procedura: Consentire agli utenti di risolvere orari ambigui</span><span class="sxs-lookup"><span data-stu-id="c5286-126">How to: let users resolve ambiguous times</span></span>](let-users-resolve-ambiguous-times.md)



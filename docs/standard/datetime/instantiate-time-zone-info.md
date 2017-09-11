---
title: 'Procedura: Creare un&quot;istanza di un oggetto TimeZoneInfo'
description: Come creare un&quot;istanza di un oggetto TimeZoneInfo
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: bff137e5-d550-44c3-b460-b3f2dabd4035
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f2584d446c92d2df2f6d74533ef07fe96888d36a
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="a5f97-104">Procedura: Creare un'istanza di un oggetto TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="a5f97-104">How to: instantiate a TimeZoneInfo object</span></span>

<span data-ttu-id="a5f97-105">Il modo più comune per creare un'istanza di un oggetto [TimeZoneInfo](xref:System.TimeZoneInfo) è recuperare le relative informazioni dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a5f97-105">The most common way to instantiate a [TimeZoneInfo](xref:System.TimeZoneInfo) object is to retrieve information about it from the operating system.</span></span> <span data-ttu-id="a5f97-106">Questo argomento illustra come creare un'istanza di un oggetto [TimeZoneInfo](xref:System.TimeZoneInfo) dal sistema locale.</span><span class="sxs-lookup"><span data-stu-id="a5f97-106">This topic discusses how to instantiate a [TimeZoneInfo](xref:System.TimeZoneInfo) object from the local system.</span></span>

## <a name="to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="a5f97-107">Per creare un'istanza di un oggetto TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="a5f97-107">To instantiate a TimeZoneInfo Object</span></span>

1. <span data-ttu-id="a5f97-108">Dichiarare un oggetto [TimeZoneInfo](xref:System.TimeZoneInfo).</span><span class="sxs-lookup"><span data-stu-id="a5f97-108">Declare a [TimeZoneInfo](xref:System.TimeZoneInfo) object.</span></span>

2. <span data-ttu-id="a5f97-109">Chiamare il metodo `static` (`Shared` in Visual Basic) [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)).</span><span class="sxs-lookup"><span data-stu-id="a5f97-109">Call the `static` (`Shared` in Visual Basic) [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)) method.</span></span>

3. <span data-ttu-id="a5f97-110">Gestire le eccezioni generate dal metodo.</span><span class="sxs-lookup"><span data-stu-id="a5f97-110">Handle any exceptions thrown by the method.</span></span>

## <a name="example"></a><span data-ttu-id="a5f97-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5f97-111">Example</span></span>

<span data-ttu-id="a5f97-112">Il codice seguente consente di recuperare un oggetto [TimeZoneInfo](xref:System.TimeZoneInfo) che rappresenta il l'ora solare fuso orientale e di visualizzare l'ora solare fuso orientale corrispondente all'ora locale.</span><span class="sxs-lookup"><span data-stu-id="a5f97-112">The following code retrieves a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the Eastern Standard Time zone and displays the Eastern Standard time that corresponds to the local time.</span></span>

```csharp
DateTime timeNow = DateTime.Now;
try
{
   TimeZoneInfo easternZone = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time");
   DateTime easternTimeNow = TimeZoneInfo.ConvertTime(timeNow, TimeZoneInfo.Local, 
                                                   easternZone);
   Console.WriteLine("{0} {1} corresponds to {2} {3}.",
                     timeNow, 
                     TimeZoneInfo.Local.IsDaylightSavingTime(timeNow) ?
                               TimeZoneInfo.Local.DaylightName : 
                               TimeZoneInfo.Local.StandardName,
                     easternTimeNow, 
                     easternZone.IsDaylightSavingTime(easternTimeNow) ?
                                 easternZone.DaylightName : 
                                 easternZone.StandardName);
}
// Handle exception
//
// As an alternative to simply displaying an error message, an alternate Eastern
// Standard Time TimeZoneInfo object could be instantiated here either by restoring
// it from a serialized string or by providing the necessary data to the
// CreateCustomTimeZone method.
catch (InvalidTimeZoneException)
{
   Console.WriteLine("The Eastern Standard Time Zone contains invalid or missing data.");
}
catch (SecurityException)
{
   Console.WriteLine("The application lacks permission to read time zone information from the registry.");
}
catch (OutOfMemoryException)
{
   Console.WriteLine("Not enough memory is available to load information on the Eastern Standard Time zone.");
}
// If we weren't passing FindSystemTimeZoneById a literal string, we also 
// would handle an ArgumentNullException.
```

```vb
Dim timeNow As Date = Date.Now
Try
   Dim easternZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time")
   Dim easternTimeNow As Date = TimeZoneInfo.ConvertTime(timeNow, TimeZoneInfo.Local, easternZone)
   Console.WriteLine("{0} {1} corresponds to {2} {3}.", _
                     timeNow, _
                     IIf(TimeZoneInfo.Local.IsDaylightSavingTime(timeNow), _
                         TimeZoneInfo.Local.DaylightName, TimeZoneInfo.Local.StandardName), _
                     easternTimeNow, _
                     IIf(easternZone.IsDaylightSavingTime(easternTimeNow), _
                         easternZone.DaylightName, easternZone.StandardName))
' Handle exception
'
' As an alternative to simply displaying an error message, an alternate Eastern
' Standard Time TimeZoneInfo object could be instantiated here either by restoring
' it from a serialized string or by providing the necessary data to the
' CreateCustomTimeZone method.
Catch e As InvalidTimeZoneException
   Console.WriteLine("The Eastern Standard Time Zone contains invalid or missing data.")   
Catch e As SecurityException
   Console.WriteLine("The application lacks permission to read time zone information from the registry.")
Catch e As OutOfMemoryException
   Console.WriteLine("Not enough memory is available to load information on the Eastern Standard Time zone.")
' If we weren't passing FindSystemTimeZoneById a literal string, we also 
' would handle an ArgumentNullException.
End
``` 

<span data-ttu-id="a5f97-113">L'unico parametro del metodo [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)) è l'identificatore del fuso orario da recuperare, che corrisponde alla proprietà [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id) dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="a5f97-113">The [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)) method's single parameter is the identifier of the time zone that you want to retrieve, which corresponds to the object's [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id) property.</span></span> <span data-ttu-id="a5f97-114">L'identificatore del fuso orario è un campo chiave che identifica in modo univoco il fuso orario.</span><span class="sxs-lookup"><span data-stu-id="a5f97-114">The time zone identifier is a key field that uniquely identifies the time zone.</span></span> <span data-ttu-id="a5f97-115">Benché la maggior parte delle chiavi sia relativamente breve, in confronto l'identificatore del fuso orario è piuttosto lungo.</span><span class="sxs-lookup"><span data-stu-id="a5f97-115">While most keys are relatively short, the time zone identifier is comparatively long.</span></span> <span data-ttu-id="a5f97-116">Nella maggior parte dei casi il suo valore corrisponde alla proprietà [StandardName](xref:System.TimeZoneInfo.StandardName) di un oggetto [TimeZoneInfo](xref:System.TimeZoneInfo), che viene usata per specificare il nome dell'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="a5f97-116">In most cases, its value corresponds to the [StandardName](xref:System.TimeZoneInfo.StandardName) property of a [TimeZoneInfo](xref:System.TimeZoneInfo) object, which is used to provide the name of the time zone's standard time.</span></span> <span data-ttu-id="a5f97-117">Esistono tuttavia alcune eccezioni.</span><span class="sxs-lookup"><span data-stu-id="a5f97-117">However, there are exceptions.</span></span> <span data-ttu-id="a5f97-118">Il modo migliore per verificare che venga fornito un identificatore valido consiste nell'enumerare i fusi orari disponibili nel sistema e annotare i relativi identificatori dei fusi orari.</span><span class="sxs-lookup"><span data-stu-id="a5f97-118">The best way to make sure that you supply a valid identifier is to enumerate the time zones available on your system and note the identifiers of the time zones present on them.</span></span> <span data-ttu-id="a5f97-119">Per un'illustrazione, vedere [Procedura: enumerare i fusi orari presenti in un computer](enumerate-time-zones.md).</span><span class="sxs-lookup"><span data-stu-id="a5f97-119">For an illustration, see [How to: enumerate time zones present on a computer](enumerate-time-zones.md).</span></span> <span data-ttu-id="a5f97-120">L'argomento [Ricerca dei fusi orari definiti in un sistema locale](finding-the-time-zones-on-local-system.md) include anche l'elenco degli identificatori dei fusi orari selezionati.</span><span class="sxs-lookup"><span data-stu-id="a5f97-120">The [Finding the time zones defined on a local system](finding-the-time-zones-on-local-system.md) topic also contains a list of selected time zone identifiers.</span></span>

<span data-ttu-id="a5f97-121">Se il fuso orario viene trovato, il metodo restituisce l'oggetto [TimeZoneInfo](xref:System.TimeZoneInfo).</span><span class="sxs-lookup"><span data-stu-id="a5f97-121">If the time zone is found, the method returns its [TimeZoneInfo](xref:System.TimeZoneInfo) object.</span></span> <span data-ttu-id="a5f97-122">Se invece il fuso orario viene trovato, ma i dati sono danneggiati o incompleti, il metodo genera un'eccezione [InvalidTimeZoneException](xref:System.InvalidTimeZoneException).</span><span class="sxs-lookup"><span data-stu-id="a5f97-122">If the time zone is found but its data is corrupted or incomplete, the method throws an [InvalidTimeZoneException](xref:System.InvalidTimeZoneException).</span></span> 

## <a name="see-also"></a><span data-ttu-id="a5f97-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5f97-123">See Also</span></span>

[<span data-ttu-id="a5f97-124">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="a5f97-124">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="a5f97-125">Ricerca dei fusi orari definiti in un sistema locale</span><span class="sxs-lookup"><span data-stu-id="a5f97-125">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)

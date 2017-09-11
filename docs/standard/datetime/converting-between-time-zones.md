---
title: Conversione degli orari tra fusi orari
description: Conversione degli orari tra fusi orari
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: bf8f74e6-e7f2-4c2a-a04c-57db0e28dd36
ms.translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: c2baa48c3b79dfbc5d39652cc57fe015a2313d6e
ms.contentlocale: it-it
ms.lasthandoff: 11/16/2016

---

# <a name="converting-times-between-time-zones"></a><span data-ttu-id="3b434-104">Conversione degli orari tra fusi orari</span><span class="sxs-lookup"><span data-stu-id="3b434-104">Converting times between time zones</span></span>

<span data-ttu-id="3b434-105">La gestione delle differenze tra fusi orari sta divenendo sempre più importante per le applicazioni che usano date e ore.</span><span class="sxs-lookup"><span data-stu-id="3b434-105">It is becoming increasingly important for any application that works with dates and times to handle differences between time zones.</span></span> <span data-ttu-id="3b434-106">Non è più possibile presupporre che tutti gli orari possano essere espressi su base locale, ovvero in base all'orario disponibile dalla struttura [System.DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="3b434-106">An application can no longer assume that all times can be expressed in the local time, which is the time available from the [System.DateTime](xref:System.DateTime) structure.</span></span> <span data-ttu-id="3b434-107">Ad esempio, una pagina Web che visualizza l'orario corrente della parte orientale degli Stati Uniti risulterà non attendibile per un cliente dell'Asia orientale.</span><span class="sxs-lookup"><span data-stu-id="3b434-107">For example, a Web page that displays the current time in the eastern part of the United States will lack credibility to a customer in eastern Asia.</span></span> <span data-ttu-id="3b434-108">In questo argomento viene illustrato come convertire gli orari da un fuso orario all'altro, nonché come convertire i valori [System.DateTimeOffset](xref:System.DateTimeOffset) che dipendono in parte dal fuso orario.</span><span class="sxs-lookup"><span data-stu-id="3b434-108">This topic explains how to convert times from one time zone to another, as well as how to convert [System.DateTimeOffset](xref:System.DateTimeOffset) values that have limited time zone awareness.</span></span>

## <a name="converting-to-coordinated-universal-time"></a><span data-ttu-id="3b434-109">Conversione nel formato UTC</span><span class="sxs-lookup"><span data-stu-id="3b434-109">Converting to Coordinated Universal Time</span></span>

<span data-ttu-id="3b434-110">UTC (Coordinated Universal Time) è uno standard di alta precisione basato sul tempo atomico.</span><span class="sxs-lookup"><span data-stu-id="3b434-110">Coordinated Universal Time (UTC) is a high-precision, atomic time standard.</span></span> <span data-ttu-id="3b434-111">I fusi orari del mondo sono espressi come offset positivi o negativi dall'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="3b434-111">The world’s time zones are expressed as positive or negative offsets from UTC.</span></span> <span data-ttu-id="3b434-112">L'ora espressa in UTC è quindi indipendente dal fuso orario.</span><span class="sxs-lookup"><span data-stu-id="3b434-112">Thus, UTC provides a kind of time-zone free or time-zone neutral time.</span></span> <span data-ttu-id="3b434-113">L'uso dell'ora UTC è consigliato quando la portabilità di data e ora tra i computer è importante.</span><span class="sxs-lookup"><span data-stu-id="3b434-113">The use of UTC time is recommended when a date and time's portability across computers is important.</span></span> <span data-ttu-id="3b434-114">La conversione di singoli fusi orari in ore UTC semplifica i confronti tra gli orari.</span><span class="sxs-lookup"><span data-stu-id="3b434-114">Converting individual time zones to UTC makes time comparisons easy.</span></span>

> [!NOTE]
> <span data-ttu-id="3b434-115">È anche possibile serializzare una struttura [DateTimeOffset](xref:System.DateTimeOffset) per rappresentare in modo non ambiguo un momento preciso.</span><span class="sxs-lookup"><span data-stu-id="3b434-115">You can also serialize a [DateTimeOffset](xref:System.DateTimeOffset) structure to unambiguously represent a single point in time.</span></span> <span data-ttu-id="3b434-116">Poiché gli oggetti [DateTimeOffset](xref:System.DateTimeOffset) archiviano un valore di data e ora insieme all'offset dall'ora UTC, rappresentano sempre un momento preciso in relazione all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="3b434-116">Because [DateTimeOffset](xref:System.DateTimeOffset) objects store a date and time value along with its offset from UTC, they always represent a particular point in time in relationship to UTC.</span></span>

<span data-ttu-id="3b434-117">Il modo più semplice per convertire un orario in ora UTC è chiamare il metodo `static` (`Shared` in Visual Basic) [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="3b434-117">The easiest way to convert a time to UTC is to call the `static` (`Shared` in Visual Basic) [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3b434-118">Il metodo `TimeZoneInfo.ConvertTimeToUtc(DateTime)` non è attualmente disponibile in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3b434-118">The `TimeZoneInfo.ConvertTimeToUtc(DateTime)` method isn't currently available in .NET Core.</span></span> 

<span data-ttu-id="3b434-119">Il tipo specifico di conversione eseguita dal metodo dipende dal valore della proprietà [Kind](xref:System.DateTime.Kind) del parametro `DateTime`, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3b434-119">The exact conversion performed by the method depends on the value of the `DateTime` parameter's [Kind](xref:System.DateTime.Kind) property, as the following table shows.</span></span>

<span data-ttu-id="3b434-120">Proprietà [DateTime.Kind](xref:System.DateTimeKind)</span><span class="sxs-lookup"><span data-stu-id="3b434-120">[DateTime.Kind](xref:System.DateTimeKind) property</span></span> | <span data-ttu-id="3b434-121">Conversione</span><span class="sxs-lookup"><span data-stu-id="3b434-121">Conversion</span></span>
---------------------------------------------------------------------------------------------- | ----------
[<span data-ttu-id="3b434-122">DateTimeKind.Local</span><span class="sxs-lookup"><span data-stu-id="3b434-122">DateTimeKind.Local</span></span>](xref:System.DateTimeKind.Local) | <span data-ttu-id="3b434-123">Converte l'ora locale in ora UTC.</span><span class="sxs-lookup"><span data-stu-id="3b434-123">Converts local time to UTC.</span></span>
[<span data-ttu-id="3b434-124">DateTimeKind.Unspecified</span><span class="sxs-lookup"><span data-stu-id="3b434-124">DateTimeKind.Unspecified</span></span>](xref:System.DateTimeKind.Unspecified) | <span data-ttu-id="3b434-125">Presuppone che il parametro `DateTime` sia l'ora locale e converte l'ora locale in ora UTC.</span><span class="sxs-lookup"><span data-stu-id="3b434-125">Assumes the `DateTime` parameter is local time and converts local time to UTC.</span></span>
[<span data-ttu-id="3b434-126">DateTimeKind.Utc</span><span class="sxs-lookup"><span data-stu-id="3b434-126">DateTimeKind.Utc</span></span>](xref:System.DateTimeKind.Utc) | <span data-ttu-id="3b434-127">Restituisce il parametro `DateTime` invariato.</span><span class="sxs-lookup"><span data-stu-id="3b434-127">Returns the `DateTime` parameter unchanged.</span></span>

<span data-ttu-id="3b434-128">Il codice seguente converte l'ora locale corrente in ora UTC e visualizza il risultato nella console.</span><span class="sxs-lookup"><span data-stu-id="3b434-128">The following code converts the current local time to UTC and displays the result to the console.</span></span>

```csharp
DateTime dateNow = DateTime.Now;
Console.WriteLine("The date and time are {0} UTC.", 
                   TimeZoneInfo.ConvertTimeToUtc(dateNow));
```

```vb
Dim dateNow As Date = Date.Now      
Console.WriteLine("The date and time are {0} UTC.", _
                  TimeZoneInfo.ConvertTimeToUtc(dateNow))
```

> [!NOTE]
><span data-ttu-id="3b434-129">Il metodo [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) non comporta necessariamente risultati identici a quelli forniti dai metodi [TimeZone.ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) e [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime).</span><span class="sxs-lookup"><span data-stu-id="3b434-129">The [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) method does not necessarily produce results that are identical to the [TimeZone.ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) and [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime) methods.</span></span> <span data-ttu-id="3b434-130">Se il fuso orario locale del sistema host prevede più regole di modifica, il metodo, [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/System.TimeZone.ConvertTimeToUtc(v=vs.110).aspx) applica la regola appropriata a una data e a un'ora specifiche.</span><span class="sxs-lookup"><span data-stu-id="3b434-130">If the host system's local time zone includes multiple adjustment rules, [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/System.TimeZone.ConvertTimeToUtc(v=vs.110).aspx) applies the appropriate rule to a particular date and time.</span></span> <span data-ttu-id="3b434-131">Gli altri due metodi vengono sempre applicati alla regola di modifica più recente.</span><span class="sxs-lookup"><span data-stu-id="3b434-131">The other two methods always apply the latest adjustment rule.</span></span>

<span data-ttu-id="3b434-132">Se il valore di data e ora non rappresenta l'ora locale o l'ora UTC, il metodo [ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) restituirà probabilmente un risultato errato.</span><span class="sxs-lookup"><span data-stu-id="3b434-132">If the date and time value does not represent either the local time or UTC, the [ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) method will likely return an erroneous result.</span></span> <span data-ttu-id="3b434-133">È tuttavia possibile usare il metodo [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) per convertire la data e l'ora da un fuso orario specifico.</span><span class="sxs-lookup"><span data-stu-id="3b434-133">However, you can use the [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) method to convert the date and time from a specified time zone.</span></span> <span data-ttu-id="3b434-134">Per informazioni dettagliate sul recupero di un oggetto TimeZoneInfo che rappresenta il fuso orario di destinazione, vedere [Ricerca dei fusi orari definiti in un sistema locale](finding-the-time-zones-on-local-system.md).</span><span class="sxs-lookup"><span data-stu-id="3b434-134">(For details on retrieving a TimeZoneInfo object that represents the destination time zone, see [Finding the time zones defined on a local system](finding-the-time-zones-on-local-system.md).</span></span> <span data-ttu-id="3b434-135">Nel codice seguente viene usato il metodo [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) per convertire l'ora solare fuso orientale in ora UTC.</span><span class="sxs-lookup"><span data-stu-id="3b434-135">The following code uses the [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) method to convert Eastern Standard Time to UTC.</span></span>

```csharp
DateTime easternTime = new DateTime(2007, 01, 02, 12, 16, 00);
string easternZoneId = "Eastern Standard Time";
try
{
   TimeZoneInfo easternZone = TimeZoneInfo.FindSystemTimeZoneById(easternZoneId);
   Console.WriteLine("The date and time are {0} UTC.", 
                     TimeZoneInfo.ConvertTimeToUtc(easternTime, easternZone));
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("Unable to find the {0} zone in the registry.", 
                     easternZoneId);
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the {0} zone has been corrupted.", 
                     easternZoneId);
}
```

```vb
Dim easternTime As New Date(2007, 01, 02, 12, 16, 00)
Dim easternZoneId As String = "Eastern Standard Time"
Try
   Dim easternZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(easternZoneId)
   Console.WriteLine("The date and time are {0} UTC.", _ 
                     TimeZoneInfo.ConvertTimeToUtc(easternTime, easternZone))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("Unable to find the {0} zone in the registry.", _
                     easternZoneId)
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the {0} zone has been corrupted.", _ 
                     easternZoneId)
End Try    
```

<span data-ttu-id="3b434-136">Si noti che questo metodo genera un'eccezione [ArgumentException](xref:System.ArgumentException) se la proprietà [Kind](xref:System.DateTimeKind) dell'oggetto [DateTime](xref:System.DateTime) e il fuso orario non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="3b434-136">Note that this method throws an [ArgumentException](xref:System.ArgumentException) if the [DateTime](xref:System.DateTime) object's [Kind](xref:System.DateTimeKind) property and the time zone are mismatched.</span></span> <span data-ttu-id="3b434-137">Una mancata corrispondenza viene rilevata se la proprietà Kind è [DateTimeKind.Local](xref:System.DateTimeKind.Local) ma l'oggetto [TimeZoneInfo](xref:System.TimeZoneInfo) non rappresenta il fuso orario locale oppure se la proprietà Kind è [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) ma l'oggetto [TimeZoneInfo](xref:System.TimeZoneInfo) non è uguale a [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span><span class="sxs-lookup"><span data-stu-id="3b434-137">A mismatch occurs if the Kind property is [DateTimeKind.Local](xref:System.DateTimeKind.Local) but the [TimeZoneInfo](xref:System.TimeZoneInfo) object does not represent the local time zone, or if the Kind property is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) but the [TimeZoneInfo](xref:System.TimeZoneInfo) object does not equal [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

<span data-ttu-id="3b434-138">Tutti questi metodi accettano valori [DateTime](xref:System.DateTime) come parametri e restituiscono un valore [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="3b434-138">All of these methods take [DateTime](xref:System.DateTime) values as parameters and return a [DateTime](xref:System.DateTime) value.</span></span> <span data-ttu-id="3b434-139">Per i valori [DateTimeOffset](xref:System.DateTimeOffset) la struttura [DateTimeOffset](xref:System.DateTimeOffset) presenta un metodo di istanza [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) che converte la data e ora dell'istanza corrente in ora UTC.</span><span class="sxs-lookup"><span data-stu-id="3b434-139">For [DateTimeOffset](xref:System.DateTimeOffset) values, the [DateTimeOffset](xref:System.DateTimeOffset) structure has a [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) instance method that converts the date and time of the current instance to UTC.</span></span> <span data-ttu-id="3b434-140">Nell'esempio seguente viene chiamato il metodo [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) per convertire l'ora locale e diversi altri orari nell'ora UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="3b434-140">The following example calls the [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) method to convert a local time and several other times to Coordinated Universal Time (UTC).</span></span>

```csharp
DateTimeOffset localTime, otherTime, universalTime;

// Define local time in local time zone
localTime = new DateTimeOffset(new DateTime(2007, 6, 15, 12, 0, 0));
Console.WriteLine("Local time: {0}", localTime);
Console.WriteLine();

// Convert local time to offset 0 and assign to otherTime
otherTime = localTime.ToOffset(TimeSpan.Zero);
Console.WriteLine("Other time: {0}", otherTime);
Console.WriteLine("{0} = {1}: {2}", 
                  localTime, otherTime, 
                  localTime.Equals(otherTime));
Console.WriteLine("{0} exactly equals {1}: {2}", 
                  localTime, otherTime, 
                  localTime.EqualsExact(otherTime));
Console.WriteLine();

// Convert other time to UTC
universalTime = localTime.ToUniversalTime(); 
Console.WriteLine("Universal time: {0}", universalTime);
Console.WriteLine("{0} = {1}: {2}", 
                  otherTime, universalTime, 
                  universalTime.Equals(otherTime));
Console.WriteLine("{0} exactly equals {1}: {2}", 
                  otherTime, universalTime, 
                  universalTime.EqualsExact(otherTime));
Console.WriteLine();
// The example produces the following output to the console:
//    Local time: 6/15/2007 12:00:00 PM -07:00
//    
//    Other time: 6/15/2007 7:00:00 PM +00:00
//    6/15/2007 12:00:00 PM -07:00 = 6/15/2007 7:00:00 PM +00:00: True
//    6/15/2007 12:00:00 PM -07:00 exactly equals 6/15/2007 7:00:00 PM +00:00: False
//    
//    Universal time: 6/15/2007 7:00:00 PM +00:00
//    6/15/2007 7:00:00 PM +00:00 = 6/15/2007 7:00:00 PM +00:00: True
//    6/15/2007 7:00:00 PM +00:00 exactly equals 6/15/2007 7:00:00 PM +00:00: True 
```

```vb
Dim localTime, otherTime, universalTime As DateTimeOffset

' Define local time in local time zone
localTime = New DateTimeOffset(#6/15/2007 12:00:00PM#)
Console.WriteLine("Local time: {0}", localTime)
Console.WriteLine()

' Convert local time to offset 0 and assign to otherTime
otherTime = localTime.ToOffset(TimeSpan.Zero)
Console.WriteLine("Other time: {0}", otherTime)
Console.WriteLine("{0} = {1}: {2}", _
                  localTime, otherTime, _
                  localTime.Equals(otherTime))
Console.WriteLine("{0} exactly equals {1}: {2}", _ 
                  localTime, otherTime, _
                  localTime.EqualsExact(otherTime))
Console.WriteLine()

' Convert other time to UTC
universalTime = localTime.ToUniversalTime() 
Console.WriteLine("Universal time: {0}", universalTime)
Console.WriteLine("{0} = {1}: {2}", _
                  otherTime, universalTime, _ 
                  universalTime.Equals(otherTime))
Console.WriteLine("{0} exactly equals {1}: {2}", _ 
                  otherTime, universalTime, _
                  universalTime.EqualsExact(otherTime))
Console.WriteLine()
' The example produces the following output to the console:
'    Local time: 6/15/2007 12:00:00 PM -07:00
'    
'    Other time: 6/15/2007 7:00:00 PM +00:00
'    6/15/2007 12:00:00 PM -07:00 = 6/15/2007 7:00:00 PM +00:00: True
'    6/15/2007 12:00:00 PM -07:00 exactly equals 6/15/2007 7:00:00 PM +00:00: False
'    
'    Universal time: 6/15/2007 7:00:00 PM +00:00
'    6/15/2007 7:00:00 PM +00:00 = 6/15/2007 7:00:00 PM +00:00: True
'    6/15/2007 7:00:00 PM +00:00 exactly equals 6/15/2007 7:00:00 PM +00:00: True 
```

## <a name="converting-utc-to-a-designated-time-zone"></a><span data-ttu-id="3b434-141">Conversione dell'ora UTC in un determinato fuso orario</span><span class="sxs-lookup"><span data-stu-id="3b434-141">Converting UTC to a designated time zone</span></span>

<span data-ttu-id="3b434-142">Per convertire l'ora UTC nell'ora locale, vedere la sezione seguente [Conversione dell'ora UTC nell'ora locale](#converting-utc-to-local-time).</span><span class="sxs-lookup"><span data-stu-id="3b434-142">To convert UTC to local time, see the [Converting UTC to local time](#converting-utc-to-local-time) section that follows.</span></span> 

<span data-ttu-id="3b434-143">Per convertire l'ora UTC nell'ora di un determinato fuso orario, chiamare il metodo [ConvertTimeFromUtc](https://msdn.microsoft.com/en-us/library/System.TimeZoneInfo.converttimefromutc(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="3b434-143">To convert UTC to the time in any time zone that you designate, call the [ConvertTimeFromUtc](https://msdn.microsoft.com/en-us/library/System.TimeZoneInfo.converttimefromutc(v=vs.110).aspx) method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3b434-144">Il metodo 'TimeZoneInfo.ConvertTimeFromUtc' non è attualmente disponibile in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3b434-144">The \`TimeZoneInfo.ConvertTimeFromUtc' method isn't currently available in .NET Core.</span></span> 

<span data-ttu-id="3b434-145">Questo metodo accetta due parametri:</span><span class="sxs-lookup"><span data-stu-id="3b434-145">The method takes two parameters:</span></span>

* <span data-ttu-id="3b434-146">L'ora UTC da convertire.</span><span class="sxs-lookup"><span data-stu-id="3b434-146">The UTC to convert.</span></span> <span data-ttu-id="3b434-147">Deve essere un valore [DateTime](xref:System.DateTime) la cui proprietà [Kind](xref:System.DateTime.Kind) è impostata su [DateTimeKind](xref:System.DateTimeKind.Utc) o [DateTimeKind](xref:System.DateTimeKind.Unspecified).</span><span class="sxs-lookup"><span data-stu-id="3b434-147">This must be a [DateTime](xref:System.DateTime) value whose [Kind](xref:System.DateTime.Kind) property is set to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) or [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span></span> 

* <span data-ttu-id="3b434-148">Il fuso orario nel quale convertire l'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="3b434-148">The time zone to convert the UTC to.</span></span> 

<span data-ttu-id="3b434-149">Nel codice seguente l'ora UTC viene convertita nell'ora solare fuso centrale.</span><span class="sxs-lookup"><span data-stu-id="3b434-149">The following code converts UTC to Central Standard Time.</span></span>

```csharp
DateTime timeUtc = DateTime.UtcNow;
try
{
   TimeZoneInfo cstZone = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time");
   DateTime cstTime = TimeZoneInfo.ConvertTimeFromUtc(timeUtc, cstZone);
   Console.WriteLine("The date and time are {0} {1}.", 
                     cstTime, 
                     cstZone.IsDaylightSavingTime(cstTime) ?
                             cstZone.DaylightName : cstZone.StandardName);
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The registry does not define the Central Standard Time zone.");
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the Central Standard Time zone has been corrupted.");
}
```

```vb
Dim timeUtc As Date = Date.UtcNow
Try
   Dim cstZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time")
   Dim cstTime As Date = TimeZoneInfo.ConvertTimeFromUtc(timeUtc, cstZone)
   Console.WriteLine("The date and time are {0} {1}.", _
                     cstTime, _
                     IIf(cstZone.IsDaylightSavingTime(cstTime), _
                         cstZone.DaylightName, cstZone.StandardName))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The registry does not define the Central Standard Time zone.")
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the Central Standard Time zone has been corrupted.")
End Try
``` 

## <a name="converting-utc-to-local-time"></a><span data-ttu-id="3b434-150">Conversione dell'ora UTC nell'ora locale</span><span class="sxs-lookup"><span data-stu-id="3b434-150">Converting UTC to local time</span></span>

<span data-ttu-id="3b434-151">Per convertire l'ora UTC nell'ora locale, chiamare il metodo [DateTime.ToLocalTime](xref:System.DateTime) dell'oggetto [DateTime](xref:System.DateTime) di cui si vuole convertire l'orario.</span><span class="sxs-lookup"><span data-stu-id="3b434-151">To convert UTC to local time, call the [DateTime.ToLocalTime](xref:System.DateTime) method of the [DateTime](xref:System.DateTime) object whose time you want to convert.</span></span> <span data-ttu-id="3b434-152">Il comportamento del metodo dipende dal valore della proprietà [Kind](xref:System.DateTime.Kind) dell'oggetto, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3b434-152">The exact behavior of the method depends on the value of the object’s [Kind](xref:System.DateTime.Kind) property, as the following table shows.</span></span>

<span data-ttu-id="3b434-153">Proprietà [DateTime.Kind](xref:System.DateTimeKind)</span><span class="sxs-lookup"><span data-stu-id="3b434-153">[DateTime.Kind](xref:System.DateTimeKind) property</span></span> | <span data-ttu-id="3b434-154">Conversione</span><span class="sxs-lookup"><span data-stu-id="3b434-154">Conversion</span></span>
---------------------------------------------------------------------------------------------- | ----------
[<span data-ttu-id="3b434-155">DateTimeKind.Local</span><span class="sxs-lookup"><span data-stu-id="3b434-155">DateTimeKind.Local</span></span>](xref:System.DateTimeKind.Local) | <span data-ttu-id="3b434-156">Restituisce il valore [DateTime](xref:System.DateTime) invariato.</span><span class="sxs-lookup"><span data-stu-id="3b434-156">Returns the [DateTime](xref:System.DateTime) value unchanged.</span></span>
[<span data-ttu-id="3b434-157">DateTimeKind.Unspecified</span><span class="sxs-lookup"><span data-stu-id="3b434-157">DateTimeKind.Unspecified</span></span>](xref:System.DateTimeKind.Unspecified) | <span data-ttu-id="3b434-158">Presuppone che il valore [DateTime](xref:System.DateTime) sia UTC e converte l'ora UTC nell'ora locale.</span><span class="sxs-lookup"><span data-stu-id="3b434-158">Assumes that the [DateTime](xref:System.DateTime) value is UTC and converts the UTC to local time.</span></span>
[<span data-ttu-id="3b434-159">DateTimeKind.Utc</span><span class="sxs-lookup"><span data-stu-id="3b434-159">DateTimeKind.Utc</span></span>](xref:System.DateTimeKind.Utc) | <span data-ttu-id="3b434-160">Converte il valore [DateTime](xref:System.DateTime) nell'ora locale.</span><span class="sxs-lookup"><span data-stu-id="3b434-160">Converts the [DateTime](xref:System.DateTime) value to local time.</span></span>

## <a name="converting-between-any-two-time-zones"></a><span data-ttu-id="3b434-161">Conversione tra due fusi orari</span><span class="sxs-lookup"><span data-stu-id="3b434-161">Converting between any two time zones</span></span>

<span data-ttu-id="3b434-162">È possibile eseguire una conversione tra due fusi orari usando il metodo statico [TimeZoneInfo.ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)).</span><span class="sxs-lookup"><span data-stu-id="3b434-162">You can convert between any two time zones by using the static [TimeZoneInfo.ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method.</span></span> <span data-ttu-id="3b434-163">I parametri di questo metodo sono il valore [DateTime](xref:System.DateTime) da convertire, un oggetto [TimeZoneInfo](xref:System.TimeZoneInfo) che rappresenta il fuso orario del valore di data e ora e un oggetto [TimeZoneInfo](xref:System.TimeZoneInfo) che rappresenta il fuso orario in cui convertire il valore di data e ora.</span><span class="sxs-lookup"><span data-stu-id="3b434-163">This method's parameters are the [DateTime](xref:System.DateTime) value to convert, a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the time zone of the date and time value, and a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the time zone to convert the date and time value to.</span></span>

<span data-ttu-id="3b434-164">Questo metodo richiede che la proprietà [Kind](xref:System.DateTime.Kind) del valore di data e ora da convertire e l'oggetto [TimeZoneInfo](xref:System.TimeZoneInfo) o l'identificatore del fuso orario che rappresenta il relativo fuso orario corrispondano tra loro.</span><span class="sxs-lookup"><span data-stu-id="3b434-164">The method requires that the [Kind](xref:System.DateTime.Kind) property of the date and time value to convert and the [TimeZoneInfo](xref:System.TimeZoneInfo) object or time zone identifier that represents its time zone correspond to one another.</span></span> <span data-ttu-id="3b434-165">In caso contrario, viene generata un'eccezione [ArgumentException](xref:System.ArgumentException).</span><span class="sxs-lookup"><span data-stu-id="3b434-165">Otherwise, an [ArgumentException](xref:System.ArgumentException) is thrown.</span></span> <span data-ttu-id="3b434-166">Se, ad esempio, la proprietà [Kind](xref:System.DateTime.Kind)del valore di data e ora è [DateTimeKind.Local](xref:System.DateTimeKind.Local), viene generata un'eccezione se l'oggetto [TimeZoneInfo](xref:System.TimeZoneInfo) passato come parametro al metodo non è uguale a [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local).</span><span class="sxs-lookup"><span data-stu-id="3b434-166">For example, if the [Kind](xref:System.DateTime.Kind) property of the date and time value is [DateTimeKind.Local](xref:System.DateTimeKind.Local), an exception is thrown if the [TimeZoneInfo](xref:System.TimeZoneInfo) object passed as a parameter to the method is not equal to [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local).</span></span> <span data-ttu-id="3b434-167">Un'eccezione viene generata anche se l'identificatore passato come parametro al metodo non è uguale a [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id).</span><span class="sxs-lookup"><span data-stu-id="3b434-167">An exception is also thrown if the identifier passed as a parameter to the method is not equal to [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id).</span></span>

<span data-ttu-id="3b434-168">Nell'esempio seguente viene usato il metodo [ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) per eseguire la conversione dall'ora solare Hawaii all'ora locale.</span><span class="sxs-lookup"><span data-stu-id="3b434-168">The following example uses the [ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method to convert from Hawaiian Standard Time to local time.</span></span>

```csharp
DateTime hwTime = new DateTime(2007, 02, 01, 08, 00, 00);
try
{
   TimeZoneInfo hwZone = TimeZoneInfo.FindSystemTimeZoneById("Hawaiian Standard Time");
   Console.WriteLine("{0} {1} is {2} local time.", 
           hwTime, 
           hwZone.IsDaylightSavingTime(hwTime) ? hwZone.DaylightName : hwZone.StandardName, 
           TimeZoneInfo.ConvertTime(hwTime, hwZone, TimeZoneInfo.Local));
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The registry does not define the Hawaiian Standard Time zone.");
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the Hawaiian STandard Time zone has been corrupted.");
}
```

```vb
Dim hwTime As Date = #2/01/2007 8:00:00 AM#
Try
   Dim hwZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Hawaiian Standard Time")
   Console.WriteLine("{0} {1} is {2} local time.", _
                     hwTime, _
                     IIf(hwZone.IsDaylightSavingTime(hwTime), hwZone.DaylightName, hwZone.StandardName), _
                     TimeZoneInfo.ConvertTime(hwTime, hwZone, TimeZoneInfo.Local))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The registry does not define the Hawaiian Standard Time zone.")
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the Hawaiian Standard Time zone has been corrupted.")
End Try
```

## <a name="converting-datetimeoffset-values"></a><span data-ttu-id="3b434-169">Conversione dei valori DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="3b434-169">Converting DateTimeOffset values</span></span>

<span data-ttu-id="3b434-170">I valori di data e ora rappresentati dagli oggetti [System.DateTimeOffset](xref:System.DateTimeOffset) non dipendono completamente dal fuso orario poiché è stata annullata l'associazione dell'oggetto al relativo fuso orario al momento della creazione dell'istanza di tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="3b434-170">Date and time values represented by [System.DateTimeOffset](xref:System.DateTimeOffset) objects are not fully time-zone aware because the object is disassociated from its time zone at the time it is instantiated.</span></span> <span data-ttu-id="3b434-171">In molti casi è tuttavia necessario convertire semplicemente una data e un'ora in base a due offset dall'ora UTC diversi anziché in base all'ora di determinati fusi orari.</span><span class="sxs-lookup"><span data-stu-id="3b434-171">However, in many cases an application simply needs to convert a date and time based on two different offsets from UTC rather than on the time in particular time zones.</span></span> <span data-ttu-id="3b434-172">Per eseguire questa conversione, è possibile chiamare il metodo [ToOffset](xref:System.DateTimeOffset.ToOffset(System.TimeSpan)) dell'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="3b434-172">To perform this conversion, you can call the current instance's [ToOffset](xref:System.DateTimeOffset.ToOffset(System.TimeSpan)) method.</span></span> <span data-ttu-id="3b434-173">L'unico parametro del metodo è [TimeSpan](xref:System.TimeSpan), che rappresenta l'offset del nuovo valore di data e ora restituito dal metodo.</span><span class="sxs-lookup"><span data-stu-id="3b434-173">The method's single parameter is [TimeSpan](xref:System.TimeSpan) representing the offset of the new date and time value that the method is to return.</span></span>  

<span data-ttu-id="3b434-174">Se, ad esempio, la data e l'ora della richiesta di una pagina Web da parte di un utente sono note e serializzate sotto forma di stringa nel formato MM/gg/aaaa hh:mm:ss zzzz, il metodo `ReturnTimeOnServer` seguente converte questo valore di data e ora nella data e nell'ora del server Web.</span><span class="sxs-lookup"><span data-stu-id="3b434-174">For example, if the date and time of a user request for a Web page is known and is serialized as a string in the format MM/dd/yyyy hh:mm:ss zzzz, the following `ReturnTimeOnServer` method converts this date and time value to the date and time on the Web server.</span></span>

```csharp
public DateTimeOffset ReturnTimeOnServer(string clientString)
{
   string format = @"M/d/yyyy H:m:s zzz";
   TimeSpan serverOffset = TimeZoneInfo.Local.GetUtcOffset(DateTimeOffset.Now);

   try
   {      
      DateTimeOffset clientTime = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture);
      DateTimeOffset serverTime = clientTime.ToOffset(serverOffset);
      return serverTime;
   }
   catch (FormatException)
   {
      return DateTimeOffset.MinValue;
   }
}
```

```vb
Public Function ReturnTimeOnServer(clientString As String) As DateTimeOffset
   Dim format As String = "M/d/yyyy H:m:s zzz"
   Dim serverOffset As TimeSpan = TimeZoneInfo.Local.GetUtcOffset(DateTimeOffset.Now)

   Try      
      Dim clientTime As DateTimeOffset = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture)
      Dim serverTime As DateTimeOffset = clientTime.ToOffset(serverOffset)
      Return serverTime
   Catch e As FormatException
      Return DateTimeOffset.MinValue
   End Try    
End Function
```

<span data-ttu-id="3b434-175">Se al metodo viene passata la stringa "9/1/2007 5:32:07 -05:00" che rappresenta la data e l'ora in un fuso orario indietro di cinque ore rispetto all'ora UTC, viene restituito 9/1/2007 3:32:07 AM -07:00 per un server situato nel fuso orario Ora solare del Pacifico (Stati Uniti).</span><span class="sxs-lookup"><span data-stu-id="3b434-175">If the method is passed the string "9/1/2007 5:32:07 -05:00", which represents the date and time in a time zone five hours earlier than UTC, it returns 9/1/2007 3:32:07 AM -07:00 for a server located in the U.S. Pacific Standard Time zone.</span></span>

<span data-ttu-id="3b434-176">La classe [TimeZoneInfo](xref:System.TimeZoneInfo) include anche un overload del metodo [TimeZoneInfo.ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)) che esegue le conversioni del fuso orario con i valori [System.DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="3b434-176">The [TimeZoneInfo](xref:System.TimeZoneInfo) class also includes an overloaded [TimeZoneInfo.ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)) method that performs time zone conversions with [System.DateTimeOffset](xref:System.DateTimeOffset) values.</span></span> <span data-ttu-id="3b434-177">I parametri del metodo sono un valore [System.DateTimeOffset](xref:System.DateTimeOffset) e un riferimento al fuso orario in cui convertire l'ora.</span><span class="sxs-lookup"><span data-stu-id="3b434-177">The method's parameters are a [System.DateTimeOffset](xref:System.DateTimeOffset) value and a reference to the time zone to which the time is to be converted.</span></span> <span data-ttu-id="3b434-178">La chiamata al metodo restituisce un valore [System.DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="3b434-178">The method call returns a [System.DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="3b434-179">Ad esempio, il metodo `ReturnTimeOnServer` dell'esempio precedente potrebbe essere riscritto come segue per chiamare il metodo [ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)).</span><span class="sxs-lookup"><span data-stu-id="3b434-179">For example, the `ReturnTimeOnServer` method in the previous example could be rewritten as follows to call the [ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)) method.</span></span>

```csharp
public DateTimeOffset ReturnTimeOnServer(string clientString)
{
   string format = @"M/d/yyyy H:m:s zzz";

   try
   {      
      DateTimeOffset clientTime = DateTimeOffset.ParseExact(clientString, format, 
                                  CultureInfo.InvariantCulture);
      DateTimeOffset serverTime = TimeZoneInfo.ConvertTime(clientTime, 
                                  TimeZoneInfo.Local);
      return serverTime;
   }
   catch (FormatException)
   {
      return DateTimeOffset.MinValue;
   }
}
```

```vb
Public Function ReturnTimeOnServer(clientString As String) As DateTimeOffset
   Dim format As String = "M/d/yyyy H:m:s zzz"

   Try      
      Dim clientTime As DateTimeOffset = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture)
      Dim serverTime As DateTimeOffset = TimeZoneInfo.ConvertTime(clientTime, TimeZoneInfo.Local)
      Return serverTime
   Catch e As FormatException
      Return DateTimeOffset.MinValue
   End Try    
End Function
```

## <a name="see-also"></a><span data-ttu-id="3b434-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b434-180">See also</span></span>

[<span data-ttu-id="3b434-181">TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="3b434-181">TimeZoneInfo</span></span>](xref:System.TimeZoneInfo)

[<span data-ttu-id="3b434-182">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="3b434-182">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="3b434-183">Ricerca dei fusi orari definiti in un sistema locale</span><span class="sxs-lookup"><span data-stu-id="3b434-183">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)




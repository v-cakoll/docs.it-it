---
title: Creazione di un&quot;istanza di un oggetto DateTimeOffset
description: Creazione di un&quot;istanza di un oggetto DateTimeOffset
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 476fe67b-6be4-4435-88ab-ced37304f1d1
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 26be324eb5d58b94a71e89aba213f107cf8dfd1e
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="instantiating-a-datetimeoffset-object"></a><span data-ttu-id="78f8e-104">Creazione di un'istanza di un oggetto DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="78f8e-104">Instantiating a DateTimeOffset object</span></span>

<span data-ttu-id="78f8e-105">La struttura [System.DateTimeOffset](xref:System.DateTimeOffset) offre diverse opzioni per creare nuovi valori [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="78f8e-105">The [System.DateTimeOffset](xref:System.DateTimeOffset) structure offers a number of ways to create new [DateTimeOffset](xref:System.DateTimeOffset) values.</span></span> <span data-ttu-id="78f8e-106">Molti corrispondono direttamente ai metodi disponibili per creare istanze dei nuovi valori [System.DateTime](xref:System.DateTime), con miglioramenti che consentono di specificare l'offset del valore di data e ora rispetto all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="78f8e-106">Many of them correspond directly to the methods available for instantiating new [System.DateTime](xref:System.DateTime) values, with enhancements that allow you to specify the date and time value's offset from Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="78f8e-107">In particolare è possibile creare istanze di un valore [DateTimeOffset](xref:System.DateTimeOffset) nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="78f8e-107">In particular, you can instantiate a [DateTimeOffset](xref:System.DateTimeOffset) value in the following ways:</span></span>

* <span data-ttu-id="78f8e-108">Chiamando il costruttore [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="78f8e-108">By calling a [DateTimeOffset](xref:System.DateTimeOffset) constructor.</span></span>

* <span data-ttu-id="78f8e-109">Convertendo in modo implicito un valore in un valore [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="78f8e-109">By implicitly converting a value to [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

* <span data-ttu-id="78f8e-110">Analizzando la rappresentazione di stringa di una data e dell'ora.</span><span class="sxs-lookup"><span data-stu-id="78f8e-110">By parsing the string representation of a date and time.</span></span>

## <a name="date-and-time-literals"></a><span data-ttu-id="78f8e-111">Valori letterali di data e ora</span><span class="sxs-lookup"><span data-stu-id="78f8e-111">Date and Time Literals</span></span>

<span data-ttu-id="78f8e-112">Per linguaggi che supportano questa opzione, uno dei modi più comuni per creare un'istanza di un valore [DateTime](xref:System.DateTime) consiste nello specificare la data e l'ora come valore letterale specificato hardcoded.</span><span class="sxs-lookup"><span data-stu-id="78f8e-112">For languages that support it, one of the most common ways to instantiate a [DateTime](xref:System.DateTime) value is to provide the date and time as a hard-coded literal value.</span></span> <span data-ttu-id="78f8e-113">Con il codice Visual Basic seguente viene, ad esempio, creato un oggetto [DateTime](xref:System.DateTime) il cui valore corrisponde al 1 gennaio 2008, alle 10:00.</span><span class="sxs-lookup"><span data-stu-id="78f8e-113">For example, the following Visual Basic code creates a [DateTime](xref:System.DateTime) object whose value is January 1, 2008, at 10:00 AM.</span></span>

```vb
Dim literalDate1 As Date = #05/01/2008 8:06:32 AM#
Console.WriteLine(literalDate1.ToString())
' Displays:
'              5/1/2008 8:06:32 AM
```

<span data-ttu-id="78f8e-114">I valori [DateTimeOffset](xref:System.DateTimeOffset) possono essere inizializzati anche con valori letterali di data e ora, quando si usano linguaggi che supportano i valori letterali [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="78f8e-114">[DateTimeOffset](xref:System.DateTimeOffset) values can also be initialized using date and time literals when using languages that support [DateTime](xref:System.DateTime) literals.</span></span> <span data-ttu-id="78f8e-115">Il codice Visual Basic seguente, ad esempio, consente di creare un oggetto [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="78f8e-115">For example, the following Visual Basic code creates a [DateTimeOffset](xref:System.DateTimeOffset) object.</span></span>

```vb
Dim literalDate As DateTimeOffset = #05/01/2008 8:06:32 AM#
Console.WriteLine(literalDate.ToString())
' Displays:
'              5/1/2008 8:06:32 AM -07:00
```

<span data-ttu-id="78f8e-116">Come mostrato nell'output della console, al valore [DateTimeOffset](xref:System.DateTimeOffset) così creato viene assegnato l'offset del fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="78f8e-116">As the console output shows, the [DateTimeOffset](xref:System.DateTimeOffset) value created in this way is assigned the offset of the local time zone.</span></span> <span data-ttu-id="78f8e-117">Ciò significa che un valore [DateTimeOffset](xref:System.DateTimeOffset) assegnato usando un valore letterale del carattere non identifica un momento specifico se il codice viene eseguito su computer diversi.</span><span class="sxs-lookup"><span data-stu-id="78f8e-117">This means that a [DateTimeOffset](xref:System.DateTimeOffset) value assigned using a character literal does not identify a single point of time if the code is run on different computers.</span></span>

## <a name="datetimeoffset-constructors"></a><span data-ttu-id="78f8e-118">Costruttori DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="78f8e-118">DateTimeOffset Constructors</span></span>

<span data-ttu-id="78f8e-119">Il tipo [System.DateTimeOffset](xref:System.DateTimeOffset) definisce cinque costruttori.</span><span class="sxs-lookup"><span data-stu-id="78f8e-119">The [System.DateTimeOffset](xref:System.DateTimeOffset) type defines five constructors.</span></span> <span data-ttu-id="78f8e-120">Tre corrispondono direttamente a costruttori [DateTime](xref:System.DateTime), con un parametro aggiuntivo di tipo [System.TimeSpan](xref:System.TimeSpan) che definisce l'offset di data e ora rispetto all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="78f8e-120">Three of them correspond directly to [DateTime](xref:System.DateTime) constructors, with an additional parameter of type [System.TimeSpan](xref:System.TimeSpan) that defines the date and time's offset from UTC.</span></span> <span data-ttu-id="78f8e-121">Questi consentono di definire un valore [DateTimeOffset](xref:System.DateTimeOffset) in base al valore dei singoli componenti di data e ora.</span><span class="sxs-lookup"><span data-stu-id="78f8e-121">These allow you to define a [DateTimeOffset](xref:System.DateTimeOffset) value based on the value of its individual date and time components.</span></span> <span data-ttu-id="78f8e-122">Nel codice seguente vengono, ad esempio, usati questi tre costruttori per creare istanze di oggetti [DateTimeOffset](xref:System.DateTimeOffset) con valori identici di 7/1/2008 00:05 +01:00.</span><span class="sxs-lookup"><span data-stu-id="78f8e-122">For example, the following code uses these three constructors to instantiate [DateTimeOffset](xref:System.DateTimeOffset) objects with identical values of 7/1/2008 12:05 AM +01:00.</span></span>

```csharp
DateTimeOffset dateAndTime;

// Instantiate date and time using years, months, days, 
// hours, minutes, and seconds
dateAndTime = new DateTimeOffset(2008, 5, 1, 8, 6, 32, 
                                 new TimeSpan(1, 0, 0));
Console.WriteLine(dateAndTime);
// Instantiate date and time using years, months, days,
// hours, minutes, seconds, and milliseconds
dateAndTime = new DateTimeOffset(2008, 5, 1, 8, 6, 32, 545, 
                                 new TimeSpan(1, 0, 0));
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), 
                             dateAndTime.ToString("zzz"));

// Instantiate date and time using number of ticks
// 05/01/2008 8:06:32 AM is 633,452,259,920,000,000 ticks
dateAndTime = new DateTimeOffset(633452259920000000, new TimeSpan(1, 0, 0));  
Console.WriteLine(dateAndTime);
// The example displays the following output to the console:
//       5/1/2008 8:06:32 AM +01:00
//       5/1/2008 8:06:32 AM +01:00
//       5/1/2008 8:06:32 AM +01:00
```

```vb
Dim dateAndTime As DateTimeOffset

' Instantiate date and time using years, months, days, 
' hours, minutes, and seconds
dateAndTime = New DateTimeOffset(2008, 5, 1, 8, 6, 32, _
                                 New TimeSpan(1, 0, 0))
Console.WriteLine(dateAndTime)
' Instantiate date and time using years, months, days,
' hours, minutes, seconds, and milliseconds
dateAndTime = New DateTimeOffset(2008, 5, 1, 8, 6, 32, 545, _
                                 New TimeSpan(1, 0, 0))
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), _
                             dateAndTime.ToString("zzz"))

' Instantiate date and time using Persian calendar with years,
' months, days, hours, minutes, seconds, and milliseconds
dateAndTime = New DateTimeOffset(1387, 2, 12, 8, 6, 32, 545, New PersianCalendar, New TimeSpan(1, 0, 0))
' Note that the console output displays the date in the Gregorian
' calendar, not the Persian calendar. 
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), _
                             dateAndTime.ToString("zzz"))

' Instantiate date and time using number of ticks
' 05/01/2008 8:06:32 AM is 633,452,259,920,000,000 ticks
dateAndTime = New DateTimeOffset(633452259920000000, New TimeSpan(1, 0, 0))  
Console.WriteLine(dateAndTime)
' The example displays the following output to the console:
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
```

<span data-ttu-id="78f8e-123">Si noti che, quando il valore dell'oggetto [DateTimeOffset](xref:System.DateTimeOffset) di cui si è creata un'istanza usando un oggetto [PersianCalendar](xref:System.Globalization.PersianCalendar) come uno degli argomenti per il relativo costruttore viene visualizzato sulla console, viene espresso come data del calendario gregoriano anziché persiano.</span><span class="sxs-lookup"><span data-stu-id="78f8e-123">Note that, when the value of the [DateTimeOffset](xref:System.DateTimeOffset) object instantiated using a [PersianCalendar](xref:System.Globalization.PersianCalendar) object as one of the arguments to its constructor is displayed to the console, it is expressed as a date in the Gregorian rather than the Persian calendar.</span></span> 

<span data-ttu-id="78f8e-124">Gli altri due costruttori creano un oggetto [DateTimeOffset](xref:System.DateTimeOffset) da un valore DateTime.</span><span class="sxs-lookup"><span data-stu-id="78f8e-124">The other two constructors create a [DateTimeOffset](xref:System.DateTimeOffset) object from a DateTime value.</span></span> <span data-ttu-id="78f8e-125">Il primo ha un solo parametro, il valore [DateTime](xref:System.DateTime) da convertire in un valore [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="78f8e-125">The first of these has a single parameter, the [DateTime](xref:System.DateTime) value to convert to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="78f8e-126">L'offset del valore [DateTimeOffset](xref:System.DateTimeOffset) risultante dipende dalla proprietà [Kind](xref:System.DateTime.Kind) del solo parametro [DateTime](xref:System.DateTime) del costruttore.</span><span class="sxs-lookup"><span data-stu-id="78f8e-126">The offset of the resulting [DateTimeOffset](xref:System.DateTimeOffset) value depends on the [Kind](xref:System.DateTime.Kind) property of the constructor's single [DateTime](xref:System.DateTime) parameter.</span></span> <span data-ttu-id="78f8e-127">Se il valore è [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), l'offset viene impostato su un valore uguale a [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span><span class="sxs-lookup"><span data-stu-id="78f8e-127">If its value is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), the offset is set equal to [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> <span data-ttu-id="78f8e-128">In caso contrario, l'offset viene impostato su un valore uguale a quello del fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="78f8e-128">Otherwise, its offset is set equal to that of the local time zone.</span></span> <span data-ttu-id="78f8e-129">L'esempio seguente illustra l'uso di questo costruttore per creare istanze di oggetti [DateTimeOffset](xref:System.DateTimeOffset) che rappresentano l'ora UTC e il fuso orario locale:</span><span class="sxs-lookup"><span data-stu-id="78f8e-129">The following example illustrates the use of this constructor to instantiate [DateTimeOffset](xref:System.DateTimeOffset) objects representing UTC and the local time zone:</span></span>

```csharp
// Declare date; Kind property is DateTimeKind.Unspecified
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
DateTimeOffset targetTime;

// Instantiate a DateTimeOffset value from a UTC time 
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = new DateTimeOffset(utcTime);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc, 
// the offset is TimeSpan.Zero.

// Instantiate a DateTimeOffset value from a UTC time with a zero offset
targetTime = new DateTimeOffset(utcTime, TimeSpan.Zero);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc, 
// the call to the constructor succeeds

// Instantiate a DateTimeOffset value from a UTC time with a negative offset
try
{
   targetTime = new DateTimeOffset(utcTime, new TimeSpan(-2, 0, 0));
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      targetTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM +00:00 failed.

// Instantiate a DateTimeOffset value from a local time
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = new DateTimeOffset(localTime);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Local, 
// the offset is that of the local time zone.

// Instantiate a DateTimeOffset value from an unspecified time
targetTime = new DateTimeOffset(sourceDate);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Unspecified, 
// the offset is that of the local time zone.
```

```vb
' Declare date; Kind property is DateTimeKind.Unspecified
Dim sourceDate As Date = #5/1/2008 8:30 AM#
Dim targetTime As DateTimeOffset

' Instantiate a DateTimeOffset value from a UTC time 
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = New DateTimeOffset(utcTime)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM +00:00
' Because the Kind property is DateTimeKind.Utc, 
' the offset is TimeSpan.Zero.


' Instantiate a DateTimeOffset value from a local time
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = New DateTimeOffset(localTime)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -07:00
' Because the Kind property is DateTimeKind.Local, 
' the offset is that of the local time zone.

' Instantiate a DateTimeOffset value from an unspecified time
targetTime = New DateTimeOffset(sourceDate)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -07:00
' Because the Kind property is DateTimeKind.Unspecified, 
' the offset is that of the local time zone.
```

> [!NOTE]
> <span data-ttu-id="78f8e-130">La chiamata dell'overload del costruttore [DateTimeOffset](xref:System.DateTimeOffset) che ha un solo parametro [DateTime](xref:System.DateTime) equivale all'esecuzione di una conversione implicita di un valore [DateTime](xref:System.DateTime) in un valore [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="78f8e-130">Calling the overload of the [DateTimeOffset](xref:System.DateTimeOffset) constructor that has a single [DateTime](xref:System.DateTime) parameter is equivalent to performing an implicit conversion of a [DateTime](xref:System.DateTime) value to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

<span data-ttu-id="78f8e-131">Il secondo costruttore che crea un oggetto [DateTimeOffset](xref:System.DateTimeOffset) da un valore [DateTime](xref:System.DateTime) ha due parametri: il valore [DateTime](xref:System.DateTime) da convertire e un valore [TimeSpan](xref:System.TimeSpan) che rappresenta l'offset di data e ora rispetto all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="78f8e-131">The second constructor that creates a [DateTimeOffset](xref:System.DateTimeOffset) object from a [DateTime](xref:System.DateTime) value has two parameters: the [DateTime](xref:System.DateTime) value to convert, and a [TimeSpan](xref:System.TimeSpan) value representing the date and time's offset from UTC.</span></span> <span data-ttu-id="78f8e-132">Tale valore dell'offset deve corrispondere alla proprietà [Kind](xref:System.DateTime.Kind) del primo parametro del costruttore oppure viene generata un'eccezione [System.ArgumentException](xref:System.ArgumentException).</span><span class="sxs-lookup"><span data-stu-id="78f8e-132">This offset value must correspond to the [Kind](xref:System.DateTime.Kind) property of the constructor's first parameter or an [System.ArgumentException](xref:System.ArgumentException) is thrown.</span></span> <span data-ttu-id="78f8e-133">Se la proprietà [Kind](xref:System.DateTime.Kind) del primo parametro è [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), il valore del secondo parametro deve essere [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span><span class="sxs-lookup"><span data-stu-id="78f8e-133">If the [Kind](xref:System.DateTime.Kind) property of the first parameter is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), the value of the second parameter must be [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> <span data-ttu-id="78f8e-134">Se la proprietà [Kind](xref:System.DateTime.Kind) del primo parametro è [DateTimeKind.Local](xref:System.DateTimeKind.Local), il valore del secondo parametro deve essere l'offset del fuso orario del sistema locale.</span><span class="sxs-lookup"><span data-stu-id="78f8e-134">If the [Kind](xref:System.DateTime.Kind) property of the first parameter is [DateTimeKind.Local](xref:System.DateTimeKind.Local), the value of the second parameter must be the offset of the local system's time zone.</span></span> <span data-ttu-id="78f8e-135">Se la proprietà [Kind](xref:System.DateTime.Kind) del primo parametro è [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), l'offset può essere qualsiasi valore valido.</span><span class="sxs-lookup"><span data-stu-id="78f8e-135">If the [Kind](xref:System.DateTime.Kind) property of the first parameter is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), the offset can be any valid value.</span></span> <span data-ttu-id="78f8e-136">Il codice seguente illustra le chiamate a questo costruttore per convertire [DateTime](xref:System.DateTime) in valori [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="78f8e-136">The following code illustrates calls to this constructor to convert [DateTime](xref:System.DateTime) to [DateTimeOffset](xref:System.DateTimeOffset) values.</span></span>

```csharp
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
DateTimeOffset targetTime;

// Instantiate a DateTimeOffset value from a UTC time with a zero offset.
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = new DateTimeOffset(utcTime, TimeSpan.Zero);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc,  
// the call to the constructor succeeds

// Instantiate a DateTimeOffset value from a UTC time with a non-zero offset.
try
{
   targetTime = new DateTimeOffset(utcTime, new TimeSpan(-2, 0, 0));
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      utcTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

// Instantiate a DateTimeOffset value from a local time with 
// the offset of the local time zone
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = new DateTimeOffset(localTime, 
                                TimeZoneInfo.Local.GetUtcOffset(localTime));
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Local and the offset matches
// that of the local time zone, the call to the constructor succeeds.

// Instantiate a DateTimeOffset value from a local time with a zero offset.
try
{
   targetTime = new DateTimeOffset(localTime, TimeSpan.Zero);
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      localTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

// Instantiate a DateTimeOffset value with an arbitary time zone. 
string timeZoneName = "Central Standard Time";
TimeSpan offset = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName). 
                         GetUtcOffset(sourceDate); 
targetTime = new DateTimeOffset(sourceDate, offset);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -05:00
```

```vb
Dim sourceDate As Date = #5/1/2008 8:30 AM#
Dim targetTime As DateTimeOffset

' Instantiate a DateTimeOffset value from a UTC time with a zero offset.
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = New DateTimeOffset(utcTime, TimeSpan.Zero)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM +00:00
' Because the Kind property is DateTimeKind.Utc,  
' the call to the constructor succeeds.

' Instantiate a DateTimeOffset value from a UTC time with a non-zero offset.
Try
   targetTime = New DateTimeOffset(utcTime, New TimeSpan(-2, 0, 0))
   Console.WriteLine(targetTime)
Catch e As ArgumentException
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", _
                      utcTime)
End Try   
' Throws exception and displays the following to the console:
'   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

' Instantiate a DateTimeOffset value from a local time with 
' the offset of the local time zone.
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = New DateTimeOffset(localTime, _
                                TimeZoneInfo.Local.GetUtcOffset(localTime))
Console.WriteLine(targetTime)
' Because the Kind property is DateTimeKind.Local and the offset matches
' that of the local time zone, the call to the constructor succeeds.

' Instantiate a DateTimeOffset value from a local time with a zero offset.
Try
   targetTime = New DateTimeOffset(localTime, TimeSpan.Zero)
   Console.WriteLine(targetTime)
Catch e As ArgumentException
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", _
                      localTime)
End Try   
' Throws exception and displays the following to the console:
'   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

' Instantiate a DateTimeOffset value with an arbitary time zone. 
Dim timeZoneName As String = "Central Standard Time"
Dim offset As TimeSpan = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName). _
                         GetUtcOffset(sourceDate) 
targetTime = New DateTimeOffset(sourceDate, offset)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -05:00
```

## <a name="implicit-type-conversion"></a><span data-ttu-id="78f8e-137">Conversione implicita di tipi</span><span class="sxs-lookup"><span data-stu-id="78f8e-137">Implicit Type Conversion</span></span>
 
<span data-ttu-id="78f8e-138">Il tipo [System.DateTimeOffset](xref:System.DateTimeOffset) supporta una conversione implicita di tipi: da un valore [System.DateTime](xref:System.DateTime) in un valore [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="78f8e-138">The [System.DateTimeOffset](xref:System.DateTimeOffset) type supports one implicit type conversion: from a [System.DateTime](xref:System.DateTime) value to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="78f8e-139">Una conversione implicita di tipi è una conversione da un tipo in un altro che non richiede un cast esplicito (in C#) o una conversione esplicita (in Visual Basic) e nella quale non vengono perse informazioni.</span><span class="sxs-lookup"><span data-stu-id="78f8e-139">(An implicit type conversion is a conversion from one type to another that does not require an explicit cast (in C#) or conversion (in Visual Basic) and that does not lose information.</span></span> <span data-ttu-id="78f8e-140">Rende possibile la scrittura di codice come il seguente.</span><span class="sxs-lookup"><span data-stu-id="78f8e-140">It makes code like the following possible.</span></span>

```csharp
DateTimeOffset targetTime;

// The Kind property of sourceDate is DateTimeKind.Unspecified
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
targetTime = sourceDate;
Console.WriteLine(targetTime);   
// Displays 5/1/2008 8:30:00 AM -07:00

// define a UTC time (Kind property is DateTimeKind.Utc)
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = utcTime;
Console.WriteLine(targetTime);   
// Displays 5/1/2008 8:30:00 AM +00:00

// Define a local time (Kind property is DateTimeKind.Local)
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = localTime;
Console.WriteLine(targetTime);      
// Displays 5/1/2008 8:30:00 AM -07:00
```

```vb
Dim targetTime As DateTimeOffset

' The Kind property of sourceDate is DateTimeKind.Unspecified
Dim sourceDate As Date = #5/1/2008 8:30 AM#
targetTime = sourceDate
Console.WriteLine(targetTime)   
' Displays 5/1/2008 8:30:00 AM -07:00

' define a UTC time (Kind property is DateTimeKind.Utc)
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = utcTime
Console.WriteLine(targetTime)   
' Displays 5/1/2008 8:30:00 AM +00:00

' Define a local time (Kind property is DateTimeKind.Local)
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = localTime
Console.WriteLine(targetTime)      
' Displays 5/1/2008 8:30:00 AM -07:00
```

<span data-ttu-id="78f8e-141">L'offset del valore [DateTimeOffset](xref:System.DateTimeOffset) risultante dipende dal valore della proprietà DateTime.Kind](xref:System.DateTime.Kind).</span><span class="sxs-lookup"><span data-stu-id="78f8e-141">The offset of the resulting [DateTimeOffset](xref:System.DateTimeOffset) value depends on the DateTime.Kind](xref:System.DateTime.Kind) property value.</span></span> <span data-ttu-id="78f8e-142">Se il valore è [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), l'offset viene impostato su un valore uguale a [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span><span class="sxs-lookup"><span data-stu-id="78f8e-142">If its value is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), the offset is set equal to [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> <span data-ttu-id="78f8e-143">Se il valore è [DateTimeKind.Local](xref:System.DateTimeKind.Local) o [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), l'offset viene impostato su un valore uguale a quello del fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="78f8e-143">If its value is either [DateTimeKind.Local](xref:System.DateTimeKind.Local) or [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), the offset is set equal to that of the local time zone.</span></span>

## <a name="parsing-the-string-representation-of-a-date-and-time"></a><span data-ttu-id="78f8e-144">Analisi della rappresentazione di stringa di data e ora</span><span class="sxs-lookup"><span data-stu-id="78f8e-144">Parsing the String Representation of a Date and Time</span></span>

<span data-ttu-id="78f8e-145">Il tipo [System.DateTimeOffset](xref:System.DateTimeOffset) supporta quattro metodi che consentono di convertire la rappresentazione di stringa di data e ora in un valore [DateTimeOffset](xref:System.DateTimeOffset):</span><span class="sxs-lookup"><span data-stu-id="78f8e-145">The [System.DateTimeOffset](xref:System.DateTimeOffset) type supports four methods that allow you to convert the string representation of a date and time into a [DateTimeOffset](xref:System.DateTimeOffset) value:</span></span>

* <span data-ttu-id="78f8e-146">[Parse](xref:System.DateTimeOffset.Parse(System.String)), che tenta di convertire la rappresentazione di stringa di una data e dell'ora in un valore [DateTimeOffset](xref:System.DateTimeOffset) e genera un'eccezione se la conversione non riesce.</span><span class="sxs-lookup"><span data-stu-id="78f8e-146">[Parse](xref:System.DateTimeOffset.Parse(System.String)), which tries to convert the string representation of a date and time to a [DateTimeOffset](xref:System.DateTimeOffset) value and throws an exception if the conversion fails.</span></span>

* <span data-ttu-id="78f8e-147">[TryParse](xref:System.DateTimeOffset.TryParse(System.String,System.DateTimeOffset@)), che tenta di convertire la rappresentazione di stringa di una data e dell'ora in un valore [DateTimeOffset](xref:System.DateTimeOffset) e restituisce `false` se la conversione non riesce.</span><span class="sxs-lookup"><span data-stu-id="78f8e-147">[TryParse](xref:System.DateTimeOffset.TryParse(System.String,System.DateTimeOffset@)), which tries to convert the string representation of a date and time to a [DateTimeOffset](xref:System.DateTimeOffset) value and returns `false` if the conversion fails.</span></span>

* <span data-ttu-id="78f8e-148">[ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)), che tenta di convertire la rappresentazione di stringa di una data e dell'ora in un formato specifico in un valore [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="78f8e-148">[ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)), which tries to convert the string representation of a date and time in a specified format to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="78f8e-149">Il metodo genera un'eccezione se la conversione non riesce.</span><span class="sxs-lookup"><span data-stu-id="78f8e-149">The method throws an exception if the conversion fails.</span></span>

* <span data-ttu-id="78f8e-150">[TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)), che tenta di convertire la rappresentazione di stringa di una data e dell'ora in un formato specifico in un valore [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="78f8e-150">[TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)), which tries to convert the string representation of a date and time in a specified format to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="78f8e-151">Il metodo restituisce `false` se la conversione non riesce.</span><span class="sxs-lookup"><span data-stu-id="78f8e-151">The method returns `false` if the conversion fails.</span></span>

<span data-ttu-id="78f8e-152">L'esempio seguente illustra le chiamate a ognuno di questi quattro metodi di conversione di stringhe per la creazione di un'istanza di un valore [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="78f8e-152">The following example illustrates calls to each of these four string conversion methods to instantiate a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

```csharp
string timeString; 
DateTimeOffset targetTime;

timeString = "05/01/2008 8:30 AM +01:00";
try
{
   targetTime = DateTimeOffset.Parse(timeString);
   Console.WriteLine(targetTime);
}
catch (FormatException)
{
   Console.WriteLine("Unable to parse {0}.", timeString);   
}   

timeString = "05/01/2008 8:30 AM";
if (DateTimeOffset.TryParse(timeString, out targetTime))
   Console.WriteLine(targetTime);
else
   Console.WriteLine("Unable to parse {0}.", timeString);   

timeString = "Thursday, 01 May 2008 08:30";
try
{
   targetTime = DateTimeOffset.ParseExact(timeString, "f", 
                CultureInfo.InvariantCulture);
   Console.WriteLine(targetTime);
}
catch (FormatException)
{
   Console.WriteLine("Unable to parse {0}.", timeString);   
}   

timeString = "Thursday, 01 May 2008 08:30 +02:00";
string formatString; 
formatString = CultureInfo.InvariantCulture.DateTimeFormat.LongDatePattern +
                " " +
                CultureInfo.InvariantCulture.DateTimeFormat.ShortTimePattern +
                " zzz"; 
if (DateTimeOffset.TryParseExact(timeString, 
                                formatString, 
                                CultureInfo.InvariantCulture, 
                                DateTimeStyles.AllowLeadingWhite, 
                                out targetTime))
   Console.WriteLine(targetTime);
else
   Console.WriteLine("Unable to parse {0}.", timeString);
// The example displays the following output to the console:
//    5/1/2008 8:30:00 AM +01:00
//    5/1/2008 8:30:00 AM -07:00
//    5/1/2008 8:30:00 AM -07:00
//    5/1/2008 8:30:00 AM +02:00
```

```vb
Dim timeString As String 
Dim targetTime As DateTimeOffset

timeString = "05/01/2008 8:30 AM +01:00"
Try
   targetTime = DateTimeOffset.Parse(timeString)
   Console.WriteLine(targetTime)
Catch e As FormatException
   Console.WriteLine("Unable to parse {0}.", timeString)   
End Try   

timeString = "05/01/2008 8:30 AM"
If DateTimeOffset.TryParse(timeString, targetTime) Then
   Console.WriteLine(targetTime)
Else
   Console.WriteLine("Unable to parse {0}.", timeString)   
End If

timeString = "Thursday, 01 May 2008 08:30"
Try
   targetTime = DateTimeOffset.ParseExact(timeString, "f", _
                CultureInfo.InvariantCulture)
   Console.WriteLine(targetTime)
Catch e As FormatException
   Console.WriteLine("Unable to parse {0}.", timeString)   
End Try   

timeString = "Thursday, 01 May 2008 08:30 +02:00"
Dim formatString As String 
formatString = CultureInfo.InvariantCulture.DateTimeFormat.LongDatePattern & _
                " " & _
                CultureInfo.InvariantCulture.DateTimeFormat.ShortTimePattern & _
                " zzz" 
If DateTimeOffset.TryParseExact(timeString, _
                                formatString, _
                                CultureInfo.InvariantCulture, _
                                DateTimeStyles.AllowLeadingWhite, _
                                targetTime) Then
   Console.WriteLine(targetTime)
Else
   Console.WriteLine("Unable to parse {0}.", timeString)
End If      
' The example displays the following output to the console:
'    5/1/2008 8:30:00 AM +01:00
'    5/1/2008 8:30:00 AM -07:00
'    5/1/2008 8:30:00 AM -07:00
'    5/1/2008 8:30:00 AM +02:00
```

## <a name="see-also"></a><span data-ttu-id="78f8e-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78f8e-153">See Also</span></span>

[<span data-ttu-id="78f8e-154">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="78f8e-154">Dates, times, and time zones</span></span>](index.md)



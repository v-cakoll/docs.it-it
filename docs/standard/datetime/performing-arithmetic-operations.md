---
title: Esecuzione di operazioni aritmetiche con date e ore
description: Esecuzione di operazioni aritmetiche con date e ore
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 589ac5ec-8365-4a0d-bc38-72183718110c
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: b872cc4c2b799ddafc9df263795d860754d1ec17
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="performing-arithmetic-operations-with-dates-and-times"></a><span data-ttu-id="2819c-104">Esecuzione di operazioni aritmetiche con date e ore</span><span class="sxs-lookup"><span data-stu-id="2819c-104">Performing arithmetic operations with dates and times</span></span>

<span data-ttu-id="2819c-105">Sebbene le strutture [System.DateTime](xref:System.DateTime) e [System.DateTimeOffset](xref:System.DateTimeOffset) contengano entrambe membri che eseguono operazioni aritmetiche sui propri valori, i risultati delle operazioni aritmetiche sono molto diversi.</span><span class="sxs-lookup"><span data-stu-id="2819c-105">Although both the [System.DateTime](xref:System.DateTime) and the [System.DateTimeOffset](xref:System.DateTimeOffset) structures provide members that perform arithmetic operations on their values, the results of arithmetic operations are very different.</span></span> <span data-ttu-id="2819c-106">In questo articolo vengono esaminate tali differenze, in relazione alla presenza del fuso orario nei dati di data e ora, e viene descritto come eseguire operazioni completamente compatibili con il fuso orario usando i dati di data e ora.</span><span class="sxs-lookup"><span data-stu-id="2819c-106">This article examines those differences, relates them to degrees of time zone awareness in date and time data, and discusses how to perform fully time zone aware operations using date and time data.</span></span>

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a><span data-ttu-id="2819c-107">Confronti e operazioni aritmetiche con i valori DateTime</span><span class="sxs-lookup"><span data-stu-id="2819c-107">Comparisons and Arithmetic Operations with DateTime Values</span></span>

<span data-ttu-id="2819c-108">I valori [System.DateTime](xref:System.DateTime) sono caratterizzati da un livello limitato di riferimenti al fuso orario.</span><span class="sxs-lookup"><span data-stu-id="2819c-108">[System.DateTime](xref:System.DateTime) values possess a limited degree of time zone awareness.</span></span> <span data-ttu-id="2819c-109">La proprietà [DateTime.Kind](xref:System.DateTime.Kind) consente di assegnare un valore [System.DateTimeKind](xref:System.DateTimeKind) a data e ora per indicare se rappresenta l'ora locale, l'ora UTC (Coordinated Universal Time) o l'ora in un fuso orario non specificato.</span><span class="sxs-lookup"><span data-stu-id="2819c-109">The [DateTime.Kind](xref:System.DateTime.Kind) property allows a [System.DateTimeKind](xref:System.DateTimeKind) value to be assigned to the date and time to indicate whether it represents local time, Coordinated Universal Time (UTC), or the time in an unspecified time zone.</span></span> <span data-ttu-id="2819c-110">Queste informazioni limitate sul fuso orario vengono tuttavia ignorate durante il confronto o l'esecuzione di operazioni aritmetiche con data e ora per i valori [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="2819c-110">However, this limited time zone information is ignored when comparing or performing date and time arithmetic on [DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="2819c-111">Questa condizione è illustrata nell'esempio seguente, in cui si confronta l'ora locale corrente con l'ora UTC corrente.</span><span class="sxs-lookup"><span data-stu-id="2819c-111">The following example, which compares the current local time with the current UTC time, illustrates this.</span></span>

```csharp
using System;

public enum TimeComparison
{
   EarlierThan = -1,
   TheSameAs = 0,
   LaterThan = 1
}

public class DateManipulation
{
   public static void Main()
   {
      DateTime localTime = DateTime.Now;
      DateTime utcTime = DateTime.UtcNow;

      Console.WriteLine("Difference between {0} and {1} time: {2}:{3} hours", 
                        localTime.Kind.ToString(), 
                        utcTime.Kind.ToString(), 
                        (localTime - utcTime).Hours, 
                        (localTime - utcTime).Minutes);
      Console.WriteLine("The {0} time is {1} the {2} time.", 
                        localTime.Kind.ToString(), 
                        Enum.GetName(typeof(TimeComparison), localTime.CompareTo(utcTime)), 
                        utcTime.Kind.ToString());  
   }
}
// If run in the U.S. Pacific Standard Time zone, the example displays 
// the following output to the console:
//    Difference between Local and Utc time: -7:0 hours
//    The Local time is EarlierThan the Utc time.
```

```vb
Public Enum TimeComparison As Integer
   EarlierThan = -1
   TheSameAs = 0
   LaterThan = 1
End Enum

Module DateManipulation
   Public Sub Main()
      Dim localTime As Date = Date.Now
      Dim utcTime As Date = Date.UtcNow

      Console.WriteLine("Difference between {0} and {1} time: {2}:{3} hours", _
                        localTime.Kind.ToString(), _
                        utcTime.Kind.ToString(), _
                        (localTime - utcTime).Hours, _
                        (localTime - utcTime).Minutes)
      Console.WriteLine("The {0} time is {1} the {2} time.", _
                        localTime.Kind.ToString(), _ 
                        [Enum].GetName(GetType(TimeComparison), localTime.CompareTo(utcTime)), _
                        utcTime.Kind.ToString())  
      ' If run in the U.S. Pacific Standard Time zone, the example displays 
      ' the following output to the console:
      '    Difference between Local and Utc time: -7:0 hours
      '    The Local time is EarlierThan the Utc time.                                                    
   End Sub
End Module
```

<span data-ttu-id="2819c-112">Il metodo [DateTime.CompareTo(DateTime, DateTime)](xref:System.DateTime.Compare(System.DateTime,System.DateTime)) indica che l'ora locale è più indietro rispetto all'ora UTC e l'operazione di sottrazione indica che la differenza tra l'ora UTC e l'ora locale per un sistema nel fuso orario standard del Pacifico (Stati Uniti) è sette ore.</span><span class="sxs-lookup"><span data-stu-id="2819c-112">The [DateTime.CompareTo(DateTime, DateTime)](xref:System.DateTime.Compare(System.DateTime,System.DateTime)) method reports that the local time is earlier than (or less than) the UTC time, and the subtraction operation indicates that the difference between UTC and the local time for a system in the U.S. Pacific Standard Time zone is seven hours.</span></span> <span data-ttu-id="2819c-113">Ma poiché questi due valori indicano rappresentazioni diverse di un singolo momento, è chiaro in questo caso che l'intervallo di tempo è completamente attribuibile all'offset del fuso orario locale rispetto all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="2819c-113">But because these two values provide different representations of a single point in time, it is clear in this case that this time interval is completely attributable to the local time zone's offset from UTC.</span></span> 

<span data-ttu-id="2819c-114">Più in generale, la proprietà [DateTimeKind](xref:System.DateTimeKind) non influisce sui risultati restituiti dai metodi di confronto e aritmetici [DateTime](xref:System.DateTime) (come indica il confronto tra due identici momenti), anche se può influire sull'interpretazione dei risultati.</span><span class="sxs-lookup"><span data-stu-id="2819c-114">More generally, the [DateTimeKind](xref:System.DateTimeKind) property does not affect the results returned by [DateTime](xref:System.DateTime) comparison and arithmetic methods (as the comparison of two identical points in time indicates), although it can affect the interpretation of those results.</span></span> <span data-ttu-id="2819c-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2819c-115">For example:</span></span>

* <span data-ttu-id="2819c-116">Il risultato di qualsiasi operazione aritmetica eseguita su due valori di data e ora le cui proprietà [DateTimeKind](xref:System.DateTimeKind) sono entrambe uguali a [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) riflette l'intervallo di tempo effettivo tra i due valori.</span><span class="sxs-lookup"><span data-stu-id="2819c-116">The result of any arithmetic operation performed on two date and time values whose [DateTimeKind](xref:System.DateTimeKind) properties both equal [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) reflects the actual time interval between the two values.</span></span> <span data-ttu-id="2819c-117">Analogamente, il confronto di due valori di data e ora di questo tipo riflette esattamente la relazione tra le ore.</span><span class="sxs-lookup"><span data-stu-id="2819c-117">Similarly, the comparison of two such date and time values accurately reflects the relationship between times.</span></span>

* <span data-ttu-id="2819c-118">Il risultato di qualsiasi operazione aritmetica o di confronto eseguita su due valori di data e ora le cui proprietà [DateTimeKind](xref:System.DateTimeKind) sono entrambe uguali a [DateTimeKind.Local](xref:System.DateTimeKind.Local) su due valori di data e ora con valori della proprietà [DateTimeKind](xref:System.DateTimeKind) diversi riflette la differenza di ora tra i due valori.</span><span class="sxs-lookup"><span data-stu-id="2819c-118">The result of any arithmetic or comparison operation performed on two date and time values whose [DateTimeKind](xref:System.DateTimeKind) properties both equal [DateTimeKind.Local](xref:System.DateTimeKind.Local) or on two date and time values with different [DateTimeKind](xref:System.DateTimeKind) property values reflects the difference in clock time between the two values.</span></span> 

* <span data-ttu-id="2819c-119">Le operazioni aritmetiche o di confronto sui valori locali di data e ora non considerano se un particolare valore è ambiguo o non valido e non tengono conto dell'effetto di eventuali regole di regolazione risultanti dalla transizione del fuso orario locale a o dall'ora legale.</span><span class="sxs-lookup"><span data-stu-id="2819c-119">Arithmetic or comparison operations on local date and time values do not consider whether a particular value is ambiguous or invalid, nor do they take account of the effect of any adjustment rules that result from the local time zone's transition to or from daylight saving time.</span></span>

* <span data-ttu-id="2819c-120">Qualsiasi operazione che confronta o calcola la differenza tra ora UTC e ora locale include un intervallo di tempo uguale all'offset del fuso orario locale rispetto all'ora UTC nel risultato.</span><span class="sxs-lookup"><span data-stu-id="2819c-120">Any operation that compares or calculates the difference between UTC and a local time includes a time interval equal to the local time zone's offset from UTC in the result.</span></span> 

* <span data-ttu-id="2819c-121">Qualsiasi operazione che confronta o calcola la differenza tra un'ora non specificata e l'ora UTC o l'ora locale riflette l'ora dell'orologio.</span><span class="sxs-lookup"><span data-stu-id="2819c-121">Any operation that compares or calculates the difference between an unspecified time and either UTC or the local time reflects simple clock time.</span></span> <span data-ttu-id="2819c-122">Le differenze di fuso orario non vengono considerate e il risultato non riflette l'applicazione delle regole di regolazione del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="2819c-122">Time zone differences are not considered, and the result does not reflect the application of time zone adjustment rules.</span></span> 

* <span data-ttu-id="2819c-123">Qualsiasi operazione che confronta o calcola la differenza tra due ore non specificate può includere un intervallo sconosciuto che riflette la differenza di orario in due fusi orari diversi.</span><span class="sxs-lookup"><span data-stu-id="2819c-123">Any operation that compares or calculates the difference between two unspecified times may include an unknown interval that reflects the difference between the time in two different time zones.</span></span>

<span data-ttu-id="2819c-124">Esistono molti scenari in cui le differenze di fuso orario non influiscono sui calcoli di data e ora o in cui il contesto dei dati di data e ora definisce il significato delle operazioni aritmetiche o di confronto.</span><span class="sxs-lookup"><span data-stu-id="2819c-124">There are many scenarios in which time zone differences do not affect date and time calculations or in which the context of the date and time data defines the meaning of comparison or arithmetic operations.</span></span> <span data-ttu-id="2819c-125">Per una discussione su alcuni di questi elementi, vedere [Scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo](choosing-between-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="2819c-125">For a discussion of some of these, see [Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](choosing-between-datetime.md).</span></span>

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a><span data-ttu-id="2819c-126">Confronti e operazioni aritmetiche con i valori DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="2819c-126">Comparisons and Arithmetic Operations with DateTimeOffset Values</span></span>

<span data-ttu-id="2819c-127">Un valore [System.DateTimeOffset](xref:System.DateTimeOffset) include non solo una data e un'ora, ma anche un offset che definisce in modo univoco tale data e ora rispetto all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="2819c-127">A [System.DateTimeOffset](xref:System.DateTimeOffset) value includes not only a date and time, but also an offset that unambiguously defines that date and time relative to UTC.</span></span> <span data-ttu-id="2819c-128">In questo modo è possibile definire l'uguaglianza in modo diverso rispetto ai valori [System.DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="2819c-128">This makes it possible to define equality somewhat differently than for [System.DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="2819c-129">Mentre i valori [DateTime](xref:System.DateTime) sono uguali se hanno lo stesso valore di data e ora, i valori [DateTimeOffset](xref:System.DateTimeOffset) sono uguali se si riferiscono entrambi allo stesso momento.</span><span class="sxs-lookup"><span data-stu-id="2819c-129">Whereas [DateTime](xref:System.DateTime) values are equal if they have the same date and time value, [DateTimeOffset](xref:System.DateTimeOffset) values are equal if they both refer to the same point in time.</span></span> <span data-ttu-id="2819c-130">Un valore [DateTimeOffset](xref:System.DateTimeOffset) è quindi più preciso e meno soggetto a interpretazione quando viene usato nei confronti e nella maggior parte delle operazioni aritmetiche che determinano l'intervallo tra due date e ore.</span><span class="sxs-lookup"><span data-stu-id="2819c-130">This makes a [DateTimeOffset](xref:System.DateTimeOffset) value more accurate and less in need of interpretation when used in comparisons and in most arithmetic operations that determine the interval between two dates and times.</span></span> <span data-ttu-id="2819c-131">L'esempio seguente, identico a quello precedente in cui si confrontano i valori DateTime locali e UTC ma con [DateTimeOffset](xref:System.DateTimeOffset), illustra questa differenza di comportamento.</span><span class="sxs-lookup"><span data-stu-id="2819c-131">The following example, which is the [DateTimeOffset](xref:System.DateTimeOffset) equivalent to the previous example that compared local and UTC DateTime values, illustrates this difference in behavior.</span></span>

```csharp
using System;

public enum TimeComparison
{
   EarlierThan = -1,
   TheSameAs = 0,
   LaterThan = 1
}

public class DateTimeOffsetManipulation
{
   public static void Main()
   {
      DateTimeOffset localTime = DateTimeOffset.Now;
      DateTimeOffset utcTime = DateTimeOffset.UtcNow;

      Console.WriteLine("Difference between local time and UTC: {0}:{1:D2} hours", 
                        (localTime - utcTime).Hours, 
                        (localTime - utcTime).Minutes);
      Console.WriteLine("The local time is {0} UTC.", 
                        Enum.GetName(typeof(TimeComparison), localTime.CompareTo(utcTime)));  
   }
}
// Regardless of the local time zone, the example displays 
// the following output to the console:
//    Difference between local time and UTC: 0:00 hours.
//    The local time is TheSameAs UTC.
```

```vb
Public Enum TimeComparison As Integer
   EarlierThan = -1
   TheSameAs = 0
   LaterThan = 1
End Enum

Module DateTimeOffsetManipulation
   Public Sub Main()
      Dim localTime As DateTimeOffset = DateTimeOffset.Now
      Dim utcTime As DateTimeOffset = DateTimeOffset.UtcNow

      Console.WriteLine("Difference between local time and UTC: {0}:{1:D2} hours.", _
                        (localTime - utcTime).Hours, _
                        (localTime - utcTime).Minutes)
      Console.WriteLine("The local time is {0} UTC.", _
                        [Enum].GetName(GetType(TimeComparison), localTime.CompareTo(utcTime)))  
   End Sub
End Module
' Regardless of the local time zone, the example displays 
' the following output to the console:
'    Difference between local time and UTC: 0:00 hours.
'    The local time is TheSameAs UTC.
'          Console.WriteLine(e.GetType().Name)
```

<span data-ttu-id="2819c-132">In questo esempio il metodo [DateTimeOffset.CompareTo](xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)) indica che l'ora locale corrente e l'ora UTC corrente sono uguali e la sottrazione dei valori [DateTimeOffset](xref:System.DateTimeOffset) indica che la differenza tra i due orari è [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span><span class="sxs-lookup"><span data-stu-id="2819c-132">In this example, the [DateTimeOffset.CompareTo](xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)) method indicates that the current local time and the current UTC time are equal, and subtraction of [DateTimeOffset](xref:System.DateTimeOffset) values indicates that the difference between the two times is [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> 

<span data-ttu-id="2819c-133">La limitazione principale dell'uso dei valori [DateTimeOffset](xref:System.DateTimeOffset) nelle operazioni aritmetiche con data e ora è che il fuso orario non è completamente rappresentato, benché i valori [DateTimeOffset](xref:System.DateTimeOffset) contengano riferimenti al fuso orario.</span><span class="sxs-lookup"><span data-stu-id="2819c-133">The chief limitation of using [DateTimeOffset](xref:System.DateTimeOffset) values in date and time arithmetic is that although [DateTimeOffset](xref:System.DateTimeOffset) values have some time zone awareness, they are not fully time zone aware.</span></span> <span data-ttu-id="2819c-134">Sebbene il valore [DateTimeOffset](xref:System.DateTimeOffset) rifletta l'offset del fuso orario rispetto all'ora UTC quando a una variabile [DateTimeOffset](xref:System.DateTimeOffset) viene assegnato per la prima volta un valore, in un secondo tempo l'associazione al fuso orario viene annullata.</span><span class="sxs-lookup"><span data-stu-id="2819c-134">Although the [DateTimeOffset](xref:System.DateTimeOffset) value's offset reflects a time zone's offset from UTC when a [DateTimeOffset](xref:System.DateTimeOffset) variable is first assigned a value, it becomes disassociated from the time zone thereafter.</span></span> <span data-ttu-id="2819c-135">Poiché non è più associato direttamente a un'ora identificabile, l'aggiunta e la sottrazione degli intervalli di data e ora non considerano le regole di regolazione del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="2819c-135">Because it is no longer directly associated with an identifiable time, the addition and subtraction of date and time intervals does not consider a time zone's adjustment rules.</span></span> 

<span data-ttu-id="2819c-136">A titolo esemplificativo, la transizione all'ora legale negli Stati Uniti, ora solare fuso centrale, avviene alle 2.00</span><span class="sxs-lookup"><span data-stu-id="2819c-136">To illustrate, the transition to daylight saving time in the U.S. Central Standard Time zone occurs at 2:00 A.M.</span></span> <span data-ttu-id="2819c-137">del 9 marzo 2008.</span><span class="sxs-lookup"><span data-stu-id="2819c-137">on March 9, 2008.</span></span> <span data-ttu-id="2819c-138">Ciò significa che l'aggiunta di un intervallo di due ore e mezzo all'1.30</span><span class="sxs-lookup"><span data-stu-id="2819c-138">This means that adding a two and a half hour interval to a Central Standard time of 1:30 A.M.</span></span> <span data-ttu-id="2819c-139">del 9 marzo 2008 nel fuso orario standard centrale deve generare una data e un'ora equivalente alle 5.00</span><span class="sxs-lookup"><span data-stu-id="2819c-139">on March 9, 2008, should produce a date and time of 5:00 A.M.</span></span> <span data-ttu-id="2819c-140">del 9 marzo 2008.</span><span class="sxs-lookup"><span data-stu-id="2819c-140">on March 9, 2008.</span></span> <span data-ttu-id="2819c-141">Tuttavia, come mostrato nell'esempio seguente, il risultato dell'addizione è 4.00</span><span class="sxs-lookup"><span data-stu-id="2819c-141">However, as the following example shows, the result of the addition is 4:00 A.M.</span></span> <span data-ttu-id="2819c-142">del 9 marzo 2008.</span><span class="sxs-lookup"><span data-stu-id="2819c-142">on March 9, 2008.</span></span> <span data-ttu-id="2819c-143">Si noti che il risultato di questa operazione rappresenta il momento corretto, sebbene non sia l'ora nel fuso orario che interessa (ovvero, non presenta l'offset previsto per il fuso orario).</span><span class="sxs-lookup"><span data-stu-id="2819c-143">Note that this result of this operation does represent the correct point in time, although it is not the time in the time zone in which we are interested (that is, it does not have the expected time zone offset).</span></span>

```csharp
using System;

public class IntervalArithmetic
{
   public static void Main()
   {
      DateTime generalTime = new DateTime(2008, 3, 9, 1, 30, 0);
      const string tzName = "Central Standard Time";
      TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

      // Instantiate DateTimeOffset value to have correct CST offset
      try
      {
         DateTimeOffset centralTime1 = new DateTimeOffset(generalTime, 
                    TimeZoneInfo.FindSystemTimeZoneById(tzName).GetUtcOffset(generalTime));

         // Add two and a half hours      
         DateTimeOffset centralTime2 = centralTime1.Add(twoAndAHalfHours);
         // Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, 
                                                    twoAndAHalfHours.ToString(), 
                                                    centralTime2);  
      }
      catch (TimeZoneNotFoundException)
      {
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.");
      }
   }
}
// The example displays the following output to the console:
//    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 4:00:00 AM -06:00
```

```vb
Module IntervalArithmetic
   Public Sub Main()
      Dim generalTime As Date = #03/09/2008 1:30AM#
      Const tzName As String = "Central Standard Time"
      Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

      ' Instantiate DateTimeOffset value to have correct CST offset
      Try
         Dim centralTime1 As New DateTimeOffset(generalTime, _
                    TimeZoneInfo.FindSystemTimeZoneById(tzName).GetUtcOffset(generalTime))

         ' Add two and a half hours      
         Dim centralTime2 As DateTimeOffset = centralTime1.Add(twoAndAHalfHours)
         ' Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, _
                                                    twoAndAHalfHours.ToString(), _
                                                    centralTime2)   
      Catch e As TimeZoneNotFoundException
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.")
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 4:00:00 AM -06:00
```

## <a name="arithmetic-operations-with-times-in-time-zones"></a><span data-ttu-id="2819c-144">Operazioni aritmetiche con ore in fusi orari</span><span class="sxs-lookup"><span data-stu-id="2819c-144">Arithmetic Operations with Times in Time Zones</span></span>

<span data-ttu-id="2819c-145">La classe [System.TimeZoneInfo](xref:System.TimeZoneInfo) non offre metodi che applicano automaticamente regole di regolazione quando si eseguono operazioni aritmetiche con data e ora.</span><span class="sxs-lookup"><span data-stu-id="2819c-145">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class does not provide any methods that automatically apply adjustment rules when you perform date and time arithmetic.</span></span> <span data-ttu-id="2819c-146">Tuttavia, è possibile convertire l'ora in un fuso orario in ora UTC, eseguendo l'operazione aritmetica, e quindi convertirla di nuovo da ora UTC a ora nel fuso orario.</span><span class="sxs-lookup"><span data-stu-id="2819c-146">However, you can do this by converting the time in a time zone to UTC, performing the arithmetic operation, and then converting from UTC back to the time in the time zone.</span></span> <span data-ttu-id="2819c-147">Per i dettagli, vedere [Procedura: Usare fusi orari nell'aritmetica di data e ora](use-time-zones-in-arithmetic.md).</span><span class="sxs-lookup"><span data-stu-id="2819c-147">For details, see [How to: Use Time Zones in Date and Time Arithmetic](use-time-zones-in-arithmetic.md).</span></span>

<span data-ttu-id="2819c-148">Ad esempio, il codice seguente è simile al codice precedente che ha aggiunto due ore e mezzo alle 2.00</span><span class="sxs-lookup"><span data-stu-id="2819c-148">For example, the following code is similar to the previous code that added two-and-a-half hours to 2:00 A.M.</span></span> <span data-ttu-id="2819c-149">del 9 marzo 2008.</span><span class="sxs-lookup"><span data-stu-id="2819c-149">on March 9, 2008.</span></span> <span data-ttu-id="2819c-150">Tuttavia, perché il codice converte un'ora solare nel fuso orario centrale in ora UTC prima di eseguire un'operazione aritmetica con data e ora e quindi converte di nuovo il risultato da ora UTC in ora solare nel fuso orario centrale, l'ora risultante riflette la transizione dell'ora solare nel fuso orario centrale all'ora legale.</span><span class="sxs-lookup"><span data-stu-id="2819c-150">However, because it converts a Central Standard time to UTC before it performs date and time arithmetic, and then converts the result from UTC back to Central Standard time, the resulting time reflects the Central Standard Time Zone's transition to daylight saving time.</span></span>

```csharp
using System;

public class TimeZoneAwareArithmetic
{
   public static void Main()
   {
      const string tzName = "Central Standard Time";

      DateTime generalTime = new DateTime(2008, 3, 9, 1, 30, 0);
      TimeZoneInfo cst = TimeZoneInfo.FindSystemTimeZoneById(tzName);
      TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

      // Instantiate DateTimeOffset value to have correct CST offset
      try
      {
         DateTimeOffset centralTime1 = new DateTimeOffset(generalTime, 
                                       cst.GetUtcOffset(generalTime));

         // Add two and a half hours
         DateTimeOffset utcTime = centralTime1.ToUniversalTime();
         utcTime += twoAndAHalfHours;

         DateTimeOffset centralTime2 = TimeZoneInfo.ConvertTime(utcTime, cst);
         // Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, 
                                                    twoAndAHalfHours.ToString(), 
                                                    centralTime2);  
      }
      catch (TimeZoneNotFoundException)
      {
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.");
      }
   }
}
// The example displays the following output to the console:
//    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 5:00:00 AM -05:00
```

```vb
Module TimeZoneAwareArithmetic
   Public Sub Main()
      Const tzName As String = "Central Standard Time"

      Dim generalTime As Date = #03/09/2008 1:30AM#
      Dim cst As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(tzName) 
      Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

      ' Instantiate DateTimeOffset value to have correct CST offset
      Try
         Dim centralTime1 As New DateTimeOffset(generalTime, _
                    cst.GetUtcOffset(generalTime))

         ' Add two and a half hours 
         Dim utcTime As DateTimeOffset = centralTime1.ToUniversalTime()
         utcTime += twoAndAHalfHours

         Dim centralTime2 As DateTimeOffset = TimeZoneInfo.ConvertTime(utcTime, cst)
         ' Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, _
                                                    twoAndAHalfHours.ToString(), _
                                                    centralTime2)   
      Catch e As TimeZoneNotFoundException
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.")
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 5:00:00 AM -05:00
```

## <a name="see-also"></a><span data-ttu-id="2819c-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2819c-151">See Also</span></span>

[<span data-ttu-id="2819c-152">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="2819c-152">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="2819c-153">Procedura: Usare fusi orari nell'aritmetica di data e ora</span><span class="sxs-lookup"><span data-stu-id="2819c-153">How to: use time zones in date and time arithmetic</span></span>](use-time-zones-in-arithmetic.md)




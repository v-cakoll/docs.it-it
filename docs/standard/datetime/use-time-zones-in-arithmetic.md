---
title: 'Procedura: Usare fusi orari nell&quot;aritmetica di data e ora'
description: Come usare i fusi orari nell&quot;aritmetica di data e ora
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 26870cdc-1709-4978-831b-ff2a2f24856f
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: a86471972d42adcbc412cc8eeb300410ca8a9c42
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a><span data-ttu-id="c5265-104">Procedura: Usare fusi orari nell'aritmetica di data e ora</span><span class="sxs-lookup"><span data-stu-id="c5265-104">How to: use time zones in date and time arithmetic</span></span>

<span data-ttu-id="c5265-105">In genere, quando si eseguono operazioni aritmetiche di data e ora con i valori [System.DateTimeOffset](xref:System.DateTimeOffset), il risultato non riflette nessuna regola di rettifica del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="c5265-105">Ordinarily, when you perform date and time arithmetic using [System.DateTimeOffset](xref:System.DateTimeOffset) values, the result does not reflect any time zone adjustment rules.</span></span> <span data-ttu-id="c5265-106">Ciò resta vero anche quando il fuso orario del valore di data ora è chiaramente identificabile.</span><span class="sxs-lookup"><span data-stu-id="c5265-106">This is true even when the time zone of the date and time value is clearly identifiable.</span></span> <span data-ttu-id="c5265-107">In questo articolo viene illustrato come eseguire operazioni aritmetiche su valori di data e ora appartenenti a un determinato fuso orario.</span><span class="sxs-lookup"><span data-stu-id="c5265-107">This article shows how to perform arithmetic operations on date and time values that belong to a particular time zone.</span></span> <span data-ttu-id="c5265-108">I risultati delle operazioni aritmetiche rifletteranno le regole di rettifica del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="c5265-108">The results of the arithmetic operations will reflect the time zone's adjustment rules.</span></span>

## <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a><span data-ttu-id="c5265-109">Per applicare regole di rettifica ai calcoli aritmetici di data e ora</span><span class="sxs-lookup"><span data-stu-id="c5265-109">To apply adjustment rules to date and time arithmetic</span></span>

1. <span data-ttu-id="c5265-110">Implementare un metodo per vincolare un valore di data e ora al fuso orario al quale appartiene.</span><span class="sxs-lookup"><span data-stu-id="c5265-110">Implement some method of closely coupling a date and time value with the time zone to which it belongs.</span></span> <span data-ttu-id="c5265-111">Ad esempio, dichiarare una struttura che include sia il valore di data e ora sia il fuso orario al quale appartiene.</span><span class="sxs-lookup"><span data-stu-id="c5265-111">For example, declare a structure that includes both the date and time value and its time zone.</span></span> <span data-ttu-id="c5265-112">Nell'esempio seguente viene usato questo approccio per collegare un valore [DateTimeOffset](xref:System.DateTimeOffset) al fuso orario di appartenenza.</span><span class="sxs-lookup"><span data-stu-id="c5265-112">The following example uses this approach to link a [DateTimeOffset](xref:System.DateTimeOffset) value with its time zone.</span></span>

    ```csharp
    // Define a structure for DateTime values for internal use only
    internal struct TimeWithTimeZone
    {
    TimeZoneInfo TimeZone;
    DateTimeOffset Time;
    }
    ```

    ```vb
    ' Define a structure for DateTime values for internal use only
    Friend Structure TimeWithTimeZone
       Dim TimeZone As TimeZoneInfo
       Dim Time As Date
    End Structure
    ```
    
2. <span data-ttu-id="c5265-113">Convertire un'ora nell'ora Coordinated Universal Time (UTC) chiamando il metodo [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)).</span><span class="sxs-lookup"><span data-stu-id="c5265-113">Convert a time to Coordinated Universal Time (UTC) by calling the [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method.</span></span>

3. <span data-ttu-id="c5265-114">Eseguire l'operazione aritmetica sull'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="c5265-114">Perform the arithmetic operation on the UTC time.</span></span>

4. <span data-ttu-id="c5265-115">Convertire l'ora da UTC al fuso orario associato all'ora originale, chiamando il metodo [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)).</span><span class="sxs-lookup"><span data-stu-id="c5265-115">Convert the time from UTC to the original time's associated time zone by calling the [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method.</span></span> 

## <a name="example"></a><span data-ttu-id="c5265-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5265-116">Example</span></span>

<span data-ttu-id="c5265-117">L'esempio seguente aggiunge due ore e trenta minuti al 9 marzo 2008, alle 1.30</span><span class="sxs-lookup"><span data-stu-id="c5265-117">The following example adds two hours and thirty minutes to March 9, 2008, at 1:30 A.M.</span></span> <span data-ttu-id="c5265-118">ora solare fuso centrale (CST).</span><span class="sxs-lookup"><span data-stu-id="c5265-118">Central Standard Time.</span></span> <span data-ttu-id="c5265-119">La transizione del fuso orario all'ora legale si verifica trenta minuti dopo, alle 2.00</span><span class="sxs-lookup"><span data-stu-id="c5265-119">The time zone's transition to daylight saving time occurs thirty minutes later, at 2:00 A.M.</span></span> <span data-ttu-id="c5265-120">del 9 marzo 2008.</span><span class="sxs-lookup"><span data-stu-id="c5265-120">on March 9, 2008.</span></span> <span data-ttu-id="c5265-121">Poiché nell'esempio vengono seguiti i quattro passaggi elencati nella sezione precedente, l'orario corretto risultante corrisponderà alle 5.00</span><span class="sxs-lookup"><span data-stu-id="c5265-121">Because the example follows the four steps listed in the previous section, it correctly reports the resulting time as 5:00 A.M.</span></span> <span data-ttu-id="c5265-122">del 9 marzo 2008.</span><span class="sxs-lookup"><span data-stu-id="c5265-122">on March 9, 2008.</span></span> 

```csharp
using System;

public struct TimeZoneTime
{
   public TimeZoneInfo TimeZone;
   public DateTimeOffset Time;

   public TimeZoneTime(TimeZoneInfo tz, DateTimeOffset time)
   {
      if (tz == null) 
         throw new ArgumentNullException("The time zone cannot be a null reference.");

      this.TimeZone = tz;
      this.Time = time;   
   }

   public TimeZoneTime AddTime(TimeSpan interval)
   {
      // Convert time to UTC
      DateTimeOffset utcTime = TimeZoneInfo.ConvertTime(this.Time, TimeZoneInfo.Utc);      
      // Add time interval to time
      utcTime = utcTime.Add(interval);
      // Convert time back to time in time zone
      return new TimeZoneTime(this.TimeZone, TimeZoneInfo.ConvertTime(utcTime, this.TimeZone));
   }
}

public class TimeArithmetic
{
   public const string tzName = "Central Standard Time";

   public static void Main()
   {
      try
      {
         TimeZoneTime cstTime1, cstTime2;

         TimeZoneInfo cst = TimeZoneInfo.FindSystemTimeZoneById(tzName);
         DateTime time1 = new DateTime(2008, 3, 9, 1, 30, 0);          
         TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

         cstTime1 = new TimeZoneTime(cst, 
                        new DateTimeOffset(time1, cst.GetUtcOffset(time1)));
         cstTime2 = cstTime1.AddTime(twoAndAHalfHours);
         Console.WriteLine("{0} + {1} hours = {2}", cstTime1.Time, 
                                                    twoAndAHalfHours.ToString(),  
                                                    cstTime2.Time);
      }
      catch
      {
         Console.WriteLine("Unable to find {0}.", tzName);
      }
   }
}
```

```vb
Public Structure TimeZoneTime
   Public TimeZone As TimeZoneInfo
   Public Time As Date

   Public Sub New(tz As TimeZoneInfo, time As Date)
      If tz Is Nothing Then _
         Throw New ArgumentNullException("The time zone cannot be a null reference.")

      Me.TimeZone = tz
      Me.Time = time
   End Sub

   Public Function AddTime(interval As TimeSpan) As TimeZoneTime
      ' Convert time to UTC
      Dim utcTime As DateTime = TimeZoneInfo.ConvertTimeToUtc(Me.Time, _
                                                              Me.TimeZone)      
      ' Add time interval to time
      utcTime = utcTime.Add(interval)
      ' Convert time back to time in time zone
      Return New TimeZoneTime(Me.TimeZone, TimeZoneInfo.ConvertTime(utcTime, _
                              TimeZoneInfo.Utc, Me.TimeZone))
   End Function
End Structure

Module TimeArithmetic
   Public Const tzName As String = "Central Standard Time"

   Public Sub Main()
      Try
         Dim cstTime1, cstTime2 As TimeZoneTime

         Dim cst As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(tzName)
         Dim time1 As Date = #03/09/2008 1:30AM#
         Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

         cstTime1 = New TimeZoneTime(cst, time1)
         cstTime2 = cstTime1.AddTime(twoAndAHalfHours)

         Console.WriteLine("{0} + {1} hours = {2}", cstTime1.Time, _
                                                    twoAndAHalfHours.ToString(), _ 
                                                    cstTime2.Time)  
      Catch
         Console.WriteLine("Unable to find {0}.", tzName)
      End Try   
   End Sub   
End Module
```

<span data-ttu-id="c5265-123">Se questa aggiunta viene eseguita semplicemente al valore [DateTimeOffset](xref:System.DateTimeOffset) senza prima convertirlo a UTC, il risultato riflette l'orario corretto, ma il suo offset non riflette quello del fuso orario designato per l'orario.</span><span class="sxs-lookup"><span data-stu-id="c5265-123">Note that if this addition is simply performed on the [DateTimeOffset](xref:System.DateTimeOffset) value without first converting it to UTC, the result reflects the correct point in time but its offset does not reflect that of the designated time zone for that time.</span></span> 

<span data-ttu-id="c5265-124">I valori [DateTimeOffset](xref:System.DateTimeOffset) sono dissociati da qualsiasi fuso orario al quale appartengono.</span><span class="sxs-lookup"><span data-stu-id="c5265-124">[DateTimeOffset](xref:System.DateTimeOffset) values are disassociated from any time zone to which they might belong.</span></span> <span data-ttu-id="c5265-125">Per eseguire operazioni aritmetiche di data ora con una modalità che applica automaticamente le regole di rettifica del fuso orario, il fuso orario di appartenenza di qualsiasi valore di data e ora deve essere immediatamente identificabile.</span><span class="sxs-lookup"><span data-stu-id="c5265-125">To perform date and time arithmetic in a way that automatically applies a time zone's adjustment rules, the time zone to which any date and time value belongs must be immediately identifiable.</span></span> <span data-ttu-id="c5265-126">Ciò significa che una data e ora e il fuso orario associato devono essere strettamente collegati.</span><span class="sxs-lookup"><span data-stu-id="c5265-126">This means that a date and time and its associated time zone must be tightly coupled.</span></span> <span data-ttu-id="c5265-127">Esistono diversi modi per ottenere questo risultato, tra cui i seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5265-127">There are several ways to do this, which include the following:</span></span>

* <span data-ttu-id="c5265-128">Presupporre che tutti gli orari usati in un'applicazione appartengano a un determinato fuso orario.</span><span class="sxs-lookup"><span data-stu-id="c5265-128">Assume that all times used in an application belong to a particular time zone.</span></span> <span data-ttu-id="c5265-129">Pur essendo appropriato in alcuni casi, questo approccio offre una flessibilità limitata e potenzialmente anche una portabilità limitata.</span><span class="sxs-lookup"><span data-stu-id="c5265-129">Although appropriate in some cases, this approach offers limited flexibility and possibly limited portability.</span></span>

* <span data-ttu-id="c5265-130">Definire un tipo che vincoli in modo stretto una data e ora con il fuso orario associato, includendo entrambi come campi del tipo.</span><span class="sxs-lookup"><span data-stu-id="c5265-130">Define a type that tightly couples a date and time with its associated time zone by including both as fields of the type.</span></span> <span data-ttu-id="c5265-131">Questo approccio viene usato nell'esempio di codice, che definisce una struttura per l'archiviazione della data e ora e del fuso orario in due campi membro.</span><span class="sxs-lookup"><span data-stu-id="c5265-131">This approach is used in the code example, which defines a structure to store the date and time and the time zone in two member fields.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5265-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5265-132">See Also</span></span>

[<span data-ttu-id="c5265-133">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="c5265-133">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="c5265-134">Esecuzione di operazioni aritmetiche con date e ore</span><span class="sxs-lookup"><span data-stu-id="c5265-134">Performing arithmetic operations with dates and times</span></span>](performing-arithmetic-operations.md)


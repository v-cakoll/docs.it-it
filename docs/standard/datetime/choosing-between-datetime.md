---
title: Scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo
description: Scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/11/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 2dd84ee8-9f0f-4054-9537-155857a460cd
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: aeb1928be32584ee4b6acf7c9a4f4330daedc590
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="choosing-between-datetime-datetimeoffset-timespan-and-timezoneinfo"></a><span data-ttu-id="34e7f-104">Scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="34e7f-104">Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo</span></span>

<span data-ttu-id="34e7f-105">Le applicazioni .NET che usano informazioni su data e ora sono molto diversificate e possono usare tali informazioni in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="34e7f-105">.NET applications that use date and time information are very diverse and can use that information in several ways.</span></span> <span data-ttu-id="34e7f-106">Gli utilizzi più comuni delle informazioni su data e ora includono uno o più dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="34e7f-106">The more common uses of date and time information include one or more of the following:</span></span>

* <span data-ttu-id="34e7f-107">Indicare solo una data, perché le informazioni sull'ora non sono importanti.</span><span class="sxs-lookup"><span data-stu-id="34e7f-107">To reflect a date only, so that time information is not important.</span></span>

* <span data-ttu-id="34e7f-108">Indicare solo un'ora, perché le informazioni sulla data non sono importanti.</span><span class="sxs-lookup"><span data-stu-id="34e7f-108">To reflect a time only, so that date information is not important.</span></span>

* <span data-ttu-id="34e7f-109">Indicare una data e un'ora astratte e non associate a un momento e un luogo specifici. Ad esempio, la maggior parte dei negozi di una catena internazionale apre alle 9.00 di ogni giorno feriale.</span><span class="sxs-lookup"><span data-stu-id="34e7f-109">To reflect an abstract date and time that is not tied to a specific time and place (for example, most stores in an international chain open on weekdays at 9:00 A.M.).</span></span>

* <span data-ttu-id="34e7f-110">Recuperare informazioni su data e ora da origini esterne all'applicazione .NET, in genere quando tali informazioni sono archiviate in un tipo di dati semplice.</span><span class="sxs-lookup"><span data-stu-id="34e7f-110">To retrieve date and time information from sources outside of the .NET application, typically where date and time information is stored in a simple data type.</span></span>

* <span data-ttu-id="34e7f-111">Identificare in modo univoco e senza ambiguità un singolo momento.</span><span class="sxs-lookup"><span data-stu-id="34e7f-111">To uniquely and unambiguously identify a single point in time.</span></span> <span data-ttu-id="34e7f-112">In alcune applicazioni è necessario che la data e l'ora siano non ambigue solo nel sistema host, in altre devono non esserlo in tutti i sistemi (ovvero, una data serializzata in un sistema può essere deserializzata in modo significativo e usata in un altro sistema in qualsiasi parte del mondo).</span><span class="sxs-lookup"><span data-stu-id="34e7f-112">Some applications require that a date and time be unambiguous only on the host system; others require that it be unambiguous across systems (that is, a date serialized on one system can be meaningfully deserialized and used on another system anywhere in the world).</span></span> 

* <span data-ttu-id="34e7f-113">Mantenere più ore correlate, ad esempio l'ora locale del richiedente e l'ora di ricezione di una richiesta Web nel server.</span><span class="sxs-lookup"><span data-stu-id="34e7f-113">To preserve multiple related times (such as the requestor's local time and the server's time of receipt for a Web request).</span></span>

* <span data-ttu-id="34e7f-114">Eseguire operazioni aritmetiche per date e ore, possibilmente con un risultato che identifichi in modo univoco e senza ambiguità una singolo momento.</span><span class="sxs-lookup"><span data-stu-id="34e7f-114">To perform date and time arithmetic, possibly with a result that uniquely and unambiguously identifies a single point in time.</span></span> 

<span data-ttu-id="34e7f-115">.NET include i tipi [System.DateTime](xref:System.DateTime), [System.DateTimeOffset](xref:System.DateTimeOffset), [System.TimeSpan](xref:System.TimeSpan) e [System.TimeZoneInfo](xref:System.TimeZoneInfo). Tutti i tipi possono essere usati per compilare applicazioni che impiegano date e ore.</span><span class="sxs-lookup"><span data-stu-id="34e7f-115">.NET includes the [System.DateTime](xref:System.DateTime), [System.DateTimeOffset](xref:System.DateTimeOffset), [System.TimeSpan](xref:System.TimeSpan), and [System.TimeZoneInfo](xref:System.TimeZoneInfo) types, all of which can be used to build applications that work with dates and times.</span></span> 

> [!NOTE]
> <span data-ttu-id="34e7f-116">Questo argomento non descrive `TimeZone`, un tipo mene recente la cui funzionalità è quasi interamente integrata nella classe [System.TimeZoneInfo](xref:System.TimeZoneInfo).</span><span class="sxs-lookup"><span data-stu-id="34e7f-116">This topic does not discuss the older `TimeZone` type, because its functionality is almost entirely incorporated in the [System.TimeZoneInfo](xref:System.TimeZoneInfo) class.</span></span> <span data-ttu-id="34e7f-117">Quando è possibile, gli sviluppatori devono usare la classe [System.TimeZoneInfo](xref:System.TimeZoneInfo) anziché la classe `TimeZone`.</span><span class="sxs-lookup"><span data-stu-id="34e7f-117">Whenever possible, developers should use the [System.TimeZoneInfo](xref:System.TimeZoneInfo) class instead of the `TimeZone` class.</span></span>


## <a name="the-datetime-structure"></a><span data-ttu-id="34e7f-118">Struttura DateTime</span><span class="sxs-lookup"><span data-stu-id="34e7f-118">The DateTime structure</span></span>

<span data-ttu-id="34e7f-119">Un valore [System.DateTime](xref:System.DateTime) definisce una data e un'ora specifiche.</span><span class="sxs-lookup"><span data-stu-id="34e7f-119">A [System.DateTime](xref:System.DateTime) value defines a particular date and time.</span></span> <span data-ttu-id="34e7f-120">Include la proprietà [Kind](xref:System.DateTime.Kind) che contiene informazioni limitate sul fuso orario cui appartengono la data e l'ora.</span><span class="sxs-lookup"><span data-stu-id="34e7f-120">It includes a [Kind](xref:System.DateTime.Kind) property that provides limited information about the time zone to which that date and time belongs.</span></span> <span data-ttu-id="34e7f-121">Il valore [DateTimeKind](xref:System.DateTimeKind) restituito dalla proprietà [Kind](xref:System.DateTime.Kind) indica se il valore [DateTime](xref:System.DateTime) si riferisce all'ora locale [DateTimeKind.Local](xref:System.DateTimeKind.Local)), Coordinated Universal Time (UTC) [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) o a un'ora non specificata [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span><span class="sxs-lookup"><span data-stu-id="34e7f-121">The [DateTimeKind](xref:System.DateTimeKind) value returned by the [Kind](xref:System.DateTime.Kind) property indicates whether the [DateTime](xref:System.DateTime) value represents the local time [DateTimeKind.Local](xref:System.DateTimeKind.Local)), Coordinated Universal Time (UTC) [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), or an unspecified time [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span></span>

<span data-ttu-id="34e7f-122">La struttura [DateTime](xref:System.DateTime) è adatta per le applicazioni che hanno le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="34e7f-122">The [DateTime](xref:System.DateTime) structure is suitable for applications that do the following:</span></span> 

* <span data-ttu-id="34e7f-123">Usano solo date.</span><span class="sxs-lookup"><span data-stu-id="34e7f-123">Work with dates only.</span></span>

* <span data-ttu-id="34e7f-124">Usano solo ore.</span><span class="sxs-lookup"><span data-stu-id="34e7f-124">Work with times only.</span></span>

* <span data-ttu-id="34e7f-125">Usano date e ore astratte.</span><span class="sxs-lookup"><span data-stu-id="34e7f-125">Work with abstract dates and times.</span></span>

* <span data-ttu-id="34e7f-126">Usano date e ore per le quali mancano informazioni sul fuso orario.</span><span class="sxs-lookup"><span data-stu-id="34e7f-126">Work with dates and times for which time zone information is missing.</span></span> 

* <span data-ttu-id="34e7f-127">Usano solo date e ore UTC.</span><span class="sxs-lookup"><span data-stu-id="34e7f-127">Work with UTC dates and times only.</span></span> 

* <span data-ttu-id="34e7f-128">Recuperano informazioni sulla data e sull'ora da origini esterne a .NET Framework, come i database SQL.</span><span class="sxs-lookup"><span data-stu-id="34e7f-128">Retrieve date and time information from sources outside the .NET Framework, such as SQL databases.</span></span> <span data-ttu-id="34e7f-129">In genere, queste origini archiviano le informazioni su data e ora in un formato semplice, compatibile con la struttura [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="34e7f-129">Typically, these sources store date and time information in a simple format that is compatible with the [DateTime](xref:System.DateTime) structure.</span></span>

* <span data-ttu-id="34e7f-130">Eseguono operazioni aritmetiche su date e ore, ma con particolare attenzione ai risultati generali.</span><span class="sxs-lookup"><span data-stu-id="34e7f-130">Perform date and time arithmetic, but are concerned with general results.</span></span> <span data-ttu-id="34e7f-131">Ad esempio, in un'operazione di addizione che aggiunge sei mesi a una data e un'ora specifiche, spesso non è importante se il risultato viene adattato per l'ora legale.</span><span class="sxs-lookup"><span data-stu-id="34e7f-131">For example, in an addition operation that adds six months to a particular date and time, it is often not important whether the result is adjusted for daylight saving time.</span></span>

<span data-ttu-id="34e7f-132">A meno che un determinato valore [DateTime](xref:System.DateTime) non rappresenti un'ora UTC, il valore di data e ora è spesso ambiguo e limitato in termini di portabilità.</span><span class="sxs-lookup"><span data-stu-id="34e7f-132">Unless a particular [DateTime](xref:System.DateTime) value represents UTC, that date and time value is often ambiguous or limited in its portability.</span></span> <span data-ttu-id="34e7f-133">Ad esempio, se un valore [DateTime](xref:System.DateTime) rappresenta l'ora locale, è portabile all'interno del fuso orario locale. Di conseguenza, se il valore viene deserializzato in un altro sistema con lo stesso fuso orario, identifica comunque un singolo momento senza ambiguità.</span><span class="sxs-lookup"><span data-stu-id="34e7f-133">For example, if a [DateTime](xref:System.DateTime) value represents the local time, it is portable within that local time zone (that is, if the value is deserialized on another system in the same time zone, that value still unambiguously identifies a single point in time).</span></span> <span data-ttu-id="34e7f-134">Al di fuori del fuso orario locale, tale valore [DateTime](xref:System.DateTime) è soggetto a più interpretazioni.</span><span class="sxs-lookup"><span data-stu-id="34e7f-134">Outside the local time zone, that [DateTime](xref:System.DateTime) value can have multiple interpretations.</span></span> <span data-ttu-id="34e7f-135">Se la proprietà [Kind](xref:System.DateTime.Kind) del valore è [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), il valore è ancora meno portabile, in quanto è ora ambiguo all'interno dello stesso fuso orario e probabilmente anche nello stesso sistema in cui è stato inizialmente serializzato.</span><span class="sxs-lookup"><span data-stu-id="34e7f-135">If the value's [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), it is even less portable: it is now ambiguous within the same time zone and possibly even on the same system on which it was first serialized.</span></span> <span data-ttu-id="34e7f-136">Solo se un valore [DateTime](xref:System.DateTime) rappresenta un'ora UTC, identifica senza ambiguità un singolo momento, indipendentemente dal sistema o dal fuso orario in cui viene usato.</span><span class="sxs-lookup"><span data-stu-id="34e7f-136">Only if a [DateTime](xref:System.DateTime) value represents UTC does that value unambiguously identify a single point in time regardless of the system or time zone in which the value is used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34e7f-137">Quando si salvano o condividono dati [DateTime](xref:System.DateTime), è consigliabile usare l'ora UTC e la proprietà [Kind](xref:System.DateTime) del valore [DateTime](xref:System.DateTime.Kind) deve essere impostata su [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span><span class="sxs-lookup"><span data-stu-id="34e7f-137">When saving or sharing [DateTime](xref:System.DateTime) data, UTC should be used and the [DateTime](xref:System.DateTime) value's [Kind](xref:System.DateTime.Kind) property should be set to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

## <a name="the-datetimeoffset-structure"></a><span data-ttu-id="34e7f-138">Struttura DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="34e7f-138">The DateTimeOffset structure</span></span>

<span data-ttu-id="34e7f-139">La struttura [System.DateTimeOffset](xref:System.DateTimeOffset) rappresenta un valore di data e ora, insieme a un offset che indica la differenza di tale valore rispetto all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="34e7f-139">The [System.DateTimeOffset](xref:System.DateTimeOffset) structure represents a date and time value, together with an offset that indicates how much that value differs from UTC.</span></span> <span data-ttu-id="34e7f-140">In questo modo, il valore identifica sempre senza ambiguità un singolo momento.</span><span class="sxs-lookup"><span data-stu-id="34e7f-140">Thus, the value always unambiguously identifies a single point in time.</span></span> 

<span data-ttu-id="34e7f-141">Il tipo [DateTimeOffset](xref:System.DateTimeOffset) include tutte le funzionalità del tipo [DateTime](xref:System.DateTime) insieme alla compatibilità del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="34e7f-141">The [DateTimeOffset](xref:System.DateTimeOffset) type includes all of the functionality of the [DateTime](xref:System.DateTime) type along with time zone awareness.</span></span> <span data-ttu-id="34e7f-142">Lo rende adatto per le applicazioni che hanno le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="34e7f-142">This makes it is suitable for applications that do the following:</span></span> 

* <span data-ttu-id="34e7f-143">Identificano in modo univoco e non ambiguo un singolo momento.</span><span class="sxs-lookup"><span data-stu-id="34e7f-143">Uniquely and unambiguously identify a single point in time.</span></span> <span data-ttu-id="34e7f-144">Il tipo [DateTimeOffset](xref:System.DateTimeOffset) può essere usato per definire senza ambiguità il significato di "adesso", per registrare data e ora delle transazioni, del sistema o degli eventi delle applicazioni, nonché registrare data e ora di creazione e modifica dei file.</span><span class="sxs-lookup"><span data-stu-id="34e7f-144">The [DateTimeOffset](xref:System.DateTimeOffset) type can be used to unambiguously define the meaning of "now", to log transaction times, to log the times of system or application events, and to record file creation and modification times.</span></span> 

* <span data-ttu-id="34e7f-145">Eseguono operazioni aritmetiche su data e ora.</span><span class="sxs-lookup"><span data-stu-id="34e7f-145">Perform general date and time arithmetic.</span></span>

* <span data-ttu-id="34e7f-146">Mantengono più date e ore correlate, purché vengano archiviate come due valori separati o due membri di una struttura.</span><span class="sxs-lookup"><span data-stu-id="34e7f-146">Preserve multiple related times, as long as those times are stored as two separate values or as two members of a structure.</span></span>

> [!NOTE]
> <span data-ttu-id="34e7f-147">Questi usi per i valori [DateTimeOffset](xref:System.DateTimeOffset) sono molto più comuni di quelli per i valori [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="34e7f-147">These uses for [DateTimeOffset](xref:System.DateTimeOffset) values are much more common than those for [DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="34e7f-148">Di conseguenza, [DateTimeOffset](xref:System.DateTimeOffset) deve essere considerato il tipo di data e ora predefinito per lo sviluppo di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="34e7f-148">As a result, [DateTimeOffset](xref:System.DateTimeOffset) should be considered the default date and time type for application development.</span></span>

<span data-ttu-id="34e7f-149">Un valore [DateTimeOffset](xref:System.DateTimeOffset) non è associato a un determinato fuso orario, ma può derivare da svariati fusi orari.</span><span class="sxs-lookup"><span data-stu-id="34e7f-149">A [DateTimeOffset](xref:System.DateTimeOffset) value is not tied to a particular time zone, but can originate from any of a variety of time zones.</span></span> <span data-ttu-id="34e7f-150">Per illustrare questo concetto, l'esempio seguente elenca i fusi orari cui può appartenere un certo numero di valori [DateTimeOffset](xref:System.DateTimeOffset), incluso un valore con ora solare Pacifico locale.</span><span class="sxs-lookup"><span data-stu-id="34e7f-150">To illustrate this, the following example lists the time zones to which a number of [DateTimeOffset](xref:System.DateTimeOffset) values (including a local Pacific Standard Time) can belong.</span></span>

```csharp
using System;
using System.Collections.ObjectModel;

public class TimeOffsets
{
   public static void Main()
   {
      DateTime thisDate = new DateTime(2007, 3, 10, 0, 0, 0);
      DateTime dstDate = new DateTime(2007, 6, 10, 0, 0, 0);
      DateTimeOffset thisTime;

      thisTime = new DateTimeOffset(dstDate, new TimeSpan(-7, 0, 0));
      ShowPossibleTimeZones(thisTime);

      thisTime = new DateTimeOffset(thisDate, new TimeSpan(-6, 0, 0));  
      ShowPossibleTimeZones(thisTime);

      thisTime = new DateTimeOffset(thisDate, new TimeSpan(+1, 0, 0));
      ShowPossibleTimeZones(thisTime);
   }

   private static void ShowPossibleTimeZones(DateTimeOffset offsetTime)
   {
      TimeSpan offset = offsetTime.Offset;
      ReadOnlyCollection<TimeZoneInfo> timeZones;

      Console.WriteLine("{0} could belong to the following time zones:", 
                        offsetTime.ToString());
      // Get all time zones defined on local system
      timeZones = TimeZoneInfo.GetSystemTimeZones();     
      // Iterate time zones 
      foreach (TimeZoneInfo timeZone in timeZones)
      {
         // Compare offset with offset for that date in that time zone
         if (timeZone.GetUtcOffset(offsetTime.DateTime).Equals(offset))
            Console.WriteLine("   {0}", timeZone.DisplayName);
      }
      Console.WriteLine();
   } 
}
// This example displays the following output to the console:
//       6/10/2007 12:00:00 AM -07:00 could belong to the following time zones:
//          (GMT-07:00) Arizona
//          (GMT-08:00) Pacific Time (US & Canada)
//          (GMT-08:00) Tijuana, Baja California
//       
//       3/10/2007 12:00:00 AM -06:00 could belong to the following time zones:
//          (GMT-06:00) Central America
//          (GMT-06:00) Central Time (US & Canada)
//          (GMT-06:00) Guadalajara, Mexico City, Monterrey - New
//          (GMT-06:00) Guadalajara, Mexico City, Monterrey - Old
//          (GMT-06:00) Saskatchewan
//       
//       3/10/2007 12:00:00 AM +01:00 could belong to the following time zones:
//          (GMT+01:00) Amsterdam, Berlin, Bern, Rome, Stockholm, Vienna
//          (GMT+01:00) Belgrade, Bratislava, Budapest, Ljubljana, Prague
//          (GMT+01:00) Brussels, Copenhagen, Madrid, Paris
//          (GMT+01:00) Sarajevo, Skopje, Warsaw, Zagreb
//          (GMT+01:00) West Central Africa
```

```vb
Imports System.Collections.ObjectModel

Module TimeOffsets
   Public Sub Main()
      Dim thisTime As DateTimeOffset 

      thisTime = New DateTimeOffset(#06/10/2007#, New TimeSpan(-7, 0, 0))
      ShowPossibleTimeZones(thisTime) 

      thisTime = New DateTimeOffset(#03/10/2007#, New TimeSpan(-6, 0, 0))  
      ShowPossibleTimeZones(thisTime)

      thisTime = New DateTimeOffset(#03/10/2007#, New TimeSpan(+1, 0, 0))
      ShowPossibleTimeZones(thisTime)
   End Sub

   Private Sub ShowPossibleTimeZones(offsetTime As DateTimeOffset)
      Dim offset As TimeSpan = offsetTime.Offset
      Dim timeZones As ReadOnlyCollection(Of TimeZoneInfo)

      Console.WriteLine("{0} could belong to the following time zones:", _
                        offsetTime.ToString())
      ' Get all time zones defined on local system
      timeZones = TimeZoneInfo.GetSystemTimeZones()     
      ' Iterate time zones
      For Each timeZone As TimeZoneInfo In timeZones
         ' Compare offset with offset for that date in that time zone
         If timeZone.GetUtcOffset(offsetTime.DateTime).Equals(offset) Then
            Console.WriteLine("   {0}", timeZone.DisplayName)
         End If   
      Next
      Console.WriteLine()
   End Sub
End Module
' This example displays the following output to the console:
'       6/10/2007 12:00:00 AM -07:00 could belong to the following time zones:
'          (GMT-07:00) Arizona
'          (GMT-08:00) Pacific Time (US & Canada)
'          (GMT-08:00) Tijuana, Baja California
'       
'       3/10/2007 12:00:00 AM -06:00 could belong to the following time zones:
'          (GMT-06:00) Central America
'          (GMT-06:00) Central Time (US & Canada)
'          (GMT-06:00) Guadalajara, Mexico City, Monterrey - New
'          (GMT-06:00) Guadalajara, Mexico City, Monterrey - Old
'          (GMT-06:00) Saskatchewan
'       
'       3/10/2007 12:00:00 AM +01:00 could belong to the following time zones:
'          (GMT+01:00) Amsterdam, Berlin, Bern, Rome, Stockholm, Vienna
'          (GMT+01:00) Belgrade, Bratislava, Budapest, Ljubljana, Prague
'          (GMT+01:00) Brussels, Copenhagen, Madrid, Paris
'          (GMT+01:00) Sarajevo, Skopje, Warsaw, Zagreb
'          (GMT+01:00) West Central Africa
```

<span data-ttu-id="34e7f-151">L'output mostra che ogni valore di data e ora nell'esempio può appartenere almeno a tre fusi orari diversi.</span><span class="sxs-lookup"><span data-stu-id="34e7f-151">The output shows that each date and time value in this example can belong to at least three different time zones.</span></span> <span data-ttu-id="34e7f-152">Il valore [DateTimeOffset](xref:System.DateTimeOffset) 6/10/2007 indica che se un valore di data e ora rappresenta un orario con ora legale, la sua differenza dall'ora UTC non corrisponde necessariamente alla differenza dall'ora UTC di base del fuso orario di origine o alla differenza dall'ora UTC indicata nel nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="34e7f-152">The [DateTimeOffset](xref:System.DateTimeOffset) value of 6/10/2007 shows that if a date and time value represents a daylight saving time, its offset from UTC does not even necessarily correspond to the originating time zone's base UTC offset or to the offset from UTC found in its display name.</span></span> <span data-ttu-id="34e7f-153">Questo significa che poiché un singolo valore [DateTimeOffset](xref:System.DateTimeOffset) non è strettamente collegato al proprio fuso orario, non può indicare la transizione di un fuso orario da e verso l'ora legale.</span><span class="sxs-lookup"><span data-stu-id="34e7f-153">This means that, because a single [DateTimeOffset](xref:System.DateTimeOffset)  value is not tightly coupled with its time zone, it cannot reflect a time zone's transition to and from daylight saving time.</span></span> <span data-ttu-id="34e7f-154">Questo comportamento può rivelarsi particolarmente problematico quando vengono usate operazioni aritmetiche per date e ore per modificare un valore [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="34e7f-154">This can be particularly problematic when date and time arithmetic is used to manipulate a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="34e7f-155">Per informazioni su come eseguire operazioni aritmetiche per date e ore che tengano conto delle regole di adeguamento del fuso orario, vedere [Performing arithmetic operations with dates and times](performing-arithmetic-operations.md) (Esecuzione di operazioni aritmetiche con date e ore).</span><span class="sxs-lookup"><span data-stu-id="34e7f-155">For a discussion of how to perform date and time arithmetic in a way that takes account of a time zone's adjustment rules, see [Performing arithmetic operations with dates and times](performing-arithmetic-operations.md).</span></span>

## <a name="the-timespan-structure"></a><span data-ttu-id="34e7f-156">Struttura TimeSpan</span><span class="sxs-lookup"><span data-stu-id="34e7f-156">The TimeSpan structure</span></span>

<span data-ttu-id="34e7f-157">La struttura [System.TimeSpan](xref:System.TimeSpan) rappresenta un intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="34e7f-157">The [System.TimeSpan](xref:System.TimeSpan) structure represents a time interval.</span></span> <span data-ttu-id="34e7f-158">Ecco i due utilizzi tipici:</span><span class="sxs-lookup"><span data-stu-id="34e7f-158">Its two typical uses are:</span></span> 

* <span data-ttu-id="34e7f-159">Indicare l'intervallo di tempo tra due valori di data e ora.</span><span class="sxs-lookup"><span data-stu-id="34e7f-159">Reflecting the time interval between two date and time values.</span></span> <span data-ttu-id="34e7f-160">Ad esempio, la sottrazione di un valore [DateTime](xref:System.DateTime) da un altro restituisce un valore [TimeSpan](xref:System.TimeSpan).</span><span class="sxs-lookup"><span data-stu-id="34e7f-160">For example, subtracting one [DateTime](xref:System.DateTime) value from another returns a [TimeSpan](xref:System.TimeSpan) value.</span></span> 

* <span data-ttu-id="34e7f-161">Misurare il tempo trascorso.</span><span class="sxs-lookup"><span data-stu-id="34e7f-161">Measuring elapsed time.</span></span> <span data-ttu-id="34e7f-162">Ad esempio, la proprietà [Stopwatch.Elapsed](xref:System.Diagnostics.Stopwatch.Elapsed) restituisce un valore [TimeSpan](xref:System.TimeSpan) che indica l'intervallo di tempo trascorso dalla chiamata a uno dei metodi [System.Diagnostics.Stopwatch](xref:System.Diagnostics.Stopwatch) che inizia a misurare il tempo trascorso.</span><span class="sxs-lookup"><span data-stu-id="34e7f-162">For example, the [Stopwatch.Elapsed](xref:System.Diagnostics.Stopwatch.Elapsed) property returns a [TimeSpan](xref:System.TimeSpan) value that reflects the time interval that has elapsed since the call to one of the [System.Diagnostics.Stopwatch](xref:System.Diagnostics.Stopwatch) methods that begins to measure elapsed time.</span></span>

<span data-ttu-id="34e7f-163">Un valore [TimeSpan](xref:System.TimeSpan) può essere usato anche come sostituzione di un valore [DateTime](xref:System.DateTime) quando tale valore indica un momento senza riferimento a una determinata ora del giorno.</span><span class="sxs-lookup"><span data-stu-id="34e7f-163">A [TimeSpan](xref:System.TimeSpan) value can also be used as a replacement for a [DateTime](xref:System.DateTime) value when that value reflects a time without reference to a particular time of day.</span></span> <span data-ttu-id="34e7f-164">Questo uso è simile alle proprietà [DateTime.TimeOfDay](xref:System.DateTime.TimeOfDay) e [DateTimeOffset.TimeOfDay](xref:System.DateTimeOffset.TimeOfDay), che restituiscono un valore [TimeSpan](xref:System.TimeSpan) che rappresenta l'ora senza riferimento a una data.</span><span class="sxs-lookup"><span data-stu-id="34e7f-164">This usage is similar to the [DateTime.TimeOfDay](xref:System.DateTime.TimeOfDay) and [DateTimeOffset.TimeOfDay](xref:System.DateTimeOffset.TimeOfDay) properties, which return a [TimeSpan](xref:System.TimeSpan) value that represents the time without reference to a date.</span></span> <span data-ttu-id="34e7f-165">Ad esempio, la struttura [TimeSpan](xref:System.TimeSpan) può essere usata per indicare l'ora di apertura o di chiusura di un negozio oppure per rappresentare l'ora in cui si verifica un evento regolare.</span><span class="sxs-lookup"><span data-stu-id="34e7f-165">For example, the [TimeSpan](xref:System.TimeSpan) structure can be used to reflect a store's daily opening or closing time, or it can be used to represent the time at which any regular event occurs.</span></span>

<span data-ttu-id="34e7f-166">L'esempio seguente definisce una struttura `StoreInfo` che include oggetti [TimeSpan](xref:System.TimeSpan) per le ore di apertura e di chiusura di un negozio, nonché un oggetto [TimeZoneInfo](xref:System.TimeZoneInfo) che rappresenta il fuso orario del negozio.</span><span class="sxs-lookup"><span data-stu-id="34e7f-166">The following example defines a `StoreInfo` structure that includes [TimeSpan](xref:System.TimeSpan) objects for store opening and closing times, as well as a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the store's time zone.</span></span> <span data-ttu-id="34e7f-167">La struttura include anche due metodi, `IsOpenNow` e `IsOpenAt`, che indicano se il negozio è aperto a un'ora specificata dall'utente, che si suppone si trovi nel fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="34e7f-167">The structure also includes two methods, `IsOpenNow` and `IsOpenAt`, that indicates whether the store is open at a time specified by the user, who is assumed to be in the local time zone.</span></span>  

```csharp
using System;

public struct StoreInfo
{
   public String store;
   public TimeZoneInfo tz;
   public TimeSpan open;
   public TimeSpan close;

   public bool IsOpenNow()
   {
      return IsOpenAt(DateTime.TimeOfDay);
   }

   public bool IsOpenAt(TimeSpan time)
   {
      TimeZoneInfo local = TimeZoneInfo.Local;
      TimeSpan offset = TimeZoneInfo.BaseUtcOffset;

      // Is the store in the same time zone?
      if (tz.Equals(local)) {
         return time >= open & time <= close;
      }
   }
}
```

```vb
Public Structure StoreInfo
   Dim store As String
   Dim tz As TimeZoneInfo
   Dim open As TimeSpan
   Dim close As TimeSpan

   Public Function IsOpenNow() As Boolean
      Return IsOpenAt(Date.Now.TimeOfDay)
   End Function

   Public Function IsOpenAt(time As TimeSpan) As Boolean
      Dim local As TimeZoneInfo = TimeZoneInfo.Local
      Dim offset As TimeSpan = TimeZoneInfo.Local.BaseUtcOffset

      ' Is the store in the same time zone?
      If tz.Equals(local) Then
         Return time >= open And time <= close
      Else
         Dim delta As TimeSpan = TimeSpan.Zero
         Dim storeDelta As TimeSpan = TimeSpan.Zero

         ' Is it daylight saving time in either time zone?
         If local.IsDaylightSavingTime(Date.Now.Date + time) Then
            delta = local.GetAdjustmentRules(local.GetAdjustmentRules().Length - 1).DaylightDelta
         End If
         If tz.IsDaylightSavingTime(TimeZoneInfo.ConvertTime(Date.Now.Date + time, local, tz))
            storeDelta = tz.GetAdjustmentRules(local.GetAdjustmentRules().Length - 1).DaylightDelta
         End If
         Dim comparisonTime As TimeSpan = time + (offset - tz.BaseUtcOffset).Negate() + (delta - storeDelta).Negate
         Return (comparisonTime >= open And comparisonTime <= close)
      End If
   End Function
End Structure
```

<span data-ttu-id="34e7f-168">La struttura `StoreInfo` può quindi essere usata da codice client simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="34e7f-168">The `StoreInfo` structure can then be used by client code like the following.</span></span> 

```csharp
public class Example
{
   public static void Main()
   {
      // Instantiate a StoreInfo object.
      var store103 = new StoreInfo();
      store103.store = "Store #103";
      store103.tz = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time");
      // Store opens at 8:00.
      store103.open = new TimeSpan(8, 0, 0);
      // Store closes at 9:30.
      store103.close = new TimeSpan(21, 30, 0);

      Console.WriteLine("Store is open now at {0}: {1}",
                        DateTime.TimeOfDay, store103.IsOpenNow());
      TimeSpan[] times = { new TimeSpan(8, 0, 0), new TimeSpan(21, 0, 0),
                           new TimeSpan(4, 59, 0), new TimeSpan(18, 31, 0) };
      foreach (var time in times)
         Console.WriteLine("Store is open at {0}: {1}",
                           time, store103.IsOpenAt(time));
   }
}
// The example displays the following output:
//       Store is open now at 15:29:01.6129911: True
//       Store is open at 08:00:00: True
//       Store is open at 21:00:00: False
//       Store is open at 04:59:00: False
//       Store is open at 18:31:00: False
```

```vb
Module Example
   Public Sub Main()
      ' Instantiate a StoreInfo object.
      Dim store103 As New StoreInfo()
      store103.store = "Store #103"
      store103.tz = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time")
      ' Store opens at 8:00.
      store103.open = new TimeSpan(8, 0, 0)
      ' Store closes at 9:30.
      store103.close = new TimeSpan(21, 30, 0)

      Console.WriteLine("Store is open now at {0}: {1}",
                        Date.Now.TimeOfDay, store103.IsOpenNow())
      Dim times() As TimeSpan = { New TimeSpan(8, 0, 0),
                                  New TimeSpan(21, 0, 0),
                                  New TimeSpan(4, 59, 0),
                                  New TimeSpan(18, 31, 0) }
      For Each time In times
         Console.WriteLine("Store is open at {0}: {1}",
                           time, store103.IsOpenAt(time))
      Next
   End Sub
End Module
' The example displays the following output:
'       Store is open now at 15:29:01.6129911: True
'       Store is open at 08:00:00: True
'       Store is open at 21:00:00: False
'       Store is open at 04:59:00: False
'       Store is open at 18:31:00: False
```

## <a name="the-timezoneinfo-class"></a><span data-ttu-id="34e7f-169">Classe TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="34e7f-169">The TimeZoneInfo class</span></span>

<span data-ttu-id="34e7f-170">La classe [System.TimeZoneInfo](xref:System.TimeZoneInfo) rappresenta uno dei fusi orari della terra e consente la conversione di qualsiasi data e ora di un fuso orario negli equivalenti di un altro fuso orario.</span><span class="sxs-lookup"><span data-stu-id="34e7f-170">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class represents any of the earth's time zones, and enables the conversion of any date and time in one time zone to its equivalent in another time zone.</span></span> <span data-ttu-id="34e7f-171">La classe [TimeZoneInfo](xref:System.TimeZoneInfo) consente di usare date e ore in modo che qualsiasi valore di data e ora identifichi un singolo momento senza ambiguità.</span><span class="sxs-lookup"><span data-stu-id="34e7f-171">The [TimeZoneInfo](xref:System.TimeZoneInfo) class makes it possible to work with dates and times so that any date and time value unambiguously identifies a single point in time.</span></span>

<span data-ttu-id="34e7f-172">In alcuni casi, per sfruttare tutti i vantaggi della classe [TimeZoneInfo](xref:System.TimeZoneInfo) possono essere necessarie attività aggiuntive di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="34e7f-172">In some cases, taking full advantage of the [TimeZoneInfo](xref:System.TimeZoneInfo) class may require further development work.</span></span> <span data-ttu-id="34e7f-173">I valori di data e ora non sono strettamente collegati ai fusi orari cui appartengono.</span><span class="sxs-lookup"><span data-stu-id="34e7f-173">Date and time values are not tightly coupled with the time zones to which they belong.</span></span> <span data-ttu-id="34e7f-174">Di conseguenza, a meno che l'applicazione non fornisca un meccanismo per collegare una data e un'ora al fuso orario associato, è facile che una data e un'ora specifiche non risultino associate al rispettivo fuso orario.</span><span class="sxs-lookup"><span data-stu-id="34e7f-174">As a result, unless your application provides some mechanism for linking a date and time with its associated time zone, it is easy for a particular date and time value to become disassociated from its time zone.</span></span> <span data-ttu-id="34e7f-175">Un metodo per collegare queste informazioni consiste nel definire una classe o una struttura che contiene sia i valori di data e ora sia l'oggetto fuso orario associato.</span><span class="sxs-lookup"><span data-stu-id="34e7f-175">One method of linking this information is to define a class or structure that contains both the date and time value and its associated time zone object.</span></span>

<span data-ttu-id="34e7f-176">L'uso del supporto per i fusi orari in .NET è possibile solo se il fuso orario cui appartengono la data e l'ora è noto quando viene creata un'istanza dell'oggetto data e ora.</span><span class="sxs-lookup"><span data-stu-id="34e7f-176">Taking advantage of time zone support in .NET is possible only if the time zone to which a date and time value belongs is known when that date and time object is instantiated.</span></span> <span data-ttu-id="34e7f-177">Questo è un caso piuttosto raro, in particolare nelle applicazioni Web o di rete.</span><span class="sxs-lookup"><span data-stu-id="34e7f-177">This is often not the case, particularly in Web or network applications.</span></span>

## <a name="see-also"></a><span data-ttu-id="34e7f-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34e7f-178">See Also</span></span>

[<span data-ttu-id="34e7f-179">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="34e7f-179">Dates, times, and time zones</span></span>](index.md)

---
title: 'Procedura: Consentire agli utenti di risolvere orari ambigui'
description: Come consentire agli utenti di risolvere orari ambigui
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: d6858a5c-02ab-4367-9e08-fa22c051c38d
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: ede8d021a4f524cf37f7ad00b6aed89d1b1729f8
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-let-users-resolve-ambiguous-times"></a><span data-ttu-id="c98a4-104">Procedura: Consentire agli utenti di risolvere orari ambigui</span><span class="sxs-lookup"><span data-stu-id="c98a4-104">How to: let users resolve ambiguous times</span></span>

<span data-ttu-id="c98a4-105">Un'ora ambigua è un'ora associata a più ore UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="c98a4-105">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="c98a4-106">Si verifica quando l'orologio viene riportato indietro, ad esempio durante la transizione dall'ora legale all'ora solare di un determinato fuso orario.</span><span class="sxs-lookup"><span data-stu-id="c98a4-106">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="c98a4-107">Quando si gestisce un'ora ambigua è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c98a4-107">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="c98a4-108">Se l'ora ambigua è un elemento di dati immesso dall'utente, sarà l'utente a risolvere l'ambiguità.</span><span class="sxs-lookup"><span data-stu-id="c98a4-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

* <span data-ttu-id="c98a4-109">Fare una supposizione sulla modalità di associazione dell'ora all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="c98a4-109">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="c98a4-110">Si può, ad esempio, presupporre che un'ora ambigua sia sempre espressa nell'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="c98a4-110">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

<span data-ttu-id="c98a4-111">Questo articolo illustra come consentire a un utente di risolvere orari ambigui.</span><span class="sxs-lookup"><span data-stu-id="c98a4-111">This article shows how to let a user resolve an ambiguous time.</span></span>

## <a name="to-let-a-user-resolve-an-ambiguous-time"></a><span data-ttu-id="c98a4-112">Consentire a un utente di risolvere orari ambigui</span><span class="sxs-lookup"><span data-stu-id="c98a4-112">To let a user resolve an ambiguous time</span></span>

1. <span data-ttu-id="c98a4-113">Ottenere l'input di data e ora dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c98a4-113">Get the date and time input by the user.</span></span>

2. <span data-ttu-id="c98a4-114">Chiamare il metodo [IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) o [IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) per determinare se l'ora è ambigua.</span><span class="sxs-lookup"><span data-stu-id="c98a4-114">Call the [IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) or [IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) method to determine whether the time is ambiguous.</span></span>

3. <span data-ttu-id="c98a4-115">Consentire all'utente di selezionare l'offset desiderato.</span><span class="sxs-lookup"><span data-stu-id="c98a4-115">Let the user select the desired offset.</span></span>

4. <span data-ttu-id="c98a4-116">Ottenere la data e l'ora UTC sottraendo dall'ora locale l'offset selezionato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c98a4-116">Get the UTC date and time by subtracting the offset selected by the user from the local time.</span></span>

5. <span data-ttu-id="c98a4-117">Chiamare il metodo `static` (`Shared` in Visual Basic) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) per impostare la proprietà [Kind](xref:System.DateTime.Kind) del valore di data e ora UTC su [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span><span class="sxs-lookup"><span data-stu-id="c98a4-117">Call the `static` (`Shared` in Visual Basic ) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method to set the UTC date and time value's [Kind](xref:System.DateTime.Kind) property to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

## <a name="example"></a><span data-ttu-id="c98a4-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="c98a4-118">Example</span></span>

<span data-ttu-id="c98a4-119">Nell'esempio seguente si richiede all'utente di immettere una data e l'ora e, se è ambigua, si consente all'utente di selezionare l'ora UTC alla quale è associata l'ora ambigua.</span><span class="sxs-lookup"><span data-stu-id="c98a4-119">The following example prompts the user to enter a date and time and, if it is ambiguous, lets the user select the UTC time that the ambiguous time maps to.</span></span> <span data-ttu-id="c98a4-120">L'esempio usa un oggetto [DateTime](xref:System.DateTime). Se lo si vuole, è possibile sostituirlo con un oggetto [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="c98a4-120">The example uses a [DateTime](xref:System.DateTime) object; you can substitute a [DateTimeOffset](xref:System.DateTimeOffset) object if desired.</span></span>

```csharp
private void GetUserDateInput()
{
   // Get date and time from user
   DateTime inputDate = GetUserDateTime();
   DateTime utcDate;

   // Exit if date has no significant value
   if (inputDate == DateTime.MinValue) return;

   if (TimeZoneInfo.Local.IsAmbiguousTime(inputDate))
   {
      Console.WriteLine("The date you've entered is ambiguous.");
      Console.WriteLine("Please select the correct offset from Universal Coordinated Time:");
      TimeSpan[] offsets = TimeZoneInfo.Local.GetAmbiguousTimeOffsets(inputDate);
      for (int ctr = 0; ctr < offsets.Length; ctr++)
      {
         Console.WriteLine("{0}.) {1} hours, {2} minutes", ctr, offsets[ctr].Hours, offsets[ctr].Minutes);
      }
      Console.Write("> ");
      int selection = Convert.ToInt32(Console.ReadLine());

      // Convert local time to UTC, and set Kind property to DateTimeKind.Utc
      utcDate = DateTime.SpecifyKind(inputDate - offsets[selection], DateTimeKind.Utc);

      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString());
   }
   else
   {
      utcDate = inputDate.ToUniversalTime();
      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString());    
   }
}

private DateTime GetUserDateTime() 
{
   bool exitFlag = false;             // flag to exit loop if date is valid
   string dateString;  
   DateTime inputDate = DateTime.MinValue;

   Console.Write("Enter a local date and time: ");
   while (! exitFlag)
   {
      dateString = Console.ReadLine();
      if (dateString.ToUpper() == "E")
         exitFlag = true;

      if (DateTime.TryParse(dateString, out inputDate))
         exitFlag = true;
      else
         Console.Write("Enter a valid date and time, or enter 'e' to exit: ");
   }

   return inputDate;        
}
```

```vb
Private Sub GetUserDateInput()
   ' Get date and time from user
   Dim inputDate As Date = GetUserDateTime()
   Dim utcDate As Date

   ' Exit if date has no significant value
   If inputDate = Date.MinValue Then Exit Sub

   If TimeZoneInfo.Local.IsAmbiguousTime(inputDate) Then
      Console.WriteLine("The date you've entered is ambiguous.")
      Console.WriteLine("Please select the correct offset from Universal Coordinated Time:")
      Dim offsets() As TimeSpan = TimeZoneInfo.Local.GetAmbiguousTimeOffsets(inputDate)
      For ctr As Integer = 0 to offsets.Length - 1
         Dim zoneDescription As String
         If offsets(ctr).Equals(TimeZoneInfo.Local.BaseUtcOffset) Then 
            zoneDescription = TimeZoneInfo.Local.StandardName
         Else
            zoneDescription = TimeZoneInfo.Local.DaylightName
         End If
         Console.WriteLine("{0}.) {1} hours, {2} minutes ({3})", _
                           ctr, offsets(ctr).Hours, offsets(ctr).Minutes, zoneDescription)
      Next         
      Console.Write("> ")
      Dim selection As Integer = CInt(Console.ReadLine())

      ' Convert local time to UTC, and set Kind property to DateTimeKind.Utc
      utcDate = Date.SpecifyKind(inputDate - offsets(selection), DateTimeKind.Utc)

      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString())
   Else
      utcDate = inputDate.ToUniversalTime()
      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString())    
   End If
End Sub

Private Function GetUserDateTime() As Date
   Dim exitFlag As Boolean = False            ' flag to exit loop if date is valid
   Dim dateString As String 
   Dim inputDate As Date = Date.MinValue

   Console.Write("Enter a local date and time: ")
   Do While Not exitFlag
      dateString = Console.ReadLine()
      If dateString.ToUpper = "E" Then exitFlag = True
      If Date.TryParse(dateString, inputDate) Then
         exitFlag = true
      Else   
         Console.Write("Enter a valid date and time, or enter 'e' to exit: ")
      End If
   Loop

   Return inputDate        
End Function
```

<span data-ttu-id="c98a4-121">Il nucleo del codice di esempio usa una matrice di oggetti [TimeSpan](xref:System.TimeSpan) per indicare i possibili offset dell'ora ambigua dall'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="c98a4-121">The core of the example code uses an array of [TimeSpan](xref:System.TimeSpan) objects to indicate possible offsets of the ambiguous time from UTC.</span></span> <span data-ttu-id="c98a4-122">Tuttavia, questi offset probabilmente non sono significativi per l'utente.</span><span class="sxs-lookup"><span data-stu-id="c98a4-122">However, these offsets are unlikely to be meaningful to the user.</span></span> <span data-ttu-id="c98a4-123">Per chiarire il significato degli offset, il codice indica anche se un offset rappresenta l'ora solare o l'ora legale del fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="c98a4-123">To clarify the meaning of the offsets, the code also notes whether an offset represents the local time zone's standard time or its daylight saving time.</span></span> <span data-ttu-id="c98a4-124">Il codice determina quale sia l'ora solare e quale l'ora legale confrontando l'offset con il valore della proprietà [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset).</span><span class="sxs-lookup"><span data-stu-id="c98a4-124">The code determines which time is standard and which time is daylight by comparing the offset with the value of the [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property.</span></span> <span data-ttu-id="c98a4-125">Questa proprietà indica la differenza tra l'ora solare del fuso orario corrente e l'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="c98a4-125">This property indicates the difference between the UTC and the time zone's standard time.</span></span>

<span data-ttu-id="c98a4-126">In questo esempio, tutti i riferimenti al fuso orario locale vengono eseguiti mediante la proprietà [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local). Il fuso orario locale non viene mai assegnato a una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="c98a4-126">In this example, all references to the local time zone are made through the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="c98a4-127">Si tratta di una procedura consigliata in quanto un'altra chiamata può cancellare i dati memorizzati nella cache e invalidare tutti gli oggetti ai quali è assegnato il fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="c98a4-127">This is a recommended practice because another call could clear the cached data and invalidate any objects that the local time zone is assigned to.</span></span>

## <a name="see-also"></a><span data-ttu-id="c98a4-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c98a4-128">See Also</span></span>

[<span data-ttu-id="c98a4-129">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="c98a4-129">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="c98a4-130">Procedura: Risolvere orari ambigui</span><span class="sxs-lookup"><span data-stu-id="c98a4-130">How to: resolve ambiguous times</span></span>](resolve-ambiguous-times.md)



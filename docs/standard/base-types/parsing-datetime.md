---
title: Analisi di stringhe di data e ora in .NET
description: Analisi di stringhe di data e ora in .NET
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e61514cd-5329-4eb8-b122-482fffb54ab7
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f0131baa0874880b6697458426da5ae9ce1705b7
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-date-and-time-strings-in-net"></a><span data-ttu-id="38fec-104">Analisi di stringhe di data e ora in .NET</span><span class="sxs-lookup"><span data-stu-id="38fec-104">Parsing date and time strings in .NET</span></span>

<span data-ttu-id="38fec-105">I metodi di analisi consentono di convertire la rappresentazione di stringa di una data e un'ora in un oggetto [DateTime](xref:System.DateTime) equivalente.</span><span class="sxs-lookup"><span data-stu-id="38fec-105">Parsing methods convert the string representation of a date and time to an equivalent [DateTime](xref:System.DateTime) object.</span></span> <span data-ttu-id="38fec-106">I metodi [Parse](xref:System.DateTime.Parse(System.String)) e [TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) convertono qualsiasi rappresentazione di data e ora tra quelle usate comunemente.</span><span class="sxs-lookup"><span data-stu-id="38fec-106">The [Parse](xref:System.DateTime.Parse(System.String)) and [TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) methods convert any of several common representations of a date and time.</span></span> <span data-ttu-id="38fec-107">I metodi [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) e [TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)) convertono una rappresentazione di stringa conforme al criterio specificato da una stringa di formato di data e ora.</span><span class="sxs-lookup"><span data-stu-id="38fec-107">The [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) and [TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)) methods convert a string representation that conforms to the pattern specified by a date and time format string.</span></span> <span data-ttu-id="38fec-108">Vedere gli argomenti relativi alle [stringhe di formato di data e ora standard](standard-datetime.md) e alle [stringhe di formato di data e ora personalizzato](custom-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="38fec-108">(See the topics on [standard date and time format strings](standard-datetime.md) and [custom date and time format strings](custom-datetime.md).)</span></span> 

<span data-ttu-id="38fec-109">L'analisi è influenzata dalle proprietà di un provider di formato che rende disponibili informazioni quali le stringhe usate per i separatori di data e ora e i nomi di mesi, giorni ed ere.</span><span class="sxs-lookup"><span data-stu-id="38fec-109">Parsing is influenced by the properties of a format provider that supplies information such as the strings used for date and time separators, and the names of months, days, and eras.</span></span> <span data-ttu-id="38fec-110">Il provider di formato è l'oggetto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) corrente, che viene definito in modo implicito dalle impostazioni cultura del thread corrente o in modo esplicito dal parametro [IFormatProvider](xref:System.IFormatProvider) di un metodo di analisi.</span><span class="sxs-lookup"><span data-stu-id="38fec-110">The format provider is the current [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object, which is provided implicitly by the current thread culture or explicitly by the [IFormatProvider](xref:System.IFormatProvider) parameter of a parsing method.</span></span> <span data-ttu-id="38fec-111">Per il parametro [IFormatProvider](xref:System.IFormatProvider) specificare un oggetto [CultureInfo](xref:System.Globalization.CultureInfo), che rappresenta le impostazioni cultura, o un oggetto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo).</span><span class="sxs-lookup"><span data-stu-id="38fec-111">For the [IFormatProvider](xref:System.IFormatProvider) parameter, specify a [CultureInfo](xref:System.Globalization.CultureInfo) object, which represents a culture, or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object.</span></span> 

<span data-ttu-id="38fec-112">La rappresentazione di stringa di una data da analizzare deve includere il mese e almeno un giorno o anno.</span><span class="sxs-lookup"><span data-stu-id="38fec-112">The string representation of a date to be parsed must include the month and at least a day or year.</span></span> <span data-ttu-id="38fec-113">La rappresentazione di stringa di un'ora deve includere l'ora e almeno i minuti o l'indicazione AM/PM.</span><span class="sxs-lookup"><span data-stu-id="38fec-113">The string representation of a time must include the hour and at least minutes or the AM/PM designator.</span></span> <span data-ttu-id="38fec-114">Se possibile, tuttavia, l'analisi indica i valori predefiniti per i componenti omessi.</span><span class="sxs-lookup"><span data-stu-id="38fec-114">However, parsing supplies default values for omitted components if possible.</span></span> <span data-ttu-id="38fec-115">Per impostazione predefinita, per una data mancante viene indicata la data corrente, per un anno mancante viene indicato l'anno in corso, per un giorno del mese mancante viene indicato il primo giorno del mese e per un'ora mancante viene indicata la mezzanotte.</span><span class="sxs-lookup"><span data-stu-id="38fec-115">A missing date defaults to the current date, a missing year defaults to the current year, a missing day of the month defaults to the first day of the month, and a missing time defaults to midnight.</span></span> 

<span data-ttu-id="38fec-116">Se la rappresentazione di stringa specifica solo l'ora, l'analisi restituisce un oggetto [DateTime](xref:System.DateTime) con le relative proprietà [Year](xref:System.DateTime.Year), [Month](xref:System.DateTime.Month) e [Day](xref:System.DateTime.Day) impostate sui valori corrispondenti della proprietà [Today](xref:System.DateTime.Today).</span><span class="sxs-lookup"><span data-stu-id="38fec-116">If the string representation specifies only a time, parsing returns a [DateTime](xref:System.DateTime) object with its [Year](xref:System.DateTime.Year), [Month](xref:System.DateTime.Month), and [Day](xref:System.DateTime.Day) properties set to the corresponding values of the [Today](xref:System.DateTime.Today) property.</span></span> <span data-ttu-id="38fec-117">Tuttavia, se viene specificata la costante [NoCurrentDateDefault](xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault) nel metodo di analisi, le proprietà relative ad anno, mese e giorno vengono impostate sul valore 1.</span><span class="sxs-lookup"><span data-stu-id="38fec-117">However, if the [DateTimeStyles.NoCurrentDateDefault](xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault) constant is specified in the parsing method, the resulting year, month, and day properties are set to the value 1.</span></span>

<span data-ttu-id="38fec-118">Oltre a un componente di data e ora, la rappresentazione di stringa di una data e un'ora può includere un offset che indica in che misura l'ora differisce dall'ora UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="38fec-118">In addition to a date and a time component, the string representation of a date and time can include an offset that indicates how much the time differs from Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="38fec-119">Ad esempio, la stringa "2/14/2007 5:32:00 -7:00" definisce un'ora che precede di sette ore l'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="38fec-119">For example, the string "2/14/2007 5:32:00 -7:00" defines a time that is seven hours earlier than UTC.</span></span> <span data-ttu-id="38fec-120">Se viene omesso l'offset dalla rappresentazione di stringa di un'ora, l'analisi restituisce un oggetto [DateTime](xref:System.DateTime) con la relativa proprietà [Kind](xref:System.DateTime.Kind) impostata su [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span><span class="sxs-lookup"><span data-stu-id="38fec-120">If an offset is omitted from the string representation of a time, parsing returns a [DateTime](xref:System.DateTime) object with its [Kind](xref:System.DateTime.Kind) property set to [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span></span> <span data-ttu-id="38fec-121">Se viene specificato un offset, l'analisi restituisce un oggetto [DateTime](xref:System.DateTime) con la proprietà [Kind](xref:System.DateTime.Kind) impostata su [Local](xref:System.DateTimeKind.Local) e il relativo valore adeguato in base al fuso orario locale del computer.</span><span class="sxs-lookup"><span data-stu-id="38fec-121">If an offset is specified, parsing returns a [DateTime](xref:System.DateTime) object with its [Kind](xref:System.DateTime.Kind) property set to [Local](xref:System.DateTimeKind.Local) and its value adjusted to the local time zone of your machine.</span></span> <span data-ttu-id="38fec-122">È possibile modificare questo comportamento usando una costante [DateTimeStyles](xref:System.Globalization.DateTimeStyles) con il metodo di analisi.</span><span class="sxs-lookup"><span data-stu-id="38fec-122">You can modify this behavior by using a [DateTimeStyles](xref:System.Globalization.DateTimeStyles) constant with the parsing method.</span></span>

<span data-ttu-id="38fec-123">Il provider di formato viene usato anche per interpretare una data numerica ambigua.</span><span class="sxs-lookup"><span data-stu-id="38fec-123">The format provider is also used to interpret an ambiguous numeric date.</span></span> <span data-ttu-id="38fec-124">Ad esempio, non risulta chiaro quali componenti della data rappresentata dalla stringa "02/03/04" sono il mese, il giorno e l'anno.</span><span class="sxs-lookup"><span data-stu-id="38fec-124">For example, it is not clear which components of the date represented by the string "02/03/04" are the month, day, and year.</span></span> <span data-ttu-id="38fec-125">In questo caso i componenti vengono interpretati in base all'ordine dei formati di data simili nel provider di formato.</span><span class="sxs-lookup"><span data-stu-id="38fec-125">In this case, the components are interpreted according to the order of similar date formats in the format provider.</span></span> 

## <a name="parse"></a><span data-ttu-id="38fec-126">Parse</span><span class="sxs-lookup"><span data-stu-id="38fec-126">Parse</span></span>

<span data-ttu-id="38fec-127">L'esempio di codice seguente illustra l'uso del metodo `Parse` per convertire una stringa in un oggetto `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="38fec-127">The following code example illustrates the use of the `Parse` method to convert a string into a `DateTime`.</span></span> <span data-ttu-id="38fec-128">In questo esempio vengono usate le impostazioni cultura associate al thread corrente per eseguire l'analisi.</span><span class="sxs-lookup"><span data-stu-id="38fec-128">This example uses the culture associated with the current thread to perform the parse.</span></span> <span data-ttu-id="38fec-129">Se l'oggetto [CultureInfo](xref:System.Globalization.CultureInfo) associato alle impostazioni cultura correnti non è in grado di analizzare la stringa di input, viene generata un'eccezione [FormatException](xref:System.FormatException).</span><span class="sxs-lookup"><span data-stu-id="38fec-129">If the [CultureInfo](xref:System.Globalization.CultureInfo) associated with the current culture cannot parse the input string, a [FormatException](xref:System.FormatException) is thrown.</span></span>

```csharp
string MyString = "Jan 1, 2009";
DateTime MyDateTime = DateTime.Parse(MyString);
Console.WriteLine(MyDateTime);
// Displays the following output on a system whose culture is en-US:
//       1/1/2009 12:00:00 AM
```

```vb
Dim MyString As String = "Jan 1, 2009"
Dim MyDateTime As DateTime = DateTime.Parse(MyString)
Console.WriteLine(MyDateTime)
' Displays the following output on a system whose culture is en-US:
'       1/1/2009 12:00:00 AM
```

<span data-ttu-id="38fec-130">È anche possibile specificare un oggetto `CultureInfo` impostato su una delle impostazioni cultura definite da tale oggetto oppure specificare uno degli oggetti [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) standard restituiti dalla proprietà [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat).</span><span class="sxs-lookup"><span data-stu-id="38fec-130">You can also specify a `CultureInfo` set to one of the cultures defined by that object, or you can specify one of the standard [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) objects returned by the [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat) property.</span></span> <span data-ttu-id="38fec-131">L'esempio di codice seguente usa un provider di formato per analizzare una stringa in lingua tedesca in un `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="38fec-131">The following code example uses a format provider to parse a German string into a `DateTime`.</span></span> <span data-ttu-id="38fec-132">Un oggetto `CultureInfo` che rappresenta le impostazioni cultura de-DE viene definito e passato con la stringa da analizzare per garantire che tale stringa venga analizzata correttamente.</span><span class="sxs-lookup"><span data-stu-id="38fec-132">A `CultureInfo` representing the de-DE culture is defined and passed with the string being parsed to ensure successful parsing of this particular string.</span></span> <span data-ttu-id="38fec-133">Questo preclude qualsiasi impostazione in `CurrentCulture` di `CurrentThread`.</span><span class="sxs-lookup"><span data-stu-id="38fec-133">This precludes whatever setting is in the `CurrentCulture` of the `CurrentThread`.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("de-DE");
      string MyString = "12 Juni 2008";
      DateTime MyDateTime = DateTime.Parse(MyString, MyCultureInfo);
      Console.WriteLine(MyDateTime);
   }
}
// The example displays the following output:
//       6/12/2008 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("de-DE")
      Dim MyString As String = "12 Juni 2008"
      Dim MyDateTime As DateTime = DateTime.Parse(MyString, MyCultureInfo)
      Console.WriteLine(MyDateTime)
   End Sub
End Module
' The example displays the following output:
'       6/12/2008 12:00:00 AM
```

<span data-ttu-id="38fec-134">Tuttavia, sebbene sia possibile usare overload del metodo [Parse](xref:System.DateTime.Parse(System.String)) per specificare provider di formato personalizzati, il metodo non supporta l'uso di provider di formato non standard.</span><span class="sxs-lookup"><span data-stu-id="38fec-134">However, although you can use overloads of the [Parse](xref:System.DateTime.Parse(System.String)) method to specify custom format providers, the method does not support the use of non-standard format providers.</span></span> <span data-ttu-id="38fec-135">Per analizzare una data e un'ora espresse in un formato non standard, usare il metodo [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)).</span><span class="sxs-lookup"><span data-stu-id="38fec-135">To parse a date and time expressed in a non-standard format, use the [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) method instead.</span></span>

<span data-ttu-id="38fec-136">Nell'esempio di codice seguente viene usata l'enumerazione [DateTimeStyles](xref:System.Globalization.DateTimeStyles) per specificare che la data e l'ora correnti non devono essere aggiunte a `DateTime` per i campi che la stringa non definisce.</span><span class="sxs-lookup"><span data-stu-id="38fec-136">The following code example uses the [DateTimeStyles](xref:System.Globalization.DateTimeStyles) enumeration to specify that the current date and time information should not be added to the `DateTime` for fields that the string does not define.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("de-DE");
      string MyString = "12 Juni 2008";
      DateTime MyDateTime = DateTime.Parse(MyString, MyCultureInfo, 
                                           DateTimeStyles.NoCurrentDateDefault);
      Console.WriteLine(MyDateTime);
   }
}
// The example displays the following output if the current culture is en-US:
//      6/12/2008 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("de-DE")
      Dim MyString As String = "12 Juni 2008"
      Dim MyDateTime As DateTime = DateTime.Parse(MyString, MyCultureInfo)
      Console.WriteLine(MyDateTime)
   End Sub
End Module
' The example displays the following output:
'       6/12/2008 12:00:00 AM
```

## <a name="parseexact"></a><span data-ttu-id="38fec-137">ParseExact</span><span class="sxs-lookup"><span data-stu-id="38fec-137">ParseExact</span></span>

<span data-ttu-id="38fec-138">Il metodo [DateTime.ParseExact]((xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) converte una stringa conforme a un modello di stringa specificato in un oggetto `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="38fec-138">The [DateTime.ParseExact]((xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) method converts a string that conforms to a specified string pattern to a `DateTime` object.</span></span> <span data-ttu-id="38fec-139">Quando una stringa che non è nel formato specificato viene passata a questo metodo, viene generata un'eccezione [FormatException](xref:System.FormatException).</span><span class="sxs-lookup"><span data-stu-id="38fec-139">When a string that is not of the form specified is passed to this method, a [FormatException](xref:System.FormatException) is thrown.</span></span> <span data-ttu-id="38fec-140">È possibile specificare uno degli identificatori di formato di data e ora standard o una combinazione limitata degli identificatori di formato di data e ora personalizzato.</span><span class="sxs-lookup"><span data-stu-id="38fec-140">You can specify one of the standard date and time format specifiers or a limited combination of the custom date and time format specifiers.</span></span> <span data-ttu-id="38fec-141">Usando gli identificatori di formato personalizzato è possibile costruire una stringa di riconoscimento personalizzata.</span><span class="sxs-lookup"><span data-stu-id="38fec-141">Using the custom format specifiers, it is possible for you to construct a custom recognition string.</span></span> <span data-ttu-id="38fec-142">Per una spiegazione degli identificatori, vedere gli argomenti relativi alle [stringhe di formato di data e ora standard](standard-datetime.md) e alle [stringhe di formato di data e ora personalizzato](custom-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="38fec-142">For an explanation of the specifiers, see the topics on [standard date and time format strings](standard-datetime.md) and [custom date and time format strings](custom-datetime.md).</span></span> 

<span data-ttu-id="38fec-143">Ogni overload del metodo [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) usa anche un parametro [IFormatProvider](xref:System.IFormatProvider) che in genere indica informazioni specifiche delle impostazioni cultura sulla formattazione della stringa.</span><span class="sxs-lookup"><span data-stu-id="38fec-143">Each overload of the [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) method also has an [IFormatProvider](xref:System.IFormatProvider) parameter that typically provides culture-specific information about the formatting of the string.</span></span> <span data-ttu-id="38fec-144">In genere, questo oggetto [IFormatProvider](xref:System.IFormatProvider) è un oggetto [CultureInfo](xref:System.Globalization.CultureInfo) che rappresenta le impostazioni cultura standard o un oggetto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) restituito dalla proprietà [DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat).</span><span class="sxs-lookup"><span data-stu-id="38fec-144">Typically, this [IFormatProvider](xref:System.IFormatProvider) object is a [CultureInfo](xref:System.Globalization.CultureInfo) object that represents a standard culture or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that is returned by the [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat) property.</span></span> <span data-ttu-id="38fec-145">Tuttavia, a differenza di altre funzioni di analisi di data e ora, questo metodo supporta anche un oggetto [IFormatProvider](xref:System.IFormatProvider) che definisce un formato di data e ora non standard.</span><span class="sxs-lookup"><span data-stu-id="38fec-145">However, unlike the other date and time parsing functions, this method also supports an [IFormatProvider](xref:System.IFormatProvider) that defines a non-standard date and time format.</span></span> 

<span data-ttu-id="38fec-146">Nell'esempio di codice seguente, al metodo `ParseExact` viene passato un oggetto stringa da analizzare, seguito da un identificatore di formato, seguito da un oggetto `CultureInfo`.</span><span class="sxs-lookup"><span data-stu-id="38fec-146">In the following code example, the `ParseExact` method is passed a string object to parse, followed by a format specifier, followed by a `CultureInfo` object.</span></span> <span data-ttu-id="38fec-147">Questo metodo `ParseExact` consente di analizzare solo le stringhe con il modello di data estesa nelle impostazioni cultura en-US.</span><span class="sxs-lookup"><span data-stu-id="38fec-147">This `ParseExact` method can only parse strings that exhibit the long date pattern in the en-US culture.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("en-US");
      string[] MyString = {" Friday, April 10, 2009", "Friday, April 10, 2009"};
      foreach (string dateString in MyString)
      {
         try {
            DateTime MyDateTime = DateTime.ParseExact(dateString, "D", MyCultureInfo);
            Console.WriteLine(MyDateTime);
         }
         catch (FormatException) {
            Console.WriteLine("Unable to parse '{0}'", dateString);
         }
      }
   }
}
// The example displays the following output:
//       Unable to parse ' Friday, April 10, 2009'
//       4/10/2009 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("en-US")
      Dim MyString() As String = {" Friday, April 10, 2009", "Friday, April 10, 2009"}
      For Each dateString As String In MyString
         Try
            Dim MyDateTime As DateTime = DateTime.ParseExact(dateString, "D", _
                                                             MyCultureInfo)
            Console.WriteLine(MyDateTime)
         Catch e As FormatException
            Console.WriteLine("Unable to parse '{0}'", dateString)
         End Try
      Next
   End Sub
End Module
' The example displays the following output:
'       Unable to parse ' Friday, April 10, 2009'
'       4/10/2009 12:00:00 AM
```

## <a name="see-also"></a><span data-ttu-id="38fec-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38fec-148">See Also</span></span>

[<span data-ttu-id="38fec-149">Analisi di stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="38fec-149">Parsing strings in .NET</span></span>](parsing-strings.md)

[<span data-ttu-id="38fec-150">Formattazione di tipi in .NET</span><span class="sxs-lookup"><span data-stu-id="38fec-150">Formatting types in .NET</span></span>](formatting-types.md)

[<span data-ttu-id="38fec-151">Conversione di tipi in .NET</span><span class="sxs-lookup"><span data-stu-id="38fec-151">Type conversion in .NET</span></span>](type-conversion.md)



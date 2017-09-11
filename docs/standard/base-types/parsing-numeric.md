---
title: Analisi di stringhe numeriche in .NET
description: Analisi di stringhe numeriche in .NET
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e393430a-731a-49fa-83de-ff7ed52d5704
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 85cd57d33b03f7a2105ee3f770b2f8bcc0a57ee4
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-numeric-strings-in-net"></a><span data-ttu-id="a7331-104">Analisi di stringhe numeriche in .NET</span><span class="sxs-lookup"><span data-stu-id="a7331-104">Parsing numeric strings in .NET</span></span>

<span data-ttu-id="a7331-105">Tutti i tipi numerici hanno due metodi di analisi statici, `Parse` e `TryParse`, che è possibile usare per convertire la rappresentazione di stringa di un numero in un tipo numerico.</span><span class="sxs-lookup"><span data-stu-id="a7331-105">All numeric types have two static parsing methods, `Parse` and `TryParse`, that you can use to convert the string representation of a number into a numeric type.</span></span> <span data-ttu-id="a7331-106">Tali metodi consentono di analizzare le stringhe generate usando le stringhe di formato documentate in [Stringhe di formato numerico standard](standard-numeric.md) e [Stringhe di formato numerico personalizzato](custom-numeric.md).</span><span class="sxs-lookup"><span data-stu-id="a7331-106">These methods enable you to parse strings that were produced by using the format strings documented in [Standard Numeric Format Strings](standard-numeric.md) and [Custom Numeric Format Strings](custom-numeric.md).</span></span> <span data-ttu-id="a7331-107">Per impostazione predefinita, i metodi `Parse` e `TryParse` consentono di convertire correttamente le stringhe contenenti cifre decimali integrali solo in valori integer.</span><span class="sxs-lookup"><span data-stu-id="a7331-107">By default, the `Parse` and `TryParse` methods can successfully convert strings that contain integral decimal digits only to integer values.</span></span> <span data-ttu-id="a7331-108">Consentono di convertire correttamente le stringhe che contengono cifre decimali integrali e frazionarie, separatori di gruppi e un separatore decimale in valori a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="a7331-108">They can successfully convert strings that contain integral and fractional decimal digits, group separators, and a decimal separator to floating-point values.</span></span> <span data-ttu-id="a7331-109">Il metodo `Parse` genera un'eccezione se l'operazione ha esito negativo, mentre il metodo `TryParse` restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="a7331-109">The `Parse` method throws an exception if the operation fails, whereas the `TryParse` method returns `false`.</span></span>

## <a name="parsing-and-format-providers"></a><span data-ttu-id="a7331-110">Analisi e provider di formato</span><span class="sxs-lookup"><span data-stu-id="a7331-110">Parsing and format providers</span></span>

<span data-ttu-id="a7331-111">In genere, le rappresentazioni di stringa dei valori numerici differiscono in base alle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="a7331-111">Typically, the string representations of numeric values differ by culture.</span></span> <span data-ttu-id="a7331-112">Gli elementi delle stringhe numeriche, ad esempio simboli di valuta, separatori di gruppi (o migliaia) e separatori decimali, variano in base alle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="a7331-112">Elements of numeric strings such as currency symbols, group (or thousands) separators, and decimal separators all vary by culture.</span></span> <span data-ttu-id="a7331-113">I metodi di analisi usano in modo implicito o esplicito un provider di formato che riconosce le variazioni specifiche delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="a7331-113">Parsing methods either implicitly or explicitly use a format provider that recognizes these culture-specific variations.</span></span> <span data-ttu-id="a7331-114">Se non viene specificato alcun provider di formato in una chiamata al metodo `Parse` o `TryParse`, viene usato il provider di formato associato alle impostazioni cultura del thread corrente, ossia l'oggetto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) restituito dalla proprietà [NumberFormatInfo.CurrentInfo](xref:System.Globalization.NumberFormatInfo.CurrentInfo).</span><span class="sxs-lookup"><span data-stu-id="a7331-114">If no format provider is specified in a call to the `Parse` or `TryParse` method, the format provider associated with the current thread culture (the [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object returned by the [NumberFormatInfo.CurrentInfo](xref:System.Globalization.NumberFormatInfo.CurrentInfo) property) is used.</span></span> 

<span data-ttu-id="a7331-115">Un provider di formato è rappresentato da un'implementazione [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo).</span><span class="sxs-lookup"><span data-stu-id="a7331-115">A format provider is represented by an [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) implementation.</span></span> <span data-ttu-id="a7331-116">Questa interfaccia ha un singolo membro, il metodo [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)), il cui unico parametro è un oggetto [Type](xref:System.Type) che rappresenta il tipo da formattare.</span><span class="sxs-lookup"><span data-stu-id="a7331-116">This interface has a single member, the [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method, whose single parameter is a [Type](xref:System.Type) object that represents the type to be formatted.</span></span> <span data-ttu-id="a7331-117">Questo metodo restituisce l'oggetto che fornisce le informazioni di formattazione.</span><span class="sxs-lookup"><span data-stu-id="a7331-117">This method returns the object that provides formatting information.</span></span> <span data-ttu-id="a7331-118">.NET supporta le due implementazioni [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) seguenti per l'analisi di stringhe numeriche:</span><span class="sxs-lookup"><span data-stu-id="a7331-118">.NET supports the following two [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) implementations for parsing numeric strings:</span></span>

* <span data-ttu-id="a7331-119">Un oggetto [CultureInfo](xref:System.Globalization.CultureInfo) il cui metodo [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) restituisce un oggetto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) con informazioni di formattazione specifiche delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="a7331-119">A [CultureInfo](xref:System.Globalization.CultureInfo) object whose [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) method returns a [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object that provides culture-specific formatting information.</span></span>

* <span data-ttu-id="a7331-120">Un oggetto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) il cui metodo [NumberFormatInfo.GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) restituisce se stesso.</span><span class="sxs-lookup"><span data-stu-id="a7331-120">A [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object whose [NumberFormatInfo.GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) method returns itself.</span></span>

<span data-ttu-id="a7331-121">Nell'esempio seguente si tenta di convertire ogni stringa in una matrice in un valore [Double](xref:System.Double).</span><span class="sxs-lookup"><span data-stu-id="a7331-121">The following example tries to convert each string in an array to a [Double](xref:System.Double) value.</span></span> <span data-ttu-id="a7331-122">Per prima cosa si tenta di analizzare la stringa usando un provider di formato che riflette le convenzioni delle impostazioni cultura Inglese (Stati Uniti).</span><span class="sxs-lookup"><span data-stu-id="a7331-122">It first tries to parse the string by using a format provider that reflects the conventions of the English (United States) culture.</span></span> <span data-ttu-id="a7331-123">Se questa operazione genera un'eccezione [FormatException](xref:System.FormatException), si tenta di analizzare la stringa usando un provider di formato che riflette le convenzioni delle impostazioni cultura Francese (Francia).</span><span class="sxs-lookup"><span data-stu-id="a7331-123">If this operation throws a [FormatException](xref:System.FormatException), it tries to parse the string by using a format provider that reflects the conventions of the French (France) culture.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string[] values = { "1,304.16", "$1,456.78", "1,094", "152", 
                          "123,45 €", "1 304,16", "Ae9f" };
      double number;
      CultureInfo culture = null;

      foreach (string value in values) {
         try {
            culture = CultureInfo.CreateSpecificCulture("en-US");
            number = Double.Parse(value, culture);
            Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number);
         }   
         catch (FormatException) {
            Console.WriteLine("{0}: Unable to parse '{1}'.", 
                              culture.Name, value);
            culture = CultureInfo.CreateSpecificCulture("fr-FR");
            try {
               number = Double.Parse(value, culture);
               Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number);
            }
            catch (FormatException) {
               Console.WriteLine("{0}: Unable to parse '{1}'.", 
                                 culture.Name, value);
            }
         }
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//    en-US: 1,304.16 --> 1304.16
//    
//    en-US: Unable to parse '$1,456.78'.
//    fr-FR: Unable to parse '$1,456.78'.
//    
//    en-US: 1,094 --> 1094
//    
//    en-US: 152 --> 152
//    
//    en-US: Unable to parse '123,45 €'.
//    fr-FR: Unable to parse '123,45 €'.
//    
//    en-US: Unable to parse '1 304,16'.
//    fr-FR: 1 304,16 --> 1304.16
//    
//    en-US: Unable to parse 'Ae9f'.
//    fr-FR: Unable to parse 'Ae9f'.
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim values() As String = { "1,304.16", "$1,456.78", "1,094", "152", 
                                 "123,45 €", "1 304,16", "Ae9f" }
      Dim number As Double
      Dim culture As CultureInfo = Nothing

      For Each value As String In values
         Try
            culture = CultureInfo.CreateSpecificCulture("en-US")
            number = Double.Parse(value, culture)
            Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number)
         Catch e As FormatException
            Console.WriteLine("{0}: Unable to parse '{1}'.", 
                              culture.Name, value)
            culture = CultureInfo.CreateSpecificCulture("fr-FR")
            Try
               number = Double.Parse(value, culture)
               Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number)
            Catch ex As FormatException
               Console.WriteLine("{0}: Unable to parse '{1}'.", 
                                 culture.Name, value)
            End Try
         End Try
         Console.WriteLine()
      Next
   End Sub
End Module
' The example displays the following output:
'    en-US: 1,304.16 --> 1304.16
'    
'    en-US: Unable to parse '$1,456.78'.
'    fr-FR: Unable to parse '$1,456.78'.
'    
'    en-US: 1,094 --> 1094
'    
'    en-US: 152 --> 152
'    
'    en-US: Unable to parse '123,45 €'.
'    fr-FR: Unable to parse '123,45 €'.
'    
'    en-US: Unable to parse '1 304,16'.
'    fr-FR: 1 304,16 --> 1304.16
'    
'    en-US: Unable to parse 'Ae9f'.
'    fr-FR: Unable to parse 'Ae9f'.
```

## <a name="parsing-and-numberstyles-values"></a><span data-ttu-id="a7331-124">Analisi e valori NumberStyles</span><span class="sxs-lookup"><span data-stu-id="a7331-124">Parsing and NumberStyles values</span></span>

<span data-ttu-id="a7331-125">Gli elementi di stile, ad esempio spazi vuoti, separatori di gruppi e separatore decimale, che l'operazione di analisi è in grado di gestire sono definiti da un valore di enumerazione [NumberStyles](xref:System.Globalization.NumberStyles).</span><span class="sxs-lookup"><span data-stu-id="a7331-125">The style elements (such as white space, group separators, and decimal separator) that the parse operation can handle are defined by a [NumberStyles](xref:System.Globalization.NumberStyles) enumeration value.</span></span> <span data-ttu-id="a7331-126">Per impostazione predefinita, le stringhe che rappresentano i valori integer vengono analizzate usando il valore [NumberStyles.Integer](xref:System.Globalization.NumberStyles.Integer), che consente solo cifre numeriche, spazi vuoti iniziali e finali e un segno iniziale.</span><span class="sxs-lookup"><span data-stu-id="a7331-126">By default, strings that represent integer values are parsed by using the [NumberStyles.Integer](xref:System.Globalization.NumberStyles.Integer) value, which permits only numeric digits, leading and trailing white space, and a leading sign.</span></span> <span data-ttu-id="a7331-127">Le stringhe che rappresentano valori a virgola mobile vengono analizzate usando una combinazione dei valori [NumberStyles.Float](xref:System.Globalization.NumberStyles.Float) e [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands). Questo stile composto consente cifre decimali con spazi vuoti iniziali e finali, un segno iniziale, un separatore decimale, un separatore di gruppi e un esponente.</span><span class="sxs-lookup"><span data-stu-id="a7331-127">Strings that represent floating-point values are parsed using a combination of the [NumberStyles.Float](xref:System.Globalization.NumberStyles.Float) and [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) values; this composite style permits decimal digits along with leading and trailing white space, a leading sign, a decimal separator, a group separator, and an exponent.</span></span> <span data-ttu-id="a7331-128">Chiamando un overload del metodo `Parse` o `TryParse` che include un parametro di tipo [NumberStyles](xref:System.Globalization.NumberStyles) e impostando uno o più flag [NumberStyles](xref:System.Globalization.NumberStyles), è possibile stabilire quali elementi di stile possono essere presenti nella stringa per fare in modo che l'operazione di analisi abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a7331-128">By calling an overload of the `Parse` or `TryParse` method that includes a parameter of type [NumberStyles](xref:System.Globalization.NumberStyles) and setting one or more [NumberStyles](xref:System.Globalization.NumberStyles) flags, you can control the style elements that can be present in the string for the parse operation to succeed.</span></span> 

<span data-ttu-id="a7331-129">Ad esempio, una stringa contenente un separatore di gruppo non può essere convertita in un valore [Int32](xref:System.Int32) usando il metodo [Int32.Parse(String)](xref:System.Int32.Parse(System.String)).</span><span class="sxs-lookup"><span data-stu-id="a7331-129">For example, a string that contains a group separator cannot be converted to an [Int32](xref:System.Int32) value by using the [Int32.Parse(String)](xref:System.Int32.Parse(System.String)) method.</span></span> <span data-ttu-id="a7331-130">Tuttavia, la conversione viene completata correttamente se si utilizza il flag [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands), come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a7331-130">However, the conversion succeeds if you use the [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) flag, as the following example illustrates.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string value = "1,304";
      int number;
      IFormatProvider provider = CultureInfo.CreateSpecificCulture("en-US");
      if (Int32.TryParse(value, out number))
         Console.WriteLine("{0} --> {1}", value, number);
      else
         Console.WriteLine("Unable to convert '{0}'", value);

      if (Int32.TryParse(value, NumberStyles.Integer | NumberStyles.AllowThousands, 
                        provider, out number))
         Console.WriteLine("{0} --> {1}", value, number);
      else
         Console.WriteLine("Unable to convert '{0}'", value);
   }
}
// The example displays the following output:
//       Unable to convert '1,304'
//       1,304 --> 1304
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim value As String = "1,304"
      Dim number As Integer
      Dim provider As IFormatProvider = CultureInfo.CreateSpecificCulture("en-US")
      If Int32.TryParse(value, number) Then
         Console.WriteLine("{0} --> {1}", value, number)
      Else
         Console.WriteLine("Unable to convert '{0}'", value)
      End If

      If Int32.TryParse(value, NumberStyles.Integer Or NumberStyles.AllowThousands, 
                        provider, number) Then
         Console.WriteLine("{0} --> {1}", value, number)
      Else
         Console.WriteLine("Unable to convert '{0}'", value)
      End If
   End Sub
End Module
' The example displays the following output:
'       Unable to convert '1,304'
'       1,304 --> 1304
```

> <span data-ttu-id="a7331-131">**Avviso**</span><span class="sxs-lookup"><span data-stu-id="a7331-131">**Warning**</span></span>
>
> <span data-ttu-id="a7331-132">L'operazione di analisi usa sempre le convenzioni di formattazione di determinate impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="a7331-132">The parse operation always uses the formatting conventions of a particular culture.</span></span> <span data-ttu-id="a7331-133">Se non si specificano le impostazioni cultura passando un oggetto [CultureInfo](xref:System.Globalization.CultureInfo) o [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), vengono usate le impostazioni cultura associate al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="a7331-133">If you do not specify a culture by passing a [CultureInfo](xref:System.Globalization.CultureInfo) or [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object, the culture associated with the current thread is used.</span></span>
 
<span data-ttu-id="a7331-134">Nella tabella seguente sono elencati i membri dell'enumerazione [NumberStyles](xref:System.Globalization.NumberStyles) e viene descritto l'effetto degli stessi sull'operazione di analisi.</span><span class="sxs-lookup"><span data-stu-id="a7331-134">The following table lists the members of the [NumberStyles](xref:System.Globalization.NumberStyles) enumeration and describes the effect that they have on the parsing operation.</span></span>

<span data-ttu-id="a7331-135">Valore NumberStyles</span><span class="sxs-lookup"><span data-stu-id="a7331-135">NumberStyles value</span></span> | <span data-ttu-id="a7331-136">Effetto sulla stringa da analizzare</span><span class="sxs-lookup"><span data-stu-id="a7331-136">Effect on the string to be parsed</span></span>
------------------ | --------------------------------- 
[<span data-ttu-id="a7331-137">NumberStyles.None</span><span class="sxs-lookup"><span data-stu-id="a7331-137">NumberStyles.None</span></span>](xref:System.Globalization.NumberStyles.None) | <span data-ttu-id="a7331-138">Sono consentiti solo valori numerici.</span><span class="sxs-lookup"><span data-stu-id="a7331-138">Only numeric digits are permitted.</span></span>
[<span data-ttu-id="a7331-139">NumberStyles.AllowDecimalPoint</span><span class="sxs-lookup"><span data-stu-id="a7331-139">NumberStyles.AllowDecimalPoint</span></span>](xref:System.Globalization.NumberStyles.AllowDecimalPoint) | <span data-ttu-id="a7331-140">Sono consentiti il separatore decimale e i numeri frazionari.</span><span class="sxs-lookup"><span data-stu-id="a7331-140">The decimal separator and fractional digits are permitted.</span></span> <span data-ttu-id="a7331-141">Per i valori integer è consentito solo lo zero come numero frazionario.</span><span class="sxs-lookup"><span data-stu-id="a7331-141">For integer values, only zero is permitted as a fractional digit.</span></span> <span data-ttu-id="a7331-142">I separatori decimali validi sono determinati dalla proprietà [NumberFormatInfo.NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) o [NumberFormatInfo.CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator).</span><span class="sxs-lookup"><span data-stu-id="a7331-142">Valid decimal separators are determined by the [NumberFormatInfo.NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) or [NumberFormatInfo.CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) property.</span></span>
[<span data-ttu-id="a7331-143">NumberStyles.AllowExponent</span><span class="sxs-lookup"><span data-stu-id="a7331-143">NumberStyles.AllowExponent</span></span>](xref:System.Globalization.NumberStyles.AllowExponent) | <span data-ttu-id="a7331-144">Il carattere "e" o "E" può essere usato per indicare la notazione esponenziale.</span><span class="sxs-lookup"><span data-stu-id="a7331-144">The "e" or "E" character can be used to indicate exponential notation.</span></span>
[<span data-ttu-id="a7331-145">NumberStyles.AllowLeadingWhite</span><span class="sxs-lookup"><span data-stu-id="a7331-145">NumberStyles.AllowLeadingWhite</span></span>](xref:System.Globalization.NumberStyles.AllowLeadingWhite) | <span data-ttu-id="a7331-146">È consentito lo spazio vuoto iniziale.</span><span class="sxs-lookup"><span data-stu-id="a7331-146">Leading white space is permitted.</span></span>
[<span data-ttu-id="a7331-147">NumberStyles.AllowTrailingWhite</span><span class="sxs-lookup"><span data-stu-id="a7331-147">NumberStyles.AllowTrailingWhite</span></span>](xref:System.Globalization.NumberStyles.AllowTrailingWhite) | <span data-ttu-id="a7331-148">È consentito lo spazio vuoto finale.</span><span class="sxs-lookup"><span data-stu-id="a7331-148">Trailing white space is permitted.</span></span>
[<span data-ttu-id="a7331-149">NumberStyles.AllowLeadingSign</span><span class="sxs-lookup"><span data-stu-id="a7331-149">NumberStyles.AllowLeadingSign</span></span>](xref:System.Globalization.NumberStyles.AllowLeadingSign) | <span data-ttu-id="a7331-150">Un segno positivo o negativo può precedere le cifre numeriche.</span><span class="sxs-lookup"><span data-stu-id="a7331-150">A positive or negative sign can precede numeric digits.</span></span>
[<span data-ttu-id="a7331-151">NumberStyles.AllowTrailingSign</span><span class="sxs-lookup"><span data-stu-id="a7331-151">NumberStyles.AllowTrailingSign</span></span>](xref:System.Globalization.NumberStyles.AllowTrailingSign) | <span data-ttu-id="a7331-152">Un segno positivo o negativo può seguire le cifre numeriche.</span><span class="sxs-lookup"><span data-stu-id="a7331-152">A positive or negative sign can follow numeric digits.</span></span>
[<span data-ttu-id="a7331-153">NumberStyles.AllowParentheses</span><span class="sxs-lookup"><span data-stu-id="a7331-153">NumberStyles.AllowParentheses</span></span>](xref:System.Globalization.NumberStyles.AllowParentheses) | <span data-ttu-id="a7331-154">Si possono usare parentesi per indicare i valori negativi.</span><span class="sxs-lookup"><span data-stu-id="a7331-154">Parentheses can be used to indicate negative values.</span></span>
[<span data-ttu-id="a7331-155">NumberStyles.AllowThousands</span><span class="sxs-lookup"><span data-stu-id="a7331-155">NumberStyles.AllowThousands</span></span>](xref:System.Globalization.NumberStyles.AllowThousands) | <span data-ttu-id="a7331-156">È consentito il separatore di gruppi.</span><span class="sxs-lookup"><span data-stu-id="a7331-156">The group separator is permitted.</span></span> <span data-ttu-id="a7331-157">Il carattere separatore di gruppi è determinato dalla proprietà [NumberFormatInfo.NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) o [NumberFormatInfo.CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator).</span><span class="sxs-lookup"><span data-stu-id="a7331-157">The group separator character is determined by the [NumberFormatInfo.NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) or [NumberFormatInfo.CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) property.</span></span>
[<span data-ttu-id="a7331-158">NumberStyles.AllowCurrencySymbol</span><span class="sxs-lookup"><span data-stu-id="a7331-158">NumberStyles.AllowCurrencySymbol</span></span>](xref:System.Globalization.NumberStyles.AllowCurrencySymbol) | <span data-ttu-id="a7331-159">È consentito il simbolo di valuta.</span><span class="sxs-lookup"><span data-stu-id="a7331-159">The currency symbol is permitted.</span></span> <span data-ttu-id="a7331-160">Il simbolo di valuta è definito dalla proprietà [NumberFormatInfo.CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol).</span><span class="sxs-lookup"><span data-stu-id="a7331-160">The currency symbol is defined by the [NumberFormatInfo.CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) property.</span></span>
[<span data-ttu-id="a7331-161">NumberStyles.AllowHexSpecifier</span><span class="sxs-lookup"><span data-stu-id="a7331-161">NumberStyles.AllowHexSpecifier</span></span>](xref:System.Globalization.NumberStyles.AllowHexSpecifier) | <span data-ttu-id="a7331-162">La stringa da analizzare viene interpretata come numero esadecimale.</span><span class="sxs-lookup"><span data-stu-id="a7331-162">The string to be parsed is interpreted as a hexadecimal number.</span></span> <span data-ttu-id="a7331-163">Può includere le cifre esadecimali 0-9, A-F e a-f.</span><span class="sxs-lookup"><span data-stu-id="a7331-163">It can include the hexadecimal digits 0-9, A-F, and a-f.</span></span> <span data-ttu-id="a7331-164">Questo flag può essere usato solo per analizzare i valori integer.</span><span class="sxs-lookup"><span data-stu-id="a7331-164">This flag can be used only to parse integer values.</span></span>
 
<span data-ttu-id="a7331-165">L'enumerazione [NumberStyles](xref:System.Globalization.NumberStyles) usa anche i seguenti stili compositi, che includono più flag [NumberStyles](xref:System.Globalization.NumberStyles).</span><span class="sxs-lookup"><span data-stu-id="a7331-165">In addition, the [NumberStyles](xref:System.Globalization.NumberStyles) enumeration provides the following composite styles, which include multiple [NumberStyles](xref:System.Globalization.NumberStyles) flags.</span></span> 

<span data-ttu-id="a7331-166">Valore composito NumberStyles</span><span class="sxs-lookup"><span data-stu-id="a7331-166">Composite NumberStyles value</span></span> | <span data-ttu-id="a7331-167">Include i membri</span><span class="sxs-lookup"><span data-stu-id="a7331-167">Includes members</span></span>
---------------------------- | ---------------- 
[<span data-ttu-id="a7331-168">NumberStyles.Integer</span><span class="sxs-lookup"><span data-stu-id="a7331-168">NumberStyles.Integer</span></span>](xref:System.Globalization.NumberStyles.Integer) | <span data-ttu-id="a7331-169">Include gli stili [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) e [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign).</span><span class="sxs-lookup"><span data-stu-id="a7331-169">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), and [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign) styles.</span></span> <span data-ttu-id="a7331-170">Questo è lo stile predefinito usato per analizzare i valori integer.</span><span class="sxs-lookup"><span data-stu-id="a7331-170">This is the default style used to parse integer values.</span></span>
[<span data-ttu-id="a7331-171">NumberStyles.Number</span><span class="sxs-lookup"><span data-stu-id="a7331-171">NumberStyles.Number</span></span>](xref:System.Globalization.NumberStyles.Number) | <span data-ttu-id="a7331-172">Include gli stili [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowTrailingSign](xref:System.Globalization.NumberStyles.AllowTrailingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) e [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands).</span><span class="sxs-lookup"><span data-stu-id="a7331-172">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowTrailingSign](xref:System.Globalization.NumberStyles.AllowTrailingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint), and [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) styles.</span></span>
[<span data-ttu-id="a7331-173">NumberStyles.Float</span><span class="sxs-lookup"><span data-stu-id="a7331-173">NumberStyles.Float</span></span>](xref:System.Globalization.NumberStyles.Float) | <span data-ttu-id="a7331-174">Include gli stili [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) e [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent).</span><span class="sxs-lookup"><span data-stu-id="a7331-174">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint), and [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) styles.</span></span>
[<span data-ttu-id="a7331-175">NumberStyles.Currency</span><span class="sxs-lookup"><span data-stu-id="a7331-175">NumberStyles.Currency</span></span>](xref:System.Globalization.NumberStyles.Currency) | <span data-ttu-id="a7331-176">Include tutti gli stili tranne [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) e [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span><span class="sxs-lookup"><span data-stu-id="a7331-176">Includes all styles except [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) and [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span></span>
[<span data-ttu-id="a7331-177">NumberStyles.Any</span><span class="sxs-lookup"><span data-stu-id="a7331-177">NumberStyles.Any</span></span>](xref:System.Globalization.NumberStyles.Any) | <span data-ttu-id="a7331-178">Include tutti gli stili tranne [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span><span class="sxs-lookup"><span data-stu-id="a7331-178">Includes all styles except [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span></span>
[<span data-ttu-id="a7331-179">NumberStyles.HexNumber</span><span class="sxs-lookup"><span data-stu-id="a7331-179">NumberStyles.HexNumber</span></span>](xref:System.Globalization.NumberStyles.HexNumber) | <span data-ttu-id="a7331-180">Include gli stili [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) e [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span><span class="sxs-lookup"><span data-stu-id="a7331-180">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), and [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier) styles.</span></span>
 
## <a name="parsing-and-unicode-digits"></a><span data-ttu-id="a7331-181">Analisi e cifre Unicode</span><span class="sxs-lookup"><span data-stu-id="a7331-181">Parsing and Unicode digits</span></span>

<span data-ttu-id="a7331-182">Lo standard Unicode definisce gli elementi di codice per le cifre in diversi sistemi di scrittura.</span><span class="sxs-lookup"><span data-stu-id="a7331-182">The Unicode standard defines code points for digits in various writing systems.</span></span> <span data-ttu-id="a7331-183">Ad esempio, gli elementi di codice compresi tra U+0030 e U+0039 rappresentano le cifre latine di base da 0 a 9, gli elementi di codice compresi tra U+09E6 e U+09EF rappresentano le cifre bengalesi da 0 a 9 e gli elementi di codice compresi tra U+FF10 e U+FF19 rappresentano le cifre Fullwidth da 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="a7331-183">For example, code points from U+0030 to U+0039 represent the basic Latin digits 0 through 9, code points from U+09E6 to U+09EF represent the Bangla digits 0 through 9, and code points from U+FF10 to U+FF19 represent the Fullwidth digits 0 through 9.</span></span> <span data-ttu-id="a7331-184">Tuttavia, solo cifre numeriche riconosciute dai metodi di analisi sono le cifre latine di base da 0 a 9 con elementi di codice da U+0030 a U+0039.</span><span class="sxs-lookup"><span data-stu-id="a7331-184">However, the only numeric digits recognized by parsing methods are the basic Latin digits 0-9 with code points from U+0030 to U+0039.</span></span> <span data-ttu-id="a7331-185">Se a un metodo di analisi numerico viene passata una stringa che contiene altre cifre, il metodo genera un'eccezione [FormatException](xref:System.FormatException).</span><span class="sxs-lookup"><span data-stu-id="a7331-185">If a numeric parsing method is passed a string that contains any other digits, the method throws a [FormatException](xref:System.FormatException).</span></span>

<span data-ttu-id="a7331-186">Nell'esempio seguente viene usato il metodo [Int32.Parse](xref:System.Int32.Parse(System.String)) per analizzare le stringhe costituite da cifre in diversi sistemi di scrittura.</span><span class="sxs-lookup"><span data-stu-id="a7331-186">The following example uses the [Int32.Parse](xref:System.Int32.Parse(System.String)) method to parse strings that consist of digits in different writing systems.</span></span> <span data-ttu-id="a7331-187">Come illustrato nell'output dell'esempio, il tentativo di analizzare le cifre latine di base ha esito positivo, mentre il tentativo di analisi delle cifre Fullwidth, indoarabiche e bengalesi ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="a7331-187">As the output from the example shows, the attempt to parse the basic Latin digits succeeds, but the attempt to parse the Fullwidth, Arabic-Indic, and Bangla digits fails.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string value;
      // Define a string of basic Latin digits 1-5.
      value = "\u0031\u0032\u0033\u0034\u0035";
      ParseDigits(value);

      // Define a string of Fullwidth digits 1-5.
      value = "\uFF11\uFF12\uFF13\uFF14\uFF15";
      ParseDigits(value);

      // Define a string of Arabic-Indic digits 1-5.
      value = "\u0661\u0662\u0663\u0664\u0665";
      ParseDigits(value);

      // Define a string of Bangla digits 1-5.
      value = "\u09e7\u09e8\u09e9\u09ea\u09eb";
      ParseDigits(value);
   }

   static void ParseDigits(string value)
   {
      try {
         int number = Int32.Parse(value);
         Console.WriteLine("'{0}' --> {1}", value, number);
      }   
      catch (FormatException) {
         Console.WriteLine("Unable to parse '{0}'.", value);      
      }     
   }
}
// The example displays the following output:
//       '12345' --> 12345
//       Unable to parse '１２３４５'.
//       Unable to parse '١٢٣٤٥'.
//       Unable to parse '১২৩৪৫'.
```

```vb
Module Example
   Public Sub Main()
      Dim value As String
      ' Define a string of basic Latin digits 1-5.
      value = ChrW(&h31) + ChrW(&h32) + ChrW(&h33) + ChrW(&h34) + ChrW(&h35)
      ParseDigits(value)

      ' Define a string of Fullwidth digits 1-5.
      value = ChrW(&hff11) + ChrW(&hff12) + ChrW(&hff13) + ChrW(&hff14) + ChrW(&hff15)
      ParseDigits(value)

      ' Define a string of Arabic-Indic digits 1-5.
      value = ChrW(&h661) + ChrW(&h662) + ChrW(&h663) + ChrW(&h664) + ChrW(&h665)
      ParseDigits(value)

      ' Define a string of Bangla digits 1-5.
      value = ChrW(&h09e7) + ChrW(&h09e8) + ChrW(&h09e9) + ChrW(&h09ea) + ChrW(&h09eb)
      ParseDigits(value)
   End Sub

   Sub ParseDigits(value As String)
      Try
         Dim number As Integer = Int32.Parse(value)
         Console.WriteLine("'{0}' --> {1}", value, number)
      Catch e As FormatException
         Console.WriteLine("Unable to parse '{0}'.", value)      
      End Try     
   End Sub
End Module
' The example displays the following output:
'       '12345' --> 12345
'       Unable to parse '１２３４５'.
'       Unable to parse '١٢٣٤٥'.
'       Unable to parse '১২৩৪৫'.
```

## <a name="see-also"></a><span data-ttu-id="a7331-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7331-188">See also</span></span>

[<span data-ttu-id="a7331-189">System.Globalization.NumberStyles</span><span class="sxs-lookup"><span data-stu-id="a7331-189">System.Globalization.NumberStyles</span></span>](xref:System.Globalization.NumberStyles)

[<span data-ttu-id="a7331-190">Analisi di stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="a7331-190">Parsing strings in .NET</span></span>](parsing-strings.md)

[<span data-ttu-id="a7331-191">Formattazione di tipi in .NET</span><span class="sxs-lookup"><span data-stu-id="a7331-191">Formatting types in .NET</span></span>](formatting-types.md)



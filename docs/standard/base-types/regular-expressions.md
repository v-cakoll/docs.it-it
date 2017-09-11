---
title: Espressioni regolari in .NET
description: Espressioni regolari in .NET
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: d1a640cf-09ca-48f7-800c-a627a6d549c9
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: ac26821819b22aa3ea47e6945bb5c8575dcd9807
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="regular-expressions-in-net"></a><span data-ttu-id="3e784-104">Espressioni regolari in .NET</span><span class="sxs-lookup"><span data-stu-id="3e784-104">Regular expressions in .NET</span></span>

<span data-ttu-id="3e784-105">Le espressioni regolari ("regular expression") garantiscono un metodo efficace e flessibile per elaborare del testo.</span><span class="sxs-lookup"><span data-stu-id="3e784-105">Regular expressions provide a powerful, flexible, and efficient method for processing text.</span></span> <span data-ttu-id="3e784-106">L'ampia notazione per la formulazione dei criteri di ricerca fornita dalle espressioni regolari consente di analizzare rapidamente grandi quantità di testo per trovare combinazioni di caratteri specifiche, per convalidare il testo verificandone la corrispondenza con un modello predefinito, ad esempio un indirizzo di posta elettronica, per estrarre, modificare, sostituire o eliminare sottostringhe di testo e per aggiungere le stringhe estratte a una raccolta per generare un rapporto.</span><span class="sxs-lookup"><span data-stu-id="3e784-106">The extensive pattern-matching notation of regular expressions enables you to quickly parse large amounts of text to find specific character patterns; to validate text to ensure that it matches a predefined pattern (such as an e-mail address); to extract, edit, replace, or delete text substrings; and to add the extracted strings to a collection in order to generate a report.</span></span> <span data-ttu-id="3e784-107">Per numerose applicazioni che gestiscono stringhe o che analizzano grandi blocchi di testo, le espressioni regolari rappresentano uno strumento indispensabile.</span><span class="sxs-lookup"><span data-stu-id="3e784-107">For many applications that deal with strings or that parse large blocks of text, regular expressions are an indispensable tool.</span></span>

## <a name="how-regular-expressions-work"></a><span data-ttu-id="3e784-108">Funzionamento delle espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="3e784-108">How Regular Expressions Work</span></span>

<span data-ttu-id="3e784-109">L'elemento centrale dell'elaborazione del testo con le espressioni regolari è il motore delle espressioni regolari, rappresentato dall'oggetto [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) in .NET.</span><span class="sxs-lookup"><span data-stu-id="3e784-109">The centerpiece of text processing with regular expressions is the regular expression engine, which is represented by the [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) object in .NET.</span></span> <span data-ttu-id="3e784-110">L'elaborazione di testo tramite espressioni regolari richiede che al motore delle espressioni regolari vengano fornite almeno le due informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e784-110">At a minimum, processing text using regular expressions requires that the regular expression engine be provided with the following two items of information:</span></span>

* <span data-ttu-id="3e784-111">Criterio di espressione regolare da identificare nel testo.</span><span class="sxs-lookup"><span data-stu-id="3e784-111">The regular expression pattern to identify in the text.</span></span> 
  
  <span data-ttu-id="3e784-112">In .NET i criteri di espressione regolare vengono definiti a un linguaggio o una sintassi speciale, compatibile con le espressioni regolari Perl 5, che offre funzionalità aggiuntive come la corrispondenza da destra verso sinistra.</span><span class="sxs-lookup"><span data-stu-id="3e784-112">In .NET, regular expression patterns are defined by a special syntax or language, which is compatible with Perl 5 regular expressions and adds some additional features such as right-to-left matching.</span></span> <span data-ttu-id="3e784-113">Per altre informazioni, vedere [Linguaggio di espressioni regolari - Riferimento rapido](quick-ref.md).</span><span class="sxs-lookup"><span data-stu-id="3e784-113">For more information, see [Regular Expression Language - Quick Reference](quick-ref.md).</span></span>
  
* <span data-ttu-id="3e784-114">Testo da analizzare per il criterio di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="3e784-114">The text to parse for the regular expression pattern.</span></span>

<span data-ttu-id="3e784-115">I metodi della classe [Regex](xref:System.Text.RegularExpressions.Regex) consentono di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e784-115">The methods of the [Regex](xref:System.Text.RegularExpressions.Regex) class let you perform the following operations:</span></span>

* <span data-ttu-id="3e784-116">Determinare se il criterio di espressione regolare è presente nel testo di input chiamando il metodo [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)).</span><span class="sxs-lookup"><span data-stu-id="3e784-116">Determine whether the regular expression pattern occurs in the input text by calling the [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) method.</span></span> <span data-ttu-id="3e784-117">Per un esempio di uso del metodo [IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) per la convalida del testo, vedere [Procedura: Verificare che le stringhe siano in formato di posta elettronica valido](verify-format.md).</span><span class="sxs-lookup"><span data-stu-id="3e784-117">For an example that uses the [IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) method for validating text, see [How to: Verify that Strings Are in Valid Email Format](verify-format.md).</span></span>

* <span data-ttu-id="3e784-118">Recuperare una o tutte le occorrenze del testo che corrisponde al criterio di espressione regolare chiamando il metodo [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) o [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)).</span><span class="sxs-lookup"><span data-stu-id="3e784-118">Retrieve one or all occurrences of text that matches the regular expression pattern by calling the [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) or [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) method.</span></span> <span data-ttu-id="3e784-119">Il primo metodo restituisce un oggetto [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) che visualizza informazioni sul testo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="3e784-119">The former method returns a [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) object that provides information about the matching text.</span></span> <span data-ttu-id="3e784-120">I secondo metodo restituisce un oggetto [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) che contiene un oggetto [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) per ogni corrispondenza trovata nel testo analizzato.</span><span class="sxs-lookup"><span data-stu-id="3e784-120">The latter returns a [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) object that contains one [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) object for each match found in the parsed text.</span></span> 

* <span data-ttu-id="3e784-121">Sostituire il testo che corrisponde al criterio di espressione regolare chiamando il metodo [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)).</span><span class="sxs-lookup"><span data-stu-id="3e784-121">Replace text that matches the regular expression pattern by calling the [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) method.</span></span> <span data-ttu-id="3e784-122">Per esempi di uso del metodo [Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) per modificare i formati di data e rimuovere i caratteri non validi da una stringa, vedere [Procedura: Rimuovere caratteri non validi da una stringa](strip-characters.md) e [Procedura: Modificare i formati di data](changing-formats.md).</span><span class="sxs-lookup"><span data-stu-id="3e784-122">For examples that use the [Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) method to change date formats and remove invalid characters from a string, see [How to: Strip Invalid Characters from a String](strip-characters.md) and [Regular Expression Example: Changing Date Formats](changing-formats.md).</span></span>

<span data-ttu-id="3e784-123">Per una panoramica del modello a oggetti delle espressioni regolari, vedere [Modello a oggetti delle espressioni regolari](object-model.md).</span><span class="sxs-lookup"><span data-stu-id="3e784-123">For an overview of the regular expression object model, see [The Regular Expression Object Model](object-model.md).</span></span>

<span data-ttu-id="3e784-124">Per altre informazioni sul linguaggio delle espressioni regolari, vedere [Linguaggio di espressioni regolari - Riferimento rapido](quick-ref.md).</span><span class="sxs-lookup"><span data-stu-id="3e784-124">For more information about the regular expression language, see [Regular Expression Language - Quick Reference](quick-ref.md).</span></span>

## <a name="regular-expression-examples"></a><span data-ttu-id="3e784-125">Esempi di espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="3e784-125">Regular Expression Examples</span></span>

<span data-ttu-id="3e784-126">La classe [String](xref:System.String) include alcuni metodi di ricerca e sostituzione di stringhe che è possibile usare quando si vogliono individuare stringhe letterali in una stringa più grande.</span><span class="sxs-lookup"><span data-stu-id="3e784-126">The [String](xref:System.String) class includes a number of string search and replacement methods that you can use when you want to locate literal strings in a larger string.</span></span> <span data-ttu-id="3e784-127">Le espressioni regolari sono utili per lo più quando si vuole individuare una di diverse sottostringhe in una stringa più grande o quando si vogliono identificare dei modelli in una stringa, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="3e784-127">Regular expressions are most useful either when you want to locate one of several substrings in a larger string, or when you want to identify patterns in a string, as the following examples illustrate.</span></span> 

### <a name="example-1-replacing-substrings"></a><span data-ttu-id="3e784-128">Esempio 1: sostituzione di sottostringhe</span><span class="sxs-lookup"><span data-stu-id="3e784-128">Example 1: Replacing Substrings</span></span>

<span data-ttu-id="3e784-129">Si presupponga che una lista di distribuzione contenga nomi che talvolta includono un titolo (Mr., Mrs., Miss o Ms.) oltre al nome e al cognome.</span><span class="sxs-lookup"><span data-stu-id="3e784-129">Assume that a mailing list contains names that sometimes include a title (Mr., Mrs., Miss, or Ms.) along with a first and last name.</span></span> <span data-ttu-id="3e784-130">Se non si vogliono includere i titoli quando si generano etichette per le buste dall'elenco, è possibile usare un'espressione regolare per rimuovere i titoli, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3e784-130">If you do not want to include the titles when you generate envelope labels from the list, you can use a regular expression to remove the titles, as the following example illustrates.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "(Mr\\.? |Mrs\\.? |Miss |Ms\\.? )";
      string[] names = { "Mr. Henry Hunt", "Ms. Sara Samuels", 
                         "Abraham Adams", "Ms. Nicole Norris" };
      foreach (string name in names)
         Console.WriteLine(Regex.Replace(name, pattern, String.Empty));
   }
}
// The example displays the following output:
//    Henry Hunt
//    Sara Samuels
//    Abraham Adams
//    Nicole Norris
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(Mr\.? |Mrs\.? |Miss |Ms\.? )"
      Dim names() As String = { "Mr. Henry Hunt", "Ms. Sara Samuels", _
                                "Abraham Adams", "Ms. Nicole Norris" }
      For Each name As String In names
         Console.WriteLine(Regex.Replace(name, pattern, String.Empty))
      Next                                
   End Sub
End Module
' The example displays the following output:
'    Henry Hunt
'    Sara Samuels
'    Abraham Adams
'    Nicole Norris
```

<span data-ttu-id="3e784-131">Il criterio di espressione regolare `(Mr\.? |Mrs\.? |Miss |Ms\.? )` trova una corrispondenza di tutte le occorrenze di "Mr", "Mr.", "Mrs", "Mrs.", "Miss", "Ms" o "Ms.".</span><span class="sxs-lookup"><span data-stu-id="3e784-131">The regular expression pattern `(Mr\.? |Mrs\.? |Miss |Ms\.? )` matches any occurrence of "Mr ", "Mr. ", "Mrs ", "Mrs. ", "Miss ", "Ms or "Ms. ".</span></span> <span data-ttu-id="3e784-132">La chiamata al metodo [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) sostituisce la stringa corrispondente con [String.Empty](xref:System.String.Empty), ovvero la rimuove dalla stringa originale.</span><span class="sxs-lookup"><span data-stu-id="3e784-132">The call to the [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) method replaces the matched string with [String.Empty](xref:System.String.Empty); in other words, it removes it from the original string.</span></span>

### <a name="example-2-identifying-duplicated-words"></a><span data-ttu-id="3e784-133">Esempio 2: identificazione di parole duplicate</span><span class="sxs-lookup"><span data-stu-id="3e784-133">Example 2: Identifying Duplicated Words</span></span>

<span data-ttu-id="3e784-134">La duplicazione accidentale delle parole è un errore comune commesso dagli autori.</span><span class="sxs-lookup"><span data-stu-id="3e784-134">Accidentally duplicating words is a common error that writers make.</span></span> <span data-ttu-id="3e784-135">È possibile usare un'espressione regolare per identificare le parole duplicate, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3e784-135">A regular expression can be used to identify duplicated words, as the following example shows.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Class1
{
   public static void Main()
   {
      string pattern = @"\b(\w+?)\s\1\b";
      string input = "This this is a nice day. What about this? This tastes good. I saw a a dog.";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
         Console.WriteLine("{0} (duplicates '{1}') at position {2}", 
                           match.Value, match.Groups[1].Value, match.Index);
   }
}
// The example displays the following output:
//       This this (duplicates 'This)' at position 0
//       a a (duplicates 'a)' at position 66
```

```vb
Imports System.Text.RegularExpressions

Module modMain
   Public Sub Main()
      Dim pattern As String = "\b(\w+?)\s\1\b"
      Dim input As String = "This this is a nice day. What about this? This tastes good. I saw a a dog."
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
         Console.WriteLine("{0} (duplicates '{1}') at position {2}", _
                           match.Value, match.Groups(1).Value, match.Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       This this (duplicates 'This)' at position 0
'       a a (duplicates 'a)' at position 66
```

<span data-ttu-id="3e784-136">Il criterio di espressione regolare `\b(\w+?)\s\1\b` può essere interpretato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="3e784-136">The regular expression pattern `\b(\w+?)\s\1\b` can be interpreted as follows:</span></span>

<span data-ttu-id="3e784-137">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e784-137">Syntax</span></span> | <span data-ttu-id="3e784-138">Significato</span><span class="sxs-lookup"><span data-stu-id="3e784-138">Meaning</span></span>
------ | -------
`\b` | <span data-ttu-id="3e784-139">Inizia dal confine di una parola.</span><span class="sxs-lookup"><span data-stu-id="3e784-139">Start at a word boundary.</span></span>
`(\w+?)` | <span data-ttu-id="3e784-140">Corrisponde a uno o più caratteri alfanumerici, ma il minor numero di caratteri possibile.</span><span class="sxs-lookup"><span data-stu-id="3e784-140">Match one or more word characters, but as few characters as possible.</span></span> <span data-ttu-id="3e784-141">I caratteri insieme formano un gruppo a cui è possibile fare riferimento come `\1`.</span><span class="sxs-lookup"><span data-stu-id="3e784-141">Together, they form a group that can be referred to as `\1`.</span></span>
`\s` | <span data-ttu-id="3e784-142">Trova la corrispondenza con uno spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="3e784-142">Match a white-space character.</span></span>
`\1` | <span data-ttu-id="3e784-143">Trova la corrispondenza della sottostringa equivalente al gruppo denominato `\1`.</span><span class="sxs-lookup"><span data-stu-id="3e784-143">Match the substring that is equal to the group named `\1`.</span></span>
`\b` | <span data-ttu-id="3e784-144">Trova la corrispondenza di un confine di parola.</span><span class="sxs-lookup"><span data-stu-id="3e784-144">Match a word boundary.</span></span>

<span data-ttu-id="3e784-145">Il metodo [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) viene chiamato con le opzioni di espressioni regolari impostate su [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase).</span><span class="sxs-lookup"><span data-stu-id="3e784-145">The [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) method is called with regular expression options set to [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase).</span></span> <span data-ttu-id="3e784-146">Per l'operazione di corrispondenza non viene quindi fatta distinzione tra maiuscole e minuscole e nell'esempio la sottostringa "This this" viene identificata come duplicato.</span><span class="sxs-lookup"><span data-stu-id="3e784-146">Therefore, the match operation is case-insensitive, and the example identifies the substring "This this" as a duplication.</span></span>

<span data-ttu-id="3e784-147">Si noti che la stringa di input include la sottostringa "this?</span><span class="sxs-lookup"><span data-stu-id="3e784-147">Note that the input string includes the substring "this?</span></span> <span data-ttu-id="3e784-148">This".</span><span class="sxs-lookup"><span data-stu-id="3e784-148">This".</span></span> <span data-ttu-id="3e784-149">Dato che tuttavia tra le due parole è presente un segno di punteggiatura, le parole non vengono identificate come duplicati.</span><span class="sxs-lookup"><span data-stu-id="3e784-149">However, because of the intervening punctuation mark, it is not identified as a duplication.</span></span>

### <a name="example-3-dynamically-building-a-culture-sensitive-regular-expression"></a><span data-ttu-id="3e784-150">Esempio 3: compilazione dinamica di un'espressione regolare dipendente dalle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="3e784-150">Example 3: Dynamically Building a Culture-Sensitive Regular Expression</span></span>

<span data-ttu-id="3e784-151">L'esempio seguente illustra le potenzialità delle espressioni regolari combinate alla flessibilità offerta dalle funzionalità di globalizzazione di .NET.</span><span class="sxs-lookup"><span data-stu-id="3e784-151">The following example illustrates the power of regular expressions combined with the flexibility offered by .NET's globalization features.</span></span> <span data-ttu-id="3e784-152">Viene usato l'oggetto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) per determinare il formato dei valori di valuta nelle impostazioni cultura correnti del sistema.</span><span class="sxs-lookup"><span data-stu-id="3e784-152">It uses the [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object to determine the format of currency values in the system's current culture.</span></span> <span data-ttu-id="3e784-153">Queste informazioni vengono quindi usate per costruire in modo dinamico un'espressione regolare per l'estrazione dei valori di valuta dal testo.</span><span class="sxs-lookup"><span data-stu-id="3e784-153">It then uses that information to dynamically construct a regular expression that extracts currency values from the text.</span></span> <span data-ttu-id="3e784-154">Per ogni corrispondenza, il sottogruppo che contiene solo la stringa numerica viene estratto e convertito in un valore [Decimal](xref:System.Decimal), quindi viene calcolato un totale parziale.</span><span class="sxs-lookup"><span data-stu-id="3e784-154">For each match, it extracts the subgroup that contains the numeric string only, converts it to a [Decimal](xref:System.Decimal) value, and calculates a running total.</span></span> 

```csharp
using System;
using System.Collections.Generic;
using System.Globalization;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      // Define text to be parsed.
      string input = "Office expenses on 2/13/2008:\n" + 
                     "Paper (500 sheets)                      $3.95\n" + 
                     "Pencils (box of 10)                     $1.00\n" + 
                     "Pens (box of 10)                        $4.49\n" + 
                     "Erasers                                 $2.19\n" + 
                     "Ink jet printer                        $69.95\n\n" + 
                     "Total Expenses                        $ 81.58\n"; 

      // Get current culture's NumberFormatInfo object.
      NumberFormatInfo nfi = CultureInfo.CurrentCulture.NumberFormat;
      // Assign needed property values to variables.
      string currencySymbol = nfi.CurrencySymbol;
      bool symbolPrecedesIfPositive = nfi.CurrencyPositivePattern % 2 == 0;
      string groupSeparator = nfi.CurrencyGroupSeparator;
      string decimalSeparator = nfi.CurrencyDecimalSeparator;

      // Form regular expression pattern.
      string pattern = Regex.Escape( symbolPrecedesIfPositive ? currencySymbol : "") + 
                       @"\s*[-+]?" + "([0-9]{0,3}(" + groupSeparator + "[0-9]{3})*(" + 
                       Regex.Escape(decimalSeparator) + "[0-9]+)?)" + 
                       (! symbolPrecedesIfPositive ? currencySymbol : ""); 
      Console.WriteLine( "The regular expression pattern is:");
      Console.WriteLine("   " + pattern);      

      // Get text that matches regular expression pattern.
      MatchCollection matches = Regex.Matches(input, pattern, 
                                              RegexOptions.IgnorePatternWhitespace);               
      Console.WriteLine("Found {0} matches.", matches.Count); 

      // Get numeric string, convert it to a value, and add it to List object.
      List<decimal> expenses = new List<Decimal>();

      foreach (Match match in matches)
         expenses.Add(Decimal.Parse(match.Groups[1].Value));      

      // Determine whether total is present and if present, whether it is correct.
      decimal total = 0;
      foreach (decimal value in expenses)
         total += value;

      if (total / 2 == expenses[expenses.Count - 1]) 
         Console.WriteLine("The expenses total {0:C2}.", expenses[expenses.Count - 1]);
      else
         Console.WriteLine("The expenses total {0:C2}.", total);
   }  
}
// The example displays the following output:
//       The regular expression pattern is:
//          \$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)
//       Found 6 matches.
//       The expenses total $81.58.
```

```vb
Imports System.Collections.Generic
Imports System.Globalization
Imports System.Text.RegularExpressions

Public Module Example
   Public Sub Main()
      ' Define text to be parsed.
      Dim input As String = "Office expenses on 2/13/2008:" + vbCrLf + _
                            "Paper (500 sheets)                      $3.95" + vbCrLf + _
                            "Pencils (box of 10)                     $1.00" + vbCrLf + _
                            "Pens (box of 10)                        $4.49" + vbCrLf + _
                            "Erasers                                 $2.19" + vbCrLf + _
                            "Ink jet printer                        $69.95" + vbCrLf + vbCrLf + _
                            "Total Expenses                        $ 81.58" + vbCrLf
      ' Get current culture's NumberFormatInfo object.
      Dim nfi As NumberFormatInfo = CultureInfo.CurrentCulture.NumberFormat
      ' Assign needed property values to variables.
      Dim currencySymbol As String = nfi.CurrencySymbol
      Dim symbolPrecedesIfPositive As Boolean = CBool(nfi.CurrencyPositivePattern Mod 2 = 0)
      Dim groupSeparator As String = nfi.CurrencyGroupSeparator
      Dim decimalSeparator As String = nfi.CurrencyDecimalSeparator

      ' Form regular expression pattern.
      Dim pattern As String = Regex.Escape(CStr(IIf(symbolPrecedesIfPositive, currencySymbol, ""))) + _
                              "\s*[-+]?" + "([0-9]{0,3}(" + groupSeparator + "[0-9]{3})*(" + _
                              Regex.Escape(decimalSeparator) + "[0-9]+)?)" + _
                              CStr(IIf(Not symbolPrecedesIfPositive, currencySymbol, "")) 
      Console.WriteLine("The regular expression pattern is: ")
      Console.WriteLine("   " + pattern)      

      ' Get text that matches regular expression pattern.
      Dim matches As MatchCollection = Regex.Matches(input, pattern, RegexOptions.IgnorePatternWhitespace)               
      Console.WriteLine("Found {0} matches. ", matches.Count)

      ' Get numeric string, convert it to a value, and add it to List object.
      Dim expenses As New List(Of Decimal)

      For Each match As Match In matches
         expenses.Add(Decimal.Parse(match.Groups.Item(1).Value))      
      Next

      ' Determine whether total is present and if present, whether it is correct.
      Dim total As Decimal
      For Each value As Decimal In expenses
         total += value
      Next

      If total / 2 = expenses(expenses.Count - 1) Then
         Console.WriteLine("The expenses total {0:C2}.", expenses(expenses.Count - 1))
      Else
         Console.WriteLine("The expenses total {0:C2}.", total)
      End If   
   End Sub
End Module
' The example displays the following output:
'       The regular expression pattern is:
'          \$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)
'       Found 6 matches.
'       The expenses total $81.58.
```

<span data-ttu-id="3e784-155">In un computer le cui impostazioni cultura correnti sono Inglese - Stati Uniti (en-US), l'esempio compila l'espressione regolare `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)` dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="3e784-155">On a computer whose current culture is English - United States (en-US), the example dynamically builds the regular expression `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`.</span></span> <span data-ttu-id="3e784-156">Questo criterio di espressione regolare può essere interpretato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="3e784-156">This regular expression pattern can be interpreted as follows:</span></span>

<span data-ttu-id="3e784-157">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e784-157">Syntax</span></span> | <span data-ttu-id="3e784-158">Significato</span><span class="sxs-lookup"><span data-stu-id="3e784-158">Meaning</span></span>
------ | -------
`\$` | <span data-ttu-id="3e784-159">Cerca una singola occorrenza del simbolo di dollaro ($) nella stringa di input.</span><span class="sxs-lookup"><span data-stu-id="3e784-159">Look for a single occurrence of the dollar symbol ($) in the input string.</span></span> <span data-ttu-id="3e784-160">La stringa del criterio di espressione regolare include una barra rovesciata per indicare che il simbolo di dollaro deve essere interpretato letteralmente e non come un ancoraggio dell'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="3e784-160">The regular expression pattern string includes a backslash to indicate that the dollar symbol is to be interpreted literally rather than as a regular expression anchor.</span></span> <span data-ttu-id="3e784-161">Il simbolo $ da solo indica che il motore delle espressioni regolari deve cercare di iniziare la ricerca della corrispondenza alla fine di una stringa. Per verificare che il simbolo di valuta delle impostazioni cultura correnti non venga interpretato erroneamente come simbolo dell'espressione regolare, l'esempio chiama il metodo [Escape](xref:System.Text.RegularExpressions.Regex.Escape(System.String)) per usare caratteri di escape per il carattere.</span><span class="sxs-lookup"><span data-stu-id="3e784-161">(The $ symbol alone would indicate that the regular expression engine should try to begin its match at the end of a string.) To ensure that the current culture's currency symbol is not misinterpreted as a regular expression symbol, the example calls the [Escape](xref:System.Text.RegularExpressions.Regex.Escape(System.String)) method to escape the character.</span></span>
`\s*` | <span data-ttu-id="3e784-162">Cerca zero o più occorrenze di uno spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="3e784-162">Look for zero or more occurrences of a white-space character.</span></span>
`[-+]?` | <span data-ttu-id="3e784-163">Cerca zero o una occorrenza di un segno positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="3e784-163">Look for zero or one occurrence of either a positive sign or a negative sign.</span></span>
`([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)` | <span data-ttu-id="3e784-164">Le parentesi esterne che delimitano questa espressione la definiscono come gruppo di acquisizione o come sottoespressione.</span><span class="sxs-lookup"><span data-stu-id="3e784-164">The outer parentheses around this expression define it as a capturing group or a subexpression.</span></span> <span data-ttu-id="3e784-165">Se viene trovata una corrispondenza, è possibile recuperare informazioni relative a questa parte della stringa corrispondente dal secondo oggetto [Group](xref:System.Text.RegularExpressions.Group) nell'oggetto [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) restituito dalla proprietà [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups).</span><span class="sxs-lookup"><span data-stu-id="3e784-165">If a match is found, information about this part of the matching string can be retrieved from the second [Group](xref:System.Text.RegularExpressions.Group) object in the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) object returned by the [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) property.</span></span> <span data-ttu-id="3e784-166">Il primo elemento della raccolta rappresenta la corrispondenza completa.</span><span class="sxs-lookup"><span data-stu-id="3e784-166">(The first element in the collection represents the entire match.)</span></span>
`[0-9]{0,3}` | <span data-ttu-id="3e784-167">Cerca da zero a tre occorrenze delle cifre decimali comprese tra 0 e 9.</span><span class="sxs-lookup"><span data-stu-id="3e784-167">Look for zero to three occurrences of the decimal digits 0 through 9.</span></span>
`(,[0-9]{3})*` | <span data-ttu-id="3e784-168">Cerca zero o più occorrenze di un separatore di gruppi seguito da tre cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="3e784-168">Look for zero or more occurrences of a group separator followed by three decimal digits.</span></span>
`\.` | <span data-ttu-id="3e784-169">Cerca una singola occorrenza del separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="3e784-169">Look for a single occurrence of the decimal separator.</span></span>
`[0-9]+` | <span data-ttu-id="3e784-170">Cerca una o più cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="3e784-170">Look for one or more decimal digits.</span></span>
`(\.[0-9]+)?` | <span data-ttu-id="3e784-171">Cerca zero o una occorrenza del separatore decimale seguito da almeno una cifra decimale.</span><span class="sxs-lookup"><span data-stu-id="3e784-171">Look for zero or one occurrence of the decimal separator followed by at least one decimal digit.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3e784-172">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3e784-172">Related Topics</span></span>

<span data-ttu-id="3e784-173">Titolo</span><span class="sxs-lookup"><span data-stu-id="3e784-173">Title</span></span> | <span data-ttu-id="3e784-174">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e784-174">Description</span></span>
----- | -----------
[<span data-ttu-id="3e784-175">Linguaggio di espressioni regolari - Riferimento rapido</span><span class="sxs-lookup"><span data-stu-id="3e784-175">Regular expression language - quick reference</span></span>](quick-ref.md) | <span data-ttu-id="3e784-176">Fornisce informazioni sul set di caratteri, di operatori e di costrutti che è possibile usare per definire le espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="3e784-176">Provides information on the set of characters, operators, and constructs that you can use to define regular expressions.</span></span>
[<span data-ttu-id="3e784-177">Modello a oggetti delle espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="3e784-177">The regular expression object model</span></span>](object-model.md) | <span data-ttu-id="3e784-178">Fornisce esempi di codice e informazioni che illustrano l'uso delle classi di espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="3e784-178">Provides information and code examples that illustrate how to use the regular expression classes.</span></span>
[<span data-ttu-id="3e784-179">Dettagli sul comportamento delle espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="3e784-179">Details of regular expression behavior</span></span>](regex-behavior.md) | <span data-ttu-id="3e784-180">Offre informazioni sulle funzionalità e il funzionamento delle espressioni regolari di .NET.</span><span class="sxs-lookup"><span data-stu-id="3e784-180">Provides information about the capabilities and behavior of .NETregular expressions.</span></span>
[<span data-ttu-id="3e784-181">Esempi di espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="3e784-181">Regular expression examples</span></span>](regex-examples.md) | <span data-ttu-id="3e784-182">Fornisce esempi di codice che illustrano gli usi tipici delle espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="3e784-182">Provides code examples that illustrate typical uses of regular expressions.</span></span>


## <a name="reference"></a><span data-ttu-id="3e784-183">Riferimento</span><span class="sxs-lookup"><span data-stu-id="3e784-183">Reference</span></span>

[<span data-ttu-id="3e784-184">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="3e784-184">System.Text.RegularExpressions</span></span>](xref:System.Text.RegularExpressions)

[<span data-ttu-id="3e784-185">System.Text.RegularExpressions.Regex</span><span class="sxs-lookup"><span data-stu-id="3e784-185">System.Text.RegularExpressions.Regex</span></span>](xref:System.Text.RegularExpressions.Regex)



---
title: Guida introduttiva alle stringhe interpolate - Guida a C#
description: Questa guida introduttiva sulle stringhe interpolate spiega come scrivere il codice C# per includere il risultato di un'espressione in una stringa di dimensioni maggiori.
author: rpetrusha
ms.author: ronpet
ms.date: 01/11/2018
ms.topic: get-started-article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 14185dd4e364f12756541ac6401d1c6ff3206fe9
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2018
---
# <a name="interpolated-strings"></a><span data-ttu-id="45e64-103">Stringhe interpolate</span><span class="sxs-lookup"><span data-stu-id="45e64-103">Interpolated strings</span></span>

<span data-ttu-id="45e64-104">Questa guida introduttiva indica come usare le stringhe interpolate in C# per inserire i valori in un'unica stringa di output.</span><span class="sxs-lookup"><span data-stu-id="45e64-104">This quick start teaches you how to use interpolated strings in C# to insert values into a single ouput string.</span></span> <span data-ttu-id="45e64-105">Verranno descritte le procedure per scrivere codice C# e visualizzare i risultati della compilazione ed esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="45e64-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="45e64-106">La guida introduttiva include una serie di lezioni che spiegano come inserire i valori nelle stringhe e applicare formattazioni diverse a tali valori.</span><span class="sxs-lookup"><span data-stu-id="45e64-106">The quick start contains a series of lessons that insert values into strings, and format those values in different ways.</span></span>

<span data-ttu-id="45e64-107">Questa guida introduttiva prevede la disponibilità di un computer da usare per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="45e64-107">This quick start expects that you have a machine you can use for development.</span></span> <span data-ttu-id="45e64-108">L'argomento [Get started with .NET in 10 minutes](https://www.microsoft.com/net/core) (Iniziare a usare .NET in 10 minuti) contiene istruzioni per la configurazione dell'ambiente di sviluppo locale in Mac, PC o Linux.</span><span class="sxs-lookup"><span data-stu-id="45e64-108">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="45e64-109">Una breve panoramica dei comandi usati è disponibile nell'[introduzione alle guide introduttive locali](local-environment.md) che contiene anche collegamenti ad altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="45e64-109">A quick overview of the commands you'll use is in the [introduction to the local quick starts](local-environment.md) with links to more details.</span></span> 

## <a name="create-an-interpolated-string"></a><span data-ttu-id="45e64-110">Creare una stringa interpolata</span><span class="sxs-lookup"><span data-stu-id="45e64-110">Create an interpolated string</span></span>

<span data-ttu-id="45e64-111">Creare una directory denominata **interpolated-quickstart**.</span><span class="sxs-lookup"><span data-stu-id="45e64-111">Create a directory named **interpolated-quickstart**.</span></span> <span data-ttu-id="45e64-112">Impostarla come directory corrente ed eseguire il comando seguente da una finestra della console:</span><span class="sxs-lookup"><span data-stu-id="45e64-112">Make it the current directory and run the following command from a console window:</span></span>

```console
dotnet new console -n interpolated -o .
```

<span data-ttu-id="45e64-113">Questo comando crea una nuova applicazione console .NET Core nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="45e64-113">This command creates a new .NET Core console application in the current directory.</span></span>

<span data-ttu-id="45e64-114">Aprire **Program.cs** nell'editor preferito e sostituire la riga `Console.WriteLine("Hello World!");` con il codice seguente, sostituendo `<name>` con il nome:</span><span class="sxs-lookup"><span data-stu-id="45e64-114">Open **Program.cs** in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code, where you replace `<name>` with your name:</span></span>

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```
<span data-ttu-id="45e64-115">Per provare questo codice, digitare `dotnet run` nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="45e64-115">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="45e64-116">Quando si esegue il programma viene visualizzata un'unica stringa contenente un messaggio di saluto che include il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="45e64-116">When you run the program, it displays a single string that includes your name in the greeting.</span></span> <span data-ttu-id="45e64-117">La stringa inclusa nella chiamata al metodo <xref:System.Console.WriteLine%2A> è una *stringa interpolata*.</span><span class="sxs-lookup"><span data-stu-id="45e64-117">The string included in the <xref:System.Console.WriteLine%2A> method call is an *interpolated string*.</span></span> <span data-ttu-id="45e64-118">Si tratta di un tipo di modello che consente di costruire un'unica stringa detta *stringa di risultato* da una stringa che include codice incorporato.</span><span class="sxs-lookup"><span data-stu-id="45e64-118">It's a kind of template that lets you construct a single string (called the *result string*) from a string that includes embedded code.</span></span> <span data-ttu-id="45e64-119">Le stringhe interpolate sono particolarmente utili per inserire valori in una stringa o per concatenare (unire) più stringhe.</span><span class="sxs-lookup"><span data-stu-id="45e64-119">Interpolated strings are particularly useful for inserting values into a string or concatenating (joining together) strings.</span></span> 
    
<span data-ttu-id="45e64-120">Questo semplice esempio contiene i due elementi che devono essere presenti in ogni stringa interpolata:</span><span class="sxs-lookup"><span data-stu-id="45e64-120">This simple example contains the two elements that every interpolated string must have:</span></span> 

- <span data-ttu-id="45e64-121">Un valore letterale stringa che inizia con il carattere `$` prima delle virgolette inglesi aperte.</span><span class="sxs-lookup"><span data-stu-id="45e64-121">A string literal that begins with the `$` character before its opening quotation mark character.</span></span> <span data-ttu-id="45e64-122">Tra il simbolo `$` e le virgolette non devono essere presenti spazi.</span><span class="sxs-lookup"><span data-stu-id="45e64-122">There can't be any spaces between the `$` symbol and the quotation mark character.</span></span> <span data-ttu-id="45e64-123">Se si vuole vedere cosa accade se ne viene incluso uno, inserire uno spazio dopo il carattere `$`, salvare il file ed eseguire nuovamente il programma digitando `dotnet run` nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="45e64-123">(If you'd like to see what happens if you include one, insert a space after the `$` character, save the file, and run the program again by typing `dotnet run` in the console window.</span></span> <span data-ttu-id="45e64-124">Il compilatore C# visualizza un messaggio di errore "errore CS1056: Carattere '$'" imprevisto).</span><span class="sxs-lookup"><span data-stu-id="45e64-124">The C# compiler displays an error message, "error CS1056: Unexpected character '$'".)</span></span> 

- <span data-ttu-id="45e64-125">Una o più *espressioni interpolate*.</span><span class="sxs-lookup"><span data-stu-id="45e64-125">One or more *interpolated expressions*.</span></span> <span data-ttu-id="45e64-126">Un'espressione interpolata è indicata tra parentesi graffe di apertura e chiusura (`{` e `}`).</span><span class="sxs-lookup"><span data-stu-id="45e64-126">An interpolated expression is indicated by an opening and closing brace (`{` and `}`).</span></span> <span data-ttu-id="45e64-127">All'interno delle parentesi graffe è possibile inserire qualsiasi espressione C# che restituisce un valore, incluso `null`.</span><span class="sxs-lookup"><span data-stu-id="45e64-127">You can put any C# expression that returns a value (including `null`) inside the braces.</span></span> 

<span data-ttu-id="45e64-128">Ora si proveranno altri esempi di stringhe interpolate con altri tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="45e64-128">Let's try a few more interpolated string examples with some other data types.</span></span>
    
## <a name="include-different-data-types"></a><span data-ttu-id="45e64-129">Includere tipi di dati diversi</span><span class="sxs-lookup"><span data-stu-id="45e64-129">Include different data types</span></span>

<span data-ttu-id="45e64-130">Nella sezione precedente è stata usata una stringa interpolata per inserire una stringa in un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="45e64-130">In the previous section, you used an interpolated string to insert one string inside of another.</span></span> <span data-ttu-id="45e64-131">Un'espressione di stringa interpolata può avere qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="45e64-131">An interpolated string expression can be any data type, though.</span></span> <span data-ttu-id="45e64-132">Considerare ad esempio una stringa interpolata con valori di più tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="45e64-132">Let's try an interpolated string that has values of multiple data types.</span></span> 
    
<span data-ttu-id="45e64-133">L'esempio seguente include espressioni interpolate con un oggetto `Vegetable`, un membro dell'enumerazione `Unit`, un valore <xref:System.DateTime> e un valore <xref:System.Decimal>.</span><span class="sxs-lookup"><span data-stu-id="45e64-133">The following example includes interpolated expressions with a `Vegetable` object, a member of the `Unit` enumeration, a <xref:System.DateTime> value, and a <xref:System.Decimal> value.</span></span> <span data-ttu-id="45e64-134">Sostituire tutto il codice C# in un editor con il codice seguente e usare il comando `console run` per l'eseguirlo:</span><span class="sxs-lookup"><span data-stu-id="45e64-134">Replace all of the C# code in your editor with the following code, and then use the `console run` command to run it:</span></span>

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;
   
   public string Name { get; }
   
   public override string ToString() => Name;
}

public class Example
{
   public enum Unit { item, pound, ounce, dozen };
   
   public static void Main()
   {
      var item = new Vegetable("eggplant");
      var date = DateTime.Now;
      var price = 1.99m;
      var unit = Unit.item;
      Console.WriteLine($"On {date}, the price of {item} was {price} per {unit}.");
   }
}
```
    
<span data-ttu-id="45e64-135">Si noti che la seconda espressione interpolata include l'oggetto `item` nella stringa di risultato visualizzata nella console e che in questo caso nella stringa di risultato viene inserita la stringa "eggplant" (melanzana).</span><span class="sxs-lookup"><span data-stu-id="45e64-135">Note that the second interpolated expression includes the `item` object in the result string that's displayed to the console, and in this case the string "eggplant" is inserted into the result string.</span></span> <span data-ttu-id="45e64-136">Questo si verifica perché quando un'espressione interpolata non è di tipo stringa, il compilatore C# esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="45e64-136">That's because, when the type of an interpolated expression is not a string, the C# compiler does the following:</span></span>

- <span data-ttu-id="45e64-137">Se l'espressione interpolata è `null`, restituisce una stringa vuota ("" o <xref:System.String.Empty?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="45e64-137">If the interpolated expression is `null`, the interpolated expression returns an empty string ("", or <xref:System.String.Empty?displayProperty=nameWithType>).</span></span>

- <span data-ttu-id="45e64-138">Se l'espressione interpolata non è `null`, viene chiamato il metodo `ToString` del tipo dell'espressione interpolata.</span><span class="sxs-lookup"><span data-stu-id="45e64-138">If the interpolated expression is not `null`, the `ToString` method of the type of the interpolated expression is called.</span></span> <span data-ttu-id="45e64-139">Per il test di questo funzionamento impostare come commento la definizione del metodo `Vegetable.ToString` dell'esempio facendola precedere da un simbolo di commento (`//`).</span><span class="sxs-lookup"><span data-stu-id="45e64-139">You can test this by commenting out the definition of the `Vegetable.ToString` method in the example by putting a comment symbol (`//`) in front of it.</span></span> <span data-ttu-id="45e64-140">Nell'output la stringa "eggplant" (melanzana) viene sostituita dal nome del tipo "Vegetable" (verdura), ovvero il comportamento predefinito del metodo <xref:System.Object.ToString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="45e64-140">In the output, the string "eggplant" is replaced by the type name, "Vegetable", which is the default behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span>   

<span data-ttu-id="45e64-141">Nell'output di questo esempio la data è troppo precisa (il prezzo delle melanzane non varia ogni secondo) e il valore del prezzo non indica una valuta.</span><span class="sxs-lookup"><span data-stu-id="45e64-141">In the output from this example, the date is too precise (the price of eggplant does not vary by the second), and the price value doesn't indicate a unit of currency.</span></span> <span data-ttu-id="45e64-142">Nel sezione successiva si apprenderà come risolvere questi problemi controllando la formattazione delle stringhe restituite dalle espressioni interpolate.</span><span class="sxs-lookup"><span data-stu-id="45e64-142">In the next section, you'll learn how to fix those issues by controlling the format of strings returned by interpolated expressions.</span></span>

## <a name="control-the-formatting-of-interpolated-expressions"></a><span data-ttu-id="45e64-143">Controllare la formattazione delle espressioni interpolate</span><span class="sxs-lookup"><span data-stu-id="45e64-143">Control the formatting of interpolated expressions</span></span>

<span data-ttu-id="45e64-144">Nella sezione precedente sono state inserite nella stringa di risultato due stringhe con formattazione non valida.</span><span class="sxs-lookup"><span data-stu-id="45e64-144">In the previous section, two poorly formatted strings were inserted into the result string.</span></span> <span data-ttu-id="45e64-145">Il primo problema è un valore di data e ora nel quale solo la data risultava corretta.</span><span class="sxs-lookup"><span data-stu-id="45e64-145">One was a date and time value for which only the date was appropriate.</span></span> <span data-ttu-id="45e64-146">Il secondo è un prezzo che non indicava la valuta.</span><span class="sxs-lookup"><span data-stu-id="45e64-146">The second was a price that did not indicate its unit of currency.</span></span> <span data-ttu-id="45e64-147">Entrambi i problemi sono di facile risoluzione.</span><span class="sxs-lookup"><span data-stu-id="45e64-147">Both issues are easy to address.</span></span> <span data-ttu-id="45e64-148">Le espressioni interpolate possono includere *stringhe di formato* che controllano la formattazione di determinati tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="45e64-148">Interpolated expressions can include *format strings* that control the formatting of particular types.</span></span> <span data-ttu-id="45e64-149">Modificare la chiamata a `Console.WriteLine` dell'esempio precedente in modo da includere l'identificatore di formato per i campi data e prezzo, come indicato nella riga seguente:</span><span class="sxs-lookup"><span data-stu-id="45e64-149">Modify the call to `Console.WriteLine` from the previous example to include the format specifier for the date and price fields as shown in the following line:</span></span>

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```
    
<span data-ttu-id="45e64-150">Per specificare una stringa di formato, far seguire all'espressione interpolata i due punti e la stringa di formato desiderata.</span><span class="sxs-lookup"><span data-stu-id="45e64-150">You specify a format string by following the interpolated expression with a colon and the format string.</span></span> <span data-ttu-id="45e64-151">"d" è un [stringa di formato data e ora standard](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) che rappresenta il formato di data breve.</span><span class="sxs-lookup"><span data-stu-id="45e64-151">"d" is a [standard date and time format string](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) that represents the short date format.</span></span> <span data-ttu-id="45e64-152">"C2" è un [stringa di formato numerico standard](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) che rappresenta un numero come valore di valuta con due cifre dopo il separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="45e64-152">"C2" is a  [standard numeric format string](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) that represents a number as a currency value with two digits after the decimal point.</span></span>

<span data-ttu-id="45e64-153">Molti tipi delle librerie .NET Standard supportano un set predefinito di stringhe di formato.</span><span class="sxs-lookup"><span data-stu-id="45e64-153">A number of types in the .NET Standard libraries support a predefined set of format strings.</span></span> <span data-ttu-id="45e64-154">Tali tipi includono tutti i tipi numerici e i tipi data e ora.</span><span class="sxs-lookup"><span data-stu-id="45e64-154">These include all the numeric types and the date and time types.</span></span> <span data-ttu-id="45e64-155">Per l'elenco completo dei tipi che supportano le stringhe di formato, vedere [Stringhe di formato e tipi della libreria di classe .NET](../../standard/base-types/formatting-types.md#stringRef) nell'articolo [Formattazione di tipi in .NET](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="45e64-155">For a complete list of types that support format strings, see [Format Strings and .NET Class Library Types](../../standard/base-types/formatting-types.md#stringRef) in the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) article.</span></span> <span data-ttu-id="45e64-156">Qualsiasi tipo può supportare un set di stringhe di formato. È anche possibile sviluppare estensioni di formattazione personalizzata per aggiungere una formattazione personalizzata ai tipi esistenti.</span><span class="sxs-lookup"><span data-stu-id="45e64-156">Any type can support a set of format strings, and you can also develop custom formatting extensions that provide custom formatting for existing types.</span></span> <span data-ttu-id="45e64-157">Per informazioni sulla formattazione personalizzata con un'implementazione <xref:System.ICustomFormatter>, vedere [Formattazione personalizzata con ICustomFormatter](../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter) nell'articolo [Formattazione di tipi in .NET](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="45e64-157">For information on custom formatting by providing an <xref:System.ICustomFormatter> implementation, see [Custom Formatting with ICustomFormatter](../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter) in the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) article.</span></span>

<span data-ttu-id="45e64-158">Provare a modificare le stringhe di formato nell'editor di testo ed eseguire nuovamente il programma ogni volta che si apporta una modifica, per verificare l'effetto delle modifiche sulla formattazione di data, ora e valore numerico.</span><span class="sxs-lookup"><span data-stu-id="45e64-158">Try modifying the the format strings in your text editor and, each time you make a change, rerun the program to see how the changes affect the formatting of the date and time and the numeric value.</span></span> <span data-ttu-id="45e64-159">Modificare il valore "d" in `{date:d}` inserendo i valori "t" (per visualizzare il formato ora breve), "y" (per visualizzare anno e mese) e "yyyy" (per visualizzare l'anno come numero di quattro cifre).</span><span class="sxs-lookup"><span data-stu-id="45e64-159">Change the "d" in `{date:d}` to "t" (to display the short time format), "y" (to display the year and month), and "yyyy" (to display the year as a four-digit number).</span></span> <span data-ttu-id="45e64-160">Modificare "C2" in `{price:C2}` inserendo "e" (per la notazione esponenziale) e "F3" (per un valore numerico con tre cifre dopo il separatore decimale).</span><span class="sxs-lookup"><span data-stu-id="45e64-160">Change the "C2" in `{price:C2}` to "e" (for exponential notation) and "F3" (for a numeric value with three digits after the decimal point).</span></span>

<span data-ttu-id="45e64-161">Oltre alla formattazione è possibile controllare la larghezza del campo e l'allineamento delle stringhe restituite da un'espressione interpolata.</span><span class="sxs-lookup"><span data-stu-id="45e64-161">In addition to controlling formatting, you can also control the field width and alignment of the strings returned by an interpolated expression.</span></span> <span data-ttu-id="45e64-162">La sezione successiva spiega come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="45e64-162">In the next section, you'll learn how to do this.</span></span>

## <a name="control-the-field-width-and-alignment-of-interpolated-expressions"></a><span data-ttu-id="45e64-163">Controllare la larghezza del campo e l'allineamento delle espressioni interpolate</span><span class="sxs-lookup"><span data-stu-id="45e64-163">Control the field width and alignment of interpolated expressions</span></span>

<span data-ttu-id="45e64-164">In genere quando la stringa restituita da un'espressione interpolata è inclusa in una stringa di risultato non ha spazi iniziali o finali.</span><span class="sxs-lookup"><span data-stu-id="45e64-164">Ordinarily, when the string returned by an interpolated expression is included in a result string, it has no leading or trailing spaces.</span></span> <span data-ttu-id="45e64-165">Specie nelle istanze in cui si lavora con un set di dati, le espressioni interpolate consentono di specificare la larghezza e l'allineamento di un campo.</span><span class="sxs-lookup"><span data-stu-id="45e64-165">Particularly for instances in which you are working with a set of data, interpolated expressions let you specify a field width and its alignment.</span></span> <span data-ttu-id="45e64-166">Per verificare, sostituire tutto il codice nell'editor di testo con il codice seguente e digitare `console run` per eseguire il programma:</span><span class="sxs-lookup"><span data-stu-id="45e64-166">To see this, replace all the code in your text editor with the following code, then type `console run` to execute the program:</span></span>
    
```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>();
      titles.Add("Doyle, Arthur Conan", "Hound of the Baskervilles, The");
      titles.Add("London, Jack", "Call of the Wild, The");
      titles.Add("Shakespeare, William", "Tempest, The");

      Console.WriteLine("Author and Title List");
      Console.WriteLine($"\n{"Author",-25}    {"Title",30}\n");
      foreach (var title in titles)
         Console.WriteLine($"{title.Key,-25}     {title.Value,30}");
   }
}
```
    
<span data-ttu-id="45e64-167">I nomi degli autori vengono allineati a sinistra e i titoli da loro scritti sono allineati a destra.</span><span class="sxs-lookup"><span data-stu-id="45e64-167">The names of authors are left-aligned, and the titles they wrote are right-aligned.</span></span> <span data-ttu-id="45e64-168">Per specificare l'allineamento aggiungere una virgola (",") dopo l'espressione e quindi indicare la larghezza del campo.</span><span class="sxs-lookup"><span data-stu-id="45e64-168">You specify the alignment by adding a comma (",") after the expression and designating the field width.</span></span> <span data-ttu-id="45e64-169">Se la larghezza del campo è un numero positivo, il campo è allineato a destra:</span><span class="sxs-lookup"><span data-stu-id="45e64-169">If the field width is a positive number, the field is right-aligned:</span></span>

```text
{expression, width}
```

<span data-ttu-id="45e64-170">Se la larghezza del campo è un numero negativo, il campo è allineato a sinistra:</span><span class="sxs-lookup"><span data-stu-id="45e64-170">If the field width is a negative number, the field is left-aligned:</span></span>

```text
{expression, -width}
```

<span data-ttu-id="45e64-171">Provare a rimuovere il segno negativo dalle espressioni interpolate `{"Author",-25}` e `{title.Key,-25}` ed eseguire di nuovo l'esempio, come indicato dal codice seguente:</span><span class="sxs-lookup"><span data-stu-id="45e64-171">Try removing the negative signs from the `{"Author",-25}` and `{title.Key,-25}` interpolated expressions and run the example again, as the following code does:</span></span>

```csharp
Console.WriteLine($"\n{"Author",-25}    {"Title",30}\n");
foreach (var title in titles)
   Console.WriteLine($"{title.Key,-25}     {title.Value,30}");
```

<span data-ttu-id="45e64-172">Questa volta le informazioni sull'autore sono allineate a destra.</span><span class="sxs-lookup"><span data-stu-id="45e64-172">This time, the author information is right-aligned.</span></span>

<span data-ttu-id="45e64-173">È possibile combinare una larghezza di campo e una stringa di formato in un'unica espressione interpolata.</span><span class="sxs-lookup"><span data-stu-id="45e64-173">You can combine a field width and a format string in a single interpolated expression.</span></span> <span data-ttu-id="45e64-174">Immettere prima la larghezza del campo, seguita dai due punti e dalla stringa di formato.</span><span class="sxs-lookup"><span data-stu-id="45e64-174">The field width comes first, followed by a colon and the format string.</span></span> <span data-ttu-id="45e64-175">Sostituire tutto il codice nel metodo `Main` con il codice seguente, che consente di visualizzare tre stringhe formattate con le larghezze di campo definite.</span><span class="sxs-lookup"><span data-stu-id="45e64-175">Replace all of the code inside the `Main` method with the following code, which displays three formatted strings with defined field widths.</span></span> <span data-ttu-id="45e64-176">A questo punto eseguire il programma immettendo il comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="45e64-176">Then run the program by entering the `dotnet run` command.</span></span>

```csharp
Console.WriteLine($"{DateTime.Now,-20:d} Hour {DateTime.Now,-10:HH} {1063.342,15:N2} feet");
```
<span data-ttu-id="45e64-177">L'output è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="45e64-177">The output looks something like the following:</span></span>

```console
1/11/2018            Hour 09                1,063.34 feet
```

<span data-ttu-id="45e64-178">È stata completata la guida introduttiva per le stringhe interpolate.</span><span class="sxs-lookup"><span data-stu-id="45e64-178">You've completed the interpolated strings quick start.</span></span> 
    
<span data-ttu-id="45e64-179">È possibile continuare con la guida introduttiva [Matrici e raccolte](arrays-and-collections.md) nel proprio ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="45e64-179">You can continue with the [Arrays and collections](arrays-and-collections.md) quick start in your own development environment.</span></span>

<span data-ttu-id="45e64-180">Per altre informazioni sull'uso delle stringhe interpolate, vedere l'argomento [Stringhe interpolate](../language-reference/keywords/interpolated-strings.md) nei Riferimenti per C#.</span><span class="sxs-lookup"><span data-stu-id="45e64-180">You can learn more about working with interpolated strings in the [Interpolated Strings](../language-reference/keywords/interpolated-strings.md) topic in the C# Reference.</span></span>


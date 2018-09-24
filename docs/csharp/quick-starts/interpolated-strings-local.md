---
title: Esercitazione sull'interpolazione di stringhe - Guide introduttive locali per C#
description: Questa guida introduttiva illustrato come usare la funzionalità di interpolazione delle stringhe in C# per includere i risultati dell'espressione formattata in una stringa più grande.
author: rpetrusha
ms.author: ronpet
ms.date: 04/14/2018
ms.custom: mvc
ms.openlocfilehash: da111790ebbc299df16297650347045b9395a90f
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46580694"
---
# <a name="string-interpolation"></a><span data-ttu-id="928d3-103">Interpolazione di stringhe</span><span class="sxs-lookup"><span data-stu-id="928d3-103">String interpolation</span></span>

<span data-ttu-id="928d3-104">Questa guida introduttiva illustra come usare l'[interpolazione di stringhe](../language-reference/tokens/interpolated.md) in C# per inserire i valori in un'unica stringa di risultato.</span><span class="sxs-lookup"><span data-stu-id="928d3-104">This quickstart teaches you how to use C# [string interpolation](../language-reference/tokens/interpolated.md) to insert values into a single result string.</span></span> <span data-ttu-id="928d3-105">Verranno descritte le procedure per scrivere codice C# e visualizzare i risultati della compilazione ed esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="928d3-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="928d3-106">La guida introduttiva include una serie di lezioni che spiegano come inserire i valori in una stringa e applicare formattazioni diverse a tali valori.</span><span class="sxs-lookup"><span data-stu-id="928d3-106">The quickstart contains a series of lessons that show you how to insert values into a string and format those values in different ways.</span></span>

<span data-ttu-id="928d3-107">Questa guida introduttiva richiede un computer da usare per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="928d3-107">This quickstart expects that you have a machine you can use for development.</span></span> <span data-ttu-id="928d3-108">L'argomento [Get started with .NET in 10 minutes](https://www.microsoft.com/net/core) (Iniziare a usare .NET in 10 minuti) contiene istruzioni per la configurazione dell'ambiente di sviluppo locale in Mac, PC o Linux.</span><span class="sxs-lookup"><span data-stu-id="928d3-108">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="928d3-109">Una breve panoramica dei comandi usati è disponibile nell'[introduzione alle guide introduttive locali](local-environment.md) che contiene anche collegamenti ad altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="928d3-109">A quick overview of the commands you'll use is in the [introduction to the local quickstarts](local-environment.md) with links to more details.</span></span> <span data-ttu-id="928d3-110">È anche possibile completare la [versione interattiva](interpolated-strings.yml) di questa guida introduttiva nel browser.</span><span class="sxs-lookup"><span data-stu-id="928d3-110">You also can complete the [interactive version](interpolated-strings.yml) of this quickstart in your browser.</span></span>

## <a name="create-an-interpolated-string"></a><span data-ttu-id="928d3-111">Creare una stringa interpolata</span><span class="sxs-lookup"><span data-stu-id="928d3-111">Create an interpolated string</span></span>

<span data-ttu-id="928d3-112">Creare una directory denominata **interpolated**.</span><span class="sxs-lookup"><span data-stu-id="928d3-112">Create a directory named **interpolated**.</span></span> <span data-ttu-id="928d3-113">Impostarla come directory corrente ed eseguire il comando seguente da una finestra della console:</span><span class="sxs-lookup"><span data-stu-id="928d3-113">Make it the current directory and run the following command from a console window:</span></span>

```console
dotnet new console
```

<span data-ttu-id="928d3-114">Questo comando crea una nuova applicazione console .NET Core nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="928d3-114">This command creates a new .NET Core console application in the current directory.</span></span>

<span data-ttu-id="928d3-115">Aprire **Program.cs** nell'editor preferito e sostituire la riga `Console.WriteLine("Hello World!");` con il codice seguente, sostituendo `<name>` con il nome:</span><span class="sxs-lookup"><span data-stu-id="928d3-115">Open **Program.cs** in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code, where you replace `<name>` with your name:</span></span>

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```

<span data-ttu-id="928d3-116">Per provare questo codice, digitare `dotnet run` nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="928d3-116">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="928d3-117">Quando si esegue il programma viene visualizzata un'unica stringa contenente un messaggio di saluto che include il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="928d3-117">When you run the program, it displays a single string that includes your name in the greeting.</span></span> <span data-ttu-id="928d3-118">La stringa inclusa nella chiamata al metodo <xref:System.Console.WriteLine%2A> è una *stringa interpolata*.</span><span class="sxs-lookup"><span data-stu-id="928d3-118">The string included in the <xref:System.Console.WriteLine%2A> method call is an *interpolated string*.</span></span> <span data-ttu-id="928d3-119">Si tratta di un tipo di modello che consente di costruire un'unica stringa detta *stringa di risultato* da una stringa che include codice incorporato.</span><span class="sxs-lookup"><span data-stu-id="928d3-119">It's a kind of template that lets you construct a single string (called the *result string*) from a string that includes embedded code.</span></span> <span data-ttu-id="928d3-120">Le stringhe interpolate sono particolarmente utili per inserire valori in una stringa o per concatenare (unire) più stringhe.</span><span class="sxs-lookup"><span data-stu-id="928d3-120">Interpolated strings are particularly useful for inserting values into a string or concatenating (joining together) strings.</span></span>

<span data-ttu-id="928d3-121">Questo semplice esempio contiene i due elementi che devono essere presenti in ogni stringa interpolata:</span><span class="sxs-lookup"><span data-stu-id="928d3-121">This simple example contains the two elements that every interpolated string must have:</span></span>

- <span data-ttu-id="928d3-122">Un valore letterale stringa che inizia con il carattere `$` prima delle virgolette inglesi aperte.</span><span class="sxs-lookup"><span data-stu-id="928d3-122">A string literal that begins with the `$` character before its opening quotation mark character.</span></span> <span data-ttu-id="928d3-123">Tra il simbolo `$` e le virgolette non devono essere presenti spazi.</span><span class="sxs-lookup"><span data-stu-id="928d3-123">There can't be any spaces between the `$` symbol and the quotation mark character.</span></span> <span data-ttu-id="928d3-124">Se si vuole vedere cosa accade se ne viene incluso uno, inserire uno spazio dopo il carattere `$`, salvare il file ed eseguire nuovamente il programma digitando `dotnet run` nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="928d3-124">(If you'd like to see what happens if you include one, insert a space after the `$` character, save the file, and run the program again by typing `dotnet run` in the console window.</span></span> <span data-ttu-id="928d3-125">Il compilatore C# visualizza un messaggio di errore "errore CS1056: Carattere '$'" imprevisto).</span><span class="sxs-lookup"><span data-stu-id="928d3-125">The C# compiler displays an error message, "error CS1056: Unexpected character '$'".)</span></span>

- <span data-ttu-id="928d3-126">Una o più *espressioni interpolate*.</span><span class="sxs-lookup"><span data-stu-id="928d3-126">One or more *interpolated expressions*.</span></span> <span data-ttu-id="928d3-127">Un'espressione interpolata è indicata tra parentesi graffe di apertura e chiusura (`{` e `}`).</span><span class="sxs-lookup"><span data-stu-id="928d3-127">An interpolated expression is indicated by an opening and closing brace (`{` and `}`).</span></span> <span data-ttu-id="928d3-128">All'interno delle parentesi graffe è possibile inserire qualsiasi espressione C# che restituisce un valore, incluso `null`.</span><span class="sxs-lookup"><span data-stu-id="928d3-128">You can put any C# expression that returns a value (including `null`) inside the braces.</span></span>

<span data-ttu-id="928d3-129">Ora si proveranno altri esempi di interpolazione di stringhe con altri tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="928d3-129">Let's try a few more string interpolation examples with some other data types.</span></span>

## <a name="include-different-data-types"></a><span data-ttu-id="928d3-130">Includere tipi di dati diversi</span><span class="sxs-lookup"><span data-stu-id="928d3-130">Include different data types</span></span>

<span data-ttu-id="928d3-131">Nella sezione precedente è stata usata l'interpolazione di stringhe per inserire una stringa in un'altra.</span><span class="sxs-lookup"><span data-stu-id="928d3-131">In the previous section, you used string interpolation to insert one string inside of another.</span></span> <span data-ttu-id="928d3-132">Il risultato di un'espressione interpolata può avere qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="928d3-132">The result of an interpolated expression can be of any data type, though.</span></span> <span data-ttu-id="928d3-133">Includiamo valori di vari tipi di dati in una stringa interpolata.</span><span class="sxs-lookup"><span data-stu-id="928d3-133">Let's include values of various data types in an interpolated string.</span></span>

<span data-ttu-id="928d3-134">Nell'esempio seguente, in primo luogo, viene definito un tipo di dati [class](../programming-guide/classes-and-structs/classes.md) `Vegetable` con la [proprietà](../properties.md) `Name` e il [metodo](../methods.md) `ToString` che esegue l'[override](../language-reference/keywords/override.md) del comportamento del metodo <xref:System.Object.ToString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="928d3-134">In the following example, first, we define a [class](../programming-guide/classes-and-structs/classes.md) data type `Vegetable` that has the `Name` [property](../properties.md) and the `ToString` [method](../methods.md), which [overrides](../language-reference/keywords/override.md) the behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="928d3-135">Il [modificatore di accesso `public`](../language-reference/keywords/public.md) rende tale metodo disponibile per qualsiasi codice client per ottenere la rappresentazione stringa di un'istanza di `Vegetable`.</span><span class="sxs-lookup"><span data-stu-id="928d3-135">The [`public` access modifier](../language-reference/keywords/public.md) makes that method available to any client code to get the string representation of a `Vegetable` instance.</span></span> <span data-ttu-id="928d3-136">Nell'esempio il metodo `Vegetable.ToString` restituisce il valore della proprietà `Name` inizializzata nel [costruttore](../programming-guide/classes-and-structs/constructors.md) `Vegetable`:</span><span class="sxs-lookup"><span data-stu-id="928d3-136">In the example the `Vegetable.ToString` method returns the value of the `Name` property that is initialized at the `Vegetable` [constructor](../programming-guide/classes-and-structs/constructors.md):</span></span>

```csharp
public Vegetable(string name) => Name = name;
```

<span data-ttu-id="928d3-137">Viene quindi creata un'istanza della classe `Vegetable` usando la [parola chiave `new`](../language-reference/keywords/new-operator.md)e fornendo un parametro di nome per il costruttore `Vegetable`:</span><span class="sxs-lookup"><span data-stu-id="928d3-137">Then we create an instance of the `Vegetable` class by using [`new` keyword](../language-reference/keywords/new-operator.md) and providing a name parameter for the constructor `Vegetable`:</span></span>

```csharp
var item = new Vegetable("eggplant");
```

<span data-ttu-id="928d3-138">Infine, includere la variabile `item` in una stringa interpolata che contenga anche un valore <xref:System.DateTime>, un valore <xref:System.Decimal> e un valore di [enumerazione](../programming-guide/enumeration-types.md)`Unit`.</span><span class="sxs-lookup"><span data-stu-id="928d3-138">Finally, we include the `item` variable into an interpolated string that also contains a <xref:System.DateTime> value, a <xref:System.Decimal> value, and a `Unit` [enumeration](../programming-guide/enumeration-types.md) value.</span></span> <span data-ttu-id="928d3-139">Sostituire tutto il codice C# in un editor con il codice seguente e usare il comando `dotnet run` per l'eseguirlo:</span><span class="sxs-lookup"><span data-stu-id="928d3-139">Replace all of the C# code in your editor with the following code, and then use the `dotnet run` command to run it:</span></span>

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;
   
   public string Name { get; }
   
   public override string ToString() => Name;
}

public class Program
{
   public enum Unit { item, kilogram, gram, dozen };

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

<span data-ttu-id="928d3-140">L'espressione interpolata `item` nella stringa interpolata restituisce il testo "eggplant" nella stringa di risultato.</span><span class="sxs-lookup"><span data-stu-id="928d3-140">Note that the interpolated expression `item` in the interpolated string resolves to the text "eggplant" in the result string.</span></span> <span data-ttu-id="928d3-141">Questo accade perché, quando il tipo di risultato dell'espressione non è una stringa, il risultato restituisce una stringa nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="928d3-141">That's because, when the type of the expression result is not a string, the result is resolved to a string in the following way:</span></span>

- <span data-ttu-id="928d3-142">Se l'espressione interpolata restituisce `null`, viene usata una stringa vuota ("" o <xref:System.String.Empty?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="928d3-142">If the interpolated expression evaluates to `null`, an empty string ("", or <xref:System.String.Empty?displayProperty=nameWithType>) is used.</span></span>

- <span data-ttu-id="928d3-143">Se l'espressione interpolata non restituisce `null`, in genere viene chiamato il metodo `ToString` del tipo di risultato.</span><span class="sxs-lookup"><span data-stu-id="928d3-143">If the interpolated expression doesn't evaluate to `null`, typically the `ToString` method of the result type is called.</span></span> <span data-ttu-id="928d3-144">È possibile testare questo processo aggiornando l'implementazione del metodo `Vegetable.ToString`.</span><span class="sxs-lookup"><span data-stu-id="928d3-144">You can test this by updating the implementation of the `Vegetable.ToString` method.</span></span> <span data-ttu-id="928d3-145">Potrebbe anche non essere necessario implementare il metodo `ToString`, poiché ogni tipo prevede un'implementazione di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="928d3-145">You might not even need to implement the `ToString` method since every type has some implementation of this method.</span></span> <span data-ttu-id="928d3-146">Per il test di questo funzionamento, impostare come commento la definizione del metodo `Vegetable.ToString` nell'esempio (facendola precedere dal simbolo di commento `//`).</span><span class="sxs-lookup"><span data-stu-id="928d3-146">To test this, comment out the definition of the `Vegetable.ToString` method in the example (to do that, put a comment symbol, `//`, in front of it).</span></span> <span data-ttu-id="928d3-147">Nell'output la stringa "eggplant" viene sostituita dal nome completo del tipo ("Vegetable" in questo esempio), ovvero il comportamento predefinito del metodo <xref:System.Object.ToString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="928d3-147">In the output, the string "eggplant" is replaced by the fully qualified type name ("Vegetable" in this example), which is the default behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="928d3-148">Il comportamento predefinito del metodo `ToString` per un tipo di enumerazione prevede la restituzione della rappresentazione stringa di un valore usato nella definizione dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="928d3-148">The default behavior of the `ToString` method for an enumeration value is to return the string representation of the value.</span></span>

<span data-ttu-id="928d3-149">Nell'output di questo esempio la data è troppo precisa (il prezzo delle melanzane non varia ogni secondo) e il valore del prezzo non indica una valuta.</span><span class="sxs-lookup"><span data-stu-id="928d3-149">In the output from this example, the date is too precise (the price of eggplant doesn't change every second), and the price value doesn't indicate a unit of currency.</span></span> <span data-ttu-id="928d3-150">Nella sezione successiva si apprenderà come risolvere questi problemi controllando la formattazione delle rappresentazioni di stringa dei risultati delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="928d3-150">In the next section, you'll learn how to fix those issues by controlling the format of string representations of the expression results.</span></span>

## <a name="control-the-formatting-of-interpolated-expressions"></a><span data-ttu-id="928d3-151">Controllare la formattazione delle espressioni interpolate</span><span class="sxs-lookup"><span data-stu-id="928d3-151">Control the formatting of interpolated expressions</span></span>

<span data-ttu-id="928d3-152">Nella sezione precedente sono state inserite nella stringa di risultato due stringhe con formattazione non valida.</span><span class="sxs-lookup"><span data-stu-id="928d3-152">In the previous section, two poorly formatted strings were inserted into the result string.</span></span> <span data-ttu-id="928d3-153">Il primo problema è un valore di data e ora nel quale solo la data risultava corretta.</span><span class="sxs-lookup"><span data-stu-id="928d3-153">One was a date and time value for which only the date was appropriate.</span></span> <span data-ttu-id="928d3-154">Il secondo è un prezzo che non indica la valuta.</span><span class="sxs-lookup"><span data-stu-id="928d3-154">The second was a price that didn't indicate its unit of currency.</span></span> <span data-ttu-id="928d3-155">Entrambi i problemi sono di facile risoluzione.</span><span class="sxs-lookup"><span data-stu-id="928d3-155">Both issues are easy to address.</span></span> <span data-ttu-id="928d3-156">L'interpolazione di stringhe consente di specificare *stringhe di formato* che controllano la formattazione di determinati tipi.</span><span class="sxs-lookup"><span data-stu-id="928d3-156">String interpolation lets you specify *format strings* that control the formatting of particular types.</span></span> <span data-ttu-id="928d3-157">Modificare la chiamata in `Console.WriteLine` dell'esempio precedente in modo da includere le stringhe di formato per le espressioni di data e prezzo, come indicato nella riga seguente:</span><span class="sxs-lookup"><span data-stu-id="928d3-157">Modify the call to `Console.WriteLine` from the previous example to include the format strings for the date and price expressions as shown in the following line:</span></span>

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```

<span data-ttu-id="928d3-158">Per specificare una stringa di formato, far seguire all'espressione interpolata i due punti (":") e la stringa di formato desiderata.</span><span class="sxs-lookup"><span data-stu-id="928d3-158">You specify a format string by following the interpolated expression with a colon (":") and the format string.</span></span> <span data-ttu-id="928d3-159">"d" è un [stringa di formato data e ora standard](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) che rappresenta il formato di data breve.</span><span class="sxs-lookup"><span data-stu-id="928d3-159">"d" is a [standard date and time format string](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) that represents the short date format.</span></span> <span data-ttu-id="928d3-160">"C2" è un [stringa di formato numerico standard](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) che rappresenta un numero come valore di valuta con due cifre dopo il separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="928d3-160">"C2" is a  [standard numeric format string](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) that represents a number as a currency value with two digits after the decimal point.</span></span>

<span data-ttu-id="928d3-161">Molti tipi delle librerie .NET supportano un set predefinito di stringhe di formato.</span><span class="sxs-lookup"><span data-stu-id="928d3-161">A number of types in the .NET libraries support a predefined set of format strings.</span></span> <span data-ttu-id="928d3-162">Tali tipi includono tutti i tipi numerici e i tipi data e ora.</span><span class="sxs-lookup"><span data-stu-id="928d3-162">These include all the numeric types and the date and time types.</span></span> <span data-ttu-id="928d3-163">Per l'elenco completo dei tipi che supportano le stringhe di formato, vedere [Stringhe di formato e tipi della libreria di classe .NET](../../standard/base-types/formatting-types.md#stringRef) nell'articolo [Formattazione di tipi in .NET](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="928d3-163">For a complete list of types that support format strings, see [Format Strings and .NET Class Library Types](../../standard/base-types/formatting-types.md#stringRef) in the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) article.</span></span>

<span data-ttu-id="928d3-164">Provare a modificare le stringhe di formato nell'editor di testo ed eseguire nuovamente il programma ogni volta che si apporta una modifica, per verificare l'effetto delle modifiche sulla formattazione di data, ora e valore numerico.</span><span class="sxs-lookup"><span data-stu-id="928d3-164">Try modifying the format strings in your text editor and, each time you make a change, rerun the program to see how the changes affect the formatting of the date and time and the numeric value.</span></span> <span data-ttu-id="928d3-165">Modificare il valore "d" in `{date:d}` inserendo i valori "t" (per visualizzare il formato ora breve), "y" (per visualizzare anno e mese) e "yyyy" (per visualizzare l'anno come numero a quattro cifre).</span><span class="sxs-lookup"><span data-stu-id="928d3-165">Change the "d" in `{date:d}` to "t" (to display the short time format), "y" (to display the year and month), and "yyyy" (to display the year as a four-digit number).</span></span> <span data-ttu-id="928d3-166">Modificare "C2" in `{price:C2}` inserendo "e" (per la notazione esponenziale) e "F3" (per un valore numerico con tre cifre dopo il separatore decimale).</span><span class="sxs-lookup"><span data-stu-id="928d3-166">Change the "C2" in `{price:C2}` to "e" (for exponential notation) and "F3" (for a numeric value with three digits after the decimal point).</span></span>

<span data-ttu-id="928d3-167">Oltre alla formattazione è possibile controllare la larghezza del campo e l'allineamento delle stringhe formattate incluse nella stringa di risultato.</span><span class="sxs-lookup"><span data-stu-id="928d3-167">In addition to controlling formatting, you can also control the field width and alignment of the formatted strings that are included in the result string.</span></span> <span data-ttu-id="928d3-168">La sezione successiva spiega come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="928d3-168">In the next section, you'll learn how to do this.</span></span>

## <a name="control-the-field-width-and-alignment-of-interpolated-expressions"></a><span data-ttu-id="928d3-169">Controllare la larghezza del campo e l'allineamento delle espressioni interpolate</span><span class="sxs-lookup"><span data-stu-id="928d3-169">Control the field width and alignment of interpolated expressions</span></span>

<span data-ttu-id="928d3-170">In genere quando il risultato di un'espressione interpolata è formattato in una stringa, questa viene inclusa in una stringa di risultato senza spazi iniziali o finali.</span><span class="sxs-lookup"><span data-stu-id="928d3-170">Ordinarily, when the result of an interpolated expression is formatted to string, that string is included in a result string without leading or trailing spaces.</span></span> <span data-ttu-id="928d3-171">In particolare quando si usa un set di dati, la possibilità di controllare la larghezza di un campo e l'allineamento del testo consente di generare un output più leggibile.</span><span class="sxs-lookup"><span data-stu-id="928d3-171">Particularly when you work with a set of data, being able to control a field width and text alignment helps to produce a more readable output.</span></span> <span data-ttu-id="928d3-172">Per verificare, sostituire tutto il codice nell'editor di testo con il codice seguente e digitare `dotnet run` per eseguire il programma:</span><span class="sxs-lookup"><span data-stu-id="928d3-172">To see this, replace all the code in your text editor with the following code, then type `dotnet run` to execute the program:</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>()
      {
          ["Doyle, Arthur Conan"] = "Hound of the Baskervilles, The",
          ["London, Jack"] = "Call of the Wild, The",
          ["Shakespeare, William"] = "Tempest, The"
      };

      Console.WriteLine("Author and Title List");
      Console.WriteLine();
      Console.WriteLine($"|{"Author",-25}|{"Title",30}|");
      foreach (var title in titles)
         Console.WriteLine($"|{title.Key,-25}|{title.Value,30}|");
   }
}
```

<span data-ttu-id="928d3-173">I nomi degli autori vengono allineati a sinistra e i titoli da loro scritti sono allineati a destra.</span><span class="sxs-lookup"><span data-stu-id="928d3-173">The names of authors are left-aligned, and the titles they wrote are right-aligned.</span></span> <span data-ttu-id="928d3-174">Per specificare l'allineamento, aggiungere una virgola (",") dopo un'espressione interpolata e indicare la larghezza *minima* del campo.</span><span class="sxs-lookup"><span data-stu-id="928d3-174">You specify the alignment by adding a comma (",") after an interpolated expression and designating the *minimum* field width.</span></span> <span data-ttu-id="928d3-175">Se il valore specificato è un numero positivo, il campo è allineato a destra.</span><span class="sxs-lookup"><span data-stu-id="928d3-175">If the specified value is a positive number, the field is right-aligned.</span></span> <span data-ttu-id="928d3-176">Se è un numero negativo, il campo è allineato a sinistra.</span><span class="sxs-lookup"><span data-stu-id="928d3-176">If it is a negative number, the field is left-aligned.</span></span>

<span data-ttu-id="928d3-177">Provare a rimuovere il segno negativo dal codice `{"Author",-25}` e `{title.Key,-25}` ed eseguire di nuovo l'esempio, come indicato dal codice seguente:</span><span class="sxs-lookup"><span data-stu-id="928d3-177">Try removing the negative signs from the `{"Author",-25}` and `{title.Key,-25}` code and run the example again, as the following code does:</span></span>

```csharp
Console.WriteLine($"|{"Author",25}|{"Title",30}|");
foreach (var title in titles)
   Console.WriteLine($"|{title.Key,25}|{title.Value,30}|");
```

<span data-ttu-id="928d3-178">Questa volta le informazioni sull'autore sono allineate a destra.</span><span class="sxs-lookup"><span data-stu-id="928d3-178">This time, the author information is right-aligned.</span></span>

<span data-ttu-id="928d3-179">È possibile combinare un identificatore di allineamento e una stringa di formato per un'unica espressione interpolata.</span><span class="sxs-lookup"><span data-stu-id="928d3-179">You can combine an alignment specifier and a format string for a single interpolated expression.</span></span> <span data-ttu-id="928d3-180">A tale scopo, specificare prima l'allineamento, seguito da due punti e dalla stringa di formato.</span><span class="sxs-lookup"><span data-stu-id="928d3-180">To do that, specify the alignment first, followed by a colon and the format string.</span></span> <span data-ttu-id="928d3-181">Sostituire tutto il codice nel metodo `Main` con il codice seguente, che consente di visualizzare tre stringhe formattate con le larghezze di campo definite.</span><span class="sxs-lookup"><span data-stu-id="928d3-181">Replace all of the code inside the `Main` method with the following code, which displays three formatted strings with defined field widths.</span></span> <span data-ttu-id="928d3-182">A questo punto eseguire il programma immettendo il comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="928d3-182">Then run the program by entering the `dotnet run` command.</span></span>

```csharp
Console.WriteLine($"[{DateTime.Now,-20:d}] Hour [{DateTime.Now,-10:HH}] [{1063.342,15:N2}] feet");
```

<span data-ttu-id="928d3-183">L'output è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="928d3-183">The output looks something like the following:</span></span>

```console
[04/14/2018          ] Hour [16        ] [       1,063.34] feet
```

<span data-ttu-id="928d3-184">È stata completata la guida introduttiva all'interpolazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="928d3-184">You've completed the string interpolation quickstart.</span></span>

<span data-ttu-id="928d3-185">È possibile continuare con la guida introduttiva [Raccolte di elenchi](arrays-and-collections.md) nel proprio ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="928d3-185">You can continue with the [List collection](arrays-and-collections.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="928d3-186">Per altre informazioni, vedere l'argomento [Interpolazione di stringhe](../language-reference/tokens/interpolated.md) e l'esercitazione [Interpolazione di stringhe in C#](../tutorials/string-interpolation.md).</span><span class="sxs-lookup"><span data-stu-id="928d3-186">For more information, see the [String interpolation](../language-reference/tokens/interpolated.md) topic and the [String interpolation in C#](../tutorials/string-interpolation.md) tutorial.</span></span>

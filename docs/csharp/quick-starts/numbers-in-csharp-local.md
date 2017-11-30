---
title: Guida introduttiva - numeri in c# - c#
description: "Informazioni su c# esaminando i metodi, le proprietà e i tipi numerici."
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 821cca4ea6d6148410e9b179f05d5b74c4844628
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2017
---
# <a name="numbers-in-c-quick-start"></a><span data-ttu-id="eac6e-103">Numeri di avvio rapido di c#</span><span class="sxs-lookup"><span data-stu-id="eac6e-103">Numbers in C# quick start</span></span> #

<span data-ttu-id="eac6e-104">Questa Guida introduttiva illustra sui tipi di numero in c# in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="eac6e-104">This quick start teaches you about the number types in C# interactively.</span></span> <span data-ttu-id="eac6e-105">Si scriveranno piccole quantità di codice, quindi verrà compilare ed eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="eac6e-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="eac6e-106">La Guida introduttiva contiene una serie di lezioni progettate per esplorare i numeri e operazioni matematiche in c#.</span><span class="sxs-lookup"><span data-stu-id="eac6e-106">The quick start contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="eac6e-107">Queste lezioni presentano le nozioni fondamentali del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="eac6e-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="eac6e-108">Questa Guida introduttiva prevede di disporre di un computer in cui che è possibile utilizzare per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="eac6e-108">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="eac6e-109">L'argomento .NET [Introduzione a 10 minuti](https://www.microsoft.com/net/core) con le istruzioni per configurare l'ambiente di sviluppo locale in Mac, Linux o PC.</span><span class="sxs-lookup"><span data-stu-id="eac6e-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="eac6e-110">Esplorare le operazioni matematiche su interi</span><span class="sxs-lookup"><span data-stu-id="eac6e-110">Explore integer math</span></span>

<span data-ttu-id="eac6e-111">Creare una directory denominata **numeri quickstart**.</span><span class="sxs-lookup"><span data-stu-id="eac6e-111">Create a directory named **numbers-quickstart**.</span></span> <span data-ttu-id="eac6e-112">Impostarla come directory corrente ed eseguire `dotnet new console -n NumbersInCSharp -o .`.</span><span class="sxs-lookup"><span data-stu-id="eac6e-112">Make that the current directory and run `dotnet new console -n NumbersInCSharp -o .`.</span></span>

<span data-ttu-id="eac6e-113">Aprire **Program.cs** nel proprio editor preferito e sostituire la riga `Console.Writeline("Hello World!");` con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="eac6e-113">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following:</span></span>

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="eac6e-114">Eseguire questo codice digitando `dotnet run` nella finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="eac6e-114">Run this code by typing `dotnet run` in your command window.</span></span> 

<span data-ttu-id="eac6e-115">Questa è una delle operazioni matematiche fondamentali su interi.</span><span class="sxs-lookup"><span data-stu-id="eac6e-115">You've just seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="eac6e-116">Il tipo `int` rappresenta un **intero**, ovvero un numero intero positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="eac6e-116">The `int` type represents an **integer**, a positive or negative whole number.</span></span> <span data-ttu-id="eac6e-117">Per l'addizione si usa il simbolo `+`.</span><span class="sxs-lookup"><span data-stu-id="eac6e-117">You use the `+` symbol for addition.</span></span> <span data-ttu-id="eac6e-118">Altre operazioni matematiche comuni per gli interi includono:</span><span class="sxs-lookup"><span data-stu-id="eac6e-118">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="eac6e-119">`-` per la sottrazione</span><span class="sxs-lookup"><span data-stu-id="eac6e-119">`-` for subtraction</span></span>
- <span data-ttu-id="eac6e-120">`*` per la moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="eac6e-120">`*` for multiplication</span></span>
- <span data-ttu-id="eac6e-121">`/` per la divisione</span><span class="sxs-lookup"><span data-stu-id="eac6e-121">`/` for division</span></span>

<span data-ttu-id="eac6e-122">Per iniziare, esplorare le diverse operazioni.</span><span class="sxs-lookup"><span data-stu-id="eac6e-122">Start by exploring those different operations.</span></span> <span data-ttu-id="eac6e-123">Aggiungere queste righe dopo la riga che scrive il valore del `c`:</span><span class="sxs-lookup"><span data-stu-id="eac6e-123">Add these lines after the line that writes the value of `c`:</span></span>

```csharp
c = a - b;
Console.WriteLine(c);
c = a * b;
Console.WriteLine(c);
c = a / b;
Console.WriteLine(c);
```

<span data-ttu-id="eac6e-124">Eseguire questo codice digitando `dotnet run` nella finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="eac6e-124">Run this code by typing `dotnet run` in your command window.</span></span> 
    
<span data-ttu-id="eac6e-125">È anche possibile sperimentare eseguendo più operazioni matematiche nella stessa riga.</span><span class="sxs-lookup"><span data-stu-id="eac6e-125">You can also experiment by performing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="eac6e-126">Provare a `c = a + b - 12 * 17;` , ad esempio.</span><span class="sxs-lookup"><span data-stu-id="eac6e-126">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="eac6e-127">La combinazione di variabili e i numeri di costanti è consentita.</span><span class="sxs-lookup"><span data-stu-id="eac6e-127">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="eac6e-128">Mentre si impara a usare C# (o qualsiasi linguaggio di programmazione) sicuramente si commetteranno errori durante la scrittura del codice.</span><span class="sxs-lookup"><span data-stu-id="eac6e-128">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="eac6e-129">Il **compilatore** troverà questi errori e li segnalerà.</span><span class="sxs-lookup"><span data-stu-id="eac6e-129">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="eac6e-130">Quando l'output contiene i messaggi di errore, esaminare attentamente il codice di esempio e il codice nella finestra per visualizzare gli elementi da correggere.</span><span class="sxs-lookup"><span data-stu-id="eac6e-130">When the output contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span>
> <span data-ttu-id="eac6e-131">Questo esercizio sarà utile per imparare la struttura del codice C#.</span><span class="sxs-lookup"><span data-stu-id="eac6e-131">That exercise will help you learn the structure of C# code.</span></span>     

<span data-ttu-id="eac6e-132">Il primo passaggio per volta.</span><span class="sxs-lookup"><span data-stu-id="eac6e-132">You've finished the first step.</span></span> <span data-ttu-id="eac6e-133">Prima di iniziare la sezione successiva, è necessario spostare il codice corrente in un metodo separato.</span><span class="sxs-lookup"><span data-stu-id="eac6e-133">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="eac6e-134">In questo modo sarà più semplice iniziare a lavorare con un nuovo esempio.</span><span class="sxs-lookup"><span data-stu-id="eac6e-134">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="eac6e-135">Rinominare il metodo `Main` in `WorkingWithIntegers` e scrivere un nuovo metodo `Main` che chiama `WorkingWithIntegers`.</span><span class="sxs-lookup"><span data-stu-id="eac6e-135">Rename your `Main` method to `WorkingWithIntegers` and write a new `Main` method that calls `WorkingWithIntegers`.</span></span> <span data-ttu-id="eac6e-136">Al termine, il codice dovrebbe risultare simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="eac6e-136">When you have finished, your code should look like this:</span></span>

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;
            int c = a + b;
            Console.WriteLine(c);
            c = a - b;
            Console.WriteLine(c);
            c = a * b;
            Console.WriteLine(c);
            c = a / b;
            Console.WriteLine(c);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();
        }
    }
}
```

## <a name="explore-order-of-operations"></a><span data-ttu-id="eac6e-137">Esplorare l'ordine delle operazioni</span><span class="sxs-lookup"><span data-stu-id="eac6e-137">Explore order of operations</span></span>

<span data-ttu-id="eac6e-138">Commentare la chiamata a `WorkingWithIntegers()`.</span><span class="sxs-lookup"><span data-stu-id="eac6e-138">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="eac6e-139">L'output che meno pieno di informazioni mentre si lavora in questa sezione sarà:</span><span class="sxs-lookup"><span data-stu-id="eac6e-139">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkingWithIntegers();
```

<span data-ttu-id="eac6e-140">Il `//` avvia un **commento** in c#.</span><span class="sxs-lookup"><span data-stu-id="eac6e-140">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="eac6e-141">I commenti sono qualsiasi testo che si desidera mantenere nel codice sorgente, ma non è stato eseguito come codice.</span><span class="sxs-lookup"><span data-stu-id="eac6e-141">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="eac6e-142">Il compilatore non genera codice eseguibile da commenti.</span><span class="sxs-lookup"><span data-stu-id="eac6e-142">The compiler does not generate any executable code from comments.</span></span>

<span data-ttu-id="eac6e-143">Il linguaggio C# stabilisce un ordine di precedenza per le diverse operazioni matematiche, con regole coerenti con quelle della matematica.</span><span class="sxs-lookup"><span data-stu-id="eac6e-143">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span>
<span data-ttu-id="eac6e-144">La moltiplicazione e la divisione hanno la precedenza rispetto ad addizione e sottrazione.</span><span class="sxs-lookup"><span data-stu-id="eac6e-144">Multiplication and division take precedence over addition and subtraction.</span></span>
<span data-ttu-id="eac6e-145">Esplorare che aggiungendo il codice seguente per il `Main` metodo ed execuing `dotnet run`:</span><span class="sxs-lookup"><span data-stu-id="eac6e-145">Explore that by adding the following code to your `Main` method, and execuing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="eac6e-146">L'output dimostra che la moltiplicazione viene eseguita prima dell'addizione.</span><span class="sxs-lookup"><span data-stu-id="eac6e-146">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="eac6e-147">È possibile forzare un ordine diverso dell'operazione mediante l'aggiunta di parentesi per racchiudere l'operazione o le operazioni eseguite per prime.</span><span class="sxs-lookup"><span data-stu-id="eac6e-147">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="eac6e-148">Aggiungere le seguenti righe ed eseguire di nuovo:</span><span class="sxs-lookup"><span data-stu-id="eac6e-148">Add the following lines and run again:</span></span>

```csharp
d = (a  + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="eac6e-149">Sperimentare ulteriormente combinando molte operazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="eac6e-149">Explore more by combining many different operations.</span></span> <span data-ttu-id="eac6e-150">Aggiungi le seguenti righe in fondo il `Main` metodo.</span><span class="sxs-lookup"><span data-stu-id="eac6e-150">Add something like the following lines at the bottom of your `Main` method.</span></span> <span data-ttu-id="eac6e-151">Provare a `dotnet run` nuovamente.</span><span class="sxs-lookup"><span data-stu-id="eac6e-151">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="eac6e-152">È possibile che si sia notato un comportamento interessante per gli interi.</span><span class="sxs-lookup"><span data-stu-id="eac6e-152">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="eac6e-153">Divisione di interi sempre produce un risultato intero, anche quando ci si aspetta il risultato per includere una parte decimale o frazionaria.</span><span class="sxs-lookup"><span data-stu-id="eac6e-153">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="eac6e-154">Che significa che il problema, provare il codice seguente alla fine del `Main` metodo:</span><span class="sxs-lookup"><span data-stu-id="eac6e-154">If you haven't seen this behavior, try the following code at the end of your `Main` method:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="eac6e-155">Tipo `dotnet run` nuovamente per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="eac6e-155">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="eac6e-156">Prima di continuare, è opportuno tutto il codice è stato scritto in questa sezione e inserirlo in un nuovo metodo.</span><span class="sxs-lookup"><span data-stu-id="eac6e-156">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="eac6e-157">Chiamare il metodo nuovo `OrderPrecedence`.</span><span class="sxs-lookup"><span data-stu-id="eac6e-157">Call that new method `OrderPrecedence`.</span></span>
<span data-ttu-id="eac6e-158">Al termine con qualcosa di simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="eac6e-158">You should end up with something like this:</span></span>

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;
            int c = a + b;
            Console.WriteLine(c);
            c = a - b;
            Console.WriteLine(c);
            c = a * b;
            Console.WriteLine(c);
            c = a / b;
            Console.WriteLine(c);
        }

        static void OrderPrecedence()
        {   
            int a = 5;
            int b = 4;
            int c = 2;
            int d = a + b * c;
            Console.WriteLine(d);

            d = (a  + b) * c;
            Console.WriteLine(d);

            d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
            Console.WriteLine(d);

            int e = 7;
            int f = 4;
            int g = 3;
            int h = (e  + f) / g;
            Console.WriteLine(h);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();

            OrderPrecedence();

        }
    }
}
```

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="eac6e-159">Esplorare la precisione e i limiti delle operazioni su interi</span><span class="sxs-lookup"><span data-stu-id="eac6e-159">Explore integer precision and limits</span></span>
<span data-ttu-id="eac6e-160">L'ultimo esempio dimostra che la divisione di interi tronca il risultato.</span><span class="sxs-lookup"><span data-stu-id="eac6e-160">That last sample showed you that integer division truncates the result.</span></span>
<span data-ttu-id="eac6e-161">È possibile ottenere il **resto** utilizzando il **modulo** (operatore), il `%` carattere.</span><span class="sxs-lookup"><span data-stu-id="eac6e-161">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="eac6e-162">Provare il codice seguente nel `Main` metodo:</span><span class="sxs-lookup"><span data-stu-id="eac6e-162">Try the following code in your `Main` method:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a  + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="eac6e-163">Il tipo integer in C# è diverso dagli interi matematici per un altro aspetto, ovvero per il tipo `int` esistono limiti minimi e massimi.</span><span class="sxs-lookup"><span data-stu-id="eac6e-163">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="eac6e-164">Aggiungere questo codice per il `Main` metodo per visualizzare tali limiti:</span><span class="sxs-lookup"><span data-stu-id="eac6e-164">Add this code to your `Main` method to see those limits:</span></span>
    
```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="eac6e-165">Se un calcolo produce un valore che supera questi limiti, si genera una condizione di **underflow** o **overflow**.</span><span class="sxs-lookup"><span data-stu-id="eac6e-165">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="eac6e-166">La risposta sembra proseguire da un limite all'altro.</span><span class="sxs-lookup"><span data-stu-id="eac6e-166">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="eac6e-167">Aggiungere queste due righe per il `Main` metodo per vedere un esempio:</span><span class="sxs-lookup"><span data-stu-id="eac6e-167">Add these two lines to your `Main` method to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```
    
<span data-ttu-id="eac6e-168">Si noti che la risposta è molto vicina all'intero minimo (negativo).</span><span class="sxs-lookup"><span data-stu-id="eac6e-168">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="eac6e-169">È uguale a `min + 2`.</span><span class="sxs-lookup"><span data-stu-id="eac6e-169">It's the same as `min + 2`.</span></span> <span data-ttu-id="eac6e-170">L'operazione di addizione **ha causato l'overflow** dei valori consentiti per gli interi.</span><span class="sxs-lookup"><span data-stu-id="eac6e-170">The addition operation **overflowed** the allowed values for integers.</span></span>
<span data-ttu-id="eac6e-171">La risposta è un numero negativo molto grande, poiché un overflow "ritorna a capo" proseguendo dal valore intero più grande possibile a quello più piccolo.</span><span class="sxs-lookup"><span data-stu-id="eac6e-171">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="eac6e-172">Esistono altri tipi numerici con limiti e precisione diversi che è possibile usare quando il tipo `int` non soddisfa le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="eac6e-172">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="eac6e-173">Questi tipi verranno presentati nelle prossime lezioni.</span><span class="sxs-lookup"><span data-stu-id="eac6e-173">Let's explore those next.</span></span>

<span data-ttu-id="eac6e-174">In questo caso, si sposta il codice che scritto in questa sezione in un metodo separato.</span><span class="sxs-lookup"><span data-stu-id="eac6e-174">Once again, let's move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="eac6e-175">Assegnargli il nome `TestLimits`.</span><span class="sxs-lookup"><span data-stu-id="eac6e-175">Name it `TestLimits`.</span></span> 

## <a name="work-with-the-double-type"></a><span data-ttu-id="eac6e-176">Usare il tipo double</span><span class="sxs-lookup"><span data-stu-id="eac6e-176">Work with the double type</span></span>

<span data-ttu-id="eac6e-177">Il tipo numerico `double` rappresenta un numero a virgola mobile a precisione doppia.</span><span class="sxs-lookup"><span data-stu-id="eac6e-177">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="eac6e-178">Questi termini potrebbero risultare sconosciuti.</span><span class="sxs-lookup"><span data-stu-id="eac6e-178">Those terms may be new to you.</span></span> <span data-ttu-id="eac6e-179">Oggetto **a virgola mobile** è utile per rappresentare i numeri non integrale che possono essere molto grandi o piccole in termini di grandezza.</span><span class="sxs-lookup"><span data-stu-id="eac6e-179">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="eac6e-180">Il termine **precisione doppia** indica che questi numeri vengono archiviati con una maggiore precisione rispetto alla **precisione singola**.</span><span class="sxs-lookup"><span data-stu-id="eac6e-180">**Double-precision** means that these numbers are stored using greater precision than **single-precision**.</span></span> <span data-ttu-id="eac6e-181">Nei computer moderni è più comune usare i numeri a precisione doppia rispetto ai numeri a precisione singola.</span><span class="sxs-lookup"><span data-stu-id="eac6e-181">On modern computers, it is more common to use double precision than single precision numbers.</span></span>
<span data-ttu-id="eac6e-182">Per iniziare a esplorare questo tipo,</span><span class="sxs-lookup"><span data-stu-id="eac6e-182">Let's explore.</span></span> <span data-ttu-id="eac6e-183">Aggiungere il codice seguente e visualizzare i risultati:</span><span class="sxs-lookup"><span data-stu-id="eac6e-183">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a  + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="eac6e-184">Si noti che la risposta include la parte decimale del quoziente.</span><span class="sxs-lookup"><span data-stu-id="eac6e-184">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="eac6e-185">Provare ora un'espressione leggermente più complessa con valori double:</span><span class="sxs-lookup"><span data-stu-id="eac6e-185">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="eac6e-186">L'intervallo di un valore double è molto maggiore rispetto ai valori integer.</span><span class="sxs-lookup"><span data-stu-id="eac6e-186">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="eac6e-187">Provare a ciò che è stato scritto fino a questo punto il seguente codice:</span><span class="sxs-lookup"><span data-stu-id="eac6e-187">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="eac6e-188">Questi valori vengono stampati nella notazione scientifica.</span><span class="sxs-lookup"><span data-stu-id="eac6e-188">These values are printed out in scientific notation.</span></span> <span data-ttu-id="eac6e-189">A sinistra del numero di `E` è il separatore.</span><span class="sxs-lookup"><span data-stu-id="eac6e-189">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="eac6e-190">Il numero a destra è l'esponente, come potenza di 10.</span><span class="sxs-lookup"><span data-stu-id="eac6e-190">The number to the right is the exponent, as a power of 10.</span></span> 

<span data-ttu-id="eac6e-191">Come per i numeri decimali in matematica, i valori double in C# possono presentare errori di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="eac6e-191">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="eac6e-192">Provare questo codice:</span><span class="sxs-lookup"><span data-stu-id="eac6e-192">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="eac6e-193">Si sa che `0.3` periodico non è esattamente identico a `1/3`.</span><span class="sxs-lookup"><span data-stu-id="eac6e-193">You know that `0.3` repeating is not exactly the same as `1/3`.</span></span>

<span data-ttu-id="eac6e-194">***Esercizio***</span><span class="sxs-lookup"><span data-stu-id="eac6e-194">***Challenge***</span></span>

<span data-ttu-id="eac6e-195">Provare altri calcoli con numeri grandi, numeri piccoli, moltiplicazione e divisione usando il tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="eac6e-195">Try other calculations with large numbers, small numbers, multiplication and division using the `double` type.</span></span>  <span data-ttu-id="eac6e-196">Provare calcoli più complessi.</span><span class="sxs-lookup"><span data-stu-id="eac6e-196">Try more complicated calculations.</span></span>

<span data-ttu-id="eac6e-197">Dopo che è stato speso del tempo con la richiesta di verifica, eseguire il codice è stato scritto e inserirle in un nuovo metodo.</span><span class="sxs-lookup"><span data-stu-id="eac6e-197">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="eac6e-198">Nome di questo nuovo metodo `WorkWithDoubles`.</span><span class="sxs-lookup"><span data-stu-id="eac6e-198">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-fixed-point-types"></a><span data-ttu-id="eac6e-199">Usare i tipi a virgola fissa</span><span class="sxs-lookup"><span data-stu-id="eac6e-199">Work with fixed point types</span></span>

<span data-ttu-id="eac6e-200">Sono già stati presentati i tipi numerici di base in C#, ovvero integer e double.</span><span class="sxs-lookup"><span data-stu-id="eac6e-200">You've seen the basic numeric types in C#: integers and doubles.</span></span>  <span data-ttu-id="eac6e-201">C'è un altro tipo da conoscere, ovvero `decimal`.</span><span class="sxs-lookup"><span data-stu-id="eac6e-201">There is one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="eac6e-202">Il `decimal` tipo dispone di un intervallo più piccolo ma maggiore precisione `double`.</span><span class="sxs-lookup"><span data-stu-id="eac6e-202">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="eac6e-203">Il termine **virgola fissa** significa che il separatore decimale (o punto binario) non si sposta.</span><span class="sxs-lookup"><span data-stu-id="eac6e-203">The term **fixed point** means that the decimal point (or binary point) doesn't move.</span></span> <span data-ttu-id="eac6e-204">Esaminare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="eac6e-204">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="eac6e-205">Si noti che l'intervallo è minore rispetto al tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="eac6e-205">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="eac6e-206">Per vedere la maggiore precisione del tipo decimal, provare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="eac6e-206">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="eac6e-207">Il suffisso `M` nei numeri è il modo in cui si indica che una costante deve usare il tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="eac6e-207">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span>

<span data-ttu-id="eac6e-208">Si noti che le operazioni matematiche con il tipo decimal includono più cifre a destra del separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="eac6e-208">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span> 

<span data-ttu-id="eac6e-209">***Esercizio***</span><span class="sxs-lookup"><span data-stu-id="eac6e-209">***Challenge***</span></span>

<span data-ttu-id="eac6e-210">Dopo aver esaminato i diversi tipi numerici, scrivere codice che calcola l'area di un cerchio con raggio di 6 cm.</span><span class="sxs-lookup"><span data-stu-id="eac6e-210">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 inches.</span></span> <span data-ttu-id="eac6e-211">Ricordarsi che l'area di un cerchio si calcola moltiplicando il quadrato del raggio per Pi greco.</span><span class="sxs-lookup"><span data-stu-id="eac6e-211">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="eac6e-212">Suggerimento: c# contiene una costante di pi greco, <xref:System.Math.PI?displayProperty=nameWithType> che è possibile utilizzare per quel valore.</span><span class="sxs-lookup"><span data-stu-id="eac6e-212">One hint: C# contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span> 

<span data-ttu-id="eac6e-213">È possibile controllare la risposta da [esaminando il codice di esempio completata su GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)</span><span class="sxs-lookup"><span data-stu-id="eac6e-213">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)</span></span>

<span data-ttu-id="eac6e-214">Se si desidera, provare alcune altre formule.</span><span class="sxs-lookup"><span data-stu-id="eac6e-214">Try some other formulas if you'd like.</span></span> 

<span data-ttu-id="eac6e-215">È stata completata la "i numeri in c#" Guida introduttiva.</span><span class="sxs-lookup"><span data-stu-id="eac6e-215">You've completed the "Numbers in C#" quick start.</span></span> <span data-ttu-id="eac6e-216">È possibile continuare con la [cicli e diramazioni](branches-and-loops-local.md) avvio rapido nel proprio ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="eac6e-216">You can continue with the [Branches and loops](branches-and-loops-local.md) quick start in your own development environment.</span></span>

<span data-ttu-id="eac6e-217">Negli argomenti seguenti sono disponibili ulteriori informazioni sui numeri in C#:</span><span class="sxs-lookup"><span data-stu-id="eac6e-217">You can learn more about numbers in C# in the following topics:</span></span>

<span data-ttu-id="eac6e-218">[Tabella dei tipi integrali](../language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="eac6e-218">[Integral Types Table](../language-reference/keywords/integral-types-table.md) </span></span>  
<span data-ttu-id="eac6e-219">[Tabella dei tipi a virgola mobile](../language-reference/keywords/floating-point-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="eac6e-219">[Floating-Point Types Table](../language-reference/keywords/floating-point-types-table.md) </span></span>  
<span data-ttu-id="eac6e-220">[Tabella dei tipi predefiniti](../language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="eac6e-220">[Built-In Types Table](../language-reference/keywords/built-in-types-table.md) </span></span>  
<span data-ttu-id="eac6e-221">[Tabella delle conversioni numeriche implicite](../language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="eac6e-221">[Implicit Numeric Conversions Table](../language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
[<span data-ttu-id="eac6e-222">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="eac6e-222">Explicit Numeric Conversions Table</span></span>](../language-reference/keywords/explicit-numeric-conversions-table.md)


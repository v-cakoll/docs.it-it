---
title: Numeri in C# - Esercitazione introduttiva su C#
description: Vengono illustrati i tipi numerici, con le proprietà e i metodi, in C#.
ms.date: 10/31/2017
ms.custom: mvc
ms.openlocfilehash: 7e9af4b3b859f74d7e92ff10b3964ddd59d2473b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156545"
---
# <a name="manipulate-integral-and-floating-point-numbers-in-c"></a><span data-ttu-id="d2b99-103">Modificare numeri a virgola mobile e integrali in C\#</span><span class="sxs-lookup"><span data-stu-id="d2b99-103">Manipulate integral and floating point numbers in C\#</span></span>

<span data-ttu-id="d2b99-104">Questa esercitazione presenta in modo interattivo i tipi numerici in C#.</span><span class="sxs-lookup"><span data-stu-id="d2b99-104">This tutorial teaches you about the numeric types in C# interactively.</span></span> <span data-ttu-id="d2b99-105">Si scriveranno piccole quantità di codice, quindi si compilerà ed eseguirà tale codice.</span><span class="sxs-lookup"><span data-stu-id="d2b99-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="d2b99-106">L'esercitazione contiene una serie di lezioni che esplorano numeri e operazioni matematiche in C#.</span><span class="sxs-lookup"><span data-stu-id="d2b99-106">The tutorial contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="d2b99-107">Queste lezioni presentano le nozioni fondamentali del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="d2b99-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="d2b99-108">Questa esercitazione prevede la presenza di un computer da usare per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="d2b99-108">This tutorial expects you to have a machine you can use for development.</span></span> <span data-ttu-id="d2b99-109">L'esercitazione di .NET [Hello World in 10 minuti](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) contiene istruzioni per la configurazione dell'ambiente di sviluppo locale in Windows, Linux o macOS.</span><span class="sxs-lookup"><span data-stu-id="d2b99-109">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="d2b99-110">Una breve panoramica dei comandi usati è disponibile in [Acquisire familiarità con gli strumenti di sviluppo](local-environment.md), che contiene collegamenti a informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="d2b99-110">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="d2b99-111">Esplorare le operazioni matematiche su interi</span><span class="sxs-lookup"><span data-stu-id="d2b99-111">Explore integer math</span></span>

<span data-ttu-id="d2b99-112">Creare una directory denominata *numbers-quickstart*.</span><span class="sxs-lookup"><span data-stu-id="d2b99-112">Create a directory named *numbers-quickstart*.</span></span> <span data-ttu-id="d2b99-113">Assicurarsi che la directory corrente ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d2b99-113">Make that the current directory and run the following command:</span></span>

```dotnetcli
dotnet new console -n NumbersInCSharp -o .
```

<span data-ttu-id="d2b99-114">Aprire *Program.cs* nell'editor preferito e sostituire la riga `Console.WriteLine("Hello World!");` con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d2b99-114">Open *Program.cs* in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following:</span></span>

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="d2b99-115">Eseguire questo codice digitando `dotnet run` nella finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="d2b99-115">Run this code by typing `dotnet run` in your command window.</span></span>

<span data-ttu-id="d2b99-116">Questa è una delle operazioni matematiche fondamentali su interi.</span><span class="sxs-lookup"><span data-stu-id="d2b99-116">You've just seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="d2b99-117">Il `int` tipo rappresenta un **numero intero**, un numero intero zero, positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="d2b99-117">The `int` type represents an **integer**, a zero, positive, or negative whole number.</span></span> <span data-ttu-id="d2b99-118">Per l'addizione si usa il simbolo `+`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-118">You use the `+` symbol for addition.</span></span> <span data-ttu-id="d2b99-119">Altre operazioni matematiche comuni per gli interi includono:</span><span class="sxs-lookup"><span data-stu-id="d2b99-119">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="d2b99-120">`-` per la sottrazione</span><span class="sxs-lookup"><span data-stu-id="d2b99-120">`-` for subtraction</span></span>
- <span data-ttu-id="d2b99-121">`*` per la moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="d2b99-121">`*` for multiplication</span></span>
- <span data-ttu-id="d2b99-122">`/` per la divisione</span><span class="sxs-lookup"><span data-stu-id="d2b99-122">`/` for division</span></span>

<span data-ttu-id="d2b99-123">Per iniziare, esplorare le diverse operazioni.</span><span class="sxs-lookup"><span data-stu-id="d2b99-123">Start by exploring those different operations.</span></span> <span data-ttu-id="d2b99-124">Aggiungere queste righe dopo quella indicante il valore di `c`:</span><span class="sxs-lookup"><span data-stu-id="d2b99-124">Add these lines after the line that writes the value of `c`:</span></span>

```csharp

// subtraction
c = a - b;
Console.WriteLine(c);

// multiplication
c = a * b;
Console.WriteLine(c);

// division
c = a / b;
Console.WriteLine(c);
```

<span data-ttu-id="d2b99-125">Eseguire questo codice digitando `dotnet run` nella finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="d2b99-125">Run this code by typing `dotnet run` in your command window.</span></span>

<span data-ttu-id="d2b99-126">È anche possibile sperimentare eseguendo più operazioni matematiche nella stessa riga.</span><span class="sxs-lookup"><span data-stu-id="d2b99-126">You can also experiment by performing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="d2b99-127">Provare, esempio, `c = a + b - 12 * 17;`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-127">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="d2b99-128">È consentita la combinazione di variabili e numeri costanti.</span><span class="sxs-lookup"><span data-stu-id="d2b99-128">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="d2b99-129">Mentre si impara a usare C# (o qualsiasi linguaggio di programmazione) sicuramente si commetteranno errori durante la scrittura del codice.</span><span class="sxs-lookup"><span data-stu-id="d2b99-129">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="d2b99-130">Il **compilatore** troverà questi errori e li segnalerà.</span><span class="sxs-lookup"><span data-stu-id="d2b99-130">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="d2b99-131">Quando l'output contiene messaggi di errore, esaminare attentamente il codice di esempio e il codice nella finestra per scoprire che cosa correggere.</span><span class="sxs-lookup"><span data-stu-id="d2b99-131">When the output contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span>
> <span data-ttu-id="d2b99-132">Questo esercizio sarà utile per imparare la struttura del codice C#.</span><span class="sxs-lookup"><span data-stu-id="d2b99-132">That exercise will help you learn the structure of C# code.</span></span>

<span data-ttu-id="d2b99-133">Il primo passaggio è stato completato.</span><span class="sxs-lookup"><span data-stu-id="d2b99-133">You've finished the first step.</span></span> <span data-ttu-id="d2b99-134">Prima di iniziare la sezione successiva, è necessario spostare il codice corrente in un metodo separato.</span><span class="sxs-lookup"><span data-stu-id="d2b99-134">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="d2b99-135">In questo modo sarà più semplice iniziare a lavorare con un nuovo esempio.</span><span class="sxs-lookup"><span data-stu-id="d2b99-135">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="d2b99-136">Rinominare il metodo `Main` in `WorkingWithIntegers` e scrivere un nuovo metodo `Main` che chiama `WorkingWithIntegers`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-136">Rename your `Main` method to `WorkingWithIntegers` and write a new `Main` method that calls `WorkingWithIntegers`.</span></span> <span data-ttu-id="d2b99-137">Al termine, il codice dovrebbe essere simile al seguente:When you finish, your code should look like this:</span><span class="sxs-lookup"><span data-stu-id="d2b99-137">When you finish, your code should look like this:</span></span>

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

            // addition
            int c = a + b;
            Console.WriteLine(c);

            // subtraction
            c = a - b;
            Console.WriteLine(c);

            // multiplication
            c = a * b;
            Console.WriteLine(c);

            // division
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

## <a name="explore-order-of-operations"></a><span data-ttu-id="d2b99-138">Esplorare l'ordine delle operazioni</span><span class="sxs-lookup"><span data-stu-id="d2b99-138">Explore order of operations</span></span>

<span data-ttu-id="d2b99-139">Impostare come commento la chiamata a `WorkingWithIntegers()`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-139">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="d2b99-140">L'output risulterà in questo modo meno disordinato quando si usa questa sezione:</span><span class="sxs-lookup"><span data-stu-id="d2b99-140">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkingWithIntegers();
```

<span data-ttu-id="d2b99-141">`//` avvia un **commento** in C#.</span><span class="sxs-lookup"><span data-stu-id="d2b99-141">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="d2b99-142">Un commento è un testo che si vuole conservare nel codice sorgente senza eseguirlo come codice.</span><span class="sxs-lookup"><span data-stu-id="d2b99-142">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="d2b99-143">Il compilatore non genera codici eseguibili da commenti.</span><span class="sxs-lookup"><span data-stu-id="d2b99-143">The compiler does not generate any executable code from comments.</span></span>

<span data-ttu-id="d2b99-144">Il linguaggio C# stabilisce un ordine di precedenza per le diverse operazioni matematiche, con regole coerenti con quelle della matematica.</span><span class="sxs-lookup"><span data-stu-id="d2b99-144">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span>
<span data-ttu-id="d2b99-145">La moltiplicazione e la divisione hanno la precedenza rispetto ad addizione e sottrazione.</span><span class="sxs-lookup"><span data-stu-id="d2b99-145">Multiplication and division take precedence over addition and subtraction.</span></span>
<span data-ttu-id="d2b99-146">Per esplorare questo comportamento, è possibile aggiungere il codice seguente al metodo `Main` ed eseguire `dotnet run`:</span><span class="sxs-lookup"><span data-stu-id="d2b99-146">Explore that by adding the following code to your `Main` method, and executing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="d2b99-147">L'output dimostra che la moltiplicazione viene eseguita prima dell'addizione.</span><span class="sxs-lookup"><span data-stu-id="d2b99-147">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="d2b99-148">È possibile forzare un ordine diverso per le operazioni racchiudendo tra parentesi l'operazione o le operazioni che si vuole eseguire per prime.</span><span class="sxs-lookup"><span data-stu-id="d2b99-148">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="d2b99-149">Aggiungere le righe seguenti e ripetere l'esecuzione:</span><span class="sxs-lookup"><span data-stu-id="d2b99-149">Add the following lines and run again:</span></span>

```csharp
d = (a + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="d2b99-150">Sperimentare ulteriormente combinando molte operazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="d2b99-150">Explore more by combining many different operations.</span></span> <span data-ttu-id="d2b99-151">Aggiungere righe simili alle seguenti in fondo al metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-151">Add something like the following lines at the bottom of your `Main` method.</span></span> <span data-ttu-id="d2b99-152">Provare di nuovo `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-152">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="d2b99-153">È possibile che si sia notato un comportamento interessante per gli interi.</span><span class="sxs-lookup"><span data-stu-id="d2b99-153">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="d2b99-154">La divisione di interi genera sempre un risultato intero, anche quando ci si aspetta che il risultato includa una parte decimale o frazionaria.</span><span class="sxs-lookup"><span data-stu-id="d2b99-154">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="d2b99-155">Se questo comportamento non è stato notato, provare il codice seguente alla fine del metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="d2b99-155">If you haven't seen this behavior, try the following code at the end of your `Main` method:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="d2b99-156">Digitare di nuovo `dotnet run` per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="d2b99-156">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="d2b99-157">Prima di continuare, tutto il codice scritto in questa sezione verrà inserito in un nuovo metodo.</span><span class="sxs-lookup"><span data-stu-id="d2b99-157">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="d2b99-158">Chiamare il nuovo metodo `OrderPrecedence`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-158">Call that new method `OrderPrecedence`.</span></span>
<span data-ttu-id="d2b99-159">Si otterranno risultati simili a questi:</span><span class="sxs-lookup"><span data-stu-id="d2b99-159">You should end up with something like this:</span></span>

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

            // addition
            int c = a + b;
            Console.WriteLine(c);

            // subtraction
            c = a - b;
            Console.WriteLine(c);

            // multiplication
            c = a * b;
            Console.WriteLine(c);

            // division
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

            d = (a + b) * c;
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

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="d2b99-160">Esplorare la precisione e i limiti delle operazioni su interi</span><span class="sxs-lookup"><span data-stu-id="d2b99-160">Explore integer precision and limits</span></span>

<span data-ttu-id="d2b99-161">L'ultimo esempio dimostra che la divisione di interi tronca il risultato.</span><span class="sxs-lookup"><span data-stu-id="d2b99-161">That last sample showed you that integer division truncates the result.</span></span>
<span data-ttu-id="d2b99-162">È possibile ottenere il **resto** usando l'operatore **modulo**, ovvero il carattere `%`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-162">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="d2b99-163">Provare il codice seguente nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="d2b99-163">Try the following code in your `Main` method:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="d2b99-164">Il tipo integer in C# è diverso dagli interi matematici per un altro aspetto, ovvero per il tipo `int` esistono limiti minimi e massimi.</span><span class="sxs-lookup"><span data-stu-id="d2b99-164">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="d2b99-165">Aggiungere questo codice al metodo `Main` per visualizzare tali limiti:</span><span class="sxs-lookup"><span data-stu-id="d2b99-165">Add this code to your `Main` method to see those limits:</span></span>

```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="d2b99-166">Se un calcolo produce un valore che supera questi limiti, si genera una condizione di **underflow** o **overflow**.</span><span class="sxs-lookup"><span data-stu-id="d2b99-166">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="d2b99-167">La risposta sembra proseguire da un limite all'altro.</span><span class="sxs-lookup"><span data-stu-id="d2b99-167">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="d2b99-168">Aggiungere queste due righe al metodo `Main` per visualizzare un esempio:</span><span class="sxs-lookup"><span data-stu-id="d2b99-168">Add these two lines to your `Main` method to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```

<span data-ttu-id="d2b99-169">Si noti che la risposta è molto vicina all'intero minimo (negativo).</span><span class="sxs-lookup"><span data-stu-id="d2b99-169">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="d2b99-170">È uguale a `min + 2`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-170">It's the same as `min + 2`.</span></span>
<span data-ttu-id="d2b99-171">L'operazione di addizione **ha causato l'overflow** dei valori consentiti per gli interi.</span><span class="sxs-lookup"><span data-stu-id="d2b99-171">The addition operation **overflowed** the allowed values for integers.</span></span>
<span data-ttu-id="d2b99-172">La risposta è un numero negativo molto grande, poiché un overflow "ritorna a capo" proseguendo dal valore intero più grande possibile a quello più piccolo.</span><span class="sxs-lookup"><span data-stu-id="d2b99-172">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="d2b99-173">Esistono altri tipi numerici con limiti e precisione diversi che è possibile usare quando il tipo `int` non soddisfa le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="d2b99-173">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="d2b99-174">Questi tipi verranno presentati nelle prossime lezioni.</span><span class="sxs-lookup"><span data-stu-id="d2b99-174">Let's explore those next.</span></span>

<span data-ttu-id="d2b99-175">Ancora una volta il codice scritto in questa sezione verrà spostato in un metodo separato.</span><span class="sxs-lookup"><span data-stu-id="d2b99-175">Once again, let's move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="d2b99-176">Denominarlo `TestLimits`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-176">Name it `TestLimits`.</span></span>

## <a name="work-with-the-double-type"></a><span data-ttu-id="d2b99-177">Usare il tipo double</span><span class="sxs-lookup"><span data-stu-id="d2b99-177">Work with the double type</span></span>

<span data-ttu-id="d2b99-178">Il tipo numerico `double` rappresenta un numero a virgola mobile a precisione doppia.</span><span class="sxs-lookup"><span data-stu-id="d2b99-178">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="d2b99-179">Questi termini potrebbero risultare sconosciuti.</span><span class="sxs-lookup"><span data-stu-id="d2b99-179">Those terms may be new to you.</span></span> <span data-ttu-id="d2b99-180">Un numero **a virgola mobile** è utile per rappresentare numeri non integrali, con ordine di grandezza molto grande o molto piccolo.</span><span class="sxs-lookup"><span data-stu-id="d2b99-180">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="d2b99-181">Il termine **precisione doppia** indica che questi numeri vengono archiviati con una maggiore precisione rispetto alla **precisione singola**.</span><span class="sxs-lookup"><span data-stu-id="d2b99-181">**Double-precision** means that these numbers are stored using greater precision than **single-precision**.</span></span> <span data-ttu-id="d2b99-182">Nei computer moderni è più comune usare i numeri a precisione doppia rispetto ai numeri a precisione singola.</span><span class="sxs-lookup"><span data-stu-id="d2b99-182">On modern computers, it is more common to use double precision than single precision numbers.</span></span>
<span data-ttu-id="d2b99-183">Per iniziare a esplorare questo tipo,</span><span class="sxs-lookup"><span data-stu-id="d2b99-183">Let's explore.</span></span> <span data-ttu-id="d2b99-184">Aggiungere il codice seguente e visualizzare il risultato:</span><span class="sxs-lookup"><span data-stu-id="d2b99-184">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="d2b99-185">Si noti che la risposta include la parte decimale del quoziente.</span><span class="sxs-lookup"><span data-stu-id="d2b99-185">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="d2b99-186">Provare ora un'espressione leggermente più complessa con valori double:</span><span class="sxs-lookup"><span data-stu-id="d2b99-186">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="d2b99-187">L'intervallo di un valore double è molto maggiore rispetto ai valori integer.</span><span class="sxs-lookup"><span data-stu-id="d2b99-187">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="d2b99-188">Provare il codice seguente sotto il codice già scritto finora:</span><span class="sxs-lookup"><span data-stu-id="d2b99-188">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="d2b99-189">Questi valori vengono stampati con la notazione scientifica.</span><span class="sxs-lookup"><span data-stu-id="d2b99-189">These values are printed out in scientific notation.</span></span> <span data-ttu-id="d2b99-190">Il numero a sinistra di `E` rappresenta il significando.</span><span class="sxs-lookup"><span data-stu-id="d2b99-190">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="d2b99-191">Il numero a destra è l'esponente, come potenza di 10.</span><span class="sxs-lookup"><span data-stu-id="d2b99-191">The number to the right is the exponent, as a power of 10.</span></span>

<span data-ttu-id="d2b99-192">Come per i numeri decimali in matematica, i valori double in C# possono presentare errori di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="d2b99-192">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="d2b99-193">Provare questo codice:</span><span class="sxs-lookup"><span data-stu-id="d2b99-193">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="d2b99-194">Si sa che `0.3` periodico non è esattamente identico a `1/3`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-194">You know that `0.3` repeating is not exactly the same as `1/3`.</span></span>

<span data-ttu-id="d2b99-195">***Esercizio***</span><span class="sxs-lookup"><span data-stu-id="d2b99-195">***Challenge***</span></span>

<span data-ttu-id="d2b99-196">Provare altri calcoli con numeri grandi, numeri piccoli, moltiplicazione e divisione usando il tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-196">Try other calculations with large numbers, small numbers, multiplication and division using the `double` type.</span></span> <span data-ttu-id="d2b99-197">Provare calcoli più complessi.</span><span class="sxs-lookup"><span data-stu-id="d2b99-197">Try more complicated calculations.</span></span>

<span data-ttu-id="d2b99-198">Dopo avere dedicato un po' di tempo all'esercizio, inserire il codice scritto in un nuovo metodo.</span><span class="sxs-lookup"><span data-stu-id="d2b99-198">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="d2b99-199">Denominare il nuovo metodo `WorkWithDoubles`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-199">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-fixed-point-types"></a><span data-ttu-id="d2b99-200">Usare i tipi a virgola fissa</span><span class="sxs-lookup"><span data-stu-id="d2b99-200">Work with fixed point types</span></span>

<span data-ttu-id="d2b99-201">Sono già stati presentati i tipi numerici di base in C#, ovvero integer e double.</span><span class="sxs-lookup"><span data-stu-id="d2b99-201">You've seen the basic numeric types in C#: integers and doubles.</span></span>  <span data-ttu-id="d2b99-202">C'è un altro tipo da conoscere, ovvero `decimal`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-202">There is one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="d2b99-203">Il tipo `decimal` ha un intervallo più piccolo, ma maggiore precisione di `double`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-203">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="d2b99-204">Il termine **virgola fissa** significa che il separatore decimale (o punto binario) non si sposta.</span><span class="sxs-lookup"><span data-stu-id="d2b99-204">The term **fixed point** means that the decimal point (or binary point) doesn't move.</span></span> <span data-ttu-id="d2b99-205">Esaminare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d2b99-205">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="d2b99-206">Si noti che l'intervallo è minore rispetto al tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-206">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="d2b99-207">Per vedere la maggiore precisione del tipo decimal, provare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d2b99-207">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="d2b99-208">Il suffisso `M` nei numeri è il modo in cui si indica che una costante deve usare il tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="d2b99-208">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span>

<span data-ttu-id="d2b99-209">Si noti che le operazioni matematiche con il tipo decimal includono più cifre a destra del separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="d2b99-209">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span>

<span data-ttu-id="d2b99-210">***Esercizio***</span><span class="sxs-lookup"><span data-stu-id="d2b99-210">***Challenge***</span></span>

<span data-ttu-id="d2b99-211">Dopo aver esaminato i diversi tipi numerici, scrivere codice che calcola l'area di un cerchio con raggio di 2,5 cm.</span><span class="sxs-lookup"><span data-stu-id="d2b99-211">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 centimeters.</span></span> <span data-ttu-id="d2b99-212">Ricordarsi che l'area di un cerchio si calcola moltiplicando il quadrato del raggio per Pi greco.</span><span class="sxs-lookup"><span data-stu-id="d2b99-212">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="d2b99-213">Suggerimento: .NET contiene una costante per Pi greco, <xref:System.Math.PI?displayProperty=nameWithType>, che è possibile usare per tale valore.</span><span class="sxs-lookup"><span data-stu-id="d2b99-213">One hint: .NET contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span>

<span data-ttu-id="d2b99-214">Si otterrà una risposta compresa tra 19 e 20.</span><span class="sxs-lookup"><span data-stu-id="d2b99-214">You should get an answer between 19 and 20.</span></span>
<span data-ttu-id="d2b99-215">È possibile controllare la risposta [esaminando il codice di esempio finito su GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106).</span><span class="sxs-lookup"><span data-stu-id="d2b99-215">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106).</span></span>

<span data-ttu-id="d2b99-216">È anche possibile provare alcune altre formule.</span><span class="sxs-lookup"><span data-stu-id="d2b99-216">Try some other formulas if you'd like.</span></span>

<span data-ttu-id="d2b99-217">È stata completata la guida introduttiva "Numeri in C#".</span><span class="sxs-lookup"><span data-stu-id="d2b99-217">You've completed the "Numbers in C#" quickstart.</span></span> <span data-ttu-id="d2b99-218">È possibile continuare con la guida introduttiva [Rami e cicli](branches-and-loops-local.md) nel proprio ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="d2b99-218">You can continue with the [Branches and loops](branches-and-loops-local.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="d2b99-219">Negli argomenti seguenti sono disponibili ulteriori informazioni sui numeri in C#:</span><span class="sxs-lookup"><span data-stu-id="d2b99-219">You can learn more about numbers in C# in the following topics:</span></span>

- [<span data-ttu-id="d2b99-220">Tipi numerici integrali</span><span class="sxs-lookup"><span data-stu-id="d2b99-220">Integral numeric types</span></span>](../../language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="d2b99-221">Tipi numerici a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="d2b99-221">Floating-point numeric types</span></span>](../../language-reference/builtin-types/floating-point-numeric-types.md)
- [<span data-ttu-id="d2b99-222">Conversioni numeriche predefinite</span><span class="sxs-lookup"><span data-stu-id="d2b99-222">Built-in numeric conversions</span></span>](../../language-reference/builtin-types/numeric-conversions.md)

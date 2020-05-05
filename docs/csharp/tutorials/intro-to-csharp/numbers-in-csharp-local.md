---
title: Numeri in C# - Esercitazione introduttiva su C#
description: Impara a usare C# esplorando i tipi numerici, i loro usi, le proprietà e i metodi.
ms.date: 10/31/2017
ms.custom: mvc
ms.openlocfilehash: 3dc2a5afc6321da45351525a632f586cb84bf7fe
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794611"
---
# <a name="manipulate-integral-and-floating-point-numbers-in-c"></a><span data-ttu-id="e5201-103">Modificare numeri a virgola mobile e integrali in C\#</span><span class="sxs-lookup"><span data-stu-id="e5201-103">Manipulate integral and floating point numbers in C\#</span></span>

<span data-ttu-id="e5201-104">Questa esercitazione presenta in modo interattivo i tipi numerici in C#.</span><span class="sxs-lookup"><span data-stu-id="e5201-104">This tutorial teaches you about the numeric types in C# interactively.</span></span> <span data-ttu-id="e5201-105">Si scriveranno piccole quantità di codice, quindi si compilerà ed eseguirà tale codice.</span><span class="sxs-lookup"><span data-stu-id="e5201-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="e5201-106">L'esercitazione contiene una serie di lezioni che esplorano numeri e operazioni matematiche in C#.</span><span class="sxs-lookup"><span data-stu-id="e5201-106">The tutorial contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="e5201-107">Queste lezioni presentano le nozioni fondamentali del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="e5201-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="e5201-108">Questa esercitazione prevede la presenza di un computer da usare per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="e5201-108">This tutorial expects you to have a machine you can use for development.</span></span> <span data-ttu-id="e5201-109">L'esercitazione .NET [Hello World in 10 minuti](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) contiene le istruzioni per configurare l'ambiente di sviluppo locale in Windows, Linux o MacOS.</span><span class="sxs-lookup"><span data-stu-id="e5201-109">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="e5201-110">Una breve panoramica dei comandi usati è disponibile in [Acquisire familiarità con gli strumenti di sviluppo](local-environment.md), che contiene collegamenti a informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="e5201-110">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="e5201-111">Esplorare le operazioni matematiche su interi</span><span class="sxs-lookup"><span data-stu-id="e5201-111">Explore integer math</span></span>

<span data-ttu-id="e5201-112">Creare una directory denominata *numbers-quickstart*.</span><span class="sxs-lookup"><span data-stu-id="e5201-112">Create a directory named *numbers-quickstart*.</span></span> <span data-ttu-id="e5201-113">Rendere la directory corrente ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e5201-113">Make that the current directory and run the following command:</span></span>

```dotnetcli
dotnet new console -n NumbersInCSharp -o .
```

<span data-ttu-id="e5201-114">Aprire *Program.cs* nell'editor preferito e sostituire la riga `Console.WriteLine("Hello World!");` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="e5201-114">Open *Program.cs* in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code:</span></span>

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="e5201-115">Eseguire questo codice digitando `dotnet run` nella finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="e5201-115">Run this code by typing `dotnet run` in your command window.</span></span>

<span data-ttu-id="e5201-116">È stata rilevata una delle operazioni matematiche fondamentali con numeri interi.</span><span class="sxs-lookup"><span data-stu-id="e5201-116">You've seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="e5201-117">Il `int` tipo rappresenta un **intero**, un numero intero zero, positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="e5201-117">The `int` type represents an **integer**, a zero, positive, or negative whole number.</span></span> <span data-ttu-id="e5201-118">Per l'addizione si usa il simbolo `+`.</span><span class="sxs-lookup"><span data-stu-id="e5201-118">You use the `+` symbol for addition.</span></span> <span data-ttu-id="e5201-119">Altre operazioni matematiche comuni per gli interi includono:</span><span class="sxs-lookup"><span data-stu-id="e5201-119">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="e5201-120">`-` per la sottrazione</span><span class="sxs-lookup"><span data-stu-id="e5201-120">`-` for subtraction</span></span>
- <span data-ttu-id="e5201-121">`*` per la moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="e5201-121">`*` for multiplication</span></span>
- <span data-ttu-id="e5201-122">`/` per la divisione</span><span class="sxs-lookup"><span data-stu-id="e5201-122">`/` for division</span></span>

<span data-ttu-id="e5201-123">Per iniziare, esplorare le diverse operazioni.</span><span class="sxs-lookup"><span data-stu-id="e5201-123">Start by exploring those different operations.</span></span> <span data-ttu-id="e5201-124">Aggiungere queste righe dopo quella indicante il valore di `c`:</span><span class="sxs-lookup"><span data-stu-id="e5201-124">Add these lines after the line that writes the value of `c`:</span></span>

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

<span data-ttu-id="e5201-125">Eseguire questo codice digitando `dotnet run` nella finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="e5201-125">Run this code by typing `dotnet run` in your command window.</span></span>

<span data-ttu-id="e5201-126">È anche possibile provare a scrivere più operazioni matematiche nella stessa riga, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="e5201-126">You can also experiment by writing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="e5201-127">Provare, esempio, `c = a + b - 12 * 17;`.</span><span class="sxs-lookup"><span data-stu-id="e5201-127">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="e5201-128">È consentita la combinazione di variabili e numeri costanti.</span><span class="sxs-lookup"><span data-stu-id="e5201-128">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="e5201-129">Mentre si impara a usare C# (o qualsiasi linguaggio di programmazione) sicuramente si commetteranno errori durante la scrittura del codice.</span><span class="sxs-lookup"><span data-stu-id="e5201-129">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="e5201-130">Il **compilatore** troverà questi errori e li segnalerà.</span><span class="sxs-lookup"><span data-stu-id="e5201-130">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="e5201-131">Quando l'output contiene messaggi di errore, esaminare attentamente il codice di esempio e il codice nella finestra per scoprire che cosa correggere.</span><span class="sxs-lookup"><span data-stu-id="e5201-131">When the output contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span>
> <span data-ttu-id="e5201-132">Questo esercizio sarà utile per imparare la struttura del codice C#.</span><span class="sxs-lookup"><span data-stu-id="e5201-132">That exercise will help you learn the structure of C# code.</span></span>

<span data-ttu-id="e5201-133">Il primo passaggio è stato completato.</span><span class="sxs-lookup"><span data-stu-id="e5201-133">You've finished the first step.</span></span> <span data-ttu-id="e5201-134">Prima di iniziare la sezione successiva, è necessario spostare il codice corrente in un metodo separato.</span><span class="sxs-lookup"><span data-stu-id="e5201-134">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="e5201-135">In questo modo sarà più semplice iniziare a lavorare con un nuovo esempio.</span><span class="sxs-lookup"><span data-stu-id="e5201-135">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="e5201-136">Rinominare il metodo `Main` in `WorkingWithIntegers` e scrivere un nuovo metodo `Main` che chiama `WorkingWithIntegers`.</span><span class="sxs-lookup"><span data-stu-id="e5201-136">Rename your `Main` method to `WorkingWithIntegers` and write a new `Main` method that calls `WorkingWithIntegers`.</span></span> <span data-ttu-id="e5201-137">Al termine, il codice dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e5201-137">When you finish, your code should look like this:</span></span>

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

## <a name="explore-order-of-operations"></a><span data-ttu-id="e5201-138">Esplorare l'ordine delle operazioni</span><span class="sxs-lookup"><span data-stu-id="e5201-138">Explore order of operations</span></span>

<span data-ttu-id="e5201-139">Impostare come commento la chiamata a `WorkingWithIntegers()`.</span><span class="sxs-lookup"><span data-stu-id="e5201-139">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="e5201-140">L'output risulterà in questo modo meno disordinato quando si usa questa sezione:</span><span class="sxs-lookup"><span data-stu-id="e5201-140">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkingWithIntegers();
```

<span data-ttu-id="e5201-141">`//` avvia un **commento** in C#.</span><span class="sxs-lookup"><span data-stu-id="e5201-141">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="e5201-142">Un commento è un testo che si vuole conservare nel codice sorgente senza eseguirlo come codice.</span><span class="sxs-lookup"><span data-stu-id="e5201-142">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="e5201-143">Il compilatore non genera alcun codice eseguibile dai commenti.</span><span class="sxs-lookup"><span data-stu-id="e5201-143">The compiler doesn't generate any executable code from comments.</span></span>

<span data-ttu-id="e5201-144">Il linguaggio C# stabilisce un ordine di precedenza per le diverse operazioni matematiche, con regole coerenti con quelle della matematica.</span><span class="sxs-lookup"><span data-stu-id="e5201-144">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span>
<span data-ttu-id="e5201-145">La moltiplicazione e la divisione hanno la precedenza rispetto ad addizione e sottrazione.</span><span class="sxs-lookup"><span data-stu-id="e5201-145">Multiplication and division take precedence over addition and subtraction.</span></span>
<span data-ttu-id="e5201-146">Per esplorare questo comportamento, è possibile aggiungere il codice seguente al metodo `Main` ed eseguire `dotnet run`:</span><span class="sxs-lookup"><span data-stu-id="e5201-146">Explore that by adding the following code to your `Main` method, and executing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="e5201-147">L'output dimostra che la moltiplicazione viene eseguita prima dell'addizione.</span><span class="sxs-lookup"><span data-stu-id="e5201-147">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="e5201-148">È possibile forzare un ordine diverso per le operazioni racchiudendo tra parentesi l'operazione o le operazioni che si vuole eseguire per prime.</span><span class="sxs-lookup"><span data-stu-id="e5201-148">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="e5201-149">Aggiungere le righe seguenti e ripetere l'esecuzione:</span><span class="sxs-lookup"><span data-stu-id="e5201-149">Add the following lines and run again:</span></span>

```csharp
d = (a + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="e5201-150">Sperimentare ulteriormente combinando molte operazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="e5201-150">Explore more by combining many different operations.</span></span> <span data-ttu-id="e5201-151">Aggiungere righe simili alle seguenti in fondo al metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="e5201-151">Add something like the following lines at the bottom of your `Main` method.</span></span> <span data-ttu-id="e5201-152">Provare di nuovo `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="e5201-152">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="e5201-153">È possibile che si sia notato un comportamento interessante per gli interi.</span><span class="sxs-lookup"><span data-stu-id="e5201-153">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="e5201-154">La divisione di interi genera sempre un risultato intero, anche quando ci si aspetta che il risultato includa una parte decimale o frazionaria.</span><span class="sxs-lookup"><span data-stu-id="e5201-154">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="e5201-155">Se questo comportamento non è stato notato, provare il codice seguente alla fine del metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="e5201-155">If you haven't seen this behavior, try the following code at the end of your `Main` method:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="e5201-156">Digitare di nuovo `dotnet run` per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="e5201-156">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="e5201-157">Prima di continuare, tutto il codice scritto in questa sezione verrà inserito in un nuovo metodo.</span><span class="sxs-lookup"><span data-stu-id="e5201-157">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="e5201-158">Chiamare il nuovo metodo `OrderPrecedence`.</span><span class="sxs-lookup"><span data-stu-id="e5201-158">Call that new method `OrderPrecedence`.</span></span>
<span data-ttu-id="e5201-159">È necessario scrivere un codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e5201-159">You should write something like this:</span></span>

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

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="e5201-160">Esplorare la precisione e i limiti delle operazioni su interi</span><span class="sxs-lookup"><span data-stu-id="e5201-160">Explore integer precision and limits</span></span>

<span data-ttu-id="e5201-161">L'ultimo esempio dimostra che la divisione di interi tronca il risultato.</span><span class="sxs-lookup"><span data-stu-id="e5201-161">That last sample showed you that integer division truncates the result.</span></span>
<span data-ttu-id="e5201-162">È possibile ottenere il **resto** usando l'operatore **modulo**, ovvero il carattere `%`.</span><span class="sxs-lookup"><span data-stu-id="e5201-162">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="e5201-163">Provare il codice seguente nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="e5201-163">Try the following code in your `Main` method:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="e5201-164">Il tipo integer in C# è diverso dagli interi matematici per un altro aspetto, ovvero per il tipo `int` esistono limiti minimi e massimi.</span><span class="sxs-lookup"><span data-stu-id="e5201-164">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="e5201-165">Aggiungere questo codice al metodo `Main` per visualizzare tali limiti:</span><span class="sxs-lookup"><span data-stu-id="e5201-165">Add this code to your `Main` method to see those limits:</span></span>

```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="e5201-166">Se un calcolo produce un valore che supera questi limiti, si genera una condizione di **underflow** o **overflow**.</span><span class="sxs-lookup"><span data-stu-id="e5201-166">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="e5201-167">La risposta sembra proseguire da un limite all'altro.</span><span class="sxs-lookup"><span data-stu-id="e5201-167">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="e5201-168">Aggiungere queste due righe al metodo `Main` per visualizzare un esempio:</span><span class="sxs-lookup"><span data-stu-id="e5201-168">Add these two lines to your `Main` method to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```

<span data-ttu-id="e5201-169">Si noti che la risposta è molto vicina all'intero minimo (negativo).</span><span class="sxs-lookup"><span data-stu-id="e5201-169">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="e5201-170">È uguale a `min + 2`.</span><span class="sxs-lookup"><span data-stu-id="e5201-170">It's the same as `min + 2`.</span></span>
<span data-ttu-id="e5201-171">L'operazione di addizione **ha causato l'overflow** dei valori consentiti per gli interi.</span><span class="sxs-lookup"><span data-stu-id="e5201-171">The addition operation **overflowed** the allowed values for integers.</span></span>
<span data-ttu-id="e5201-172">La risposta è un numero negativo molto grande, poiché un overflow "ritorna a capo" proseguendo dal valore intero più grande possibile a quello più piccolo.</span><span class="sxs-lookup"><span data-stu-id="e5201-172">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="e5201-173">Esistono altri tipi numerici con limiti e precisione diversi che è possibile usare quando il tipo `int` non soddisfa le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="e5201-173">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="e5201-174">Verranno ora esaminati gli altri tipi.</span><span class="sxs-lookup"><span data-stu-id="e5201-174">Let's explore those other types next.</span></span>

<span data-ttu-id="e5201-175">Ancora una volta il codice scritto in questa sezione verrà spostato in un metodo separato.</span><span class="sxs-lookup"><span data-stu-id="e5201-175">Once again, let's move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="e5201-176">Denominarlo `TestLimits`.</span><span class="sxs-lookup"><span data-stu-id="e5201-176">Name it `TestLimits`.</span></span>

## <a name="work-with-the-double-type"></a><span data-ttu-id="e5201-177">Usare il tipo double</span><span class="sxs-lookup"><span data-stu-id="e5201-177">Work with the double type</span></span>

<span data-ttu-id="e5201-178">Il tipo numerico `double` rappresenta un numero a virgola mobile a precisione doppia.</span><span class="sxs-lookup"><span data-stu-id="e5201-178">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="e5201-179">Questi termini potrebbero risultare sconosciuti.</span><span class="sxs-lookup"><span data-stu-id="e5201-179">Those terms may be new to you.</span></span> <span data-ttu-id="e5201-180">Un numero **a virgola mobile** è utile per rappresentare numeri non integrali, con ordine di grandezza molto grande o molto piccolo.</span><span class="sxs-lookup"><span data-stu-id="e5201-180">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="e5201-181">La **precisione doppia** è un termine relativo che descrive il numero di cifre binarie usate per archiviare il valore.</span><span class="sxs-lookup"><span data-stu-id="e5201-181">**Double-precision** is a relative term that describes the number of binary digits used to store the value.</span></span> <span data-ttu-id="e5201-182">I numeri a **doppia precisione** hanno due volte il numero di cifre binarie come **precisione singola**.</span><span class="sxs-lookup"><span data-stu-id="e5201-182">**Double precision** numbers have twice the number of binary digits as **single-precision**.</span></span> <span data-ttu-id="e5201-183">Nei computer moderni è più comune usare la precisione doppia rispetto ai numeri a precisione singola.</span><span class="sxs-lookup"><span data-stu-id="e5201-183">On modern computers, it's more common to use double precision than single precision numbers.</span></span> <span data-ttu-id="e5201-184">I numeri a **precisione singola** vengono dichiarati utilizzando la `float` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="e5201-184">**Single precision** numbers are declared using the `float` keyword.</span></span>
<span data-ttu-id="e5201-185">Per iniziare a esplorare questo tipo,</span><span class="sxs-lookup"><span data-stu-id="e5201-185">Let's explore.</span></span> <span data-ttu-id="e5201-186">Aggiungere il codice seguente e visualizzare il risultato:</span><span class="sxs-lookup"><span data-stu-id="e5201-186">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="e5201-187">Si noti che la risposta include la parte decimale del quoziente.</span><span class="sxs-lookup"><span data-stu-id="e5201-187">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="e5201-188">Provare ora un'espressione leggermente più complessa con valori double:</span><span class="sxs-lookup"><span data-stu-id="e5201-188">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="e5201-189">L'intervallo di un valore double è molto maggiore rispetto ai valori integer.</span><span class="sxs-lookup"><span data-stu-id="e5201-189">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="e5201-190">Provare il codice seguente sotto il codice già scritto finora:</span><span class="sxs-lookup"><span data-stu-id="e5201-190">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="e5201-191">Questi valori vengono stampati con la notazione scientifica.</span><span class="sxs-lookup"><span data-stu-id="e5201-191">These values are printed out in scientific notation.</span></span> <span data-ttu-id="e5201-192">Il numero a sinistra di `E` rappresenta il significando.</span><span class="sxs-lookup"><span data-stu-id="e5201-192">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="e5201-193">Il numero a destra è l'esponente, come potenza di 10.</span><span class="sxs-lookup"><span data-stu-id="e5201-193">The number to the right is the exponent, as a power of 10.</span></span>

<span data-ttu-id="e5201-194">Come per i numeri decimali in matematica, i valori double in C# possono presentare errori di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="e5201-194">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="e5201-195">Provare questo codice:</span><span class="sxs-lookup"><span data-stu-id="e5201-195">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="e5201-196">Si sa che `0.3` la ripetizione non è esattamente identica `1/3`a.</span><span class="sxs-lookup"><span data-stu-id="e5201-196">You know that `0.3` repeating isn't exactly the same as `1/3`.</span></span>

<span data-ttu-id="e5201-197">***Esercizio***</span><span class="sxs-lookup"><span data-stu-id="e5201-197">***Challenge***</span></span>

<span data-ttu-id="e5201-198">Provare altri calcoli con numeri grandi, numeri piccoli, moltiplicazioni e divisioni usando `double` il tipo.</span><span class="sxs-lookup"><span data-stu-id="e5201-198">Try other calculations with large numbers, small numbers, multiplication, and division using the `double` type.</span></span> <span data-ttu-id="e5201-199">Provare calcoli più complessi.</span><span class="sxs-lookup"><span data-stu-id="e5201-199">Try more complicated calculations.</span></span>

<span data-ttu-id="e5201-200">Dopo avere dedicato un po' di tempo all'esercizio, inserire il codice scritto in un nuovo metodo.</span><span class="sxs-lookup"><span data-stu-id="e5201-200">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="e5201-201">Denominare il nuovo metodo `WorkWithDoubles`.</span><span class="sxs-lookup"><span data-stu-id="e5201-201">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-decimal-types"></a><span data-ttu-id="e5201-202">Usare i tipi decimali</span><span class="sxs-lookup"><span data-stu-id="e5201-202">Work with decimal types</span></span>

<span data-ttu-id="e5201-203">Sono già stati presentati i tipi numerici di base in C#, ovvero integer e double.</span><span class="sxs-lookup"><span data-stu-id="e5201-203">You've seen the basic numeric types in C#: integers and doubles.</span></span>  <span data-ttu-id="e5201-204">Ecco un altro tipo di apprendimento: il `decimal` tipo.</span><span class="sxs-lookup"><span data-stu-id="e5201-204">There's one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="e5201-205">Il tipo `decimal` ha un intervallo più piccolo, ma maggiore precisione di `double`.</span><span class="sxs-lookup"><span data-stu-id="e5201-205">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="e5201-206">Esaminare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="e5201-206">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="e5201-207">Si noti che l'intervallo è minore rispetto al tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="e5201-207">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="e5201-208">Per vedere la maggiore precisione del tipo decimal, provare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="e5201-208">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="e5201-209">Il suffisso `M` nei numeri è il modo in cui si indica che una costante deve usare il tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="e5201-209">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span> <span data-ttu-id="e5201-210">In caso contrario, il compilatore `double` presuppone il tipo.</span><span class="sxs-lookup"><span data-stu-id="e5201-210">Otherwise, the compiler assumes the `double` type.</span></span>

> [!NOTE]
> <span data-ttu-id="e5201-211">La lettera `M` è stata scelta come lettera più visivamente distinta tra `double` le `decimal` parole chiave e.</span><span class="sxs-lookup"><span data-stu-id="e5201-211">The letter `M` was chosen as the most visually distinct letter between the `double` and `decimal` keywords.</span></span>

<span data-ttu-id="e5201-212">Si noti che le operazioni matematiche con il tipo decimal includono più cifre a destra del separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="e5201-212">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span>

<span data-ttu-id="e5201-213">***Esercizio***</span><span class="sxs-lookup"><span data-stu-id="e5201-213">***Challenge***</span></span>

<span data-ttu-id="e5201-214">Dopo aver esaminato i diversi tipi numerici, scrivere codice che calcola l'area di un cerchio con raggio di 2,5 cm.</span><span class="sxs-lookup"><span data-stu-id="e5201-214">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 centimeters.</span></span> <span data-ttu-id="e5201-215">Ricordarsi che l'area di un cerchio si calcola moltiplicando il quadrato del raggio per Pi greco.</span><span class="sxs-lookup"><span data-stu-id="e5201-215">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="e5201-216">Suggerimento: .NET contiene una costante per Pi greco, <xref:System.Math.PI?displayProperty=nameWithType>, che è possibile usare per tale valore.</span><span class="sxs-lookup"><span data-stu-id="e5201-216">One hint: .NET contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span> <span data-ttu-id="e5201-217"><xref:System.Math.PI?displayProperty=nameWithType>, come tutte le costanti dichiarate `System.Math` nello spazio dei nomi `double` , è un valore.</span><span class="sxs-lookup"><span data-stu-id="e5201-217"><xref:System.Math.PI?displayProperty=nameWithType>, like all constants declared in the `System.Math` namespace, is a `double` value.</span></span> <span data-ttu-id="e5201-218">Per questo motivo, è consigliabile usare `double` anziché `decimal` i valori per questa richiesta di verifica.</span><span class="sxs-lookup"><span data-stu-id="e5201-218">For that reason, you should use `double` instead of `decimal` values for this challenge.</span></span>

<span data-ttu-id="e5201-219">Si otterrà una risposta compresa tra 19 e 20.</span><span class="sxs-lookup"><span data-stu-id="e5201-219">You should get an answer between 19 and 20.</span></span>
<span data-ttu-id="e5201-220">È possibile controllare la risposta esaminando [il codice di esempio completato su GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106).</span><span class="sxs-lookup"><span data-stu-id="e5201-220">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106).</span></span>

<span data-ttu-id="e5201-221">È anche possibile provare alcune altre formule.</span><span class="sxs-lookup"><span data-stu-id="e5201-221">Try some other formulas if you'd like.</span></span>

<span data-ttu-id="e5201-222">È stata completata la guida introduttiva "Numeri in C#".</span><span class="sxs-lookup"><span data-stu-id="e5201-222">You've completed the "Numbers in C#" quickstart.</span></span> <span data-ttu-id="e5201-223">È possibile continuare con la guida introduttiva [Rami e cicli](branches-and-loops-local.md) nel proprio ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="e5201-223">You can continue with the [Branches and loops](branches-and-loops-local.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="e5201-224">È possibile ottenere altre informazioni sui numeri in C# negli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5201-224">You can learn more about numbers in C# in the following articles:</span></span>

- [<span data-ttu-id="e5201-225">Tipi numerici integrali</span><span class="sxs-lookup"><span data-stu-id="e5201-225">Integral numeric types</span></span>](../../language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="e5201-226">Tipi numerici a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="e5201-226">Floating-point numeric types</span></span>](../../language-reference/builtin-types/floating-point-numeric-types.md)
- [<span data-ttu-id="e5201-227">Conversioni numeriche predefinite</span><span class="sxs-lookup"><span data-stu-id="e5201-227">Built-in numeric conversions</span></span>](../../language-reference/builtin-types/numeric-conversions.md)

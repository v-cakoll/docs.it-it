---
title: Rami e cicli - Esercitazione introduttiva su C#
description: In questa esercitazione su rami e cicli si scriverà codice C# per esplorare la sintassi del linguaggio che supporta cicli e diramazioni condizionali per eseguire ripetutamente istruzioni.
ms.date: 10/31/2017
ms.custom: mvc
ms.openlocfilehash: d8c10a7462b7c27c5353aee6d957732a8d161015
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135945"
---
# <a name="learn-conditional-logic-with-branch-and-loop-statements"></a><span data-ttu-id="6cab8-103">Informazioni sulla logica condizionale con istruzioni per rami e cicli</span><span class="sxs-lookup"><span data-stu-id="6cab8-103">Learn conditional logic with branch and loop statements</span></span>

<span data-ttu-id="6cab8-104">Questa esercitazione descrive come scrivere codice che esamina le variabili e modifica il percorso di esecuzione in base a queste variabili.</span><span class="sxs-lookup"><span data-stu-id="6cab8-104">This tutorial teaches you how to write code that examines variables and changes the execution path based on those variables.</span></span> <span data-ttu-id="6cab8-105">Verranno descritte le procedure per scrivere codice C# e visualizzare i risultati della compilazione ed esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="6cab8-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="6cab8-106">L'esercitazione contiene una serie di lezioni che esplorano i costrutti per rami e cicli in C#.</span><span class="sxs-lookup"><span data-stu-id="6cab8-106">The tutorial contains a series of lessons that explore branching and looping constructs in C#.</span></span> <span data-ttu-id="6cab8-107">Queste lezioni presentano le nozioni fondamentali del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="6cab8-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="6cab8-108">Questa esercitazione prevede la presenza di un computer da usare per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="6cab8-108">This tutorial expects you to have a machine you can use for development.</span></span> <span data-ttu-id="6cab8-109">L'esercitazione .NET [Hello World in 10 minuti](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) contiene le istruzioni per configurare l'ambiente di sviluppo locale in Windows, Linux o MacOS.</span><span class="sxs-lookup"><span data-stu-id="6cab8-109">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="6cab8-110">Una breve panoramica dei comandi usati è disponibile in [Acquisire familiarità con gli strumenti di sviluppo](local-environment.md), che contiene collegamenti a informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="6cab8-110">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="make-decisions-using-the-if-statement"></a><span data-ttu-id="6cab8-111">Prendere decisioni usando l'istruzione `if`</span><span class="sxs-lookup"><span data-stu-id="6cab8-111">Make decisions using the `if` statement</span></span>

<span data-ttu-id="6cab8-112">Creare una directory denominata *branches-tutorial*.</span><span class="sxs-lookup"><span data-stu-id="6cab8-112">Create a directory named *branches-tutorial*.</span></span> <span data-ttu-id="6cab8-113">Rendere la directory corrente ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="6cab8-113">Make that the current directory and run the following command:</span></span>

```dotnetcli
dotnet new console -n BranchesAndLoops -o .
```

<span data-ttu-id="6cab8-114">Questo comando crea una nuova applicazione console .NET Core nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="6cab8-114">This command creates a new .NET Core console application in the current directory.</span></span>

<span data-ttu-id="6cab8-115">Aprire *Program.cs* nell'editor preferito e sostituire la riga `Console.WriteLine("Hello World!");` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6cab8-115">Open *Program.cs* in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code:</span></span>

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

<span data-ttu-id="6cab8-116">Per provare questo codice, digitare `dotnet run` nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="6cab8-116">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="6cab8-117">Verrà visualizzato il messaggio "The answer is greater than 10."</span><span class="sxs-lookup"><span data-stu-id="6cab8-117">You should see the message "The answer is greater than 10."</span></span> <span data-ttu-id="6cab8-118">nella console.</span><span class="sxs-lookup"><span data-stu-id="6cab8-118">printed to your console.</span></span>

<span data-ttu-id="6cab8-119">Modificare la dichiarazione di `b` in modo che la somma sia minore di 10:</span><span class="sxs-lookup"><span data-stu-id="6cab8-119">Modify the declaration of `b` so that the sum is less than 10:</span></span>

```csharp
int b = 3;
```

<span data-ttu-id="6cab8-120">Digitare di nuovo `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="6cab8-120">Type `dotnet run` again.</span></span> <span data-ttu-id="6cab8-121">Dato che la risposta è minore a 10, non viene visualizzato nulla.</span><span class="sxs-lookup"><span data-stu-id="6cab8-121">Because the answer is less than 10, nothing is printed.</span></span> <span data-ttu-id="6cab8-122">La **condizione** testata è false.</span><span class="sxs-lookup"><span data-stu-id="6cab8-122">The **condition** you're testing is false.</span></span> <span data-ttu-id="6cab8-123">Non esiste codice da eseguire perché è stato scritto solo uno dei possibili rami per un'istruzione `if`, ovvero il ramo true.</span><span class="sxs-lookup"><span data-stu-id="6cab8-123">You don't have any code to execute because you've only written one of the possible branches for an `if` statement: the true branch.</span></span>

> [!TIP]
> <span data-ttu-id="6cab8-124">Mentre si impara a usare C# (o qualsiasi linguaggio di programmazione) sicuramente si commetteranno errori durante la scrittura del codice.</span><span class="sxs-lookup"><span data-stu-id="6cab8-124">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="6cab8-125">Il compilatore troverà e segnalerà gli errori.</span><span class="sxs-lookup"><span data-stu-id="6cab8-125">The compiler will find and report the errors.</span></span> <span data-ttu-id="6cab8-126">Esaminare attentamente l'output dell'errore e il codice che ha generato l'errore.</span><span class="sxs-lookup"><span data-stu-id="6cab8-126">Look closely at the error output and the code that generated the error.</span></span> <span data-ttu-id="6cab8-127">L'errore del compilatore consente in genere di trovare il problema.</span><span class="sxs-lookup"><span data-stu-id="6cab8-127">The compiler error can usually help you find the problem.</span></span>

<span data-ttu-id="6cab8-128">Questo primo esempio dimostra le potenzialità di `if` e dei tipi booleani.</span><span class="sxs-lookup"><span data-stu-id="6cab8-128">This first sample shows the power of `if` and Boolean types.</span></span> <span data-ttu-id="6cab8-129">Un valore *booleano* è una variabile che può avere uno di due valori: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="6cab8-129">A *Boolean* is a variable that can have one of two values: `true` or `false`.</span></span> <span data-ttu-id="6cab8-130">C# definisce un tipo speciale, `bool` per le variabili booleane.</span><span class="sxs-lookup"><span data-stu-id="6cab8-130">C# defines a special type, `bool` for Boolean variables.</span></span> <span data-ttu-id="6cab8-131">L'istruzione `if` controlla il valore di un `bool`.</span><span class="sxs-lookup"><span data-stu-id="6cab8-131">The `if` statement checks the value of a `bool`.</span></span> <span data-ttu-id="6cab8-132">Quando il valore è `true`, viene eseguita l'istruzione che segue `if`.</span><span class="sxs-lookup"><span data-stu-id="6cab8-132">When the value is `true`, the statement following the `if` executes.</span></span> <span data-ttu-id="6cab8-133">In caso contrario, l'istruzione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="6cab8-133">Otherwise, it is skipped.</span></span>

<span data-ttu-id="6cab8-134">Questo processo di controllo delle condizioni ed esecuzione di istruzioni in base a queste condizioni offre molte potenzialità.</span><span class="sxs-lookup"><span data-stu-id="6cab8-134">This process of checking conditions and executing statements based on those conditions is very powerful.</span></span>

## <a name="make-if-and-else-work-together"></a><span data-ttu-id="6cab8-135">Usare insieme if ed else</span><span class="sxs-lookup"><span data-stu-id="6cab8-135">Make if and else work together</span></span>

<span data-ttu-id="6cab8-136">Per eseguire codice diverso per i rami true e false, è necessario creare un ramo `else` che viene eseguito quando la condizione è false.</span><span class="sxs-lookup"><span data-stu-id="6cab8-136">To execute different code in both the true and false branches, you create an `else` branch that executes when the condition is false.</span></span> <span data-ttu-id="6cab8-137">Provare questo codice.</span><span class="sxs-lookup"><span data-stu-id="6cab8-137">Try this.</span></span> <span data-ttu-id="6cab8-138">Aggiungere le ultime due righe del codice seguente al metodo `Main` (le prime quattro dovrebbero essere già presenti):</span><span class="sxs-lookup"><span data-stu-id="6cab8-138">Add the last two lines in the code below to your `Main` method (you should already have the first four):</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

<span data-ttu-id="6cab8-139">L'istruzione che segue la parola chiave `else` viene eseguita solo quando la condizione testata è `false`.</span><span class="sxs-lookup"><span data-stu-id="6cab8-139">The statement following the `else` keyword executes only when the condition being tested is `false`.</span></span> <span data-ttu-id="6cab8-140">La combinazione di `if` e `else` con condizioni booleane offre tutte le potenzialità necessarie per gestire sia una condizione `true` che una condizione `false`.</span><span class="sxs-lookup"><span data-stu-id="6cab8-140">Combining `if` and `else` with Boolean conditions provides all the power you need to handle both a `true` and a `false` condition.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6cab8-141">Il rientro applicato alle righe successive alle istruzioni `if` e `else` è pensato per i lettori umani.</span><span class="sxs-lookup"><span data-stu-id="6cab8-141">The indentation under the `if` and `else` statements is for human readers.</span></span>
> <span data-ttu-id="6cab8-142">Nel linguaggio C# i rientri o gli spazi vuoti non sono significativi.</span><span class="sxs-lookup"><span data-stu-id="6cab8-142">The C# language doesn't treat indentation or white space as significant.</span></span>
> <span data-ttu-id="6cab8-143">L'istruzione che segue la parola chiave `if` o `else` verrà eseguita in base alla condizione.</span><span class="sxs-lookup"><span data-stu-id="6cab8-143">The statement following the `if` or `else` keyword will be executed based on the condition.</span></span> <span data-ttu-id="6cab8-144">Tutti gli esempi in questa esercitazione seguono una procedura comune che prevede il rientro delle righe in base al flusso di controllo delle istruzioni.</span><span class="sxs-lookup"><span data-stu-id="6cab8-144">All the samples in this tutorial follow a common practice to indent lines based on the control flow of statements.</span></span>

<span data-ttu-id="6cab8-145">Dato che il rientro non è significativo, è necessario usare `{` e `}` per indicare quando si vuole includere più di un'istruzione nel blocco con esecuzione condizionale.</span><span class="sxs-lookup"><span data-stu-id="6cab8-145">Because indentation is not significant, you need to use `{` and `}` to indicate when you want more than one statement to be part of the block that executes conditionally.</span></span> <span data-ttu-id="6cab8-146">I programmatori C# usano in genere le parentesi graffe in tutte le clausole `if` e `else`.</span><span class="sxs-lookup"><span data-stu-id="6cab8-146">C# programmers typically use those braces on all `if` and `else` clauses.</span></span> <span data-ttu-id="6cab8-147">L'esempio seguente è identico a quello appena creato.</span><span class="sxs-lookup"><span data-stu-id="6cab8-147">The following example is the same as the one you just created.</span></span> <span data-ttu-id="6cab8-148">Modificare il codice precedente in modo che corrisponda al codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6cab8-148">Modify your code above to match the following code:</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
{
    Console.WriteLine("The answer is greater than 10");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
}
```

> [!TIP]
> <span data-ttu-id="6cab8-149">Nelle parti restanti di questa esercitazione, tutti gli esempi di codice includono le parentesi graffe conformemente alle consuetudini comuni.</span><span class="sxs-lookup"><span data-stu-id="6cab8-149">Through the rest of this tutorial, the code samples all include the braces, following accepted practices.</span></span>

<span data-ttu-id="6cab8-150">È possibile testare condizioni più complesse.</span><span class="sxs-lookup"><span data-stu-id="6cab8-150">You can test more complicated conditions.</span></span> <span data-ttu-id="6cab8-151">Aggiungere il codice seguente nel metodo `Main` dopo il codice scritto finora:</span><span class="sxs-lookup"><span data-stu-id="6cab8-151">Add the following code in your `Main` method after the code you've written so far:</span></span>

```csharp
int c = 4;
if ((a + b + c > 10) && (a == b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("And the first number is equal to the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("Or the first number is not equal to the second");
}
```

<span data-ttu-id="6cab8-152">Il simbolo `==` verifica l'*uguaglianza*.</span><span class="sxs-lookup"><span data-stu-id="6cab8-152">The `==` symbol tests for *equality*.</span></span> <span data-ttu-id="6cab8-153">Il simbolo `==` distingue il test per l'uguaglianza dall'assegnazione, illustrata in `a = 5`.</span><span class="sxs-lookup"><span data-stu-id="6cab8-153">Using `==` distinguishes the test for equality from assignment, which you saw in `a = 5`.</span></span>

<span data-ttu-id="6cab8-154">`&&` rappresenta "e"</span><span class="sxs-lookup"><span data-stu-id="6cab8-154">The `&&` represents "and".</span></span> <span data-ttu-id="6cab8-155">e significa che entrambe le condizioni devono essere true per eseguire l'istruzione nel ramo true.</span><span class="sxs-lookup"><span data-stu-id="6cab8-155">It means both conditions must be true to execute the statement in the true branch.</span></span>  <span data-ttu-id="6cab8-156">Questi esempi mostrano anche che è possibile includere più istruzioni in ogni ramo condizionale, a condizione di racchiuderle tra `{` e `}`.</span><span class="sxs-lookup"><span data-stu-id="6cab8-156">These examples also show that you can have multiple statements in each conditional branch, provided you enclose them in `{` and `}`.</span></span>

<span data-ttu-id="6cab8-157">È anche possibile usare `||` per rappresentare "or".</span><span class="sxs-lookup"><span data-stu-id="6cab8-157">You can also use  `||` to represent "or".</span></span> <span data-ttu-id="6cab8-158">Aggiungere il codice seguente dopo il codice già scritto finora:</span><span class="sxs-lookup"><span data-stu-id="6cab8-158">Add the following code after what you've written so far:</span></span>

```csharp
if ((a + b + c > 10) || (a == b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("Or the first number is equal to the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("And the first number is not equal to the second");
}
```

<span data-ttu-id="6cab8-159">Modificare i valori di `a`, `b` e `c` e passare da `&&` a `||` per esplorare.</span><span class="sxs-lookup"><span data-stu-id="6cab8-159">Modify the values of `a`, `b`, and `c` and switch between `&&` and `||` to explore.</span></span> <span data-ttu-id="6cab8-160">Si otterranno più informazioni sul funzionamento degli operatori `&&` e `||`.</span><span class="sxs-lookup"><span data-stu-id="6cab8-160">You'll gain more understanding of how the `&&` and `||` operators work.</span></span>

<span data-ttu-id="6cab8-161">Il primo passaggio è stato completato.</span><span class="sxs-lookup"><span data-stu-id="6cab8-161">You've finished the first step.</span></span> <span data-ttu-id="6cab8-162">Prima di iniziare la sezione successiva, è necessario spostare il codice corrente in un metodo separato.</span><span class="sxs-lookup"><span data-stu-id="6cab8-162">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="6cab8-163">In questo modo sarà più semplice iniziare a lavorare con un nuovo esempio.</span><span class="sxs-lookup"><span data-stu-id="6cab8-163">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="6cab8-164">Rinominare il metodo `Main` in `ExploreIf` e scrivere un nuovo metodo `Main` che chiama `ExploreIf`.</span><span class="sxs-lookup"><span data-stu-id="6cab8-164">Rename your `Main` method to `ExploreIf` and write a new `Main` method that calls `ExploreIf`.</span></span> <span data-ttu-id="6cab8-165">Al termine, il codice dovrebbe risultare simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="6cab8-165">When you have finished, your code should look like this:</span></span>

```csharp
using System;

namespace BranchesAndLoops
{
    class Program
    {
        static void ExploreIf()
        {
            int a = 5;
            int b = 3;
            if (a + b > 10)
            {
                Console.WriteLine("The answer is greater than 10");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
            }

            int c = 4;
            if ((a + b + c > 10) && (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("And the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("Or the first number is not greater than the second");
            }

            if ((a + b + c > 10) || (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("Or the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("And the first number is not greater than the second");
            }
        }

        static void Main(string[] args)
        {
            ExploreIf();
        }
    }
}
```

<span data-ttu-id="6cab8-166">Impostare come commento la chiamata a `ExploreIf()`.</span><span class="sxs-lookup"><span data-stu-id="6cab8-166">Comment out the call to `ExploreIf()`.</span></span> <span data-ttu-id="6cab8-167">L'output risulterà in questo modo meno disordinato quando si usa questa sezione:</span><span class="sxs-lookup"><span data-stu-id="6cab8-167">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//ExploreIf();
```

<span data-ttu-id="6cab8-168">`//` avvia un **commento** in C#.</span><span class="sxs-lookup"><span data-stu-id="6cab8-168">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="6cab8-169">Un commento è un testo che si vuole conservare nel codice sorgente senza eseguirlo come codice.</span><span class="sxs-lookup"><span data-stu-id="6cab8-169">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="6cab8-170">Il compilatore non genera codici eseguibili da commenti.</span><span class="sxs-lookup"><span data-stu-id="6cab8-170">The compiler does not generate any executable code from comments.</span></span>

## <a name="use-loops-to-repeat-operations"></a><span data-ttu-id="6cab8-171">Usare i cicli per ripetere le operazioni</span><span class="sxs-lookup"><span data-stu-id="6cab8-171">Use loops to repeat operations</span></span>

<span data-ttu-id="6cab8-172">In questa sezione si usano i **cicli** per ripetere le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="6cab8-172">In this section you use **loops** to repeat statements.</span></span> <span data-ttu-id="6cab8-173">Provare questo codice nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="6cab8-173">Try this code in your `Main` method:</span></span>

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

<span data-ttu-id="6cab8-174">L'istruzione `while` verifica una condizione ed esegue l'istruzione o il blocco di istruzioni che segue `while`.</span><span class="sxs-lookup"><span data-stu-id="6cab8-174">The `while` statement checks a condition and executes the statement or statement block following the `while`.</span></span> <span data-ttu-id="6cab8-175">Ripete la verifica della condizione e l'esecuzione di tali istruzioni fino a quando la condizione è false.</span><span class="sxs-lookup"><span data-stu-id="6cab8-175">It repeatedly checks the condition and executing those statements until the condition is false.</span></span>

<span data-ttu-id="6cab8-176">Questo esempio include un altro operatore nuovo.</span><span class="sxs-lookup"><span data-stu-id="6cab8-176">There's one other new operator in this example.</span></span> <span data-ttu-id="6cab8-177">I caratteri `++` dopo la variabile `counter` rappresentano l'operatore di **incremento**.</span><span class="sxs-lookup"><span data-stu-id="6cab8-177">The `++` after the `counter` variable is the **increment** operator.</span></span> <span data-ttu-id="6cab8-178">Questo operatore aggiunge 1 al valore di `counter` e archivia il valore nella variabile `counter`.</span><span class="sxs-lookup"><span data-stu-id="6cab8-178">It adds 1 to the value of `counter` and stores that value in the `counter` variable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6cab8-179">Assicurarsi che la condizione del ciclo `while` passi a false quando si esegue il codice.</span><span class="sxs-lookup"><span data-stu-id="6cab8-179">Make sure that the `while` loop condition changes to false as you execute the code.</span></span> <span data-ttu-id="6cab8-180">In caso contrario, si crea un **ciclo infinito** in cui il programma non termina mai.</span><span class="sxs-lookup"><span data-stu-id="6cab8-180">Otherwise, you create an **infinite loop** where your program never ends.</span></span> <span data-ttu-id="6cab8-181">Tale situazione non è illustrata in questo esempio, perché è necessario forzare l'uscita dal programma usando **CTRL+C** o in altro modo.</span><span class="sxs-lookup"><span data-stu-id="6cab8-181">That is not demonstrated in this sample, because you have to force your program to quit using **CTRL-C** or other means.</span></span>

<span data-ttu-id="6cab8-182">Il ciclo `while` testa la condizione prima di eseguire il codice dopo `while`.</span><span class="sxs-lookup"><span data-stu-id="6cab8-182">The `while` loop tests the condition before executing the code following the `while`.</span></span> <span data-ttu-id="6cab8-183">Il ciclo `do` ... `while` esegue prima il codice e poi controlla la condizione,</span><span class="sxs-lookup"><span data-stu-id="6cab8-183">The `do` ... `while` loop executes the code first, and then checks the condition.</span></span> <span data-ttu-id="6cab8-184">Il ciclo do while è illustrato nel codice riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6cab8-184">The do while loop is shown in the following code:</span></span>

```csharp
int counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

<span data-ttu-id="6cab8-185">Questo ciclo `do` e il ciclo `while` precedente generano lo stesso output.</span><span class="sxs-lookup"><span data-stu-id="6cab8-185">This `do` loop and the earlier `while` loop produce the same output.</span></span>

## <a name="work-with-the-for-loop"></a><span data-ttu-id="6cab8-186">Usare il ciclo for</span><span class="sxs-lookup"><span data-stu-id="6cab8-186">Work with the for loop</span></span>

<span data-ttu-id="6cab8-187">Il ciclo **for** viene in genere usato in C#.</span><span class="sxs-lookup"><span data-stu-id="6cab8-187">The **for** loop is commonly used in C#.</span></span> <span data-ttu-id="6cab8-188">Provare questo codice nel metodo Main():</span><span class="sxs-lookup"><span data-stu-id="6cab8-188">Try this code in your Main() method:</span></span>

```csharp
for (int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
}
```

<span data-ttu-id="6cab8-189">Questo codice esegue le stesse operazioni di ciclo `while` e `do` già usate.</span><span class="sxs-lookup"><span data-stu-id="6cab8-189">This does the same work as the `while` loop and the `do` loop you've already used.</span></span> <span data-ttu-id="6cab8-190">L'istruzione `for` è composta da tre parti che ne controllano il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="6cab8-190">The `for` statement has three parts that control how it works.</span></span>

<span data-ttu-id="6cab8-191">La prima parte è l' **inizializzatore for**: `int index = 0;` dichiara che `index` è la variabile del ciclo e imposta il valore iniziale su `0`.</span><span class="sxs-lookup"><span data-stu-id="6cab8-191">The first part is the **for initializer**: `int index = 0;` declares that `index` is the loop variable, and sets its initial value to `0`.</span></span>

<span data-ttu-id="6cab8-192">La parte intermedia è la **condizione for**: `index < 10` dichiara che questo `for` ciclo continua a essere eseguito fino a quando il valore del contatore è minore di 10.</span><span class="sxs-lookup"><span data-stu-id="6cab8-192">The middle part is the **for condition**: `index < 10` declares that this `for` loop continues to execute as long as the value of counter is less than 10.</span></span>

<span data-ttu-id="6cab8-193">La parte finale è l' **iteratore for**: `index++` specifica come modificare la variabile del ciclo dopo l'esecuzione del blocco dopo `for` l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="6cab8-193">The final part is the **for iterator**: `index++` specifies how to modify the loop variable after executing the block following the `for` statement.</span></span> <span data-ttu-id="6cab8-194">In questo caso, specifica che `index` deve essere incrementato di 1 a ogni esecuzione del blocco.</span><span class="sxs-lookup"><span data-stu-id="6cab8-194">Here, it specifies that `index` should be incremented by 1 each time the block executes.</span></span>

<span data-ttu-id="6cab8-195">Sperimentare da soli questi elementi.</span><span class="sxs-lookup"><span data-stu-id="6cab8-195">Experiment with these yourself.</span></span> <span data-ttu-id="6cab8-196">Eseguire queste prove:</span><span class="sxs-lookup"><span data-stu-id="6cab8-196">Try each of the following:</span></span>

- <span data-ttu-id="6cab8-197">Cambiare l'inizializzatore in modo che inizi da un valore diverso.</span><span class="sxs-lookup"><span data-stu-id="6cab8-197">Change the initializer to start at a different value.</span></span>
- <span data-ttu-id="6cab8-198">Cambiare la condizione in modo che si interrompa in corrispondenza di un valore diverso.</span><span class="sxs-lookup"><span data-stu-id="6cab8-198">Change the condition to stop at a different value.</span></span>

<span data-ttu-id="6cab8-199">Al termine, passare alla prossima lezione che prevede la scrittura di codice per usare quanto finora appreso.</span><span class="sxs-lookup"><span data-stu-id="6cab8-199">When you're done, let's move on to write some code yourself to use what you've learned.</span></span>

## <a name="created-nested-loops"></a><span data-ttu-id="6cab8-200">Cicli annidati creati</span><span class="sxs-lookup"><span data-stu-id="6cab8-200">Created nested loops</span></span>

<span data-ttu-id="6cab8-201">Un `while`ciclo `do` , `for` o può essere annidato all'interno di un altro ciclo per creare una matrice utilizzando la combinazione di ogni elemento del ciclo esterno con ogni elemento del ciclo interno.</span><span class="sxs-lookup"><span data-stu-id="6cab8-201">A `while`, `do` or `for` loop can be nested inside another loop to create a matrix using the combination of each item in the outer loop with each item in the inner loop.</span></span> <span data-ttu-id="6cab8-202">A questo scopo, è necessario compilare un set di coppie alfanumeriche per rappresentare righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="6cab8-202">Let's do that to build a set of alphanumeric pairs to represent rows and columns.</span></span>

<span data-ttu-id="6cab8-203">Un `for` ciclo può generare le righe:</span><span class="sxs-lookup"><span data-stu-id="6cab8-203">One `for` loop can generate the rows:</span></span>

```csharp
for (int row = 1; row < 11; row++)
{
    Console.WriteLine($"The row is {row}");
}
```

<span data-ttu-id="6cab8-204">Un altro ciclo può generare le colonne:</span><span class="sxs-lookup"><span data-stu-id="6cab8-204">Another loop can generate the columns:</span></span>

```csharp
for (char column = 'a'; column < 'k'; column++)
{
    Console.WriteLine($"The column is {column}");
}
```

<span data-ttu-id="6cab8-205">È possibile annidare un ciclo all'interno dell'altro per formare coppie:</span><span class="sxs-lookup"><span data-stu-id="6cab8-205">You can nest one loop inside the other to form pairs:</span></span>

```csharp
for (int row = 1; row < 11; row++)
{
    for (char column = 'a'; column < 'k'; column++)
    {
        Console.WriteLine($"The cell is ({row}, {column})");
    }
}
```

<span data-ttu-id="6cab8-206">È possibile osservare che il ciclo esterno viene incrementato una volta per ogni esecuzione completa del ciclo interno.</span><span class="sxs-lookup"><span data-stu-id="6cab8-206">You can see that the outer loop increments once for each full run of the inner loop.</span></span> <span data-ttu-id="6cab8-207">Invertire l'annidamento di righe e colonne e visualizzare le modifiche per se stessi.</span><span class="sxs-lookup"><span data-stu-id="6cab8-207">Reverse the row and column nesting, and see the changes for yourself.</span></span>

## <a name="combine-branches-and-loops"></a><span data-ttu-id="6cab8-208">Combinare rami e cicli</span><span class="sxs-lookup"><span data-stu-id="6cab8-208">Combine branches and loops</span></span>

<span data-ttu-id="6cab8-209">Dopo aver esaminato l'istruzione `if` e i costrutti per i cicli nel linguaggio C#, provare a scrivere codice C# per ottenere la somma di tutti i numeri interi da 1 a 20 divisibili per 3.</span><span class="sxs-lookup"><span data-stu-id="6cab8-209">Now that you've seen the `if` statement and the looping constructs in the C# language, see if you can write C# code to find the sum of all integers 1 through 20 that are divisible by 3.</span></span>  <span data-ttu-id="6cab8-210">Ecco alcuni suggerimenti:</span><span class="sxs-lookup"><span data-stu-id="6cab8-210">Here are a few hints:</span></span>

- <span data-ttu-id="6cab8-211">L'operatore `%` restituisce il resto di un'operazione di divisione.</span><span class="sxs-lookup"><span data-stu-id="6cab8-211">The `%` operator gives you the remainder of a division operation.</span></span>
- <span data-ttu-id="6cab8-212">L'istruzione `if` offre la condizione per stabilire se un numero deve fare parte della somma.</span><span class="sxs-lookup"><span data-stu-id="6cab8-212">The `if` statement gives you the condition to see if a number should be part of the sum.</span></span>
- <span data-ttu-id="6cab8-213">Il ciclo `for` può essere utile per ripetere una serie di passaggi per tutti i numeri da 1 a 20.</span><span class="sxs-lookup"><span data-stu-id="6cab8-213">The `for` loop can help you repeat a series of steps for all the numbers 1 through 20.</span></span>

<span data-ttu-id="6cab8-214">Sperimentare e quindi</span><span class="sxs-lookup"><span data-stu-id="6cab8-214">Try it yourself.</span></span> <span data-ttu-id="6cab8-215">controllare i risultati.</span><span class="sxs-lookup"><span data-stu-id="6cab8-215">Then check how you did.</span></span> <span data-ttu-id="6cab8-216">Verrà visualizzata una risposta 63.</span><span class="sxs-lookup"><span data-stu-id="6cab8-216">You should get 63 for an answer.</span></span> <span data-ttu-id="6cab8-217">Per vedere una possibile risposta, [visualizzare il codice completo in GitHub](https://github.com/dotnet/samples/tree/master/csharp/branches-quickstart/Program.cs#L46-L54).</span><span class="sxs-lookup"><span data-stu-id="6cab8-217">You can see one possible answer by [viewing the completed code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/branches-quickstart/Program.cs#L46-L54).</span></span>

<span data-ttu-id="6cab8-218">È stata completata l'esercitazione "Cicli e rami".</span><span class="sxs-lookup"><span data-stu-id="6cab8-218">You've completed the "branches and loops" tutorial.</span></span>

<span data-ttu-id="6cab8-219">È possibile continuare con l'esercitazione [Matrici e raccolte](arrays-and-collections.md) nel proprio ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="6cab8-219">You can continue with the [Arrays and collections](arrays-and-collections.md) tutorial in your own development environment.</span></span>

<span data-ttu-id="6cab8-220">Maggiori informazioni su questi concetti sono disponibili in questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="6cab8-220">You can learn more about these concepts in these topics:</span></span>

- [<span data-ttu-id="6cab8-221">Istruzioni if ed else</span><span class="sxs-lookup"><span data-stu-id="6cab8-221">If and else statement</span></span>](../../language-reference/keywords/if-else.md)
- [<span data-ttu-id="6cab8-222">Istruzione while</span><span class="sxs-lookup"><span data-stu-id="6cab8-222">While statement</span></span>](../../language-reference/keywords/while.md)
- [<span data-ttu-id="6cab8-223">Istruzione do</span><span class="sxs-lookup"><span data-stu-id="6cab8-223">Do statement</span></span>](../../language-reference/keywords/do.md)
- [<span data-ttu-id="6cab8-224">Istruzione for</span><span class="sxs-lookup"><span data-stu-id="6cab8-224">For statement</span></span>](../../language-reference/keywords/for.md)

---
title: Avvio rapido - rami e lops - Guida per c#
description: In questa Guida introduttiva su cicli e diramazioni, scrivere codice c# per esplorare la sintassi del linguaggio che supporta rami condizionali e cicli per eseguire istruzioni ripetutamente.
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 4b077a29cf42072a93b054f50a13a4580ad54304
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2017
---
# <a name="branches-and-loops"></a><span data-ttu-id="35159-103">Rami e cicli</span><span class="sxs-lookup"><span data-stu-id="35159-103">Branches and loops</span></span>

<span data-ttu-id="35159-104">Questa Guida introduttiva illustra come scrivere codice che esamina le variabili e cambia il percorso di esecuzione in base a tali variabili.</span><span class="sxs-lookup"><span data-stu-id="35159-104">This quick start teaches you how to write code that examines variables and changes the execution path based on those variables.</span></span> <span data-ttu-id="35159-105">Scrivere codice c# e visualizzare i risultati della compilazione e l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="35159-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="35159-106">La Guida introduttiva contiene una serie di lezioni che esplorano la diramazione e costrutti del linguaggio c# di ciclo.</span><span class="sxs-lookup"><span data-stu-id="35159-106">The quick start contains a series of lessons that explore branching and looping constructs in C#.</span></span> <span data-ttu-id="35159-107">Queste lezioni presentano le nozioni fondamentali del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="35159-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="35159-108">Questa Guida introduttiva prevede di disporre di un computer in cui che è possibile utilizzare per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="35159-108">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="35159-109">L'argomento .NET [Introduzione a 10 minuti](https://www.microsoft.com/net/core) con le istruzioni per configurare l'ambiente di sviluppo locale in Mac, Linux o PC.</span><span class="sxs-lookup"><span data-stu-id="35159-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

## <a name="make-decisions-using-the-if-statement"></a><span data-ttu-id="35159-110">Prendere le decisioni utilizzando il `if` istruzione</span><span class="sxs-lookup"><span data-stu-id="35159-110">Make decisions using the `if` statement</span></span>

<span data-ttu-id="35159-111">Creare una directory denominata **Guida introduttiva di rami**.</span><span class="sxs-lookup"><span data-stu-id="35159-111">Create a directory named **branches-quickstart**.</span></span> <span data-ttu-id="35159-112">Impostarla come directory corrente ed eseguire `dotnet new console -n BranchesAndLoops -o .`.</span><span class="sxs-lookup"><span data-stu-id="35159-112">Make that the current directory and run `dotnet new console -n BranchesAndLoops -o .`.</span></span> <span data-ttu-id="35159-113">Questo comando crea una nuova applicazione console .NET Core nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="35159-113">This command creates a new .NET Core console application in the current directory.</span></span> 

<span data-ttu-id="35159-114">Aprire **Program.cs** nel proprio editor preferito e sostituire la riga `Console.Writeline("Hello World!");` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="35159-114">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following code:</span></span>

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

<span data-ttu-id="35159-115">Provare questo codice digitando `dotnet run` nella finestra di console.</span><span class="sxs-lookup"><span data-stu-id="35159-115">Try this code by typing `dotnet run` in the your console window.</span></span> <span data-ttu-id="35159-116">Verrà visualizzato il messaggio "la risposta è maggiore di 10".</span><span class="sxs-lookup"><span data-stu-id="35159-116">You should see the message "The answer is greater than 10."</span></span> <span data-ttu-id="35159-117">stampato sulla console.</span><span class="sxs-lookup"><span data-stu-id="35159-117">printed to your console.</span></span>

<span data-ttu-id="35159-118">Modificare la dichiarazione di `b` in modo che la somma sia minore di 10:</span><span class="sxs-lookup"><span data-stu-id="35159-118">Modify the declaration of `b` so that the sum is less than 10:</span></span> 

```csharp
int b = 3;
```

<span data-ttu-id="35159-119">Tipo `dotnet run` nuovamente.</span><span class="sxs-lookup"><span data-stu-id="35159-119">Type `dotnet run` again.</span></span> <span data-ttu-id="35159-120">Dato che la risposta è minore a 10, non viene visualizzato nulla.</span><span class="sxs-lookup"><span data-stu-id="35159-120">Because the answer is less than 10, nothing is printed.</span></span> <span data-ttu-id="35159-121">La **condizione** testata è false.</span><span class="sxs-lookup"><span data-stu-id="35159-121">The **condition** you're testing is false.</span></span> <span data-ttu-id="35159-122">Non esiste codice da eseguire perché è stato scritto solo uno dei possibili rami per un'istruzione `if`, ovvero il ramo true.</span><span class="sxs-lookup"><span data-stu-id="35159-122">You don't have any code to execute because you've only written one of the possible branches for an `if` statement: the true branch.</span></span>

> [!TIP]
> <span data-ttu-id="35159-123">Mentre si impara a usare C# (o qualsiasi linguaggio di programmazione) sicuramente si commetteranno errori durante la scrittura del codice.</span><span class="sxs-lookup"><span data-stu-id="35159-123">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="35159-124">Il compilatore sarà individuare e segnalare gli errori.</span><span class="sxs-lookup"><span data-stu-id="35159-124">The compiler will find and report the errors.</span></span> <span data-ttu-id="35159-125">Esaminare attentamente l'output degli errori e il codice che ha generato l'errore.</span><span class="sxs-lookup"><span data-stu-id="35159-125">Look closely the the error output and the code that generated the error.</span></span> <span data-ttu-id="35159-126">L'errore compler consentono in genere di individuare il problema.</span><span class="sxs-lookup"><span data-stu-id="35159-126">The compler error can usually help you find the problem.</span></span> 

<span data-ttu-id="35159-127">Questo primo esempio viene illustrata la potenza di `if` e i tipi booleani.</span><span class="sxs-lookup"><span data-stu-id="35159-127">This first sample shows the power of `if` and Boolean types.</span></span> <span data-ttu-id="35159-128">Oggetto *booleano* è una variabile che può avere uno dei due valori: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="35159-128">A *Boolean* is a variable that can have one of two values: `true` or `false`.</span></span> <span data-ttu-id="35159-129">C# definisce un tipo speciale, `bool` per variabili booleane.</span><span class="sxs-lookup"><span data-stu-id="35159-129">C# defines a special type, `bool` for Boolean variables.</span></span> <span data-ttu-id="35159-130">L'istruzione `if` controlla il valore di un `bool`.</span><span class="sxs-lookup"><span data-stu-id="35159-130">The `if` statement checks the value of a `bool`.</span></span> <span data-ttu-id="35159-131">Quando il valore è `true`, viene eseguita l'istruzione che segue `if`.</span><span class="sxs-lookup"><span data-stu-id="35159-131">When the value is `true`, the statement following the `if` executes.</span></span> <span data-ttu-id="35159-132">In caso contrario, l'istruzione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="35159-132">Otherwise, it is skipped.</span></span> 

<span data-ttu-id="35159-133">Questo processo di controllo delle condizioni ed esecuzione di istruzioni in base a queste condizioni offre molte potenzialità.</span><span class="sxs-lookup"><span data-stu-id="35159-133">This process of checking conditions and executing statements based on those conditions is very powerful.</span></span>


## <a name="make-if-and-else-work-together"></a><span data-ttu-id="35159-134">Usare insieme if ed else</span><span class="sxs-lookup"><span data-stu-id="35159-134">Make if and else work together</span></span>

<span data-ttu-id="35159-135">Per eseguire codice diverso per i rami true e false, è necessario creare un ramo `else` che viene eseguito quando la condizione è false.</span><span class="sxs-lookup"><span data-stu-id="35159-135">To execute different code in both the true and false branches, you create an `else` branch that executes when the condition is false.</span></span> <span data-ttu-id="35159-136">Provare questa.</span><span class="sxs-lookup"><span data-stu-id="35159-136">Try this.</span></span> <span data-ttu-id="35159-137">Aggiungere il codice seguente per le ultime due righe del `Main` metodo (dovrebbe già disporre i primi quattro):</span><span class="sxs-lookup"><span data-stu-id="35159-137">Add the last two lines in the code below to your `Main` method (you should already have the first four):</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

<span data-ttu-id="35159-138">L'istruzione che segue la parola chiave `else` viene eseguita solo quando la condizione testata è `false`.</span><span class="sxs-lookup"><span data-stu-id="35159-138">The statement following the `else` keyword executes only when the condition being tested is `false`.</span></span> <span data-ttu-id="35159-139">La combinazione di `if` e `else` con valore booleano condizioni fornisce tutte le funzionalità necessarie per gestire entrambi un `true` e `false` condizione.</span><span class="sxs-lookup"><span data-stu-id="35159-139">Combining `if` and `else` with Boolean conditions provides all the power you need to handle both a `true` and a `false` condition.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35159-140">Il rientro applicato alle righe successive alle istruzioni `if` e `else` è pensato per i lettori umani.</span><span class="sxs-lookup"><span data-stu-id="35159-140">The indentation under the `if` and `else` statements is for human readers.</span></span>
> <span data-ttu-id="35159-141">Nel linguaggio C# i rientri o gli spazi vuoti non sono significativi.</span><span class="sxs-lookup"><span data-stu-id="35159-141">The C# language doesn't treat indentation or whitespace as significant.</span></span> <span data-ttu-id="35159-142">L'istruzione che segue la parola chiave `if` o `else` verrà eseguita in base alla condizione.</span><span class="sxs-lookup"><span data-stu-id="35159-142">The statement following the `if` or `else` keyword will be executed based on the condition.</span></span> <span data-ttu-id="35159-143">Tutti gli esempi in questa Guida introduttiva seguono una pratica comune per il rientro alle righe in base al flusso di controllo di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="35159-143">All the samples in this quick start follow a common practice to indent lines based on the control flow of statements.</span></span>

<span data-ttu-id="35159-144">Dato che il rientro non è significativo, è necessario usare `{` e `}` per indicare quando si vuole includere più di un'istruzione nel blocco con esecuzione condizionale.</span><span class="sxs-lookup"><span data-stu-id="35159-144">Because indentation is not significant, you need to use `{` and `}` to indicate when you want more than one statement to be part of the block that executes conditionally.</span></span> <span data-ttu-id="35159-145">I programmatori C# usano in genere le parentesi graffe in tutte le clausole `if` e `else`.</span><span class="sxs-lookup"><span data-stu-id="35159-145">C# programmers typically use those braces on all `if` and `else` clauses.</span></span> <span data-ttu-id="35159-146">L'esempio seguente è lo stesso di quello che appena creato.</span><span class="sxs-lookup"><span data-stu-id="35159-146">The following example is the same as the one you just created.</span></span> <span data-ttu-id="35159-147">Modificare il codice precedente in modo che corrisponda il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="35159-147">Modify your code above to match the following code:</span></span>

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
> <span data-ttu-id="35159-148">Resto di questa Guida introduttiva, tutti gli esempi di codice includono le parentesi graffe dopo accettato consigliate.</span><span class="sxs-lookup"><span data-stu-id="35159-148">Through the rest of this quick start, the code samples all include the braces, following accepted practices.</span></span>

<span data-ttu-id="35159-149">È possibile verificare le condizioni più complesse.</span><span class="sxs-lookup"><span data-stu-id="35159-149">You can test more complicated conditions.</span></span> <span data-ttu-id="35159-150">Aggiungere il codice seguente nel `Main` metodo dopo il codice scritto finora:</span><span class="sxs-lookup"><span data-stu-id="35159-150">Add the following code in your `Main` method after the code you've written so far:</span></span>

```csharp
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
```

<span data-ttu-id="35159-151">`&&` rappresenta "e"</span><span class="sxs-lookup"><span data-stu-id="35159-151">The `&&` represents "and".</span></span> <span data-ttu-id="35159-152">e significa che entrambe le condizioni devono essere true per eseguire l'istruzione nel ramo true.</span><span class="sxs-lookup"><span data-stu-id="35159-152">It means both conditions must be true to execute the statement in the true branch.</span></span>  <span data-ttu-id="35159-153">Questi esempi mostrano anche che è possibile includere più istruzioni in ogni ramo condizionale, a condizione di racchiuderle tra `{` e `}`.</span><span class="sxs-lookup"><span data-stu-id="35159-153">These examples also show that you can have multiple statements in each conditional branch, provided you enclose them in `{` and `}`.</span></span>

<span data-ttu-id="35159-154">È inoltre possibile utilizzare `||` per rappresentare "o".</span><span class="sxs-lookup"><span data-stu-id="35159-154">You can also use  `||` to represent "or".</span></span> <span data-ttu-id="35159-155">Dopo di ciò che è stato scritto fino a questo punto, aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="35159-155">Add the following code after what you've written so far:</span></span>

```csharp
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
```

<span data-ttu-id="35159-156">Il primo passaggio per volta.</span><span class="sxs-lookup"><span data-stu-id="35159-156">You've finished the first step.</span></span> <span data-ttu-id="35159-157">Prima di iniziare la sezione successiva, è necessario spostare il codice corrente in un metodo separato.</span><span class="sxs-lookup"><span data-stu-id="35159-157">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="35159-158">In questo modo sarà più semplice iniziare a lavorare con un nuovo esempio.</span><span class="sxs-lookup"><span data-stu-id="35159-158">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="35159-159">Rinominare il metodo `Main` in `ExploreIf` e scrivere un nuovo metodo `Main` che chiama `ExploreIf`.</span><span class="sxs-lookup"><span data-stu-id="35159-159">Rename your `Main` method to `ExploreIf` and write a new `Main` method that calls `ExploreIf`.</span></span> <span data-ttu-id="35159-160">Al termine, il codice dovrebbe risultare simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="35159-160">When you have finished, your code should look like this:</span></span>

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

<span data-ttu-id="35159-161">Commentare la chiamata a `ExploreIf()`.</span><span class="sxs-lookup"><span data-stu-id="35159-161">Comment out the call to `ExploreIf()`.</span></span> <span data-ttu-id="35159-162">L'output che meno pieno di informazioni mentre si lavora in questa sezione sarà:</span><span class="sxs-lookup"><span data-stu-id="35159-162">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//ExploreIf();
```

<span data-ttu-id="35159-163">Il `//` avvia un **commento** in c#.</span><span class="sxs-lookup"><span data-stu-id="35159-163">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="35159-164">I commenti sono qualsiasi testo che si desidera mantenere nel codice sorgente, ma non è stato eseguito come codice.</span><span class="sxs-lookup"><span data-stu-id="35159-164">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="35159-165">Il compilatore non genera codice eseguibile da commenti.</span><span class="sxs-lookup"><span data-stu-id="35159-165">The compiler does not generate any executable code from comments.</span></span>

## <a name="use-loops-to-repeat-operations"></a><span data-ttu-id="35159-166">Usare i cicli per ripetere le operazioni</span><span class="sxs-lookup"><span data-stu-id="35159-166">Use loops to repeat operations</span></span>

<span data-ttu-id="35159-167">In questa sezione useranno **cicli** ripetere le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="35159-167">In this section you use **loops** to repeat statements.</span></span> <span data-ttu-id="35159-168">Provare questo codice nel `Main` metodo:</span><span class="sxs-lookup"><span data-stu-id="35159-168">Try this code in your `Main` method:</span></span>

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

<span data-ttu-id="35159-169">Il `while` istruzione verifica una condizione ed esegue l'istruzione o un blocco di istruzione che segue il `while`.</span><span class="sxs-lookup"><span data-stu-id="35159-169">The `while` statement checks a condition and executes the statement or statement block following the `while`.</span></span> <span data-ttu-id="35159-170">Verifica ripetutamente la condizione e l'esecuzione di tali istruzioni fino a quando la condizione è false.</span><span class="sxs-lookup"><span data-stu-id="35159-170">It repeatedly checks the condition and executing those statements until the condition is false.</span></span>

<span data-ttu-id="35159-171">Questo esempio include un altro operatore nuovo.</span><span class="sxs-lookup"><span data-stu-id="35159-171">There's one other new operator in this example.</span></span> <span data-ttu-id="35159-172">I caratteri `++` dopo la variabile `counter` rappresentano l'operatore di **incremento**.</span><span class="sxs-lookup"><span data-stu-id="35159-172">The `++` after the `counter` variable is the **increment** operator.</span></span> <span data-ttu-id="35159-173">Viene aggiunto 1 al valore di `counter` e archivia il valore nel `counter` variabile.</span><span class="sxs-lookup"><span data-stu-id="35159-173">It adds 1 to the value of `counter` and stores that value in the `counter` variable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35159-174">Assicurarsi che il `while` ciclo modifiche condizione su false quando si esegue il codice.</span><span class="sxs-lookup"><span data-stu-id="35159-174">Make sure that the `while` loop condition changes to false as you execute the code.</span></span> <span data-ttu-id="35159-175">In caso contrario, si crea un **ciclo infinito** in cui il programma non termina mai.</span><span class="sxs-lookup"><span data-stu-id="35159-175">Otherwise, you create an **infinite loop** where your program never ends.</span></span> <span data-ttu-id="35159-176">Che non viene dimostrata in questo esempio, in quanto è necessario forzare la chiusura utilizzando il programma **CTRL-C** o altri metodi.</span><span class="sxs-lookup"><span data-stu-id="35159-176">That is not demonstrated in this sample, because you have to force your program to quit using **CTRL-C** or other means.</span></span>

<span data-ttu-id="35159-177">Il ciclo `while` testa la condizione prima di eseguire il codice dopo `while`.</span><span class="sxs-lookup"><span data-stu-id="35159-177">The `while` loop tests the condition before executing the code following the `while`.</span></span> <span data-ttu-id="35159-178">Il ciclo `do` ... `while` esegue prima il codice e poi controlla la condizione,</span><span class="sxs-lookup"><span data-stu-id="35159-178">The `do` ... `while` loop executes the code first, and then checks the condition.</span></span> <span data-ttu-id="35159-179">L'attività durante il ciclo è illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="35159-179">The do while loop is shown in the following code:</span></span>

```csharp
counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

<span data-ttu-id="35159-180">Questo `do` ciclo e la precedente `while` ciclo producono lo stesso output.</span><span class="sxs-lookup"><span data-stu-id="35159-180">This `do` loop and the earlier `while` loop produce the same output.</span></span>

## <a name="work-with-the-for-loop"></a><span data-ttu-id="35159-181">Usare il ciclo for</span><span class="sxs-lookup"><span data-stu-id="35159-181">Work with the for loop</span></span>

<span data-ttu-id="35159-182">Il **per** ciclo viene utilizzato comunemente in c#.</span><span class="sxs-lookup"><span data-stu-id="35159-182">The **for** loop is commonly used in C#.</span></span> <span data-ttu-id="35159-183">Provare questo codice nel metodo Main ():</span><span class="sxs-lookup"><span data-stu-id="35159-183">Try this code in your Main() method:</span></span>

```csharp
for(int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
} 
```

<span data-ttu-id="35159-184">Questo codice esegue le stesse operazioni di ciclo `while` e `do` già usate.</span><span class="sxs-lookup"><span data-stu-id="35159-184">This does the same work as the `while` loop and the `do` loop you've already used.</span></span> <span data-ttu-id="35159-185">L'istruzione `for` è composta da tre parti che ne controllano il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="35159-185">The `for` statement has three parts that control how it works.</span></span> 

<span data-ttu-id="35159-186">La prima parte è l'**inizializzatore for**: `for index = 0;` dichiara che `index` è la variabile di ciclo e imposta il valore iniziale su `0`.</span><span class="sxs-lookup"><span data-stu-id="35159-186">The first part is the **for initializer**: `for index = 0;` declares that `index` is the loop variable, and sets its initial value to `0`.</span></span>

<span data-ttu-id="35159-187">La parte centrale è la **condizione for**: `index < 10` dichiara che questo ciclo `for` continua l'esecuzione fino a quando il valore del contatore è minore di 10.</span><span class="sxs-lookup"><span data-stu-id="35159-187">The middle part is the **for condition**: `index < 10` declares that this `for` loop continues to execute as long as the value of counter is less than 10.</span></span>

<span data-ttu-id="35159-188">La parte finale è l'**iteratore for**: `index++` specifica come modificare la variabile di ciclo dopo l'esecuzione del blocco successivo all'istruzione `for`.</span><span class="sxs-lookup"><span data-stu-id="35159-188">The final part is the **for iterator**: `index++` specifies how to modify the loop variable after executing the block following the `for` statement.</span></span> <span data-ttu-id="35159-189">In questo caso, specifica che `index` deve essere incrementato di 1 a ogni esecuzione del blocco.</span><span class="sxs-lookup"><span data-stu-id="35159-189">Here, it specifies that `index` should be incremented by 1 each time the block executes.</span></span>

<span data-ttu-id="35159-190">Sperimentare da soli questi elementi.</span><span class="sxs-lookup"><span data-stu-id="35159-190">Experiment with these yourself.</span></span> <span data-ttu-id="35159-191">Eseguire queste prove:</span><span class="sxs-lookup"><span data-stu-id="35159-191">Try each of the following:</span></span>

- <span data-ttu-id="35159-192">Cambiare l'inizializzatore in modo che inizi da un valore diverso.</span><span class="sxs-lookup"><span data-stu-id="35159-192">Change the initializer to start at a different value.</span></span>
- <span data-ttu-id="35159-193">Cambiare la condizione in modo che si interrompa in corrispondenza di un valore diverso.</span><span class="sxs-lookup"><span data-stu-id="35159-193">Change the condition to stop at a different value.</span></span>

<span data-ttu-id="35159-194">Al termine, passare alla prossima lezione che prevede la scrittura di codice per usare quanto finora appreso.</span><span class="sxs-lookup"><span data-stu-id="35159-194">When you're done, let's move on to write some code yourself to use what you've learned.</span></span>

## <a name="combine-branches-and-loops"></a><span data-ttu-id="35159-195">Combinare i cicli e diramazioni</span><span class="sxs-lookup"><span data-stu-id="35159-195">Combine branches and loops</span></span>

<span data-ttu-id="35159-196">Dopo aver esaminato l'istruzione `if` e i costrutti per i cicli nel linguaggio C#, provare a scrivere codice C# per ottenere la somma di tutti i numeri interi da 1 a 20 divisibili per 3.</span><span class="sxs-lookup"><span data-stu-id="35159-196">Now that you've seen the `if` statement and the looping constructs in the C# language, see if you can write C# code to find the sum of all integers 1 through 20 that are divisible by 3.</span></span>  <span data-ttu-id="35159-197">Ecco alcuni suggerimenti:</span><span class="sxs-lookup"><span data-stu-id="35159-197">Here are a few hints:</span></span>

- <span data-ttu-id="35159-198">L'operatore `%` restituisce il resto di un'operazione di divisione.</span><span class="sxs-lookup"><span data-stu-id="35159-198">The `%` operator gives you the remainder of a division operation.</span></span>
- <span data-ttu-id="35159-199">Il `if` istruzione che permette la condizione per vedere se un numero deve essere parte della somma.</span><span class="sxs-lookup"><span data-stu-id="35159-199">The `if` statement gives you the condition to see if a number should be part of the sum.</span></span>
- <span data-ttu-id="35159-200">Il ciclo `for` può essere utile per ripetere una serie di passaggi per tutti i numeri da 1 a 20.</span><span class="sxs-lookup"><span data-stu-id="35159-200">The `for` loop can help you repeat a series of steps for all the numbers 1 through 20.</span></span>

<span data-ttu-id="35159-201">Sperimentare e quindi</span><span class="sxs-lookup"><span data-stu-id="35159-201">Try it yourself.</span></span> <span data-ttu-id="35159-202">controllare i risultati.</span><span class="sxs-lookup"><span data-stu-id="35159-202">Then check how you did.</span></span> <span data-ttu-id="35159-203">È possibile visualizzare una possibile risposta da [visualizzando il codice completato su GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).</span><span class="sxs-lookup"><span data-stu-id="35159-203">You can see one possible answer by [viewing the completed code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).</span></span>

<span data-ttu-id="35159-204">È stata completata la "rami e cicli" Guida introduttiva.</span><span class="sxs-lookup"><span data-stu-id="35159-204">You've completed the "branches and loops" quick start.</span></span>

<span data-ttu-id="35159-205">È possibile continuare con la [matrici e raccolte](arrays-and-collections.md) avvio rapido nel proprio ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="35159-205">You can continue with the [Arrays and collections](arrays-and-collections.md) quick start in your own development environment.</span></span>

<span data-ttu-id="35159-206">Maggiori informazioni su questi concetti sono disponibili in questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="35159-206">You can learn more about these concepts in these topics:</span></span>

<span data-ttu-id="35159-207">[Istruzioni if ed else](../language-reference/keywords/if-else.md) </span><span class="sxs-lookup"><span data-stu-id="35159-207">[If and else statement](../language-reference/keywords/if-else.md) </span></span>  
<span data-ttu-id="35159-208">[Istruzione while](../language-reference/keywords/while.md) </span><span class="sxs-lookup"><span data-stu-id="35159-208">[While statement](../language-reference/keywords/while.md) </span></span>  
<span data-ttu-id="35159-209">[Istruzione do](../language-reference/keywords/do.md) </span><span class="sxs-lookup"><span data-stu-id="35159-209">[Do statement](../language-reference/keywords/do.md) </span></span>  
[<span data-ttu-id="35159-210">Istruzione for</span><span class="sxs-lookup"><span data-stu-id="35159-210">For statement</span></span>](../language-reference/keywords/for.md)   

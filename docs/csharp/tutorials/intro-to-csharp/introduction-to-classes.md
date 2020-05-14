---
title: Classi e oggetti - Esercitazione introduttiva su C#
description: Creare il primo programma C# ed esplorare i concetti della programmazione orientata a oggetti
ms.date: 10/11/2017
ms.custom: mvc
ms.openlocfilehash: 5edb2d7b11caace2d794b7958dfeb75ef502ee2b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396873"
---
# <a name="explore-object-oriented-programming-with-classes-and-objects"></a><span data-ttu-id="eec81-103">Esplorare la programmazione orientata agli oggetti con classi e oggetti</span><span class="sxs-lookup"><span data-stu-id="eec81-103">Explore object oriented programming with classes and objects</span></span>

<span data-ttu-id="eec81-104">Questa esercitazione prevede la presenza di un computer da usare per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="eec81-104">This tutorial expects that you have a machine you can use for development.</span></span> <span data-ttu-id="eec81-105">L'esercitazione .NET [Hello World in 10 minuti](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) contiene le istruzioni per configurare l'ambiente di sviluppo locale in Windows, Linux o MacOS.</span><span class="sxs-lookup"><span data-stu-id="eec81-105">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="eec81-106">Una breve panoramica dei comandi usati è disponibile in [Acquisire familiarità con gli strumenti di sviluppo](local-environment.md), che contiene collegamenti a informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="eec81-106">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="eec81-107">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="eec81-107">Create your application</span></span>

<span data-ttu-id="eec81-108">Usare una finestra del terminale per creare una directory denominata *classes*.</span><span class="sxs-lookup"><span data-stu-id="eec81-108">Using a terminal window, create a directory named *classes*.</span></span> <span data-ttu-id="eec81-109">L'applicazione verrà creata in questa posizione.</span><span class="sxs-lookup"><span data-stu-id="eec81-109">You'll build your application there.</span></span> <span data-ttu-id="eec81-110">Passare alla directory e digitare `dotnet new console` nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="eec81-110">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="eec81-111">Questo comando crea l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eec81-111">This command creates your application.</span></span> <span data-ttu-id="eec81-112">Aprire *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="eec81-112">Open *Program.cs*.</span></span> <span data-ttu-id="eec81-113">L'aspetto dovrebbe risultare simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="eec81-113">It should look like this:</span></span>

```csharp
using System;

namespace classes
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="eec81-114">In questa esercitazione verranno creati nuovi tipi che rappresentano un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="eec81-114">In this tutorial, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="eec81-115">In genere, gli sviluppatori definiscono ogni classe in un file di testo diverso.</span><span class="sxs-lookup"><span data-stu-id="eec81-115">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="eec81-116">In questo modo è più semplice gestire l'aumento di dimensioni di un programma.</span><span class="sxs-lookup"><span data-stu-id="eec81-116">That makes it easier to manage as a program grows in size.</span></span> <span data-ttu-id="eec81-117">Creare un nuovo file denominato *BankAccount.cs* nella directory *classes*.</span><span class="sxs-lookup"><span data-stu-id="eec81-117">Create a new file named *BankAccount.cs* in the *classes* directory.</span></span>

<span data-ttu-id="eec81-118">Questo file conterrà la definizione di un ***conto bancario***.</span><span class="sxs-lookup"><span data-stu-id="eec81-118">This file will contain the definition of a ***bank account***.</span></span> <span data-ttu-id="eec81-119">Nella programmazione orientata a oggetti il codice viene organizzato tramite la creazione di tipi sotto forma di ***classi***.</span><span class="sxs-lookup"><span data-stu-id="eec81-119">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="eec81-120">Queste classi contengono il codice che rappresenta un'entità specifica.</span><span class="sxs-lookup"><span data-stu-id="eec81-120">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="eec81-121">La classe `BankAccount` rappresenta un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="eec81-121">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="eec81-122">Il codice implementa operazioni specifiche tramite metodi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="eec81-122">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="eec81-123">In questa esercitazione il conto bancario supporta questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="eec81-123">In this tutorial, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="eec81-124">Esiste un numero di 10 cifre che identifica in modo univoco il conto.</span><span class="sxs-lookup"><span data-stu-id="eec81-124">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="eec81-125">Esiste una stringa in cui vengono archiviati i nomi dei titolari.</span><span class="sxs-lookup"><span data-stu-id="eec81-125">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="eec81-126">È possibile recuperare il saldo.</span><span class="sxs-lookup"><span data-stu-id="eec81-126">The balance can be retrieved.</span></span>
1. <span data-ttu-id="eec81-127">Il conto accetta versamenti.</span><span class="sxs-lookup"><span data-stu-id="eec81-127">It accepts deposits.</span></span>
1. <span data-ttu-id="eec81-128">Il conto accetta prelievi.</span><span class="sxs-lookup"><span data-stu-id="eec81-128">It accepts withdrawals.</span></span>
1. <span data-ttu-id="eec81-129">Il saldo iniziale deve essere positivo.</span><span class="sxs-lookup"><span data-stu-id="eec81-129">The initial balance must be positive.</span></span>
1. <span data-ttu-id="eec81-130">I prelievi non possono risultare in un saldo negativo.</span><span class="sxs-lookup"><span data-stu-id="eec81-130">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="eec81-131">Definire il tipo di conto bancario</span><span class="sxs-lookup"><span data-stu-id="eec81-131">Define the bank account type</span></span>

<span data-ttu-id="eec81-132">Per iniziare, è possibile creare gli elementi di base di una classe che definisce questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="eec81-132">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="eec81-133">Creare un nuovo file usando il comando **file: New** .</span><span class="sxs-lookup"><span data-stu-id="eec81-133">Create a new file using the **File:New** command.</span></span> <span data-ttu-id="eec81-134">Denominarlo *BankAccount.cs*.</span><span class="sxs-lookup"><span data-stu-id="eec81-134">Name it *BankAccount.cs*.</span></span> <span data-ttu-id="eec81-135">Aggiungere il codice seguente al file *BankAccount.cs* :</span><span class="sxs-lookup"><span data-stu-id="eec81-135">Add the following code to your *BankAccount.cs* file:</span></span>

```csharp
using System;

namespace classes
{
    public class BankAccount
    {
        public string Number { get; }
        public string Owner { get; set; }
        public decimal Balance { get; }

        public void MakeDeposit(decimal amount, DateTime date, string note)
        {
        }

        public void MakeWithdrawal(decimal amount, DateTime date, string note)
        {
        }
    }
}
```

<span data-ttu-id="eec81-136">Prima di procedere, è opportuno esaminare il codice finora creato.</span><span class="sxs-lookup"><span data-stu-id="eec81-136">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="eec81-137">La dichiarazione `namespace` offre un modo per organizzare logicamente il codice.</span><span class="sxs-lookup"><span data-stu-id="eec81-137">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="eec81-138">Poiché questa esercitazione è relativamente breve, si inserirà il codice in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="eec81-138">This tutorial is relatively small, so you'll put all the code in one namespace.</span></span>

<span data-ttu-id="eec81-139">`public class BankAccount` definisce la classe, o tipo, che si sta creando.</span><span class="sxs-lookup"><span data-stu-id="eec81-139">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="eec81-140">Tutti gli elementi all'interno di `{` e `}` che seguono la dichiarazione di classe definiscono lo stato e il comportamento della classe.</span><span class="sxs-lookup"><span data-stu-id="eec81-140">Everything inside the `{` and `}` that follows the class declaration defines the state and behavior of the class.</span></span> <span data-ttu-id="eec81-141">Esistono cinque ***membri*** della classe `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="eec81-141">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="eec81-142">I primi tre sono ***proprietà***.</span><span class="sxs-lookup"><span data-stu-id="eec81-142">The first three are ***properties***.</span></span> <span data-ttu-id="eec81-143">Le proprietà sono elementi di dati e possono contenere codice per l'applicazione della convalida o di altre regole.</span><span class="sxs-lookup"><span data-stu-id="eec81-143">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="eec81-144">Gli ultimi due sono ***metodi***.</span><span class="sxs-lookup"><span data-stu-id="eec81-144">The last two are ***methods***.</span></span> <span data-ttu-id="eec81-145">I metodi sono blocchi di codice che eseguono una singola funzione.</span><span class="sxs-lookup"><span data-stu-id="eec81-145">Methods are blocks of code that perform a single function.</span></span> <span data-ttu-id="eec81-146">La lettura dei nomi di ogni membro dovrebbe fornire informazioni sufficienti per consentire all'utente o a un altro sviluppatore di capire gli scopi della classe.</span><span class="sxs-lookup"><span data-stu-id="eec81-146">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="eec81-147">Aprire un nuovo conto</span><span class="sxs-lookup"><span data-stu-id="eec81-147">Open a new account</span></span>

<span data-ttu-id="eec81-148">La prima funzionalità da implementare è l'apertura di un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="eec81-148">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="eec81-149">Quando un cliente apre un conto, deve specificare il saldo iniziale e informazioni sul titolare o i titolari del conto.</span><span class="sxs-lookup"><span data-stu-id="eec81-149">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span>

<span data-ttu-id="eec81-150">La creazione di un nuovo oggetto di tipo `BankAccount` implica la definizione di un ***costruttore*** che assegna questi valori.</span><span class="sxs-lookup"><span data-stu-id="eec81-150">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="eec81-151">Un ***costruttore*** è un membro con lo stesso nome della classe</span><span class="sxs-lookup"><span data-stu-id="eec81-151">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="eec81-152">e viene usato per inizializzare oggetti di quel tipo di classe.</span><span class="sxs-lookup"><span data-stu-id="eec81-152">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="eec81-153">Aggiungere il costruttore seguente al `BankAccount` tipo.</span><span class="sxs-lookup"><span data-stu-id="eec81-153">Add the following constructor to the `BankAccount` type.</span></span> <span data-ttu-id="eec81-154">Inserire il codice seguente sopra la dichiarazione di `MakeDeposit` :</span><span class="sxs-lookup"><span data-stu-id="eec81-154">Place the following code above the declaration of `MakeDeposit`:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="eec81-155">I costruttori vengono chiamati quando si crea un oggetto usando [`new`](../../language-reference/operators/new-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="eec81-155">Constructors are called when you create an object using [`new`](../../language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="eec81-156">Sostituire la riga `Console.WriteLine("Hello World!");` in *Program.cs* con il codice seguente (sostituire `<name>` con il proprio nome):</span><span class="sxs-lookup"><span data-stu-id="eec81-156">Replace the line `Console.WriteLine("Hello World!");` in *Program.cs* with the following code (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name>", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="eec81-157">Eseguiamo ora le operazioni create.</span><span class="sxs-lookup"><span data-stu-id="eec81-157">Let's run what you've built so far.</span></span> <span data-ttu-id="eec81-158">Se si usa Visual Studio, scegliere **Avvia senza eseguire debug** dal menu **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="eec81-158">If you're using Visual Studio, Select **Start without debugging** from the **Run** menu.</span></span> <span data-ttu-id="eec81-159">Se si usa una riga di comando, digitare `dotnet run` la directory in cui è stato creato il progetto.</span><span class="sxs-lookup"><span data-stu-id="eec81-159">If you're using a command line, type `dotnet run` in the directory where you've created your project.</span></span>

<span data-ttu-id="eec81-160">Si è notato che il numero di conto è vuoto?</span><span class="sxs-lookup"><span data-stu-id="eec81-160">Did you notice that the account number is blank?</span></span> <span data-ttu-id="eec81-161">È tempo di correggere questa mancanza.</span><span class="sxs-lookup"><span data-stu-id="eec81-161">It's time to fix that.</span></span> <span data-ttu-id="eec81-162">Il numero di conto deve essere assegnato al momento della costruzione dell'oggetto,</span><span class="sxs-lookup"><span data-stu-id="eec81-162">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="eec81-163">ma la sua creazione non deve essere responsabilità del chiamante.</span><span class="sxs-lookup"><span data-stu-id="eec81-163">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="eec81-164">Il codice della classe `BankAccount` deve sapere come assegnare nuovi numeri di conto.</span><span class="sxs-lookup"><span data-stu-id="eec81-164">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="eec81-165">Un modo semplice per eseguire questa operazione consiste nell'iniziare con un numero da 10 cifre</span><span class="sxs-lookup"><span data-stu-id="eec81-165">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="eec81-166">e incrementarlo per la creazione di ogni nuovo conto.</span><span class="sxs-lookup"><span data-stu-id="eec81-166">Increment it when each new account is created.</span></span> <span data-ttu-id="eec81-167">Infine, il numero di conto corrente deve essere archiviato quando viene costruito un oggetto.</span><span class="sxs-lookup"><span data-stu-id="eec81-167">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="eec81-168">Aggiungere una dichiarazione di membro alla `BankAccount` classe.</span><span class="sxs-lookup"><span data-stu-id="eec81-168">Add a member declaration to the `BankAccount` class.</span></span> <span data-ttu-id="eec81-169">Posizionare la riga di codice seguente dopo la parentesi graffa `{` di apertura all'inizio della `BankAccount` classe:</span><span class="sxs-lookup"><span data-stu-id="eec81-169">Place the following line of code after the opening brace `{` at the beginning of the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="eec81-170">Questo è un membro dati.</span><span class="sxs-lookup"><span data-stu-id="eec81-170">This is a data member.</span></span> <span data-ttu-id="eec81-171">Il membro è `private`, ovvero è accessibile solo dal codice all'interno della classe `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="eec81-171">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="eec81-172">Si tratta di un modo per separare le responsabilità pubbliche, ad esempio la presenza di un numero di conto, dall'implementazione privata (in che modo vengono generati i numeri di account).</span><span class="sxs-lookup"><span data-stu-id="eec81-172">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated).</span></span> <span data-ttu-id="eec81-173">È anche `static`, ovvero è condiviso tra tutti gli oggetti `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="eec81-173">It is also `static`, which means it is shared by all of the `BankAccount` objects.</span></span> <span data-ttu-id="eec81-174">Il valore di una variabile non statica è univoco per ogni istanza dell'oggetto `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="eec81-174">The value of a non-static variable is unique to each instance of the `BankAccount` object.</span></span> <span data-ttu-id="eec81-175">Aggiungere le due righe seguenti al costruttore per assegnare il numero di conto.</span><span class="sxs-lookup"><span data-stu-id="eec81-175">Add the following two lines to the constructor to assign the account number.</span></span> <span data-ttu-id="eec81-176">Posizionarli dopo la riga seguente `this.Balance = initialBalance` :</span><span class="sxs-lookup"><span data-stu-id="eec81-176">Place them after the line that says `this.Balance = initialBalance`:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="eec81-177">Digitare `dotnet run` per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="eec81-177">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="eec81-178">Creare versamenti e prelievi</span><span class="sxs-lookup"><span data-stu-id="eec81-178">Create deposits and withdrawals</span></span>

<span data-ttu-id="eec81-179">La classe del conto bancario deve accettare versamenti e prelievi per funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="eec81-179">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="eec81-180">I versamenti e i prelievi vengono implementati tramite la creazione di un registro di ogni transazione per il conto.</span><span class="sxs-lookup"><span data-stu-id="eec81-180">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="eec81-181">Ciò presenta alcuni vantaggi rispetto al semplice aggiornamento del saldo per ogni transazione.</span><span class="sxs-lookup"><span data-stu-id="eec81-181">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="eec81-182">È possibile usare la cronologia per controllare tutte le transazioni e gestire i saldi giornalieri.</span><span class="sxs-lookup"><span data-stu-id="eec81-182">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="eec81-183">Grazie alla possibilità di calcolare il saldo dalla cronologia di tutte le transazioni all'occorrenza, eventuali errori in una singola transazione risolti saranno rispecchiati correttamente nel saldo dopo il calcolo successivo.</span><span class="sxs-lookup"><span data-stu-id="eec81-183">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="eec81-184">Per iniziare, occorre creare un nuovo tipo per rappresentare una transazione.</span><span class="sxs-lookup"><span data-stu-id="eec81-184">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="eec81-185">Si tratta di un tipo semplice senza responsabilità,</span><span class="sxs-lookup"><span data-stu-id="eec81-185">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="eec81-186">che richiede alcune proprietà.</span><span class="sxs-lookup"><span data-stu-id="eec81-186">It needs a few properties.</span></span> <span data-ttu-id="eec81-187">Creare un nuovo file denominato *Transaction.cs*.</span><span class="sxs-lookup"><span data-stu-id="eec81-187">Create a new file named *Transaction.cs*.</span></span> <span data-ttu-id="eec81-188">Aggiungere alla classe il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="eec81-188">Add the following code to it:</span></span>

[!code-csharp[Transaction](~/samples/snippets/csharp/classes-quickstart/Transaction.cs)]

<span data-ttu-id="eec81-189">A questo punto, aggiungere un <xref:System.Collections.Generic.List%601> di oggetti `Transaction` alla classe `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="eec81-189">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="eec81-190">Aggiungere la dichiarazione seguente dopo il costruttore nel file *BankAccount.cs* :</span><span class="sxs-lookup"><span data-stu-id="eec81-190">Add the following declaration after the constructor in your *BankAccount.cs* file:</span></span>

[!code-csharp[TransactionDecl](~/samples/snippets/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration)]

<span data-ttu-id="eec81-191">La classe <xref:System.Collections.Generic.List%601> richiede di importare uno spazio dei nomi diverso.</span><span class="sxs-lookup"><span data-stu-id="eec81-191">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="eec81-192">Aggiungere il codice seguente all'inizio di *BankAccount.cs*:</span><span class="sxs-lookup"><span data-stu-id="eec81-192">Add the following at the beginning of *BankAccount.cs*:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="eec81-193">A questo punto, occorre modificare il modo in cui viene indicato il saldo (`Balance`).</span><span class="sxs-lookup"><span data-stu-id="eec81-193">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="eec81-194">Per ottenere il saldo, è possibile sommare i valori di tutte le transazioni.</span><span class="sxs-lookup"><span data-stu-id="eec81-194">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="eec81-195">Modificare la dichiarazione di `Balance` nella classe `BankAccount` come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="eec81-195">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](~/samples/snippets/csharp/classes-quickstart/BankAccount.cs#BalanceComputation)]

<span data-ttu-id="eec81-196">Questo esempio illustra un aspetto importante delle ***proprietà***.</span><span class="sxs-lookup"><span data-stu-id="eec81-196">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="eec81-197">Il saldo viene ora calcolato quando un altro programmatore richiede il valore.</span><span class="sxs-lookup"><span data-stu-id="eec81-197">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="eec81-198">Il calcolo enumera tutte le transazioni e fornisce la somma come saldo corrente.</span><span class="sxs-lookup"><span data-stu-id="eec81-198">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="eec81-199">Implementare ora i metodi `MakeDeposit` e `MakeWithdrawal`.</span><span class="sxs-lookup"><span data-stu-id="eec81-199">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="eec81-200">Questi metodi applicheranno le due regole finali, ovvero che il saldo iniziale deve essere positivo e che qualsiasi prelievo non può risultare in un saldo negativo.</span><span class="sxs-lookup"><span data-stu-id="eec81-200">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span>

<span data-ttu-id="eec81-201">Viene così introdotto il concetto di ***eccezioni***.</span><span class="sxs-lookup"><span data-stu-id="eec81-201">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="eec81-202">Il modo standard per indicare che un metodo non può completare correttamente le operazioni previste consiste nel generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="eec81-202">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="eec81-203">Il tipo di eccezione e il messaggio associato descrivono l'errore.</span><span class="sxs-lookup"><span data-stu-id="eec81-203">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="eec81-204">In questo caso, il metodo `MakeDeposit` genera un'eccezione se l'importo del versamento è negativo.</span><span class="sxs-lookup"><span data-stu-id="eec81-204">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="eec81-205">Il `MakeWithdrawal` metodo genera un'eccezione se l'importo del prelievo è negativo o se l'applicazione del prelievo comporta un saldo negativo.</span><span class="sxs-lookup"><span data-stu-id="eec81-205">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance.</span></span> <span data-ttu-id="eec81-206">Aggiungere il codice seguente dopo la dichiarazione dell' `allTransactions` elenco:</span><span class="sxs-lookup"><span data-stu-id="eec81-206">Add the following code after the declaration of the `allTransactions` list:</span></span>

[!code-csharp[DepositAndWithdrawal](~/samples/snippets/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal)]

<span data-ttu-id="eec81-207">L' [`throw`](../../language-reference/keywords/throw.md) istruzione **genera** un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="eec81-207">The [`throw`](../../language-reference/keywords/throw.md) statement **throws** an exception.</span></span> <span data-ttu-id="eec81-208">L'esecuzione del blocco corrente termina e il controllo viene trasferito al primo blocco `catch` corrispondente trovato nello stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="eec81-208">Execution of the current block ends, and control transfers to the first matching `catch` block found in the call stack.</span></span> <span data-ttu-id="eec81-209">Più avanti si aggiungerà un blocco `catch` per testare questo codice.</span><span class="sxs-lookup"><span data-stu-id="eec81-209">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="eec81-210">Il costruttore deve ottenere una modifica in modo da aggiungere una transazione iniziale, invece di aggiornare direttamente il saldo.</span><span class="sxs-lookup"><span data-stu-id="eec81-210">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="eec81-211">Dato che il metodo `MakeDeposit` è già stato scritto, chiamarlo dal costruttore.</span><span class="sxs-lookup"><span data-stu-id="eec81-211">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="eec81-212">Il costruttore completato dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="eec81-212">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](~/samples/snippets/csharp/classes-quickstart/BankAccount.cs#Constructor)]

<span data-ttu-id="eec81-213"><xref:System.DateTime.Now?displayProperty=nameWithType> è una proprietà che restituisce la data e l'ora correnti.</span><span class="sxs-lookup"><span data-stu-id="eec81-213"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="eec81-214">Testare questo problema aggiungendo alcuni depositi e prelievi nel `Main` metodo, seguendo il codice che crea un nuovo `BankAccount` :</span><span class="sxs-lookup"><span data-stu-id="eec81-214">Test this by adding a few deposits and withdrawals in your `Main` method, following the code that creates a new `BankAccount`:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "Friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="eec81-215">Successivamente, verificare che si verifichino le condizioni di errore provando a creare un account con un saldo negativo.</span><span class="sxs-lookup"><span data-stu-id="eec81-215">Next, test that you are catching error conditions by trying to create an account with a negative balance.</span></span> <span data-ttu-id="eec81-216">Aggiungere il codice seguente dopo il codice precedente appena aggiunto:</span><span class="sxs-lookup"><span data-stu-id="eec81-216">Add the following code after the preceding code you just added:</span></span>

```csharp
// Test that the initial balances must be positive.
try
{
    var invalidAccount = new BankAccount("invalid", -55);
}
catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="eec81-217">Usare le [ `try` `catch` istruzioni e](../../language-reference/keywords/try-catch.md) per contrassegnare un blocco di codice che può generare eccezioni e per rilevare gli errori previsti.</span><span class="sxs-lookup"><span data-stu-id="eec81-217">You use the [`try` and `catch` statements](../../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions and to catch those errors that you expect.</span></span> <span data-ttu-id="eec81-218">È possibile utilizzare la stessa tecnica per testare il codice che genera un'eccezione per un saldo negativo.</span><span class="sxs-lookup"><span data-stu-id="eec81-218">You can use the same technique to test the code that throws an exception for a negative balance.</span></span> <span data-ttu-id="eec81-219">Aggiungere il codice seguente alla fine del `Main` Metodo:</span><span class="sxs-lookup"><span data-stu-id="eec81-219">Add the following code at the end of your `Main` method:</span></span>

```csharp
// Test for a negative balance.
try
{
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
}
catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="eec81-220">Salvare il file e digitare `dotnet run` per provare il codice.</span><span class="sxs-lookup"><span data-stu-id="eec81-220">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="eec81-221">Esercizio: registrare tutte le transazioni</span><span class="sxs-lookup"><span data-stu-id="eec81-221">Challenge - log all transactions</span></span>

<span data-ttu-id="eec81-222">Per completare questa esercitazione, è possibile scrivere il metodo `GetAccountHistory`, che crea un oggetto `string` per la cronologia delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="eec81-222">To finish this tutorial, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="eec81-223">Aggiungere questo metodo al tipo `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="eec81-223">Add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](~/samples/snippets/csharp/classes-quickstart/BankAccount.cs#History)]

<span data-ttu-id="eec81-224">Questo codice usa la classe <xref:System.Text.StringBuilder> per formattare una stringa che contiene una riga per ogni transazione.</span><span class="sxs-lookup"><span data-stu-id="eec81-224">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="eec81-225">Il codice per la formattazione delle stringhe è stato presentato in precedenza in queste esercitazioni.</span><span class="sxs-lookup"><span data-stu-id="eec81-225">You've seen the string formatting code earlier in these tutorials.</span></span> <span data-ttu-id="eec81-226">`\t` è un nuovo carattere,</span><span class="sxs-lookup"><span data-stu-id="eec81-226">One new character is `\t`.</span></span> <span data-ttu-id="eec81-227">che consente di inserire una tabulazione per formattare l'output.</span><span class="sxs-lookup"><span data-stu-id="eec81-227">That inserts a tab to format the output.</span></span>

<span data-ttu-id="eec81-228">Aggiungere questa riga per testarla in *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="eec81-228">Add this line to test it in *Program.cs*:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="eec81-229">Eseguire il programma per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="eec81-229">Run your program to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="eec81-230">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="eec81-230">Next steps</span></span>

<span data-ttu-id="eec81-231">Se si è rimasti bloccati, è possibile visualizzare l'origine di questa esercitazione [nel repository GitHub](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/classes-quickstart/).</span><span class="sxs-lookup"><span data-stu-id="eec81-231">If you got stuck, you can see the source for this tutorial [in our GitHub repo](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/classes-quickstart/).</span></span>

<span data-ttu-id="eec81-232">Congratulazioni, sono state completate tutte le esercitazioni introduttive su C#.</span><span class="sxs-lookup"><span data-stu-id="eec81-232">Congratulations, you've finished all our introduction to C# tutorials.</span></span> <span data-ttu-id="eec81-233">Per ulteriori informazioni, provare a eseguire altre [esercitazioni](../index.md).</span><span class="sxs-lookup"><span data-stu-id="eec81-233">If you're eager to learn more, try more of our [tutorials](../index.md).</span></span>

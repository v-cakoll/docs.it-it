---
title: Classi e oggetti - Esercitazione introduttiva su C#
description: Creare il primo programma C# ed esplorare i concetti della programmazione orientata a oggetti
ms.date: 10/11/2017
ms.custom: mvc
ms.openlocfilehash: 6b4c135b7adf96de3a234cde02485a1e84fc9fd3
ms.sourcegitcommit: e39d93d358974b9ed4541cedf4e25c0101015c3c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "55204782"
---
# <a name="explore-object-oriented-programming-with-classes-and-objects"></a><span data-ttu-id="7afa7-103">Esplorare la programmazione orientata agli oggetti con classi e oggetti</span><span class="sxs-lookup"><span data-stu-id="7afa7-103">Explore object oriented programming with classes and objects</span></span>

<span data-ttu-id="7afa7-104">Questa esercitazione prevede la presenza di un computer da usare per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="7afa7-104">This tutorial expects that you have a machine you can use for development.</span></span> <span data-ttu-id="7afa7-105">L'argomento [Get started with .NET in 10 minutes](https://www.microsoft.com/net/core) (Iniziare a usare .NET in 10 minuti) contiene istruzioni per la configurazione dell'ambiente di sviluppo locale in Mac, PC o Linux.</span><span class="sxs-lookup"><span data-stu-id="7afa7-105">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="7afa7-106">Una breve panoramica dei comandi usati è disponibile in [Acquisire familiarità con gli strumenti di sviluppo](local-environment.md), che contiene collegamenti a informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="7afa7-106">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="7afa7-107">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="7afa7-107">Create your application</span></span>

<span data-ttu-id="7afa7-108">Usare una finestra del terminale per creare una directory denominata **classes**.</span><span class="sxs-lookup"><span data-stu-id="7afa7-108">Using a terminal window, create a directory named **classes**.</span></span> <span data-ttu-id="7afa7-109">L'applicazione verrà creata in questa posizione.</span><span class="sxs-lookup"><span data-stu-id="7afa7-109">You'll build your application there.</span></span> <span data-ttu-id="7afa7-110">Passare alla directory e digitare `dotnet new console` nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="7afa7-110">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="7afa7-111">Questo comando crea l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7afa7-111">This command creates your application.</span></span> <span data-ttu-id="7afa7-112">Aprire **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="7afa7-112">Open **Program.cs**.</span></span> <span data-ttu-id="7afa7-113">Il codice dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7afa7-113">It should look like this:</span></span>

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

<span data-ttu-id="7afa7-114">In questa esercitazione verranno creati nuovi tipi che rappresentano un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="7afa7-114">In this tutorial, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="7afa7-115">In genere, gli sviluppatori definiscono ogni classe in un file di testo diverso.</span><span class="sxs-lookup"><span data-stu-id="7afa7-115">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="7afa7-116">In questo modo è più semplice gestire l'aumento di dimensioni di un programma.</span><span class="sxs-lookup"><span data-stu-id="7afa7-116">That makes it easier to manage as a program grows in size.</span></span>  <span data-ttu-id="7afa7-117">Creare un nuovo file denominato **BankAccount.cs** nella directory **classes**.</span><span class="sxs-lookup"><span data-stu-id="7afa7-117">Create a new file named **BankAccount.cs** in the **classes** directory.</span></span> 

<span data-ttu-id="7afa7-118">Questo file conterrà la definizione di un ***conto bancario***.</span><span class="sxs-lookup"><span data-stu-id="7afa7-118">This file will contain the definition of a ***bank account***.</span></span> <span data-ttu-id="7afa7-119">Nella programmazione orientata a oggetti il codice viene organizzato tramite la creazione di tipi sotto forma di ***classi***.</span><span class="sxs-lookup"><span data-stu-id="7afa7-119">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="7afa7-120">Queste classi contengono il codice che rappresenta un'entità specifica.</span><span class="sxs-lookup"><span data-stu-id="7afa7-120">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="7afa7-121">La classe `BankAccount` rappresenta un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="7afa7-121">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="7afa7-122">Il codice implementa operazioni specifiche tramite metodi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="7afa7-122">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="7afa7-123">In questa esercitazione il conto bancario supporta questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="7afa7-123">In this tutorial, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="7afa7-124">Esiste un numero di 10 cifre che identifica in modo univoco il conto.</span><span class="sxs-lookup"><span data-stu-id="7afa7-124">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="7afa7-125">Esiste una stringa in cui vengono archiviati i nomi dei titolari.</span><span class="sxs-lookup"><span data-stu-id="7afa7-125">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="7afa7-126">È possibile recuperare il saldo.</span><span class="sxs-lookup"><span data-stu-id="7afa7-126">The balance can be retrieved.</span></span>
1. <span data-ttu-id="7afa7-127">Il conto accetta versamenti.</span><span class="sxs-lookup"><span data-stu-id="7afa7-127">It accepts deposits.</span></span>
1. <span data-ttu-id="7afa7-128">Il conto accetta prelievi.</span><span class="sxs-lookup"><span data-stu-id="7afa7-128">It accepts withdrawals.</span></span>
1. <span data-ttu-id="7afa7-129">Il saldo iniziale deve essere positivo.</span><span class="sxs-lookup"><span data-stu-id="7afa7-129">The initial balance must be positive.</span></span>
1. <span data-ttu-id="7afa7-130">I prelievi non possono risultare in un saldo negativo.</span><span class="sxs-lookup"><span data-stu-id="7afa7-130">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="7afa7-131">Definire il tipo di conto bancario</span><span class="sxs-lookup"><span data-stu-id="7afa7-131">Define the bank account type</span></span>

<span data-ttu-id="7afa7-132">Per iniziare, è possibile creare gli elementi di base di una classe che definisce questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="7afa7-132">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="7afa7-133">Il codice sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7afa7-133">It would look like this:</span></span>

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

<span data-ttu-id="7afa7-134">Prima di procedere, è opportuno esaminare il codice finora creato.</span><span class="sxs-lookup"><span data-stu-id="7afa7-134">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="7afa7-135">La dichiarazione `namespace` offre un modo per organizzare logicamente il codice.</span><span class="sxs-lookup"><span data-stu-id="7afa7-135">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="7afa7-136">Poiché questa esercitazione è relativamente breve, si inserirà il codice in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7afa7-136">This tutorial is relatively small, so you'll put all the code in one namespace.</span></span> 

<span data-ttu-id="7afa7-137">`public class BankAccount` definisce la classe, o tipo, che si sta creando.</span><span class="sxs-lookup"><span data-stu-id="7afa7-137">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="7afa7-138">Tutti gli elementi racchiusi tra le parentesi `{` e `}` che seguono la dichiarazione della classe definiscono il comportamento della classe.</span><span class="sxs-lookup"><span data-stu-id="7afa7-138">Everything inside the `{` and `}` that follows the class declaration defines the behavior of the class.</span></span> <span data-ttu-id="7afa7-139">Esistono cinque ***membri*** della classe `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="7afa7-139">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="7afa7-140">I primi tre sono ***proprietà***.</span><span class="sxs-lookup"><span data-stu-id="7afa7-140">The first three are ***properties***.</span></span> <span data-ttu-id="7afa7-141">Le proprietà sono elementi di dati e possono contenere codice per l'applicazione della convalida o di altre regole.</span><span class="sxs-lookup"><span data-stu-id="7afa7-141">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="7afa7-142">Gli ultimi due sono ***metodi***.</span><span class="sxs-lookup"><span data-stu-id="7afa7-142">The last two are ***methods***.</span></span> <span data-ttu-id="7afa7-143">I metodi sono blocchi di codice che eseguono una singola funzione.</span><span class="sxs-lookup"><span data-stu-id="7afa7-143">Methods are blocks of code that perform a single function.</span></span> <span data-ttu-id="7afa7-144">La lettura dei nomi di ogni membro dovrebbe fornire informazioni sufficienti per consentire all'utente o a un altro sviluppatore di capire gli scopi della classe.</span><span class="sxs-lookup"><span data-stu-id="7afa7-144">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="7afa7-145">Aprire un nuovo conto</span><span class="sxs-lookup"><span data-stu-id="7afa7-145">Open a new account</span></span>

<span data-ttu-id="7afa7-146">La prima funzionalità da implementare è l'apertura di un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="7afa7-146">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="7afa7-147">Quando un cliente apre un conto, deve specificare il saldo iniziale e informazioni sul titolare o i titolari del conto.</span><span class="sxs-lookup"><span data-stu-id="7afa7-147">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span> 

<span data-ttu-id="7afa7-148">La creazione di un nuovo oggetto di tipo `BankAccount` implica la definizione di un ***costruttore*** che assegna questi valori.</span><span class="sxs-lookup"><span data-stu-id="7afa7-148">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="7afa7-149">Un ***costruttore*** è un membro con lo stesso nome della classe</span><span class="sxs-lookup"><span data-stu-id="7afa7-149">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="7afa7-150">e viene usato per inizializzare oggetti di quel tipo di classe.</span><span class="sxs-lookup"><span data-stu-id="7afa7-150">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="7afa7-151">Aggiungere il costruttore seguente al tipo `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="7afa7-151">Add the following constructor to the `BankAccount` type:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="7afa7-152">I costruttori vengono chiamati quando si crea un oggetto con [`new`](../../language-reference/keywords/new.md).</span><span class="sxs-lookup"><span data-stu-id="7afa7-152">Constructors are called when you create an object using [`new`](../../language-reference/keywords/new.md).</span></span> <span data-ttu-id="7afa7-153">Sostituire la riga `Console.WriteLine("Hello World!");` in ***program.cs*** con la riga seguente (sostituire `<name>` con il proprio nome):</span><span class="sxs-lookup"><span data-stu-id="7afa7-153">Replace the line `Console.WriteLine("Hello World!");` in ***program.cs*** with the following line (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name>", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="7afa7-154">Digitare `dotnet run` per vedere i risultati.</span><span class="sxs-lookup"><span data-stu-id="7afa7-154">Type `dotnet run` to see what happens.</span></span>  

<span data-ttu-id="7afa7-155">Si è notato che il numero di conto è vuoto?</span><span class="sxs-lookup"><span data-stu-id="7afa7-155">Did you notice that the account number is blank?</span></span> <span data-ttu-id="7afa7-156">È tempo di correggere questa mancanza.</span><span class="sxs-lookup"><span data-stu-id="7afa7-156">It's time to fix that.</span></span> <span data-ttu-id="7afa7-157">Il numero di conto deve essere assegnato al momento della costruzione dell'oggetto,</span><span class="sxs-lookup"><span data-stu-id="7afa7-157">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="7afa7-158">ma la sua creazione non deve essere responsabilità del chiamante.</span><span class="sxs-lookup"><span data-stu-id="7afa7-158">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="7afa7-159">Il codice della classe `BankAccount` deve sapere come assegnare nuovi numeri di conto.</span><span class="sxs-lookup"><span data-stu-id="7afa7-159">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="7afa7-160">Un modo semplice per eseguire questa operazione consiste nell'iniziare con un numero da 10 cifre</span><span class="sxs-lookup"><span data-stu-id="7afa7-160">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="7afa7-161">e incrementarlo per la creazione di ogni nuovo conto.</span><span class="sxs-lookup"><span data-stu-id="7afa7-161">Increment it when each new account is created.</span></span> <span data-ttu-id="7afa7-162">Infine, il numero di conto corrente deve essere archiviato quando viene costruito un oggetto.</span><span class="sxs-lookup"><span data-stu-id="7afa7-162">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="7afa7-163">Aggiungere la dichiarazione di membro seguente alla classe `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="7afa7-163">Add the following member declaration to the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="7afa7-164">Questo è un membro dati.</span><span class="sxs-lookup"><span data-stu-id="7afa7-164">This is a data member.</span></span> <span data-ttu-id="7afa7-165">Il membro è `private`, ovvero è accessibile solo dal codice all'interno della classe `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="7afa7-165">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="7afa7-166">Si tratta di un modo per separare le responsabilità pubbliche (ad esempio, la disponibilità di un numero di conto) dall'implementazione privata (il modo in cui vengono generati i numeri di conto). È anche `static`, ovvero è condiviso tra tutti gli oggetti `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="7afa7-166">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated.) It is also `static`, which means it is shared by all of the `BankAccount` objects.</span></span> <span data-ttu-id="7afa7-167">Il valore di una variabile non statica è univoco per ogni istanza dell'oggetto `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="7afa7-167">The value of a non-static variable is unique to each instance of the `BankAccount` object.</span></span> <span data-ttu-id="7afa7-168">Aggiungere le due righe seguenti al costruttore per assegnare il numero di conto:</span><span class="sxs-lookup"><span data-stu-id="7afa7-168">Add the following two lines to the constructor to assign the account number:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="7afa7-169">Digitare `dotnet run` per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="7afa7-169">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="7afa7-170">Creare versamenti e prelievi</span><span class="sxs-lookup"><span data-stu-id="7afa7-170">Create deposits and withdrawals</span></span>

<span data-ttu-id="7afa7-171">La classe del conto bancario deve accettare versamenti e prelievi per funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="7afa7-171">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="7afa7-172">I versamenti e i prelievi vengono implementati tramite la creazione di un registro di ogni transazione per il conto.</span><span class="sxs-lookup"><span data-stu-id="7afa7-172">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="7afa7-173">Ciò presenta alcuni vantaggi rispetto al semplice aggiornamento del saldo per ogni transazione.</span><span class="sxs-lookup"><span data-stu-id="7afa7-173">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="7afa7-174">È possibile usare la cronologia per controllare tutte le transazioni e gestire i saldi giornalieri.</span><span class="sxs-lookup"><span data-stu-id="7afa7-174">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="7afa7-175">Grazie alla possibilità di calcolare il saldo dalla cronologia di tutte le transazioni all'occorrenza, eventuali errori in una singola transazione risolti saranno rispecchiati correttamente nel saldo dopo il calcolo successivo.</span><span class="sxs-lookup"><span data-stu-id="7afa7-175">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="7afa7-176">Per iniziare, occorre creare un nuovo tipo per rappresentare una transazione.</span><span class="sxs-lookup"><span data-stu-id="7afa7-176">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="7afa7-177">Si tratta di un tipo semplice senza responsabilità,</span><span class="sxs-lookup"><span data-stu-id="7afa7-177">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="7afa7-178">che richiede alcune proprietà.</span><span class="sxs-lookup"><span data-stu-id="7afa7-178">It needs a few properties.</span></span> <span data-ttu-id="7afa7-179">Creare un nuovo file denominato ***Transaction.cs***.</span><span class="sxs-lookup"><span data-stu-id="7afa7-179">Create a new file named ***Transaction.cs***.</span></span> <span data-ttu-id="7afa7-180">Aggiungere il codice seguente al file:</span><span class="sxs-lookup"><span data-stu-id="7afa7-180">Add the following code to it:</span></span>

[!code-csharp[Transaction](../../../../samples/csharp/classes-quickstart/Transaction.cs "Transaction declaration")]

<span data-ttu-id="7afa7-181">A questo punto, aggiungere un <xref:System.Collections.Generic.List%601> di oggetti `Transaction` alla classe `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="7afa7-181">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="7afa7-182">Aggiungere la dichiarazione seguente:</span><span class="sxs-lookup"><span data-stu-id="7afa7-182">Add the following declaration:</span></span>

[!code-csharp[TransactionDecl](../../../../samples/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration "Transaction declaration")]

<span data-ttu-id="7afa7-183">La classe <xref:System.Collections.Generic.List%601> richiede di importare uno spazio dei nomi diverso.</span><span class="sxs-lookup"><span data-stu-id="7afa7-183">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="7afa7-184">Aggiungere il codice seguente all'inizio di **BankAccount.cs**:</span><span class="sxs-lookup"><span data-stu-id="7afa7-184">Add the following at the beginning of **BankAccount.cs**:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="7afa7-185">A questo punto, occorre modificare il modo in cui viene indicato il saldo (`Balance`).</span><span class="sxs-lookup"><span data-stu-id="7afa7-185">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="7afa7-186">Per ottenere il saldo, è possibile sommare i valori di tutte le transazioni.</span><span class="sxs-lookup"><span data-stu-id="7afa7-186">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="7afa7-187">Modificare la dichiarazione di `Balance` nella classe `BankAccount` come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7afa7-187">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](../../../../samples/csharp/classes-quickstart/BankAccount.cs#BalanceComputation "Computing the balance")]

<span data-ttu-id="7afa7-188">Questo esempio illustra un aspetto importante delle ***proprietà***.</span><span class="sxs-lookup"><span data-stu-id="7afa7-188">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="7afa7-189">Il saldo viene ora calcolato quando un altro programmatore richiede il valore.</span><span class="sxs-lookup"><span data-stu-id="7afa7-189">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="7afa7-190">Il calcolo enumera tutte le transazioni e fornisce la somma come saldo corrente.</span><span class="sxs-lookup"><span data-stu-id="7afa7-190">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="7afa7-191">Implementare ora i metodi `MakeDeposit` e `MakeWithdrawal`.</span><span class="sxs-lookup"><span data-stu-id="7afa7-191">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="7afa7-192">Questi metodi applicheranno le due regole finali, ovvero che il saldo iniziale deve essere positivo e che qualsiasi prelievo non può risultare in un saldo negativo.</span><span class="sxs-lookup"><span data-stu-id="7afa7-192">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span> 

<span data-ttu-id="7afa7-193">Viene così introdotto il concetto di ***eccezioni***.</span><span class="sxs-lookup"><span data-stu-id="7afa7-193">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="7afa7-194">Il modo standard per indicare che un metodo non può completare correttamente le operazioni previste consiste nel generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7afa7-194">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="7afa7-195">Il tipo di eccezione e il messaggio associato descrivono l'errore.</span><span class="sxs-lookup"><span data-stu-id="7afa7-195">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="7afa7-196">In questo caso, il metodo `MakeDeposit` genera un'eccezione se l'importo del versamento è negativo.</span><span class="sxs-lookup"><span data-stu-id="7afa7-196">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="7afa7-197">Il metodo `MakeWithdrawal` genera un'eccezione se l'importo del prelievo è negativo oppure se dalla conferma del prelievo risulta un saldo negativo:</span><span class="sxs-lookup"><span data-stu-id="7afa7-197">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance:</span></span>

[!code-csharp[DepositAndWithdrawal](../../../../samples/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal "Make deposits and withdrawals")]

<span data-ttu-id="7afa7-198">L'istruzione [`throw`](../../language-reference/keywords/throw.md) **genera** un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7afa7-198">The [`throw`](../../language-reference/keywords/throw.md) statement **throws** an exception.</span></span> <span data-ttu-id="7afa7-199">L'esecuzione del blocco corrente termina e il controllo viene trasferito al primo blocco `catch` corrispondente trovato nello stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="7afa7-199">Execution of the current block ends, and control transfers to the first matching `catch` block found in the call stack.</span></span> <span data-ttu-id="7afa7-200">Più avanti si aggiungerà un blocco `catch` per testare questo codice.</span><span class="sxs-lookup"><span data-stu-id="7afa7-200">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="7afa7-201">Il costruttore deve ottenere una modifica in modo da aggiungere una transazione iniziale, invece di aggiornare direttamente il saldo.</span><span class="sxs-lookup"><span data-stu-id="7afa7-201">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="7afa7-202">Dato che il metodo `MakeDeposit` è già stato scritto, chiamarlo dal costruttore.</span><span class="sxs-lookup"><span data-stu-id="7afa7-202">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="7afa7-203">Il costruttore completato dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7afa7-203">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](../../../../samples/csharp/classes-quickstart/BankAccount.cs#Constructor "The final version of the constructor")]

<span data-ttu-id="7afa7-204"><xref:System.DateTime.Now?displayProperty=nameWithType> è una proprietà che restituisce la data e l'ora correnti.</span><span class="sxs-lookup"><span data-stu-id="7afa7-204"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="7afa7-205">Provare il codice aggiungendo alcuni versamenti e prelievi nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="7afa7-205">Test this by adding a few deposits and withdrawals in your `Main` method:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "Friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="7afa7-206">Verificare poi che le condizioni di errore vengano intercettate, tentando di creare un conto con saldo negativo:</span><span class="sxs-lookup"><span data-stu-id="7afa7-206">Next, test that you are catching error conditions by trying to create an account with a negative balance:</span></span>

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

<span data-ttu-id="7afa7-207">Usare le istruzioni [, `try` e `catch`](../../language-reference/keywords/try-catch.md) per contrassegnare un blocco di codice che può generare eccezioni e intercettare gli errori previsti.</span><span class="sxs-lookup"><span data-stu-id="7afa7-207">You use the [`try` and `catch` statements](../../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions and to catch those errors that you expect.</span></span> <span data-ttu-id="7afa7-208">È possibile usare la stessa tecnica per testare il codice che genera un'eccezione per un saldo negativo:</span><span class="sxs-lookup"><span data-stu-id="7afa7-208">You can use the same technique to test the code that throws an exception for a negative balance:</span></span>

```csharp
// Test for a negative balance:
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

<span data-ttu-id="7afa7-209">Salvare il file e digitare `dotnet run` per provare il codice.</span><span class="sxs-lookup"><span data-stu-id="7afa7-209">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="7afa7-210">Esercizio: registrare tutte le transazioni</span><span class="sxs-lookup"><span data-stu-id="7afa7-210">Challenge - log all transactions</span></span>

<span data-ttu-id="7afa7-211">Per completare questa esercitazione, è possibile scrivere il metodo `GetAccountHistory`, che crea un oggetto `string` per la cronologia delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="7afa7-211">To finish this tutorial, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="7afa7-212">Aggiungere questo metodo al tipo `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="7afa7-212">Add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](../../../../samples/csharp/classes-quickstart/BankAccount.cs#History "Display transaction history")]

<span data-ttu-id="7afa7-213">Questo codice usa la classe <xref:System.Text.StringBuilder> per formattare una stringa che contiene una riga per ogni transazione.</span><span class="sxs-lookup"><span data-stu-id="7afa7-213">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="7afa7-214">Il codice per la formattazione delle stringhe è stato presentato in precedenza in queste esercitazioni.</span><span class="sxs-lookup"><span data-stu-id="7afa7-214">You've seen the string formatting code earlier in these tutorials.</span></span> <span data-ttu-id="7afa7-215">`\t` è un nuovo carattere,</span><span class="sxs-lookup"><span data-stu-id="7afa7-215">One new character is `\t`.</span></span> <span data-ttu-id="7afa7-216">che consente di inserire una tabulazione per formattare l'output.</span><span class="sxs-lookup"><span data-stu-id="7afa7-216">That inserts a tab to format the output.</span></span>

<span data-ttu-id="7afa7-217">Aggiungere questa riga per testarla in **Program.cs**:</span><span class="sxs-lookup"><span data-stu-id="7afa7-217">Add this line to test it in **Program.cs**:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="7afa7-218">Digitare `dotnet run` per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="7afa7-218">Type `dotnet run` to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7afa7-219">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="7afa7-219">Next Steps</span></span>

<span data-ttu-id="7afa7-220">In caso di problemi, è possibile visualizzare il codice sorgente per questa esercitazione nel [repository GitHub](https://github.com/dotnet/samples/tree/master/csharp/classes-quickstart/)</span><span class="sxs-lookup"><span data-stu-id="7afa7-220">If you got stuck, you can see the source for this tutorial [in our GitHub repo](https://github.com/dotnet/samples/tree/master/csharp/classes-quickstart/)</span></span>

<span data-ttu-id="7afa7-221">Congratulazioni, sono state completate tutte le esercitazioni introduttive su C#.</span><span class="sxs-lookup"><span data-stu-id="7afa7-221">Congratulations, you've finished all our introduction to C# tutorials.</span></span> <span data-ttu-id="7afa7-222">Per approfondire gli argomenti, è possibile provare altre [esercitazioni](../index.md)</span><span class="sxs-lookup"><span data-stu-id="7afa7-222">If you're eager to learn more, try more of our [tutorials](../index.md)</span></span>

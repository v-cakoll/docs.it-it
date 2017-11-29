---
title: "Testing unità di C# con MSTest e .NET Core"
description: Informazioni sui concetti relativi agli unit test in C# e .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e MSTest.
keywords: MSTest, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 09/08/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
ms.openlocfilehash: 2915c2f4b18b9e9d03915c2f17cfc96d4f401c09
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="unit-testing-c-with-mstest-and-net-core"></a><span data-ttu-id="f5fb3-104">Testing unità di C# con MSTest e .NET Core</span><span class="sxs-lookup"><span data-stu-id="f5fb3-104">Unit testing C# with MSTest and .NET Core</span></span>

<span data-ttu-id="f5fb3-105">In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-105">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="f5fb3-106">Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-106">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="f5fb3-107">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="f5fb3-107">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="creating-the-source-project"></a><span data-ttu-id="f5fb3-108">Creazione del progetto di origine</span><span class="sxs-lookup"><span data-stu-id="f5fb3-108">Creating the source project</span></span>

<span data-ttu-id="f5fb3-109">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-109">Open a shell window.</span></span> <span data-ttu-id="f5fb3-110">Creare una directory denominata *unit-testing-using-dotnet-test* in cui archiviare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-110">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span> <span data-ttu-id="f5fb3-111">In questa nuova directory, eseguire [`dotnet new sln`](../tools/dotnet-new.md) per creare un nuovo file di soluzione per la libreria di classi e il progetto di test.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-111">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="f5fb3-112">Creare quindi una directory *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-112">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="f5fb3-113">Finora è stata creata la struttura di directory e file seguente:</span><span class="sxs-lookup"><span data-stu-id="f5fb3-113">The following outline shows the directory and file structure thus far:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

<span data-ttu-id="f5fb3-114">Impostare *PrimeService* come directory corrente ed eseguire [`dotnet new classlib`](../tools/dotnet-new.md) per creare il progetto di origine.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-114">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="f5fb3-115">Assegnare il nome *PrimeService.cs* al file *Class1.cs*.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-115">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="f5fb3-116">Per usare lo sviluppo basato su test (TDD), si creerà un'implementazione non corretta della classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="f5fb3-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate) 
        {
            throw new NotImplementedException("Please create a test first");
        } 
    }
}
```

<span data-ttu-id="f5fb3-117">Tornare alla directory *unit-testing-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-117">Change the directory back to the *unit-testing-using-mstest* directory.</span></span> <span data-ttu-id="f5fb3-118">Eseguire [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) per aggiungere il progetto di libreria di classi alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-118">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span> 

### <a name="creating-the-test-project"></a><span data-ttu-id="f5fb3-119">Creazione del progetto di test</span><span class="sxs-lookup"><span data-stu-id="f5fb3-119">Creating the test project</span></span>

<span data-ttu-id="f5fb3-120">Creare quindi la directory *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="f5fb3-121">Di seguito è illustrata la struttura di directory:</span><span class="sxs-lookup"><span data-stu-id="f5fb3-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="f5fb3-122">Impostare *PrimeService.Tests* come directory corrente e creare un nuovo progetto usando [`dotnet new mstest`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="f5fb3-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="f5fb3-123">Il comando dotnet new crea un progetto di test che usa MSTest come libreria di test.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-123">The dotnet new command creates a test project that uses MStest as the test library.</span></span> <span data-ttu-id="f5fb3-124">Il modello generato configura il Test Runner nel file *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="f5fb3-124">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="f5fb3-125">Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="f5fb3-126">Nel passaggio precedente `dotnet new` ha aggiunto l'SDK MSTest, il framework di test MSTest e il Test Runner MSTest.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-126">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="f5fb3-127">Aggiungere ora la libreria di classi `PrimeService` come un'altra dipendenza del progetto.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="f5fb3-128">Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="f5fb3-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="f5fb3-129">È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-129">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="f5fb3-130">Il layout della soluzione finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="f5fb3-130">The following outline shows the final solution layout:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="f5fb3-131">Eseguire [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) nella directory *unit-testing-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-dotnet-test* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="f5fb3-132">Creazione del primo test</span><span class="sxs-lookup"><span data-stu-id="f5fb3-132">Creating the first test</span></span>

<span data-ttu-id="f5fb3-133">L'approccio di sviluppo basato su test richiede la creazione di un test con esito negativo. È quindi necessario che il test venga superato e che il processo venga ripetuto.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="f5fb3-134">Rimuovere *UnitTest1.cs* dalla directory *PrimeService.Tests* e creare un nuovo file C# denominato *PrimeService_IsPrimeShould.cs* con il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="f5fb3-134">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestClass]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [TestMethod]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="f5fb3-135">L'attributo `[TestClass]` indica una classe che contiene unit test.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-135">The `[TestClass]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="f5fb3-136">L'attributo `[TestMethod]` indica che il metodo è un metodo di test.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-136">The `[TestMethod]` attribute indicates a method is a test method.</span></span> 

<span data-ttu-id="f5fb3-137">Salvare questo file ed eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-137">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="f5fb3-138">Il Test Runner di MSTest include il punto d'ingresso del programma per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-138">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="f5fb3-139">`dotnet test` avvia il Test Runner usando il progetto di unit test creato.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="f5fb3-140">Il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-140">Your test fails.</span></span> <span data-ttu-id="f5fb3-141">Non è stata ancora creata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="f5fb3-142">Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="f5fb3-142">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Please create a test first");
}
```

<span data-ttu-id="f5fb3-143">Eseguire di nuovo `dotnet test` nella directory *unit-testing-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-143">In the *unit-testing-using-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="f5fb3-144">Il comando `dotnet test` esegue prima una compilazione del progetto `PrimeService` e quindi del progetto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-144">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="f5fb3-145">Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo,</span><span class="sxs-lookup"><span data-stu-id="f5fb3-145">After building both projects, it runs this single test.</span></span> <span data-ttu-id="f5fb3-146">che viene superato.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-146">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="f5fb3-147">Aggiunta di altre funzionalità</span><span class="sxs-lookup"><span data-stu-id="f5fb3-147">Adding more features</span></span>

<span data-ttu-id="f5fb3-148">Ora che il test è stato superato, è necessario scriverne altri.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-148">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="f5fb3-149">Esistono alcuni altri casi semplici per i numeri primi: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-149">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="f5fb3-150">È possibile aggiungere nuovi test con l'attributo `[TestMethod]`, ma questa operazione risulta rapidamente noiosa.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-150">You could add new tests with the `[TestMethod]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="f5fb3-151">Sono disponibili altri attributi di MSTest che consentono di scrivere una suite di test analoghi.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-151">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="f5fb3-152">Un attributo `[DataTestMethod]` rappresenta una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-152">A `[DataTestMethod]`attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="f5fb3-153">È possibile usare l'attributo `[DataRow]` per specificare i valori per tali input.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-153">You can use the `[DataRow]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="f5fb3-154">Anziché creare nuovi test, applicare questi due attributi per creare un singolo test basato sui dati.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-154">Instead of creating new tests, apply these two attributes to create a single data driven test.</span></span> <span data-ttu-id="f5fb3-155">Il test basato sui dati è un metodo che verifica vari valori minori di due, ovvero il numero primo più piccolo:</span><span class="sxs-lookup"><span data-stu-id="f5fb3-155">The data driven test is a method that tests several values less than two, which is the lowest prime number: :</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="f5fb3-156">Eseguire `dotnet test`. Due test hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-156">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="f5fb3-157">Per assicurare che tutti i test vengano superati, modificare la clausola `if` all'inizio del metodo:</span><span class="sxs-lookup"><span data-stu-id="f5fb3-157">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="f5fb3-158">Continuare a eseguire l'iterazione aggiungendo altri test, altre teorie e altro codice nella libreria principale.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-158">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="f5fb3-159">Si ottiene la [versione completa dei test](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) e l'[implementazione completa della libreria](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="f5fb3-159">You have the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="f5fb3-160">È stata compilata una piccola libreria e un set di unit test per tale libreria.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-160">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="f5fb3-161">La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-161">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="f5fb3-162">La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f5fb3-162">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

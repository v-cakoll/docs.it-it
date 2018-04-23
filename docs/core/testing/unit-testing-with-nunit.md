---
title: Testing unità di C# con NUnit e .NET Core
description: Informazioni sui concetti relativi agli unit test in C# e .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e NUnit.
keywords: NUnit, .NET, .NET Core
author: rprouse
ms.date: 12/01/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.openlocfilehash: b29912a58511305202a18e8da4ae57700605867a
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a><span data-ttu-id="de87a-104">Testing unità di C# con NUnit e .NET Core</span><span class="sxs-lookup"><span data-stu-id="de87a-104">Unit testing C# with NUnit and .NET Core</span></span>

<span data-ttu-id="de87a-105">In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità.</span><span class="sxs-lookup"><span data-stu-id="de87a-105">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="de87a-106">Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="de87a-106">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) before you begin.</span></span> <span data-ttu-id="de87a-107">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="de87a-107">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="de87a-108">Creazione del progetto di origine</span><span class="sxs-lookup"><span data-stu-id="de87a-108">Creating the source project</span></span>

<span data-ttu-id="de87a-109">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="de87a-109">Open a shell window.</span></span> <span data-ttu-id="de87a-110">Creare una directory denominata *unit-testing-using-nunit* in cui archiviare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="de87a-110">Create a directory called *unit-testing-using-nunit* to hold the solution.</span></span> <span data-ttu-id="de87a-111">In questa nuova directory, eseguire [`dotnet new sln`](../tools/dotnet-new.md) per creare un nuovo file di soluzione per la libreria di classi e il progetto di test.</span><span class="sxs-lookup"><span data-stu-id="de87a-111">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="de87a-112">Creare quindi una directory *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="de87a-112">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="de87a-113">Finora è stata creata la struttura di directory e file seguente:</span><span class="sxs-lookup"><span data-stu-id="de87a-113">The following outline shows the directory and file structure thus far:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

<span data-ttu-id="de87a-114">Impostare *PrimeService* come directory corrente ed eseguire [`dotnet new classlib`](../tools/dotnet-new.md) per creare il progetto di origine.</span><span class="sxs-lookup"><span data-stu-id="de87a-114">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="de87a-115">Assegnare il nome *PrimeService.cs* al file *Class1.cs*.</span><span class="sxs-lookup"><span data-stu-id="de87a-115">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="de87a-116">Per usare lo sviluppo basato su test (TDD), si creerà un'implementazione non corretta della classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="de87a-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="de87a-117">Tornare alla directory *unit-testing-using-nunit*.</span><span class="sxs-lookup"><span data-stu-id="de87a-117">Change the directory back to the *unit-testing-using-nunit* directory.</span></span> <span data-ttu-id="de87a-118">Eseguire [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) per aggiungere il progetto di libreria di classi alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="de87a-118">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="install-the-nunit-project-template"></a><span data-ttu-id="de87a-119">Installare il modello di progetto NUnit</span><span class="sxs-lookup"><span data-stu-id="de87a-119">Install the NUnit project template</span></span>

<span data-ttu-id="de87a-120">È necessario installare i modelli di progetto di test NUnit prima di creare un progetto di test.</span><span class="sxs-lookup"><span data-stu-id="de87a-120">The NUnit test project templates need to be installed before creating a test project.</span></span> <span data-ttu-id="de87a-121">Questa operazione deve essere eseguita una sola volta in ogni computer di sviluppo in cui verranno creati nuovi progetti NUnit.</span><span class="sxs-lookup"><span data-stu-id="de87a-121">This only needs to be done once on each developer machine where you'll create new NUnit projects.</span></span> <span data-ttu-id="de87a-122">Eseguire [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) per installare i modelli NUnit.</span><span class="sxs-lookup"><span data-stu-id="de87a-122">Run [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) to install the NUnit templates.</span></span>

```
dotnet new -i NUnit3.DotNetNew.Template
```

### <a name="creating-the-test-project"></a><span data-ttu-id="de87a-123">Creazione del progetto di test</span><span class="sxs-lookup"><span data-stu-id="de87a-123">Creating the test project</span></span>

<span data-ttu-id="de87a-124">Creare quindi la directory *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="de87a-124">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="de87a-125">Di seguito è illustrata la struttura di directory:</span><span class="sxs-lookup"><span data-stu-id="de87a-125">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="de87a-126">Impostare *PrimeService.Tests* come directory corrente e creare un nuovo progetto usando [`dotnet new nunit`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="de87a-126">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new nunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="de87a-127">Il comando dotnet new crea un progetto di test che usa NUnit come libreria di test.</span><span class="sxs-lookup"><span data-stu-id="de87a-127">The dotnet new command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="de87a-128">Il modello generato configura il Test Runner nel file *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="de87a-128">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="de87a-129">Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="de87a-129">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="de87a-130">`dotnet new` nel passaggio precedente aggiunge Microsoft Test SDK, il framework di test NUnit e l'adattatore di test NUnit.</span><span class="sxs-lookup"><span data-stu-id="de87a-130">`dotnet new` in the previous step added the Microsoft test SDK, the NUnit test framework, and the NUnit test adapter.</span></span> <span data-ttu-id="de87a-131">Aggiungere ora la libreria di classi `PrimeService` come un'altra dipendenza del progetto.</span><span class="sxs-lookup"><span data-stu-id="de87a-131">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="de87a-132">Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="de87a-132">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="de87a-133">È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="de87a-133">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="de87a-134">Il layout della soluzione finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="de87a-134">The following outline shows the final solution layout:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="de87a-135">Eseguire [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) nella directory *unit-testing-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="de87a-135">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-dotnet-test* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="de87a-136">Creazione del primo test</span><span class="sxs-lookup"><span data-stu-id="de87a-136">Creating the first test</span></span>

<span data-ttu-id="de87a-137">L'approccio di sviluppo basato su test richiede la creazione di un test con esito negativo. È quindi necessario che il test venga superato e che il processo venga ripetuto.</span><span class="sxs-lookup"><span data-stu-id="de87a-137">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="de87a-138">Rimuovere *UnitTest1.cs* dalla directory *PrimeService.Tests* e creare un nuovo file C# denominato *PrimeService_IsPrimeShould.cs* con il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="de87a-138">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

```csharp
using NUnit.Framework;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestFixture]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Test]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="de87a-139">L'attributo `[TestFixture]` indica una classe che contiene unit test.</span><span class="sxs-lookup"><span data-stu-id="de87a-139">The `[TestFixture]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="de87a-140">L'attributo `[Test]` indica che il metodo è un metodo di test.</span><span class="sxs-lookup"><span data-stu-id="de87a-140">The `[Test]` attribute indicates a method is a test method.</span></span>

<span data-ttu-id="de87a-141">Salvare questo file ed eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="de87a-141">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="de87a-142">Il Test Runner di NUnit include il punto d'ingresso del programma per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="de87a-142">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="de87a-143">`dotnet test` avvia il Test Runner usando il progetto di unit test creato.</span><span class="sxs-lookup"><span data-stu-id="de87a-143">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="de87a-144">Il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="de87a-144">Your test fails.</span></span> <span data-ttu-id="de87a-145">Non è stata ancora creata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="de87a-145">You haven't created the implementation yet.</span></span> <span data-ttu-id="de87a-146">Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="de87a-146">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="de87a-147">Eseguire di nuovo `dotnet test` nella directory *unit-testing-using-nunit*.</span><span class="sxs-lookup"><span data-stu-id="de87a-147">In the *unit-testing-using-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="de87a-148">Il comando `dotnet test` esegue prima una compilazione del progetto `PrimeService` e quindi del progetto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="de87a-148">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="de87a-149">Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo,</span><span class="sxs-lookup"><span data-stu-id="de87a-149">After building both projects, it runs this single test.</span></span> <span data-ttu-id="de87a-150">che viene superato.</span><span class="sxs-lookup"><span data-stu-id="de87a-150">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="de87a-151">Aggiunta di altre funzionalità</span><span class="sxs-lookup"><span data-stu-id="de87a-151">Adding more features</span></span>

<span data-ttu-id="de87a-152">Ora che il test è stato superato, è necessario scriverne altri.</span><span class="sxs-lookup"><span data-stu-id="de87a-152">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="de87a-153">Esistono alcuni altri casi semplici per i numeri primi: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="de87a-153">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="de87a-154">È possibile aggiungere nuovi test con l'attributo `[Test]`, ma questa operazione risulta rapidamente noiosa.</span><span class="sxs-lookup"><span data-stu-id="de87a-154">You could add new tests with the `[Test]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="de87a-155">Sono disponibili altri attributi NUnit che consentono di scrivere una suite di test analoghi.</span><span class="sxs-lookup"><span data-stu-id="de87a-155">There are other NUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="de87a-156">Un attributo `[TestCase]` viene usato per creare una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi.</span><span class="sxs-lookup"><span data-stu-id="de87a-156">A `[TestCase]` attribute is used to create a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="de87a-157">È possibile usare l'attributo `[TestCase]` per specificare i valori per tali input.</span><span class="sxs-lookup"><span data-stu-id="de87a-157">You can use the `[TestCase]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="de87a-158">Anziché creare nuovi test, applicare questo attributo per creare un singolo test basato sui dati.</span><span class="sxs-lookup"><span data-stu-id="de87a-158">Instead of creating new tests, apply this attribute to create a single data driven test.</span></span> <span data-ttu-id="de87a-159">Il test basato sui dati è un metodo che verifica vari valori minori di due, ovvero il numero primo più piccolo:</span><span class="sxs-lookup"><span data-stu-id="de87a-159">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="de87a-160">Eseguire `dotnet test`. Due test hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="de87a-160">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="de87a-161">Per assicurare che tutti i test vengano superati, modificare la clausola `if` all'inizio del metodo:</span><span class="sxs-lookup"><span data-stu-id="de87a-161">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="de87a-162">Continuare a eseguire l'iterazione aggiungendo altri test, altre teorie e altro codice nella libreria principale.</span><span class="sxs-lookup"><span data-stu-id="de87a-162">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="de87a-163">Si ottiene la [versione completa dei test](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) e l'[implementazione completa della libreria](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="de87a-163">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="de87a-164">È stata compilata una piccola libreria e un set di unit test per tale libreria.</span><span class="sxs-lookup"><span data-stu-id="de87a-164">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="de87a-165">La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="de87a-165">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="de87a-166">La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="de87a-166">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

---
title: Testing unità di codice C# in .NET Core usando il test dotnet e xUnit
description: Informazioni sui concetti relativi agli unit test in C# e .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e xUnit.
author: ardalis
ms.author: wiwagn
ms.date: 11/29/2017
ms.custom: seodec18
ms.openlocfilehash: 1a6c8ed515e62bed921290a54e3d9687bb889a4d
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374157"
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="232ae-103">Testing unità di C# in .NET Core usando il test dotnet e xUnit</span><span class="sxs-lookup"><span data-stu-id="232ae-103">Unit testing C# in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="232ae-104">In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità.</span><span class="sxs-lookup"><span data-stu-id="232ae-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="232ae-105">Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="232ae-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/) before you begin.</span></span> <span data-ttu-id="232ae-106">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="232ae-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="creating-the-source-project"></a><span data-ttu-id="232ae-107">Creazione del progetto di origine</span><span class="sxs-lookup"><span data-stu-id="232ae-107">Creating the source project</span></span>

<span data-ttu-id="232ae-108">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="232ae-108">Open a shell window.</span></span> <span data-ttu-id="232ae-109">Creare una directory denominata *unit-testing-using-dotnet-test* in cui archiviare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="232ae-109">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span>
<span data-ttu-id="232ae-110">In questa nuova directory eseguire [`dotnet new sln`](../tools/dotnet-new.md) per creare una nuova soluzione.</span><span class="sxs-lookup"><span data-stu-id="232ae-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="232ae-111">Con una soluzione è semplice gestire sia la libreria di classi che il progetto di unit test.</span><span class="sxs-lookup"><span data-stu-id="232ae-111">Having a solution makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="232ae-112">All'interno della directory della soluzione creare una directory *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="232ae-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="232ae-113">La struttura di directory e file fino a questo momento sarà la seguente:</span><span class="sxs-lookup"><span data-stu-id="232ae-113">The directory and file structure thus far should be as follows:</span></span>

```console
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
```

<span data-ttu-id="232ae-114">Impostare *PrimeService* come directory corrente ed eseguire [`dotnet new classlib`](../tools/dotnet-new.md) per creare il progetto di origine.</span><span class="sxs-lookup"><span data-stu-id="232ae-114">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="232ae-115">Assegnare il nome *PrimeService.cs* al file *Class1.cs*.</span><span class="sxs-lookup"><span data-stu-id="232ae-115">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="232ae-116">Creare prima di tutto un'implementazione non corretta della classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="232ae-116">You first create a failing implementation of the `PrimeService` class:</span></span>

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            throw new NotImplementedException("Please create a test first.");
        }
    }
}
```

<span data-ttu-id="232ae-117">Tornare alla directory *unit-testing-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="232ae-117">Change the directory back to the *unit-testing-using-dotnet-test* directory.</span></span>

<span data-ttu-id="232ae-118">Eseguire il comando [dotnet sln](../tools/dotnet-sln.md) per aggiungere il progetto di libreria di classi alla soluzione:</span><span class="sxs-lookup"><span data-stu-id="232ae-118">Run the [dotnet sln](../tools/dotnet-sln.md) command to add the class library project to the solution:</span></span>

```console
dotnet sln add ./PrimeService/PrimeService.csproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="232ae-119">Creazione del progetto di test</span><span class="sxs-lookup"><span data-stu-id="232ae-119">Creating the test project</span></span>

<span data-ttu-id="232ae-120">Creare quindi la directory *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="232ae-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="232ae-121">Di seguito è illustrata la struttura di directory:</span><span class="sxs-lookup"><span data-stu-id="232ae-121">The following outline shows the directory structure:</span></span>

```console
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="232ae-122">Impostare *PrimeService.Tests* come directory corrente e creare un nuovo progetto usando [`dotnet new xunit`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="232ae-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="232ae-123">Questo comando crea un progetto di test che usa [xUnit](https://xunit.github.io/) come libreria di test.</span><span class="sxs-lookup"><span data-stu-id="232ae-123">This command creates a test project that uses [xUnit](https://xunit.github.io/) as the test library.</span></span> <span data-ttu-id="232ae-124">Il modello generato configura il Test Runner nel file *PrimeServiceTests.csproj* in modo simile al codice seguente:</span><span class="sxs-lookup"><span data-stu-id="232ae-124">The generated template configures the test runner in the *PrimeServiceTests.csproj* file similar to the following code:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="232ae-125">Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="232ae-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="232ae-126">Nel passaggio precedente `dotnet new` ha aggiunto xUnit e il Runner di xUnit.</span><span class="sxs-lookup"><span data-stu-id="232ae-126">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="232ae-127">Aggiungere ora la libreria di classi `PrimeService` come un'altra dipendenza del progetto.</span><span class="sxs-lookup"><span data-stu-id="232ae-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="232ae-128">Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="232ae-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```console
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="232ae-129">È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="232ae-129">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="232ae-130">Il layout della soluzione finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="232ae-130">The following shows the final solution layout:</span></span>

```console
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="232ae-131">Per aggiungere il progetto di test alla soluzione, eseguire il comando [dotnet sln](../tools/dotnet-sln.md) nella directory *unit-testing-using-dotnet-test*:</span><span class="sxs-lookup"><span data-stu-id="232ae-131">To add the test project to the solution, run the [dotnet sln](../tools/dotnet-sln.md) command in the *unit-testing-using-dotnet-test* directory:</span></span>

```console
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="232ae-132">Creazione del primo test</span><span class="sxs-lookup"><span data-stu-id="232ae-132">Creating the first test</span></span>

<span data-ttu-id="232ae-133">Scrivere un test che genera errore, fare in modo che venga superato e quindi ripetere il processo.</span><span class="sxs-lookup"><span data-stu-id="232ae-133">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="232ae-134">Rimuovere *UnitTest1.cs* dalla directory *PrimeService.Tests* e creare un nuovo file C# denominato *PrimeService_IsPrimeShould.cs*.</span><span class="sxs-lookup"><span data-stu-id="232ae-134">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs*.</span></span> <span data-ttu-id="232ae-135">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="232ae-135">Add the following code:</span></span>

```csharp
using Xunit;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Fact]
        public void IsPrime_InputIs1_ReturnFalse()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="232ae-136">L'attributo `[Fact]` indica un metodo di test eseguito dal Test Runner.</span><span class="sxs-lookup"><span data-stu-id="232ae-136">The `[Fact]` attribute indicates a test method that is run by the test runner.</span></span> <span data-ttu-id="232ae-137">Dalla cartella *PrimeService.Tests* eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="232ae-137">From the *PrimeService.Tests* folder, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="232ae-138">Il Test Runner di xUnit include il punto d'ingresso del programma per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="232ae-138">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="232ae-139">`dotnet test` avvia il Test Runner usando il progetto di unit test creato.</span><span class="sxs-lookup"><span data-stu-id="232ae-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="232ae-140">Il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="232ae-140">Your test fails.</span></span> <span data-ttu-id="232ae-141">Non è stata ancora creata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="232ae-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="232ae-142">Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `PrimeService`.</span><span class="sxs-lookup"><span data-stu-id="232ae-142">Make this test pass by writing the simplest code in the `PrimeService` class that works.</span></span> <span data-ttu-id="232ae-143">Sostituire l'implementazione del metodo `IsPrime` esistente con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="232ae-143">Replace the existing `IsPrime` method implementation with the following code:</span></span>

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Please create a test first.");
}
```

<span data-ttu-id="232ae-144">Nella directory *PrimeService.Tests* eseguire di nuovo `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="232ae-144">In the *PrimeService.Tests* directory, run `dotnet test` again.</span></span> <span data-ttu-id="232ae-145">Il comando `dotnet test` esegue prima una compilazione del progetto `PrimeService` e quindi del progetto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="232ae-145">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="232ae-146">Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo,</span><span class="sxs-lookup"><span data-stu-id="232ae-146">After building both projects, it runs this single test.</span></span> <span data-ttu-id="232ae-147">che viene superato.</span><span class="sxs-lookup"><span data-stu-id="232ae-147">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="232ae-148">Aggiunta di altre funzionalità</span><span class="sxs-lookup"><span data-stu-id="232ae-148">Adding more features</span></span>

<span data-ttu-id="232ae-149">Ora che il test è stato superato, è necessario scriverne altri.</span><span class="sxs-lookup"><span data-stu-id="232ae-149">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="232ae-150">Esistono alcuni altri casi semplici per i numeri primi: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="232ae-150">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="232ae-151">È possibile aggiungerli come nuovi test, con l'attributo `[Fact]`, ma questa operazione risulta rapidamente noiosa.</span><span class="sxs-lookup"><span data-stu-id="232ae-151">You could add those cases as new tests with the `[Fact]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="232ae-152">Sono disponibili altri attributi xUnit che consentono di scrivere una suite di test analoghi:</span><span class="sxs-lookup"><span data-stu-id="232ae-152">There are other xUnit attributes that enable you to write a suite of similar tests:</span></span>

- <span data-ttu-id="232ae-153">`[Theory]` rappresenta una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi.</span><span class="sxs-lookup"><span data-stu-id="232ae-153">`[Theory]` represents a suite of tests that execute the same code but have different input arguments.</span></span>

- <span data-ttu-id="232ae-154">L'attributo `[InlineData]` specifica i valori per tali input.</span><span class="sxs-lookup"><span data-stu-id="232ae-154">`[InlineData]` attribute specifies values for those inputs.</span></span>

<span data-ttu-id="232ae-155">Invece di creare nuovi test, applicare questi due attributi, `[Theory]` e `[InlineData]`, per creare una singola teoria nel file *PrimeService_IsPrimeShould.cs*.</span><span class="sxs-lookup"><span data-stu-id="232ae-155">Instead of creating new tests, apply these two attributes, `[Theory]` and `[InlineData]`, to create a single theory in the *PrimeService_IsPrimeShould.cs* file.</span></span> <span data-ttu-id="232ae-156">La teoria è un metodo che verifica vari valori minori di due, ovvero il numero primo più piccolo:</span><span class="sxs-lookup"><span data-stu-id="232ae-156">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="232ae-157">Eseguire di nuovo `dotnet test`. Due di questi test non riusciranno.</span><span class="sxs-lookup"><span data-stu-id="232ae-157">Run `dotnet test` again, and two of these tests should fail.</span></span> <span data-ttu-id="232ae-158">Per assicurare che tutti i test vengano superati, modificare la clausola `if` all'inizio del metodo `IsPrime` nel file *PrimeService.cs*:</span><span class="sxs-lookup"><span data-stu-id="232ae-158">To make all of the tests pass, change the `if` clause at the beginning of the `IsPrime` method in the *PrimeService.cs* file:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="232ae-159">Continuare a eseguire l'iterazione aggiungendo altri test, altre teorie e altro codice nella libreria principale.</span><span class="sxs-lookup"><span data-stu-id="232ae-159">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="232ae-160">Si ottiene la [versione completa dei test](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) e l'[implementazione completa della libreria](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="232ae-160">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="232ae-161">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="232ae-161">Additional resources</span></span>

- [<span data-ttu-id="232ae-162">Sito ufficiale xUnit.net</span><span class="sxs-lookup"><span data-stu-id="232ae-162">xUnit.net official site</span></span>](https://xunit.github.io)
- [<span data-ttu-id="232ae-163">Test della logica dei controller in ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="232ae-163">Testing controller logic in ASP.NET Core</span></span>](/aspnet/core/mvc/controllers/testing)

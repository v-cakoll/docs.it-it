---
title: Testing unità di C# con MSTest e .NET Core
description: Informazioni sui concetti relativi agli unit test in C# e .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e MSTest.
author: ncarandini
ms.author: wiwagn
ms.date: 09/08/2017
ms.openlocfilehash: bd7891243d84277a7578089f8b4629ff5bada577
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240909"
---
# <a name="unit-testing-c-with-mstest-and-net-core"></a><span data-ttu-id="ef7fc-103">Testing unità di C# con MSTest e .NET Core</span><span class="sxs-lookup"><span data-stu-id="ef7fc-103">Unit testing C# with MSTest and .NET Core</span></span>

<span data-ttu-id="ef7fc-104">In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="ef7fc-105">Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="ef7fc-106">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="ef7fc-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="create-the-source-project"></a><span data-ttu-id="ef7fc-107">Creare il progetto di origine</span><span class="sxs-lookup"><span data-stu-id="ef7fc-107">Create the source project</span></span>

<span data-ttu-id="ef7fc-108">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-108">Open a shell window.</span></span> <span data-ttu-id="ef7fc-109">Creare una directory denominata *unit-testing-using-mstest* in cui archiviare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-109">Create a directory called *unit-testing-using-mstest* to hold the solution.</span></span> <span data-ttu-id="ef7fc-110">All'interno di [`dotnet new sln`](../tools/dotnet-new.md) questa nuova directory, eseguire per creare un nuovo file di soluzione per la libreria di classi e il progetto di test.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="ef7fc-111">Creare quindi una directory *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-111">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="ef7fc-112">Finora è stata creata la struttura di directory e file seguente:</span><span class="sxs-lookup"><span data-stu-id="ef7fc-112">The following outline shows the directory and file structure thus far:</span></span>

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

<span data-ttu-id="ef7fc-113">Impostare *PrimeService* come [`dotnet new classlib`](../tools/dotnet-new.md) directory corrente ed eseguire per creare il progetto di origine.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-113">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="ef7fc-114">Assegnare il nome *PrimeService.cs* al file *Class1.cs*.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-114">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="ef7fc-115">Si crea un'implementazione non corretta della classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="ef7fc-115">You create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="ef7fc-116">Tornare alla directory *unit-testing-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-116">Change the directory back to the *unit-testing-using-mstest* directory.</span></span> <span data-ttu-id="ef7fc-117">Esegui [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) per aggiungere il progetto di libreria di classi alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-117">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="create-the-test-project"></a><span data-ttu-id="ef7fc-118">Creare il progetto di test</span><span class="sxs-lookup"><span data-stu-id="ef7fc-118">Create the test project</span></span>

<span data-ttu-id="ef7fc-119">Creare quindi la directory *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-119">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="ef7fc-120">Di seguito è illustrata la struttura di directory:</span><span class="sxs-lookup"><span data-stu-id="ef7fc-120">The following outline shows the directory structure:</span></span>

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="ef7fc-121">Impostare la directory *PrimeService.Tests* come directory [`dotnet new mstest`](../tools/dotnet-new.md)corrente e creare un nuovo progetto utilizzando .</span><span class="sxs-lookup"><span data-stu-id="ef7fc-121">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="ef7fc-122">Il comando dotnet new crea un progetto di test che usa MSTest come libreria di test.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-122">The dotnet new command creates a test project that uses MSTest as the test library.</span></span> <span data-ttu-id="ef7fc-123">Il modello generato configura il Test Runner nel file *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="ef7fc-123">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="ef7fc-124">Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="ef7fc-125">Nel passaggio precedente `dotnet new` ha aggiunto l'SDK MSTest, il framework di test MSTest e il Test Runner MSTest.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-125">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="ef7fc-126">Aggiungere ora la libreria di classi `PrimeService` come un'altra dipendenza del progetto.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-126">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="ef7fc-127">Utilizzare [`dotnet add reference`](../tools/dotnet-add-reference.md) il comando:</span><span class="sxs-lookup"><span data-stu-id="ef7fc-127">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="ef7fc-128">È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-128">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="ef7fc-129">Il layout della soluzione finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ef7fc-129">The following outline shows the final solution layout:</span></span>

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="ef7fc-130">Eseguire [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) nella directory *unit-testing-using-mstest.*</span><span class="sxs-lookup"><span data-stu-id="ef7fc-130">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-mstest* directory.</span></span>

## <a name="create-the-first-test"></a><span data-ttu-id="ef7fc-131">Creare il primo test</span><span class="sxs-lookup"><span data-stu-id="ef7fc-131">Create the first test</span></span>

<span data-ttu-id="ef7fc-132">Scrivere un test che genera errore, fare in modo che venga superato e quindi ripetere il processo.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-132">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="ef7fc-133">Rimuovere *UnitTest1.cs* dalla directory *PrimeService.Tests* e creare un nuovo file C , denominato *PrimeService_IsPrimeShould.cs* con il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="ef7fc-133">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

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
        public void IsPrime_InputIs1_ReturnFalse()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="ef7fc-134">L'[attributo TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) indica una classe che contiene unit test.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-134">The [TestClass attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) denotes a class that contains unit tests.</span></span> <span data-ttu-id="ef7fc-135">L'[attributo TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) indica che il metodo è un metodo di test.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-135">The [TestMethod attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) indicates a method is a test method.</span></span>

<span data-ttu-id="ef7fc-136">Salvare il file [`dotnet test`](../tools/dotnet-test.md) ed eseguire per compilare i test e la libreria di classi e quindi eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-136">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="ef7fc-137">Il Test Runner di MSTest include il punto d'ingresso del programma per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-137">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="ef7fc-138">`dotnet test` avvia il Test Runner usando il progetto di unit test creato.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-138">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="ef7fc-139">Il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-139">Your test fails.</span></span> <span data-ttu-id="ef7fc-140">Non è stata ancora creata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-140">You haven't created the implementation yet.</span></span> <span data-ttu-id="ef7fc-141">Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="ef7fc-141">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="ef7fc-142">Eseguire di nuovo `dotnet test` nella directory *unit-testing-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-142">In the *unit-testing-using-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="ef7fc-143">Il comando `dotnet test` esegue prima una compilazione del progetto `PrimeService` e quindi del progetto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-143">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="ef7fc-144">Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo,</span><span class="sxs-lookup"><span data-stu-id="ef7fc-144">After building both projects, it runs this single test.</span></span> <span data-ttu-id="ef7fc-145">che viene superato.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-145">It passes.</span></span>

## <a name="add-more-features"></a><span data-ttu-id="ef7fc-146">Aggiungere altre funzionalità</span><span class="sxs-lookup"><span data-stu-id="ef7fc-146">Add more features</span></span>

<span data-ttu-id="ef7fc-147">Ora che il test è stato superato, è necessario scriverne altri.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-147">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="ef7fc-148">Esistono alcuni altri casi semplici per i numeri primi: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-148">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="ef7fc-149">È possibile aggiungere nuovi test con l'[attributo TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute), ma questa operazione risulta rapidamente noiosa.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-149">You could add new tests with the [TestMethod attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute), but that quickly becomes tedious.</span></span> <span data-ttu-id="ef7fc-150">Sono disponibili altri attributi di MSTest che consentono di scrivere una suite di test analoghi.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-150">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="ef7fc-151">Un [attributo DataTestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataTestMethodAttribute) rappresenta una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-151">A [DataTestMethod attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataTestMethodAttribute) represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="ef7fc-152">È possibile usare l'[attributo DataRow](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataRowAttribute) per specificare i valori per tali input.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-152">You can use the [DataRow attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataRowAttribute) to specify values for those inputs.</span></span>

<span data-ttu-id="ef7fc-153">Anziché creare nuovi test, applicare questi due attributi per creare un singolo test basato sui dati.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-153">Instead of creating new tests, apply these two attributes to create a single data driven test.</span></span> <span data-ttu-id="ef7fc-154">Il test basato sui dati è un metodo che verifica vari valori minori di due, ovvero il numero primo più piccolo:</span><span class="sxs-lookup"><span data-stu-id="ef7fc-154">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/snippets/core/testing/unit-testing-using-mstest/csharp/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="ef7fc-155">Eseguire `dotnet test`. Due test hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-155">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="ef7fc-156">Per assicurare che tutti i test vengano superati, modificare la clausola `if` all'inizio del metodo:</span><span class="sxs-lookup"><span data-stu-id="ef7fc-156">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="ef7fc-157">Continuare a eseguire l'iterazione aggiungendo altri test, altre teorie e altro codice nella libreria principale.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-157">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="ef7fc-158">Si ottiene la [versione completa dei test](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) e l'[implementazione completa della libreria](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="ef7fc-158">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="ef7fc-159">È stata compilata una piccola libreria e un set di unit test per tale libreria.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-159">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="ef7fc-160">La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-160">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="ef7fc-161">La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ef7fc-161">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef7fc-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef7fc-162">See also</span></span>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting>
- [<span data-ttu-id="ef7fc-163">Usare il framework MSTest negli unit test</span><span class="sxs-lookup"><span data-stu-id="ef7fc-163">Use the MSTest framework in unit tests</span></span>](/visualstudio/test/using-microsoft-visualstudio-testtools-unittesting-members-in-unit-tests)
- [<span data-ttu-id="ef7fc-164">Documentazione del framework di test MSTest V2</span><span class="sxs-lookup"><span data-stu-id="ef7fc-164">MSTest V2 test framework docs</span></span>](https://github.com/Microsoft/testfx-docs)

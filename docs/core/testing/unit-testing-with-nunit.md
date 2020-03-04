---
title: Testing unità di C# con NUnit e .NET Core
description: Informazioni sui concetti relativi agli unit test in C# e .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e NUnit.
author: rprouse
ms.date: 08/31/2018
ms.openlocfilehash: 283aa5a28ed213d4290eb3c73a98af56ec074ad0
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78240883"
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a><span data-ttu-id="febe0-103">Testing unità di C# con NUnit e .NET Core</span><span class="sxs-lookup"><span data-stu-id="febe0-103">Unit testing C# with NUnit and .NET Core</span></span>

<span data-ttu-id="febe0-104">In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità.</span><span class="sxs-lookup"><span data-stu-id="febe0-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="febe0-105">Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="febe0-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) before you begin.</span></span> <span data-ttu-id="febe0-106">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="febe0-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="prerequisites"></a><span data-ttu-id="febe0-107">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="febe0-107">Prerequisites</span></span>

- <span data-ttu-id="febe0-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="febe0-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="febe0-109">Un editor di testo o editor di codice di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="febe0-109">A text editor or code editor of your choice.</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="febe0-110">Creazione del progetto di origine</span><span class="sxs-lookup"><span data-stu-id="febe0-110">Creating the source project</span></span>

<span data-ttu-id="febe0-111">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="febe0-111">Open a shell window.</span></span> <span data-ttu-id="febe0-112">Creare una directory denominata *unit-testing-using-nunit* in cui archiviare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="febe0-112">Create a directory called *unit-testing-using-nunit* to hold the solution.</span></span> <span data-ttu-id="febe0-113">In questa nuova directory eseguire il comando seguente per creare un nuovo file di soluzione per la libreria di classi e il progetto di test:</span><span class="sxs-lookup"><span data-stu-id="febe0-113">Inside this new directory, run the following command to create a new solution file for the class library and the test project:</span></span>

```dotnetcli
dotnet new sln
```

<span data-ttu-id="febe0-114">Creare quindi una directory *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="febe0-114">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="febe0-115">Finora è stata creata la struttura di directory e file seguente:</span><span class="sxs-lookup"><span data-stu-id="febe0-115">The following outline shows the directory and file structure so far:</span></span>

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

<span data-ttu-id="febe0-116">Impostare *PrimeService* come directory corrente ed eseguire il comando seguente per creare il progetto di origine:</span><span class="sxs-lookup"><span data-stu-id="febe0-116">Make *PrimeService* the current directory and run the following command to create the source project:</span></span>

```dotnetcli
dotnet new classlib
```

<span data-ttu-id="febe0-117">Assegnare il nome *PrimeService.cs* al file *Class1.cs*.</span><span class="sxs-lookup"><span data-stu-id="febe0-117">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="febe0-118">Si crea un'implementazione non corretta della classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="febe0-118">You create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="febe0-119">Tornare alla directory *unit-testing-using-nunit*.</span><span class="sxs-lookup"><span data-stu-id="febe0-119">Change the directory back to the *unit-testing-using-nunit* directory.</span></span> <span data-ttu-id="febe0-120">Eseguire il comando seguente per aggiungere il progetto di libreria di classi alla soluzione:</span><span class="sxs-lookup"><span data-stu-id="febe0-120">Run the following command to add the class library project to the solution:</span></span>

```dotnetcli
dotnet sln add PrimeService/PrimeService.csproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="febe0-121">Creazione del progetto di test</span><span class="sxs-lookup"><span data-stu-id="febe0-121">Creating the test project</span></span>

<span data-ttu-id="febe0-122">Creare quindi la directory *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="febe0-122">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="febe0-123">Di seguito è illustrata la struttura di directory:</span><span class="sxs-lookup"><span data-stu-id="febe0-123">The following outline shows the directory structure:</span></span>

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="febe0-124">Impostare *PrimeService.Tests* come directory corrente e creare un nuovo progetto usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="febe0-124">Make the *PrimeService.Tests* directory the current directory and create a new project using the following command:</span></span>

```dotnetcli
dotnet new nunit
```

<span data-ttu-id="febe0-125">Il comando [dotnet new](../tools/dotnet-new.md) crea un progetto di test che usa NUnit come libreria di test.</span><span class="sxs-lookup"><span data-stu-id="febe0-125">The [dotnet new](../tools/dotnet-new.md) command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="febe0-126">Il modello generato configura il Test Runner nel file *PrimeService.Tests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="febe0-126">The generated template configures the test runner in the *PrimeService.Tests.csproj* file:</span></span>

[!code-xml[Packages](~/samples/snippets/core/testing/unit-testing-using-nunit/csharp/PrimeService.Tests/PrimeService.Tests.csproj#Packages)]

<span data-ttu-id="febe0-127">Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="febe0-127">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="febe0-128">`dotnet new` nel passaggio precedente aggiunge Microsoft Test SDK, il framework di test NUnit e l'adattatore di test NUnit.</span><span class="sxs-lookup"><span data-stu-id="febe0-128">`dotnet new` in the previous step added the Microsoft test SDK, the NUnit test framework, and the NUnit test adapter.</span></span> <span data-ttu-id="febe0-129">Aggiungere ora la libreria di classi `PrimeService` come un'altra dipendenza del progetto.</span><span class="sxs-lookup"><span data-stu-id="febe0-129">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="febe0-130">Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="febe0-130">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="febe0-131">È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="febe0-131">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="febe0-132">Il layout della soluzione finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="febe0-132">The following outline shows the final solution layout:</span></span>

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeService.Tests.csproj
```

<span data-ttu-id="febe0-133">Eseguire il comando seguente nella directory *unit-testing-using-nunit*:</span><span class="sxs-lookup"><span data-stu-id="febe0-133">Execute the following command in the *unit-testing-using-nunit* directory:</span></span>

```dotnetcli
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="febe0-134">Creazione del primo test</span><span class="sxs-lookup"><span data-stu-id="febe0-134">Creating the first test</span></span>

<span data-ttu-id="febe0-135">Scrivere un test che genera errore, fare in modo che venga superato e quindi ripetere il processo.</span><span class="sxs-lookup"><span data-stu-id="febe0-135">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="febe0-136">Nella directory *PrimeService.Tests* rinominare il file *UnitTest1.cs* in *PrimeService_IsPrimeShould.cs* e sostituire l'intero contenuto con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="febe0-136">In the *PrimeService.Tests* directory, rename the *UnitTest1.cs* file to *PrimeService_IsPrimeShould.cs* and replace its entire contents with the following code:</span></span>

[!code-csharp[Sample_FirstTest](~/samples/snippets/core/testing/unit-testing-using-nunit/csharp/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_FirstTest)]

<span data-ttu-id="febe0-137">L'attributo `[TestFixture]` indica una classe che contiene unit test.</span><span class="sxs-lookup"><span data-stu-id="febe0-137">The `[TestFixture]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="febe0-138">L'attributo `[Test]` indica che il metodo è un metodo di test.</span><span class="sxs-lookup"><span data-stu-id="febe0-138">The `[Test]` attribute indicates a method is a test method.</span></span>

<span data-ttu-id="febe0-139">Salvare questo file ed eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="febe0-139">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="febe0-140">Il Test Runner di NUnit include il punto d'ingresso del programma per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="febe0-140">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="febe0-141">`dotnet test` avvia il Test Runner usando il progetto di unit test creato.</span><span class="sxs-lookup"><span data-stu-id="febe0-141">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="febe0-142">Il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="febe0-142">Your test fails.</span></span> <span data-ttu-id="febe0-143">Non è stata ancora creata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="febe0-143">You haven't created the implementation yet.</span></span> <span data-ttu-id="febe0-144">Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="febe0-144">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="febe0-145">Eseguire di nuovo *nella directory*unit-testing-using-nunit`dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="febe0-145">In the *unit-testing-using-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="febe0-146">Il comando `dotnet test` esegue prima una compilazione del progetto `PrimeService` e quindi del progetto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="febe0-146">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="febe0-147">Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo,</span><span class="sxs-lookup"><span data-stu-id="febe0-147">After building both projects, it runs this single test.</span></span> <span data-ttu-id="febe0-148">Procede.</span><span class="sxs-lookup"><span data-stu-id="febe0-148">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="febe0-149">Aggiunta di altre funzionalità</span><span class="sxs-lookup"><span data-stu-id="febe0-149">Adding more features</span></span>

<span data-ttu-id="febe0-150">Ora che il test è stato superato, è necessario scriverne altri.</span><span class="sxs-lookup"><span data-stu-id="febe0-150">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="febe0-151">Esistono alcuni altri casi semplici per i numeri primi: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="febe0-151">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="febe0-152">È possibile aggiungere nuovi test con l'attributo `[Test]`, ma questa operazione risulta rapidamente noiosa.</span><span class="sxs-lookup"><span data-stu-id="febe0-152">You could add new tests with the `[Test]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="febe0-153">Sono disponibili altri attributi NUnit che consentono di scrivere una suite di test analoghi.</span><span class="sxs-lookup"><span data-stu-id="febe0-153">There are other NUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="febe0-154">Un attributo `[TestCase]` viene usato per creare una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi.</span><span class="sxs-lookup"><span data-stu-id="febe0-154">A `[TestCase]` attribute is used to create a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="febe0-155">È possibile usare l'attributo `[TestCase]` per specificare i valori per tali input.</span><span class="sxs-lookup"><span data-stu-id="febe0-155">You can use the `[TestCase]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="febe0-156">Anziché creare nuovi test, applicare questo attributo per creare un singolo test basato sui dati.</span><span class="sxs-lookup"><span data-stu-id="febe0-156">Instead of creating new tests, apply this attribute to create a single data driven test.</span></span> <span data-ttu-id="febe0-157">Il test basato sui dati è un metodo che verifica vari valori minori di due, ovvero il numero primo più piccolo:</span><span class="sxs-lookup"><span data-stu-id="febe0-157">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](~/samples/snippets/core/testing/unit-testing-using-nunit/csharp/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="febe0-158">Eseguire `dotnet test`. Due test hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="febe0-158">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="febe0-159">Per assicurare che tutti i test vengano superati, modificare la clausola `if` all'inizio del metodo `Main` nel file *PrimeService.cs*:</span><span class="sxs-lookup"><span data-stu-id="febe0-159">To make all of the tests pass, change the `if` clause at the beginning of the `Main` method in the *PrimeService.cs* file:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="febe0-160">Continuare a eseguire l'iterazione aggiungendo altri test, altre teorie e altro codice nella libreria principale.</span><span class="sxs-lookup"><span data-stu-id="febe0-160">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="febe0-161">Si ottiene la [versione completa dei test](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) e l'[implementazione completa della libreria](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="febe0-161">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="febe0-162">È stata compilata una piccola libreria e un set di unit test per tale libreria.</span><span class="sxs-lookup"><span data-stu-id="febe0-162">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="febe0-163">La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="febe0-163">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="febe0-164">La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="febe0-164">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

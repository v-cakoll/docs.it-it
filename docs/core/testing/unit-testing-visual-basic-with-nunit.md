---
title: Testing unità di Visual Basic in .NET Core con il test dotnet e NUnit
description: Informazioni sui concetti relativi agli unit test in .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di Visual Basic di esempio con NUnit.
author: rprouse
ms.date: 10/04/2018
ms.openlocfilehash: a33447457344b241b4c2376d777b0deb7f556874
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78240922"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-nunit"></a><span data-ttu-id="34512-103">Testing unità di librerie .NET Core di Visual Basic usando il test dotnet e NUnit</span><span class="sxs-lookup"><span data-stu-id="34512-103">Unit testing Visual Basic .NET Core libraries using dotnet test and NUnit</span></span>

<span data-ttu-id="34512-104">In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità.</span><span class="sxs-lookup"><span data-stu-id="34512-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="34512-105">Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-nunit/) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="34512-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-nunit/) before you begin.</span></span> <span data-ttu-id="34512-106">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="34512-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="prerequisites"></a><span data-ttu-id="34512-107">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="34512-107">Prerequisites</span></span>

- <span data-ttu-id="34512-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="34512-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="34512-109">Un editor di testo o editor di codice di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="34512-109">A text editor or code editor of your choice.</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="34512-110">Creazione del progetto di origine</span><span class="sxs-lookup"><span data-stu-id="34512-110">Creating the source project</span></span>

<span data-ttu-id="34512-111">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="34512-111">Open a shell window.</span></span> <span data-ttu-id="34512-112">Creare una directory denominata *unit-testing-vb-nunit* in cui archiviare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="34512-112">Create a directory called *unit-testing-vb-nunit* to hold the solution.</span></span> <span data-ttu-id="34512-113">In questa nuova directory eseguire il comando seguente per creare un nuovo file di soluzione per la libreria di classi e il progetto di test:</span><span class="sxs-lookup"><span data-stu-id="34512-113">Inside this new directory, run the following command to create a new solution file for the class library and the test project:</span></span>

```dotnetcli
dotnet new sln
```

<span data-ttu-id="34512-114">Creare quindi una directory *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="34512-114">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="34512-115">Di seguito viene mostrata la struttura di file disponibile fino a questo punto:</span><span class="sxs-lookup"><span data-stu-id="34512-115">The following outline shows the file structure so far:</span></span>

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
```

<span data-ttu-id="34512-116">Impostare *PrimeService* come directory corrente ed eseguire il comando seguente per creare il progetto di origine:</span><span class="sxs-lookup"><span data-stu-id="34512-116">Make *PrimeService* the current directory and run the following command to create the source project:</span></span>

```dotnetcli
dotnet new classlib -lang VB
```

<span data-ttu-id="34512-117">Rinominare *Class1.VB* in *PrimeService.VB*.</span><span class="sxs-lookup"><span data-stu-id="34512-117">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="34512-118">Si crea un'implementazione non corretta della classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="34512-118">You create a failing implementation of the `PrimeService` class:</span></span>

```vb
Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first.")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="34512-119">Tornare alla directory *unit-testing-vb-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="34512-119">Change the directory back to the *unit-testing-vb-using-mstest* directory.</span></span> <span data-ttu-id="34512-120">Eseguire il comando seguente per aggiungere il progetto di libreria di classi alla soluzione:</span><span class="sxs-lookup"><span data-stu-id="34512-120">Run the following command to add the class library project to the solution:</span></span>

```dotnetcli
dotnet sln add .\PrimeService\PrimeService.vbproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="34512-121">Creazione del progetto di test</span><span class="sxs-lookup"><span data-stu-id="34512-121">Creating the test project</span></span>

<span data-ttu-id="34512-122">Creare quindi la directory *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="34512-122">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="34512-123">Di seguito è illustrata la struttura di directory:</span><span class="sxs-lookup"><span data-stu-id="34512-123">The following outline shows the directory structure:</span></span>

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="34512-124">Impostare *PrimeService.Tests* come directory corrente e creare un nuovo progetto usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="34512-124">Make the *PrimeService.Tests* directory the current directory and create a new project using the following command:</span></span>

```dotnetcli
dotnet new nunit -lang VB
```

<span data-ttu-id="34512-125">Il comando [dotnet new](../tools/dotnet-new.md) crea un progetto di test che usa NUnit come libreria di test.</span><span class="sxs-lookup"><span data-stu-id="34512-125">The [dotnet new](../tools/dotnet-new.md) command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="34512-126">Il modello generato configura il Test Runner nel file *PrimeServiceTests.vbproj*:</span><span class="sxs-lookup"><span data-stu-id="34512-126">The generated template configures the test runner in the *PrimeServiceTests.vbproj* file:</span></span>

[!code-xml[Packages](~/samples/snippets/core/testing/unit-testing-vb-nunit/vb/PrimeService.Tests/PrimeService.Tests.vbproj#Packages)]

<span data-ttu-id="34512-127">Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="34512-127">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="34512-128">`dotnet new` nel passaggio precedente aggiunge NUnit e l'adattatore di test NUnit.</span><span class="sxs-lookup"><span data-stu-id="34512-128">`dotnet new` in the previous step added NUnit and the NUnit test adapter.</span></span> <span data-ttu-id="34512-129">Aggiungere ora la libreria di classi `PrimeService` come un'altra dipendenza del progetto.</span><span class="sxs-lookup"><span data-stu-id="34512-129">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="34512-130">Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="34512-130">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="34512-131">È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="34512-131">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="34512-132">Il layout della soluzione finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="34512-132">You have the following final solution layout:</span></span>

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeService.Tests.vbproj
```

<span data-ttu-id="34512-133">Eseguire il comando seguente nella directory *unit-testing-vb-nunit*:</span><span class="sxs-lookup"><span data-stu-id="34512-133">Execute the following command in the *unit-testing-vb-nunit* directory:</span></span>

```dotnetcli
dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="34512-134">Creazione del primo test</span><span class="sxs-lookup"><span data-stu-id="34512-134">Creating the first test</span></span>

<span data-ttu-id="34512-135">Scrivere un test che genera errore, fare in modo che venga superato e quindi ripetere il processo.</span><span class="sxs-lookup"><span data-stu-id="34512-135">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="34512-136">Nella directory *PrimeService.Tests* rinominare il file *UnitTest1.vb* in *PrimeService_IsPrimeShould.VB* e sostituire l'intero contenuto con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="34512-136">In the *PrimeService.Tests* directory, rename the *UnitTest1.vb* file to *PrimeService_IsPrimeShould.VB* and replace its entire contents with the following code:</span></span>

```vb
Imports NUnit.Framework

Namespace PrimeService.Tests
    <TestFixture>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Test>
        Sub IsPrime_InputIs1_ReturnFalse()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="34512-137">L'attributo `<TestFixture>` indica una classe che contiene test.</span><span class="sxs-lookup"><span data-stu-id="34512-137">The `<TestFixture>` attribute indicates a class that contains tests.</span></span> <span data-ttu-id="34512-138">L'attributo `<Test>` indica un metodo eseguito dal Test Runner.</span><span class="sxs-lookup"><span data-stu-id="34512-138">The `<Test>` attribute denotes a method that is run by the test runner.</span></span> <span data-ttu-id="34512-139">Da *unit-testing-vb-nunit* eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="34512-139">From the *unit-testing-vb-nunit*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="34512-140">Il Test Runner di NUnit include il punto d'ingresso del programma per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="34512-140">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="34512-141">`dotnet test` avvia il Test Runner usando il progetto di unit test creato.</span><span class="sxs-lookup"><span data-stu-id="34512-141">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="34512-142">Il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="34512-142">Your test fails.</span></span> <span data-ttu-id="34512-143">Non è stata ancora creata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="34512-143">You haven't created the implementation yet.</span></span> <span data-ttu-id="34512-144">Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="34512-144">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first.")
End Function
```

<span data-ttu-id="34512-145">Eseguire di nuovo *nella directory*unit-testing-vb-nunit`dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="34512-145">In the *unit-testing-vb-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="34512-146">Il comando `dotnet test` esegue prima una compilazione del progetto `PrimeService` e quindi del progetto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="34512-146">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="34512-147">Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo,</span><span class="sxs-lookup"><span data-stu-id="34512-147">After building both projects, it runs this single test.</span></span> <span data-ttu-id="34512-148">Procede.</span><span class="sxs-lookup"><span data-stu-id="34512-148">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="34512-149">Aggiunta di altre funzionalità</span><span class="sxs-lookup"><span data-stu-id="34512-149">Adding more features</span></span>

<span data-ttu-id="34512-150">Ora che il test è stato superato, è necessario scriverne altri.</span><span class="sxs-lookup"><span data-stu-id="34512-150">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="34512-151">Esistono alcuni altri casi semplici per i numeri primi: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="34512-151">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="34512-152">È possibile aggiungerli come nuovi test, con l'attributo `<Test>`, ma questa operazione risulta rapidamente noiosa.</span><span class="sxs-lookup"><span data-stu-id="34512-152">You could add those cases as new tests with the `<Test>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="34512-153">Sono disponibili altri attributi xUnit che consentono di scrivere una suite di test analoghi.</span><span class="sxs-lookup"><span data-stu-id="34512-153">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="34512-154">Un attributo `<TestCase>` rappresenta una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi.</span><span class="sxs-lookup"><span data-stu-id="34512-154">A `<TestCase>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="34512-155">È possibile usare l'attributo `<TestCase>` per specificare i valori per tali input.</span><span class="sxs-lookup"><span data-stu-id="34512-155">You can use the `<TestCase>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="34512-156">Anziché creare nuovi test, applicare questi due attributi per creare una serie di test che verificano diversi valori minori di due, ovvero il numero primo più basso:</span><span class="sxs-lookup"><span data-stu-id="34512-156">Instead of creating new tests, apply these two attributes to create a series of tests that test several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/snippets/core/testing/unit-testing-vb-nunit/vb/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="34512-157">Eseguire `dotnet test`. Due test hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="34512-157">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="34512-158">Per fare in modo che tutti i test vengano superati, modificare la clausola `if` all'inizio del metodo `Main` nel file *PrimeServices.cs*:</span><span class="sxs-lookup"><span data-stu-id="34512-158">To make all of the tests pass, change the `if` clause at the beginning of the `Main` method in the *PrimeServices.cs* file:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="34512-159">Continuare a eseguire l'iterazione aggiungendo altri test, altre teorie e altro codice nella libreria principale.</span><span class="sxs-lookup"><span data-stu-id="34512-159">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="34512-160">Si ottiene la [versione completa dei test](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) e l'[implementazione completa della libreria](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).</span><span class="sxs-lookup"><span data-stu-id="34512-160">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="34512-161">È stata compilata una piccola libreria e un set di unit test per tale libreria.</span><span class="sxs-lookup"><span data-stu-id="34512-161">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="34512-162">La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="34512-162">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="34512-163">La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="34512-163">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

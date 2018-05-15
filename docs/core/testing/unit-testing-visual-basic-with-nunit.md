---
title: Testing unità con Visual Basic in .NET Core usando il test dotnet e NUnit
description: Informazioni sui concetti relativi agli unit test in .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di Visual Basic di esempio con NUnit.
author: rprouse
ms.date: 12/01/2017
dev_langs:
- vb
ms.openlocfilehash: 552b60dd3937abc413c1b4410213948f3b509526
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-nunit"></a><span data-ttu-id="27fb4-103">Testing unità di librerie .NET Core di Visual Basic usando il test dotnet e NUnit</span><span class="sxs-lookup"><span data-stu-id="27fb4-103">Unit testing Visual Basic .NET Core libraries using dotnet test and NUnit</span></span>

<span data-ttu-id="27fb4-104">In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità.</span><span class="sxs-lookup"><span data-stu-id="27fb4-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="27fb4-105">Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-nunit/) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="27fb4-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-nunit/) before you begin.</span></span> <span data-ttu-id="27fb4-106">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="27fb4-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="27fb4-107">Creazione del progetto di origine</span><span class="sxs-lookup"><span data-stu-id="27fb4-107">Creating the source project</span></span>

<span data-ttu-id="27fb4-108">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="27fb4-108">Open a shell window.</span></span> <span data-ttu-id="27fb4-109">Creare una directory denominata *unit-testing-vb-nunit* in cui archiviare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="27fb4-109">Create a directory called *unit-testing-vb-nunit* to hold the solution.</span></span> <span data-ttu-id="27fb4-110">In questa nuova directory eseguire [`dotnet new sln`](../tools/dotnet-new.md) per creare una nuova soluzione.</span><span class="sxs-lookup"><span data-stu-id="27fb4-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="27fb4-111">Questa procedura semplifica la gestione sia della libreria di classi che del progetto di unit test.</span><span class="sxs-lookup"><span data-stu-id="27fb4-111">This practice makes it easier to manage both the class library and the unit test project.</span></span> <span data-ttu-id="27fb4-112">All'interno della directory della soluzione creare una directory *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="27fb4-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="27fb4-113">Finora è stata creata la struttura di directory e file seguente:</span><span class="sxs-lookup"><span data-stu-id="27fb4-113">You have the following directory and file structure thus far:</span></span>

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
```

<span data-ttu-id="27fb4-114">Impostare *PrimeService* come directory corrente ed eseguire [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) per creare il progetto di origine.</span><span class="sxs-lookup"><span data-stu-id="27fb4-114">Make *PrimeService* the current directory and run [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="27fb4-115">Rinominare *Class1.VB* in *PrimeService.VB*.</span><span class="sxs-lookup"><span data-stu-id="27fb4-115">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="27fb4-116">Per usare lo sviluppo basato su test (TDD), si creerà un'implementazione non corretta della classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="27fb4-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

```vb
Imports System

Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="27fb4-117">Tornare alla directory *unit-testing-vb-using-stest*.</span><span class="sxs-lookup"><span data-stu-id="27fb4-117">Change the directory back to the *unit-testing-vb-using-stest* directory.</span></span> <span data-ttu-id="27fb4-118">Eseguire [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) per aggiungere il progetto di libreria di classi alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="27fb4-118">Run [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="install-the-nunit-project-template"></a><span data-ttu-id="27fb4-119">Installare il modello di progetto NUnit</span><span class="sxs-lookup"><span data-stu-id="27fb4-119">Install the NUnit project template</span></span>

<span data-ttu-id="27fb4-120">È necessario installare i modelli di progetto di test NUnit prima di creare un progetto di test.</span><span class="sxs-lookup"><span data-stu-id="27fb4-120">The NUnit test project templates need to be installed before creating a test project.</span></span> <span data-ttu-id="27fb4-121">Questa operazione deve essere eseguita una sola volta in ogni computer di sviluppo in cui verranno creati nuovi progetti NUnit.</span><span class="sxs-lookup"><span data-stu-id="27fb4-121">This only needs to be done once on each developer machine where you'll create new NUnit projects.</span></span> <span data-ttu-id="27fb4-122">Eseguire [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) per installare i modelli NUnit.</span><span class="sxs-lookup"><span data-stu-id="27fb4-122">Run [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) to install the NUnit templates.</span></span>

 ```
 dotnet new -i NUnit3.DotNetNew.Template
 ```

## <a name="creating-the-test-project"></a><span data-ttu-id="27fb4-123">Creazione del progetto di test</span><span class="sxs-lookup"><span data-stu-id="27fb4-123">Creating the test project</span></span>

<span data-ttu-id="27fb4-124">Creare quindi la directory *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="27fb4-124">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="27fb4-125">Di seguito è illustrata la struttura di directory:</span><span class="sxs-lookup"><span data-stu-id="27fb4-125">The following outline shows the directory structure:</span></span>

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="27fb4-126">Impostare *PrimeService.Tests* come directory corrente e creare un nuovo progetto usando [`dotnet new nunit -lang VB`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="27fb4-126">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new nunit -lang VB`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="27fb4-127">Questo comando crea un progetto di test che usa NUnit come libreria di test.</span><span class="sxs-lookup"><span data-stu-id="27fb4-127">This command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="27fb4-128">Il modello generato configura il Test Runner nel file *PrimeServiceTests.vbproj*:</span><span class="sxs-lookup"><span data-stu-id="27fb4-128">The generated template configures the test runner in the *PrimeServiceTests.vbproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="27fb4-129">Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="27fb4-129">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="27fb4-130">`dotnet new` nel passaggio precedente aggiunge NUnit e l'adattatore di test NUnit.</span><span class="sxs-lookup"><span data-stu-id="27fb4-130">`dotnet new` in the previous step added NUnit and the NUnit test adapter.</span></span> <span data-ttu-id="27fb4-131">Aggiungere ora la libreria di classi `PrimeService` come un'altra dipendenza del progetto.</span><span class="sxs-lookup"><span data-stu-id="27fb4-131">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="27fb4-132">Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="27fb4-132">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="27fb4-133">È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="27fb4-133">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="27fb4-134">Il layout della soluzione finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="27fb4-134">You have the following final solution layout:</span></span>

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

<span data-ttu-id="27fb4-135">Eseguire [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) nella directory *unit-testing-vb-nunit*.</span><span class="sxs-lookup"><span data-stu-id="27fb4-135">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) in the *unit-testing-vb-nunit* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="27fb4-136">Creazione del primo test</span><span class="sxs-lookup"><span data-stu-id="27fb4-136">Creating the first test</span></span>

<span data-ttu-id="27fb4-137">L'approccio di sviluppo basato su test richiede la creazione di un test con esito negativo. È quindi necessario che il test venga superato e che il processo venga ripetuto.</span><span class="sxs-lookup"><span data-stu-id="27fb4-137">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="27fb4-138">Rimuovere *UnitTest1.vb* dalla directory *PrimeService.Tests* e creare un nuovo file di Visual Basic denominato *PrimeService_IsPrimeShould.VB*.</span><span class="sxs-lookup"><span data-stu-id="27fb4-138">Remove *UnitTest1.vb* from the *PrimeService.Tests* directory and create a new Visual Basic file named *PrimeService_IsPrimeShould.VB*.</span></span> <span data-ttu-id="27fb4-139">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="27fb4-139">Add the following code:</span></span>

```vb
Imports NUnit.Framework

Namespace PrimeService.Tests
    <TestFixture>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Test>
        Sub ReturnFalseGivenValueOf1()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="27fb4-140">L'attributo `<TestFixture>` indica una classe che contiene test.</span><span class="sxs-lookup"><span data-stu-id="27fb4-140">The `<TestFixture>` attribute indicates a class that contains tests.</span></span> <span data-ttu-id="27fb4-141">L'attributo `<Test>` indica un metodo eseguito dal Test Runner.</span><span class="sxs-lookup"><span data-stu-id="27fb4-141">The `<Test>` attribute denotes a method that is run by the test runner.</span></span> <span data-ttu-id="27fb4-142">Da *unit-testing-vb-nunit* eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="27fb4-142">From the *unit-testing-vb-nunit*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="27fb4-143">Il Test Runner di NUnit include il punto d'ingresso del programma per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="27fb4-143">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="27fb4-144">`dotnet test` avvia il Test Runner usando il progetto di unit test creato.</span><span class="sxs-lookup"><span data-stu-id="27fb4-144">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="27fb4-145">Il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="27fb4-145">Your test fails.</span></span> <span data-ttu-id="27fb4-146">Non è stata ancora creata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="27fb4-146">You haven't created the implementation yet.</span></span> <span data-ttu-id="27fb4-147">Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="27fb4-147">Make this test by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first")
End Function
```

<span data-ttu-id="27fb4-148">Eseguire di nuovo `dotnet test` nella directory *unit-testing-vb-nunit*.</span><span class="sxs-lookup"><span data-stu-id="27fb4-148">In the *unit-testing-vb-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="27fb4-149">Il comando `dotnet test` esegue prima una compilazione del progetto `PrimeService` e quindi del progetto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="27fb4-149">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="27fb4-150">Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo,</span><span class="sxs-lookup"><span data-stu-id="27fb4-150">After building both projects, it runs this single test.</span></span> <span data-ttu-id="27fb4-151">che viene superato.</span><span class="sxs-lookup"><span data-stu-id="27fb4-151">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="27fb4-152">Aggiunta di altre funzionalità</span><span class="sxs-lookup"><span data-stu-id="27fb4-152">Adding more features</span></span>

<span data-ttu-id="27fb4-153">Ora che il test è stato superato, è necessario scriverne altri.</span><span class="sxs-lookup"><span data-stu-id="27fb4-153">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="27fb4-154">Esistono alcuni altri casi semplici per i numeri primi: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="27fb4-154">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="27fb4-155">È possibile aggiungerli come nuovi test, con l'attributo `<Test>`, ma questa operazione risulta rapidamente noiosa.</span><span class="sxs-lookup"><span data-stu-id="27fb4-155">You could add those cases as new tests with the `<Test>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="27fb4-156">Sono disponibili altri attributi xUnit che consentono di scrivere una suite di test analoghi.</span><span class="sxs-lookup"><span data-stu-id="27fb4-156">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="27fb4-157">Un attributo `<TestCase>` rappresenta una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi.</span><span class="sxs-lookup"><span data-stu-id="27fb4-157">A `<TestCase>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="27fb4-158">È possibile usare l'attributo `<TestCase>` per specificare i valori per tali input.</span><span class="sxs-lookup"><span data-stu-id="27fb4-158">You can use the `<TestCase>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="27fb4-159">Anziché creare nuovi test, applicare questi due attributi per creare una serie di test che verificano diversi valori minori di due, ovvero il numero primo più basso:</span><span class="sxs-lookup"><span data-stu-id="27fb4-159">Instead of creating new tests, apply these two attributes to create a series of tests that test several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="27fb4-160">Eseguire `dotnet test`. Due test hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="27fb4-160">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="27fb4-161">Per assicurare che tutti i test vengano superati, modificare la clausola `if` all'inizio del metodo:</span><span class="sxs-lookup"><span data-stu-id="27fb4-161">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="27fb4-162">Continuare a eseguire l'iterazione aggiungendo altri test, altre teorie e altro codice nella libreria principale.</span><span class="sxs-lookup"><span data-stu-id="27fb4-162">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="27fb4-163">Si ottiene la [versione completa dei test](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) e l'[implementazione completa della libreria](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).</span><span class="sxs-lookup"><span data-stu-id="27fb4-163">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="27fb4-164">È stata compilata una piccola libreria e un set di unit test per tale libreria.</span><span class="sxs-lookup"><span data-stu-id="27fb4-164">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="27fb4-165">La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="27fb4-165">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="27fb4-166">La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="27fb4-166">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

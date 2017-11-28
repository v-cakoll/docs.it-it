---
title: "Testing unità con Visual Basic in .NET Core usando il test dotnet e MSTest"
description: Informazioni sui concetti relativi agli unit test in .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di Visual Basic di esempio con MSTest.
author: billwagner
ms.author: wiwagn
ms.date: 09/01/2017
ms.topic: article
dev_langs: vb
ms.prod: .net-core
ms.openlocfilehash: b656ae4746691f2e72eaa666542e98d4abc91069
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-mstest"></a><span data-ttu-id="054e2-103">Testing unità di librerie .NET Core di Visual Basic usando il test dotnet e MSTest</span><span class="sxs-lookup"><span data-stu-id="054e2-103">Unit testing Visual Basic .NET Core libraries using dotnet test and MStest</span></span>

<span data-ttu-id="054e2-104">In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità.</span><span class="sxs-lookup"><span data-stu-id="054e2-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="054e2-105">Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-mstest/) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="054e2-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="054e2-106">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="054e2-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="054e2-107">Creazione del progetto di origine</span><span class="sxs-lookup"><span data-stu-id="054e2-107">Creating the source project</span></span>

<span data-ttu-id="054e2-108">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="054e2-108">Open a shell window.</span></span> <span data-ttu-id="054e2-109">Creare una directory denominata *unit-testing-using-dotnet-test* in cui archiviare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="054e2-109">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span>
<span data-ttu-id="054e2-110">In questa nuova directory eseguire [`dotnet new sln`](../tools/dotnet-new.md) per creare una nuova soluzione.</span><span class="sxs-lookup"><span data-stu-id="054e2-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="054e2-111">Questa procedura semplifica la gestione sia della libreria di classi che del progetto di unit test.</span><span class="sxs-lookup"><span data-stu-id="054e2-111">This practice makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="054e2-112">All'interno della directory della soluzione creare una directory *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="054e2-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="054e2-113">Finora è stata creata la struttura di directory e file seguente:</span><span class="sxs-lookup"><span data-stu-id="054e2-113">You have the following directory and file structure thus far:</span></span>

```
/unit-testing-vb-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

<span data-ttu-id="054e2-114">Impostare *PrimeService* come directory corrente ed eseguire [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) per creare il progetto di origine.</span><span class="sxs-lookup"><span data-stu-id="054e2-114">Make *PrimeService* the current directory and run [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="054e2-115">Rinominare *Class1.VB* in *PrimeService.VB*.</span><span class="sxs-lookup"><span data-stu-id="054e2-115">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="054e2-116">Per usare lo sviluppo basato su test (TDD), si creerà un'implementazione non corretta della classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="054e2-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="054e2-117">Tornare alla directory *unit-testing-vb-using-stest*.</span><span class="sxs-lookup"><span data-stu-id="054e2-117">Change the directory back to the *unit-testing-vb-using-stest* directory.</span></span> <span data-ttu-id="054e2-118">Eseguire [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) per aggiungere il progetto di libreria di classi alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="054e2-118">Run [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="054e2-119">Creazione del progetto di test</span><span class="sxs-lookup"><span data-stu-id="054e2-119">Creating the test project</span></span>

<span data-ttu-id="054e2-120">Creare quindi la directory *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="054e2-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="054e2-121">Di seguito è illustrata la struttura di directory:</span><span class="sxs-lookup"><span data-stu-id="054e2-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-vb-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="054e2-122">Impostare *PrimeService.Tests* come directory corrente e creare un nuovo progetto usando [`dotnet new mstest -lang VB`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="054e2-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest -lang VB`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="054e2-123">Questo comando crea un progetto di test che usa xUnit come libreria di test.</span><span class="sxs-lookup"><span data-stu-id="054e2-123">This command creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="054e2-124">Il modello generato configura il Test Runner nel file *PrimeServiceTests.vbproj*:</span><span class="sxs-lookup"><span data-stu-id="054e2-124">The generated template configures the test runner in the *PrimeServiceTests.vbproj*:</span></span>

```xml
<ItemGroup>
<PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
<PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
<PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="054e2-125">Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="054e2-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="054e2-126">Nel passaggio precedente `dotnet new` ha aggiunto MSTest e il Runner di MSTest.</span><span class="sxs-lookup"><span data-stu-id="054e2-126">`dotnet new` in the previous step added MSTest and the MSTest runner.</span></span> <span data-ttu-id="054e2-127">Aggiungere ora la libreria di classi `PrimeService` come un'altra dipendenza del progetto.</span><span class="sxs-lookup"><span data-stu-id="054e2-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="054e2-128">Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="054e2-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="054e2-129">È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService.Tests/PrimeService.Tests.vbproj) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="054e2-129">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="054e2-130">Il layout della soluzione finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="054e2-130">You have the following final solution layout:</span></span>

```
/unit-testing-vb-using-mstest
    unit-testing-vb-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

<span data-ttu-id="054e2-131">Eseguire [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) nella directory *unit-testing-vb-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="054e2-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) in the *unit-testing-vb-using-mstest* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="054e2-132">Creazione del primo test</span><span class="sxs-lookup"><span data-stu-id="054e2-132">Creating the first test</span></span>

<span data-ttu-id="054e2-133">L'approccio di sviluppo basato su test richiede la creazione di un test con esito negativo. È quindi necessario che il test venga superato e che il processo venga ripetuto.</span><span class="sxs-lookup"><span data-stu-id="054e2-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="054e2-134">Rimuovere *UnitTest1.vb* dalla directory *PrimeService.Tests* e creare un nuovo file di Visual Basic denominato *PrimeService_IsPrimeShould.VB*.</span><span class="sxs-lookup"><span data-stu-id="054e2-134">Remove *UnitTest1.vb* from the *PrimeService.Tests* directory and create a new Visual Basic file named *PrimeService_IsPrimeShould.VB*.</span></span> <span data-ttu-id="054e2-135">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="054e2-135">Add the following code:</span></span>

```vb
Imports Microsoft.VisualStudio.TestTools.UnitTesting

Namespace PrimeService.Tests
    <TestClass>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <TestMethod>
        Sub ReturnFalseGivenValueOf1()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="054e2-136">L'attributo `<TestClass>` indica una classe che contiene test.</span><span class="sxs-lookup"><span data-stu-id="054e2-136">The `<TestClass>` attribute indicates a class that contains tests.</span></span> <span data-ttu-id="054e2-137">L'attributo `<TestMethod>` indica un metodo eseguito dal Test Runner.</span><span class="sxs-lookup"><span data-stu-id="054e2-137">The `<TestMethod>` attribute denotes a method that is run by the test runner.</span></span> <span data-ttu-id="054e2-138">Da *unit-testing-vb-using-mstest* eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="054e2-138">From the *unit-testing-vb-using-mstest*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="054e2-139">Il Test Runner di xUnit include il punto d'ingresso del programma per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="054e2-139">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="054e2-140">`dotnet test` avvia il Test Runner usando il progetto di unit test creato.</span><span class="sxs-lookup"><span data-stu-id="054e2-140">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="054e2-141">Il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="054e2-141">Your test fails.</span></span> <span data-ttu-id="054e2-142">Non è stata ancora creata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="054e2-142">You haven't created the implementation yet.</span></span> <span data-ttu-id="054e2-143">Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="054e2-143">Make this test by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first")
End Function
```

<span data-ttu-id="054e2-144">Eseguire di nuovo `dotnet test` nella directory *unit-testing-vb-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="054e2-144">In the *unit-testing-vb-using-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="054e2-145">Il comando `dotnet test` esegue prima una compilazione del progetto `PrimeService` e quindi del progetto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="054e2-145">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="054e2-146">Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo,</span><span class="sxs-lookup"><span data-stu-id="054e2-146">After building both projects, it runs this single test.</span></span> <span data-ttu-id="054e2-147">che viene superato.</span><span class="sxs-lookup"><span data-stu-id="054e2-147">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="054e2-148">Aggiunta di altre funzionalità</span><span class="sxs-lookup"><span data-stu-id="054e2-148">Adding more features</span></span>

<span data-ttu-id="054e2-149">Ora che il test è stato superato, è necessario scriverne altri.</span><span class="sxs-lookup"><span data-stu-id="054e2-149">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="054e2-150">Esistono alcuni altri casi semplici per i numeri primi: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="054e2-150">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="054e2-151">È possibile aggiungerli come nuovi test, con l'attributo `<TestMethod>`, ma questa operazione risulta rapidamente noiosa.</span><span class="sxs-lookup"><span data-stu-id="054e2-151">You could add those cases as new tests with the `<TestMethod>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="054e2-152">Sono disponibili altri attributi xUnit che consentono di scrivere una suite di test analoghi.</span><span class="sxs-lookup"><span data-stu-id="054e2-152">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="054e2-153">Un attributo `<DataTestMethod>` rappresenta una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi.</span><span class="sxs-lookup"><span data-stu-id="054e2-153">A `<DataTestMethod>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="054e2-154">È possibile usare l'attributo `<DataRow>` per specificare i valori per tali input.</span><span class="sxs-lookup"><span data-stu-id="054e2-154">You can use the `<DataRow>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="054e2-155">Anziché creare nuovi test, applicare questi due attributi per creare una singola teoria.</span><span class="sxs-lookup"><span data-stu-id="054e2-155">Instead of creating new tests, apply these two attributes to create a single theory.</span></span> <span data-ttu-id="054e2-156">La teoria è un metodo che verifica vari valori minori di due, ovvero il numero primo più piccolo:</span><span class="sxs-lookup"><span data-stu-id="054e2-156">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="054e2-157">Eseguire `dotnet test`. Due test hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="054e2-157">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="054e2-158">Per assicurare che tutti i test vengano superati, modificare la clausola `if` all'inizio del metodo:</span><span class="sxs-lookup"><span data-stu-id="054e2-158">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="054e2-159">Continuare a eseguire l'iterazione aggiungendo altri test, altre teorie e altro codice nella libreria principale.</span><span class="sxs-lookup"><span data-stu-id="054e2-159">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="054e2-160">Si ottiene la [versione completa dei test](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb) e l'[implementazione completa della libreria](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService/PrimeService.vb).</span><span class="sxs-lookup"><span data-stu-id="054e2-160">You have the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="054e2-161">È stata compilata una piccola libreria e un set di unit test per tale libreria.</span><span class="sxs-lookup"><span data-stu-id="054e2-161">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="054e2-162">La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="054e2-162">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="054e2-163">La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="054e2-163">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

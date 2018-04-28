---
title: Creazione di una soluzione .NET Core completa in Windows tramite Visual Studio 2017
description: Informazioni su come creare una soluzione .NET Core completa in Visual Studio 2017 in Windows.
author: bleroy
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 8e37eb578f9c4ac63fbc120e6227098ea69d169d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="building-a-complete-net-core-solution-on-windows-using-visual-studio-2017"></a><span data-ttu-id="13752-103">Creazione di una soluzione .NET Core completa in Windows tramite Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="13752-103">Building a complete .NET Core solution on Windows, using Visual Studio 2017</span></span>

<span data-ttu-id="13752-104">Visual Studio 2017 offre un ambiente completo per lo sviluppo di applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="13752-104">Visual Studio 2017 provides a full-featured development environment for developing .NET Core applications.</span></span> <span data-ttu-id="13752-105">Questo documento descrive le procedure necessarie per creare una soluzione .NET Core tipica contenente librerie riutilizzabili, funzionalità di test e librerie di terze parti.</span><span class="sxs-lookup"><span data-stu-id="13752-105">The procedures in this document describe the steps necessary to build a typical .NET Core solution that includes reusable libraries, testing, and using third-party libraries.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="13752-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="13752-106">Prerequisites</span></span>

<span data-ttu-id="13752-107">Seguire le istruzioni nella [pagina dei prerequisiti](../windows-prerequisites.md) per aggiornare l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="13752-107">Follow the instructions on [our prerequisites page](../windows-prerequisites.md) to update your environment.</span></span>

## <a name="a-solution-using-only-net-core-projects"></a><span data-ttu-id="13752-108">Una soluzione basata solo su progetti .NET Core</span><span class="sxs-lookup"><span data-stu-id="13752-108">A solution using only .NET Core projects</span></span>

### <a name="writing-the-library"></a><span data-ttu-id="13752-109">Scrittura della libreria</span><span class="sxs-lookup"><span data-stu-id="13752-109">Writing the library</span></span>

1. <span data-ttu-id="13752-110">In Visual Studio scegli **File**, **Nuovo**, **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="13752-110">In Visual Studio, choose **File**, **New**, **Project**.</span></span> <span data-ttu-id="13752-111">Nella finestra di dialogo **Nuovo progetto** espandere il nodo **Visual C#**, scegliere il nodo **.NET Standard** e quindi **Libreria di classi (.NET Standard)**.</span><span class="sxs-lookup"><span data-stu-id="13752-111">In the **New Project** dialog, expand the **Visual C#** node and choose the **.NET Standard** node, and then choose **Class Library (.NET Standard)**.</span></span> 

2. <span data-ttu-id="13752-112">Assegnare il nome "Library" al progetto e il nome "Golden" alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="13752-112">Name the project "Library" and the solution "Golden".</span></span> <span data-ttu-id="13752-113">Lasciare selezionata l'opzione **Crea directory per soluzione**.</span><span class="sxs-lookup"><span data-stu-id="13752-113">Leave **Create directory for solution** checked.</span></span> <span data-ttu-id="13752-114">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="13752-114">Click **OK**.</span></span>

3. <span data-ttu-id="13752-115">In Esplora soluzioni aprire il menu di scelta rapida per il nodo **Dipendenze** e scegliere **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="13752-115">In Solution Explorer, open the context menu for the **Dependencies** node and choose **Manage NuGet Packages**.</span></span>

4. <span data-ttu-id="13752-116">Scegliere "nuget.org" come **Origine pacchetto** e fare clic sulla scheda **Sfoglia**. Cercare e selezionare **Newtonsoft.Json**.</span><span class="sxs-lookup"><span data-stu-id="13752-116">Choose "nuget.org" as the **Package source**, and choose the **Browse** tab. Browse for **Newtonsoft.Json**.</span></span> <span data-ttu-id="13752-117">Fare clic su **Installa** e accettare i termini del Contratto di Licenza Microsoft.</span><span class="sxs-lookup"><span data-stu-id="13752-117">Click **Install**, and accept the license agreement.</span></span> <span data-ttu-id="13752-118">Il pacchetto è ora visibile in **Dipendenze/NuGet** e viene ripristinato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="13752-118">The package should now appear under **Dependencies/NuGet** and be automatically restored.</span></span>

5. <span data-ttu-id="13752-119">Rinominare il file `Class1.cs` in `Thing.cs`.</span><span class="sxs-lookup"><span data-stu-id="13752-119">Rename the `Class1.cs` file to `Thing.cs`.</span></span> <span data-ttu-id="13752-120">Accettare il nuovo nome della classe.</span><span class="sxs-lookup"><span data-stu-id="13752-120">Accept the rename of the class.</span></span> <span data-ttu-id="13752-121">Aggiungere un metodo: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`</span><span class="sxs-lookup"><span data-stu-id="13752-121">Add a method: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`</span></span>

7. <span data-ttu-id="13752-122">Scegliere **Compila soluzione** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="13752-122">On the **Build** menu, choose **Build Solution**.</span></span>

   <span data-ttu-id="13752-123">La soluzione dovrebbe essere compilata senza errori.</span><span class="sxs-lookup"><span data-stu-id="13752-123">The solution should build without error.</span></span>

### <a name="writing-the-test-project"></a><span data-ttu-id="13752-124">Scrittura del progetto di test</span><span class="sxs-lookup"><span data-stu-id="13752-124">Writing the test project</span></span>

1. <span data-ttu-id="13752-125">In Esplora soluzioni aprire il menu di scelta rapida per il nodo **Soluzione** e scegliere **Aggiungi**, **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="13752-125">In Solution Explorer, open the context menu for the **Solution** node and choose **Add**, **New Project**.</span></span> <span data-ttu-id="13752-126">Nell'area **Visual C# / .NET Core** della finestra di dialogo **Nuovo progetto** scegliere **Progetto unit test (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="13752-126">In the **New Project** dialog, under **Visual C# / .NET Core**, choose **Unit Test Project (.NET Core)**.</span></span> <span data-ttu-id="13752-127">Assegnare il nome "TestLibrary" al progetto e fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="13752-127">Name it "TestLibrary" and click OK.</span></span> 

2. <span data-ttu-id="13752-128">Nel progetto **TestLibrary** aprire il menu di scelta rapida per il nodo **Dipendenze** e scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="13752-128">In the **TestLibrary** project, open the context menu for the **Dependencies** node and choose **Add Reference**.</span></span> <span data-ttu-id="13752-129">Fare clic su **Progetti**, selezionare il progetto Libreria e scegliere OK.</span><span class="sxs-lookup"><span data-stu-id="13752-129">Click **Projects**, then check the Library project and click OK.</span></span> <span data-ttu-id="13752-130">Verrà aggiunto un riferimento alla libreria dal progetto di test.</span><span class="sxs-lookup"><span data-stu-id="13752-130">This adds a reference to your library from the test project.</span></span>

3. <span data-ttu-id="13752-131">Rinominare il file `UnitTest1.cs` in `LibraryTests.cs` e accettare la ridenominazione della classe.</span><span class="sxs-lookup"><span data-stu-id="13752-131">Rename the `UnitTest1.cs` file to `LibraryTests.cs` and accept the class rename.</span></span> <span data-ttu-id="13752-132">Aggiungere `using Library;` all'inizio del file e sostituire il metodo `TestMethod1` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="13752-132">Add `using Library;` to the top of the file, and replace the `TestMethod1` method with the following code:</span></span>
    ```csharp
    [TestMethod]
    public void ThingGetsObjectValFromNumber()
    {
        Assert.AreEqual(42, new Thing().Get(42));
    }
    ```

   <span data-ttu-id="13752-133">Sarà ora possibile compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="13752-133">You should now be able to build the solution.</span></span> 
   
4. <span data-ttu-id="13752-134">Dal menu **Test** scegliere **Windows**, **Esplora Test** per visualizzare la finestra Esplora test nella propria area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="13752-134">On the **Test** menu, choose **Windows**, **Test Explorer** in order to get the test explorer window into your workspace.</span></span> <span data-ttu-id="13752-135">Dopo alcuni secondi in Esplora test viene visualizzato il test `ThingGetsObjectValFromNumber`.</span><span class="sxs-lookup"><span data-stu-id="13752-135">After a few seconds, the `ThingGetsObjectValFromNumber` test should appear in the test explorer.</span></span> <span data-ttu-id="13752-136">Scegliere **Esegui tutto**.</span><span class="sxs-lookup"><span data-stu-id="13752-136">Choose **Run All**.</span></span>
   
   <span data-ttu-id="13752-137">Il test dovrebbe essere superato.</span><span class="sxs-lookup"><span data-stu-id="13752-137">The test should pass.</span></span>

### <a name="writing-the-console-app"></a><span data-ttu-id="13752-138">Scrittura dell'applicazione console</span><span class="sxs-lookup"><span data-stu-id="13752-138">Writing the console app</span></span>

1. <span data-ttu-id="13752-139">In Esplora soluzioni aprire il menu di scelta rapida relativo alla soluzione e aggiungere un nuovo progetto **Applicazione console (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="13752-139">In Solution Explorer, open the context menu for the solution, and add a new **Console App (.NET Core)** project.</span></span> <span data-ttu-id="13752-140">Assegnare il nome "App".</span><span class="sxs-lookup"><span data-stu-id="13752-140">Name it "App".</span></span>

2. <span data-ttu-id="13752-141">Nel progetto **App** aprire il menu di scelta rapida per il nodo **Dipendenze** e scegliere **Aggiungi**, **Riferimento**.</span><span class="sxs-lookup"><span data-stu-id="13752-141">In the **App** project, open the context menu for the **Dependencies** node and choose **Add**,  **Reference**.</span></span> 

3. <span data-ttu-id="13752-142">Nella finestra di dialogo **Gestione riferimenti** selezionare **Library** sotto il nodo **Progetti**, **Soluzione** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="13752-142">In the **Reference Manager** dialog, check **Library** under the **Projects**, **Solution** node, and then click **OK**</span></span>

6. <span data-ttu-id="13752-143">Aprire il menu di scelta rapida per il nodo **App** e scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="13752-143">Open the context menu for the **App** node and choose **Set as StartUp Project**.</span></span> <span data-ttu-id="13752-144">In questo modo sarà possibile avviare l'applicazione console premendo F5 o CTRL + F5.</span><span class="sxs-lookup"><span data-stu-id="13752-144">This ensures that hitting F5 or CTRL+F5 will start the console app.</span></span>

7. <span data-ttu-id="13752-145">Aprire il file `Program.cs`, aggiungere una direttiva `using Library;` all'inizio del file e quindi aggiungere `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` al metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="13752-145">Open the `Program.cs` file, add a `using Library;` directive to the top of the file, and then add `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` to the `Main` method.</span></span>

8. <span data-ttu-id="13752-146">Impostare un punto di interruzione dopo la riga appena aggiunta.</span><span class="sxs-lookup"><span data-stu-id="13752-146">Set a breakpoint after the line that you just added.</span></span>

9. <span data-ttu-id="13752-147">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="13752-147">Press F5 to run the application..</span></span>

   <span data-ttu-id="13752-148">L'applicazione dovrebbe essere compilata senza errori e dovrebbe raggiungere il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="13752-148">The application should build without error, and should hit the breakpoint.</span></span> <span data-ttu-id="13752-149">Dovrebbe inoltre essere possibile verificare che l'output dell'applicazione sia "The answer is 42".</span><span class="sxs-lookup"><span data-stu-id="13752-149">You should also be able to check that the application output "The answer is 42.".</span></span>

---
title: Creazione di una soluzione .NET Core completa in Windows tramite Visual Studio 2017
description: Informazioni su come creare una soluzione .NET Core completa in Visual Studio 2017 in Windows.
keywords: .NET, .NET Core
author: bleroy
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ba7e082c-a7c8-431e-a342-f67734b660f6
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6b164198f5fbbae5ebc6164fc281dd7de8172b70
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="building-a-complete-net-core-solution-on-windows-using-visual-studio-2017"></a><span data-ttu-id="fceb6-104">Creazione di una soluzione .NET Core completa in Windows tramite Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="fceb6-104">Building a complete .NET Core solution on Windows, using Visual Studio 2017</span></span>

<span data-ttu-id="fceb6-105">Visual Studio 2017 offre un ambiente completo per lo sviluppo di applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fceb6-105">Visual Studio 2017 provides a full-featured development environment for developing .NET Core applications.</span></span> <span data-ttu-id="fceb6-106">Questo documento descrive le procedure necessarie per creare una soluzione .NET Core tipica contenente librerie riutilizzabili, funzionalità di test e librerie di terze parti.</span><span class="sxs-lookup"><span data-stu-id="fceb6-106">The procedures in this document describe the steps necessary to build a typical .NET Core solution that includes reusable libraries, testing, and using third-party libraries.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="fceb6-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="fceb6-107">Prerequisites</span></span>

<span data-ttu-id="fceb6-108">Seguire le istruzioni nella [pagina dei prerequisiti](../windows-prerequisites.md) per aggiornare l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="fceb6-108">Follow the instructions on [our prerequisites page](../windows-prerequisites.md) to update your environment.</span></span>

## <a name="a-solution-using-only-net-core-projects"></a><span data-ttu-id="fceb6-109">Una soluzione basata solo su progetti .NET Core</span><span class="sxs-lookup"><span data-stu-id="fceb6-109">A solution using only .NET Core projects</span></span>

### <a name="writing-the-library"></a><span data-ttu-id="fceb6-110">Scrittura della libreria</span><span class="sxs-lookup"><span data-stu-id="fceb6-110">Writing the library</span></span>

1. <span data-ttu-id="fceb6-111">In Visual Studio scegliere **File**, **Nuovo**, **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="fceb6-111">In Visual Studio, choose **File**, **New**, **Project**.</span></span> <span data-ttu-id="fceb6-112">Nella finestra di dialogo **Nuovo progetto** espandere il nodo **Visual C#**, scegliere il nodo **.NET Core** e quindi **Libreria di classi (.NET Standard)**.</span><span class="sxs-lookup"><span data-stu-id="fceb6-112">In the **New Project** dialog, expand the **Visual C#** node and choose the **.NET Core** node, and then choose **Class Library (.NET Standard)**.</span></span> 

2. <span data-ttu-id="fceb6-113">Assegnare il nome "Library" al progetto e il nome "Golden" alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="fceb6-113">Name the project "Library" and the solution "Golden".</span></span> <span data-ttu-id="fceb6-114">Lasciare selezionata l'opzione **Crea directory per soluzione**.</span><span class="sxs-lookup"><span data-stu-id="fceb6-114">Leave **Create directory for solution** checked.</span></span> <span data-ttu-id="fceb6-115">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fceb6-115">Click **OK**.</span></span>

3. <span data-ttu-id="fceb6-116">In Esplora soluzioni aprire il menu di scelta rapida per il nodo **Dipendenze** e scegliere **Gestisci pacchetti NuGet**.</span><span class="sxs-lookup"><span data-stu-id="fceb6-116">In Solution Explorer, open the context menu for the **Dependencies** node and choose **Manage NuGet Packages**.</span></span>

4. <span data-ttu-id="fceb6-117">Scegliere "nuget.org" come **Origine pacchetto** e fare clic sulla scheda **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="fceb6-117">Choose "nuget.org" as the **Package source**, and choose the **Browse** tab.</span></span> <span data-ttu-id="fceb6-118">Cercare e selezionare **Newtonsoft.Json**.</span><span class="sxs-lookup"><span data-stu-id="fceb6-118">Browse for **Newtonsoft.Json**.</span></span> <span data-ttu-id="fceb6-119">Fare clic su **Installa** e accettare i termini del Contratto di Licenza Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fceb6-119">Click **Install**, and accept the license agreement.</span></span> <span data-ttu-id="fceb6-120">Il pacchetto è ora visibile in **Dipendenze/NuGet** e viene ripristinato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fceb6-120">The package should now appear under **Dependencies/NuGet** and be automatically restored.</span></span>

5. <span data-ttu-id="fceb6-121">Rinominare il file `Class1.cs` in `Thing.cs`.</span><span class="sxs-lookup"><span data-stu-id="fceb6-121">Rename the `Class1.cs` file to `Thing.cs`.</span></span> <span data-ttu-id="fceb6-122">Accettare il nuovo nome della classe.</span><span class="sxs-lookup"><span data-stu-id="fceb6-122">Accept the rename of the class.</span></span> <span data-ttu-id="fceb6-123">Aggiungere un metodo: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`</span><span class="sxs-lookup"><span data-stu-id="fceb6-123">Add a method: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`</span></span>

7. <span data-ttu-id="fceb6-124">Scegliere **Compila soluzione** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="fceb6-124">On the **Build** menu, choose **Build Solution**.</span></span>

   <span data-ttu-id="fceb6-125">La soluzione dovrebbe essere compilata senza errori.</span><span class="sxs-lookup"><span data-stu-id="fceb6-125">The solution should build without error.</span></span>

### <a name="writing-the-test-project"></a><span data-ttu-id="fceb6-126">Scrittura del progetto di test</span><span class="sxs-lookup"><span data-stu-id="fceb6-126">Writing the test project</span></span>

1. <span data-ttu-id="fceb6-127">In Esplora soluzioni aprire il menu di scelta rapida per il nodo **Soluzione** e scegliere **Aggiungi**, **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="fceb6-127">In Solution Explorer, open the context menu for the **Solution** node and choose **Add**, **New Project**.</span></span> <span data-ttu-id="fceb6-128">Nell'area **Visual C# / .NET Core** della finestra di dialogo **Nuovo progetto** scegliere **Progetto unit test (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="fceb6-128">In the **New Project** dialog, under **Visual C# / .NET Core**, choose **Unit Test Project (.NET Core)**.</span></span> <span data-ttu-id="fceb6-129">Assegnare il nome "TestLibrary" al progetto e fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fceb6-129">Name it "TestLibrary" and click OK.</span></span> 

2. <span data-ttu-id="fceb6-130">Nel progetto **TestLibrary** aprire il menu di scelta rapida per il nodo **Dipendenze** e scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="fceb6-130">In the **TestLibrary** project, open the context menu for the **Dependencies** node and choose **Add Reference**.</span></span> <span data-ttu-id="fceb6-131">Fare clic su **Progetti**, selezionare il progetto Libreria e scegliere OK.</span><span class="sxs-lookup"><span data-stu-id="fceb6-131">Click **Projects**, then check the Library project and click OK.</span></span> <span data-ttu-id="fceb6-132">Verrà aggiunto un riferimento alla libreria dal progetto di test.</span><span class="sxs-lookup"><span data-stu-id="fceb6-132">This adds a reference to your library from the test project.</span></span>

3. <span data-ttu-id="fceb6-133">Rinominare il file `UnitTest1.cs` in `LibraryTests.cs` e accettare la ridenominazione della classe.</span><span class="sxs-lookup"><span data-stu-id="fceb6-133">Rename the `UnitTest1.cs` file to `LibraryTests.cs` and accept the class rename.</span></span> <span data-ttu-id="fceb6-134">Aggiungere `using Library;` all'inizio del file e sostituire il metodo `TestMethod1` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fceb6-134">Add `using Library;` to the top of the file, and replace the `TestMethod1` method with the following code:</span></span>
    ```csharp
    [TestMethod]
    public void ThingGetsObjectValFromNumber()
    {
        Assert.AreEqual(42, new Thing().Get(42));
    }
    ```

   <span data-ttu-id="fceb6-135">Sarà ora possibile compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="fceb6-135">You should now be able to build the solution.</span></span> 
   
4. <span data-ttu-id="fceb6-136">Dal menu **Test** scegliere **Windows**, **Esplora Test** per visualizzare la finestra Esplora test nella propria area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fceb6-136">On the **Test** menu, choose **Windows**, **Test Explorer** in order to get the test explorer window into your workspace.</span></span> <span data-ttu-id="fceb6-137">Dopo alcuni secondi in Esplora test viene visualizzato il test `ThingGetsObjectValFromNumber`.</span><span class="sxs-lookup"><span data-stu-id="fceb6-137">After a few seconds, the `ThingGetsObjectValFromNumber` test should appear in the test explorer.</span></span> <span data-ttu-id="fceb6-138">Scegliere **Esegui tutto**.</span><span class="sxs-lookup"><span data-stu-id="fceb6-138">Choose **Run All**.</span></span>
   
   <span data-ttu-id="fceb6-139">Il test dovrebbe essere superato.</span><span class="sxs-lookup"><span data-stu-id="fceb6-139">The test should pass.</span></span>

### <a name="writing-the-console-app"></a><span data-ttu-id="fceb6-140">Scrittura dell'applicazione console</span><span class="sxs-lookup"><span data-stu-id="fceb6-140">Writing the console app</span></span>

1. <span data-ttu-id="fceb6-141">In Esplora soluzioni aprire il menu di scelta rapida relativo alla soluzione e aggiungere un nuovo progetto **Applicazione console (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="fceb6-141">In Solution Explorer, open the context menu for the solution, and add a new **Console App (.NET Core)** project.</span></span> <span data-ttu-id="fceb6-142">Assegnare il nome "App".</span><span class="sxs-lookup"><span data-stu-id="fceb6-142">Name it "App".</span></span>

2. <span data-ttu-id="fceb6-143">Nel progetto **App** aprire il menu di scelta rapida per il nodo **Dipendenze** e scegliere **Aggiungi**, **Riferimento**.</span><span class="sxs-lookup"><span data-stu-id="fceb6-143">In the **App** project, open the context menu for the **Dependencies** node and choose **Add**,  **Reference**.</span></span> 

3. <span data-ttu-id="fceb6-144">Nella finestra di dialogo **Gestione riferimenti** selezionare **Library** sotto il nodo **Progetti**, **Soluzione** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fceb6-144">In the **Reference Manager** dialog, check **Library** under the **Projects**, **Solution** node, and then click **OK**</span></span>

6. <span data-ttu-id="fceb6-145">Aprire il menu di scelta rapida per il nodo **App** e scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="fceb6-145">Open the context menu for the **App** node and choose **Set as StartUp Project**.</span></span> <span data-ttu-id="fceb6-146">In questo modo sarà possibile avviare l'applicazione console premendo F5 o CTRL + F5.</span><span class="sxs-lookup"><span data-stu-id="fceb6-146">This ensures that hitting F5 or CTRL+F5 will start the console app.</span></span>

7. <span data-ttu-id="fceb6-147">Aprire il file `Program.cs`, aggiungere una direttiva `using Library;` all'inizio del file e quindi aggiungere `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` al metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="fceb6-147">Open the `Program.cs` file, add a `using Library;` directive to the top of the file, and then add `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` to the `Main` method.</span></span>

8. <span data-ttu-id="fceb6-148">Impostare un punto di interruzione dopo la riga appena aggiunta.</span><span class="sxs-lookup"><span data-stu-id="fceb6-148">Set a breakpoint after the line that you just added.</span></span>

9. <span data-ttu-id="fceb6-149">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fceb6-149">Press F5 to run the application..</span></span>

   <span data-ttu-id="fceb6-150">L'applicazione dovrebbe essere compilata senza errori e dovrebbe raggiungere il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="fceb6-150">The application should build without error, and should hit the breakpoint.</span></span> <span data-ttu-id="fceb6-151">Dovrebbe inoltre essere possibile verificare che l'output dell'applicazione sia "The answer is 42".</span><span class="sxs-lookup"><span data-stu-id="fceb6-151">You should also be able to check that the application output "The answer is 42.".</span></span>


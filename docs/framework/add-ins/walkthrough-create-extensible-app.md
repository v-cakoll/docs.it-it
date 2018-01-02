---
title: 'Procedura dettagliata: creazione di un''applicazione estendibile'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [.NET Framework], add-in pipeline
- host-side adapters for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], creating
- add-in-side adapter [.NET Framework]
- contracts for add-in pipelines [.NET Framework]
ms.assetid: 694a33c5-a040-450d-aed5-ac49fc88ce61
caps.latest.revision: "32"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ac4b6fc2ae36d848306178f281cceeeb0654ec03
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-an-extensible-application"></a><span data-ttu-id="dfb0e-102">Procedura dettagliata: creazione di un'applicazione estendibile</span><span class="sxs-lookup"><span data-stu-id="dfb0e-102">Walkthrough: Creating an Extensible Application</span></span>
<span data-ttu-id="dfb0e-103">Questa procedura dettagliata viene descritto come creare una pipeline per un componente aggiuntivo che esegue funzioni calcolatrice semplice.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-103">This walkthrough describes how to create a pipeline for an add-in that performs simple calculator functions.</span></span> <span data-ttu-id="dfb0e-104">Viene illustrato uno scenario reale; invece, vengono illustrate le funzionalità di base di una pipeline e un componente aggiuntivo può come fornire servizi per un host.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-104">It does not demonstrate a real-world scenario; rather, it demonstrates the basic functionality of a pipeline and how an add-in can provide services for a host.</span></span>  
  
 <span data-ttu-id="dfb0e-105">Questa procedura dettagliata vengono descritte le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfb0e-105">This walkthrough describes the following tasks:</span></span>  
  
-   <span data-ttu-id="dfb0e-106">Creazione di una soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-106">Creating a Visual Studio solution.</span></span>  
  
-   <span data-ttu-id="dfb0e-107">Creazione della struttura di directory della pipeline.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-107">Creating the pipeline directory structure.</span></span>  
  
-   <span data-ttu-id="dfb0e-108">Creazione del contratto e viste.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-108">Creating the contract and views.</span></span>  
  
-   <span data-ttu-id="dfb0e-109">Creazione dell'adattatore sul lato del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-109">Creating the add-in-side adapter.</span></span>  
  
-   <span data-ttu-id="dfb0e-110">Creazione dell'adattatore sul lato host.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-110">Creating the host-side adapter.</span></span>  
  
-   <span data-ttu-id="dfb0e-111">Creazione dell'host.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-111">Creating the host.</span></span>  
  
-   <span data-ttu-id="dfb0e-112">Creazione del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-112">Creating the add-in.</span></span>  
  
-   <span data-ttu-id="dfb0e-113">Distribuzione della pipeline.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-113">Deploying the pipeline.</span></span>  
  
-   <span data-ttu-id="dfb0e-114">Esecuzione dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-114">Running the host application.</span></span>  
  
 <span data-ttu-id="dfb0e-115">Questa pipeline passa solo tipi serializzabili (<xref:System.Double> e <xref:System.String>), tra l'host e il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-115">This pipeline passes only serializable types (<xref:System.Double> and <xref:System.String>), between the host and the add-in.</span></span> <span data-ttu-id="dfb0e-116">Per un esempio che illustra come passare raccolte di tipi di dati complessi, vedere [procedura dettagliata: passaggio di raccolte tra host e Add-Ins](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5).</span><span class="sxs-lookup"><span data-stu-id="dfb0e-116">For an example that shows how to pass collections of complex data types, see [Walkthrough: Passing Collections Between Hosts and Add-Ins](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5).</span></span>  
  
 <span data-ttu-id="dfb0e-117">Il contratto per la pipeline definisce un modello a oggetti di quattro operazioni aritmetiche: aggiungere, sottrarre, moltiplicare e dividere.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-117">The contract for this pipeline defines an object model of four arithmetic operations: add, subtract, multiply, and divide.</span></span> <span data-ttu-id="dfb0e-118">L'host fornisce il componente aggiuntivo con un'equazione per calcolare, ad esempio 2 + 2 e il componente aggiuntivo restituisce il risultato all'host.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-118">The host provides the add-in with an equation to calculate, such as 2 + 2, and the add-in returns the result to the host.</span></span>  
  
 <span data-ttu-id="dfb0e-119">Versione 2 del componente aggiuntivo calcolatrice fornisce maggiori possibilità di calcolo e viene illustrato il controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-119">Version 2 of the calculator add-in provides more calculating possibilities and demonstrates versioning.</span></span> <span data-ttu-id="dfb0e-120">Viene descritto in [procedura dettagliata: abilitare la compatibilità come le modifiche di Host](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span><span class="sxs-lookup"><span data-stu-id="dfb0e-120">It is described in [Walkthrough: Enabling Backward Compatibility as Your Host Changes](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dfb0e-121">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="dfb0e-121">Prerequisites</span></span>  
 <span data-ttu-id="dfb0e-122">Per completare questa procedura dettagliata, sono necessari i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="dfb0e-122">You need the following to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]<span data-ttu-id="dfb0e-123">.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-123">.</span></span>  
  
## <a name="creating-a-visual-studio-solution"></a><span data-ttu-id="dfb0e-124">Creazione di una soluzione di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dfb0e-124">Creating a Visual Studio Solution</span></span>  
 <span data-ttu-id="dfb0e-125">Utilizzare una soluzione di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] per contenere i progetti dei segmenti di pipeline.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-125">Use a solution in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] to contain the projects of your pipeline segments.</span></span>  
  
#### <a name="to-create-the-pipeline-solution"></a><span data-ttu-id="dfb0e-126">Per creare la soluzione di pipeline</span><span class="sxs-lookup"><span data-stu-id="dfb0e-126">To create the pipeline solution</span></span>  
  
1.  <span data-ttu-id="dfb0e-127">In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], creare un nuovo progetto denominato `Calc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-127">In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], create a new project named `Calc1Contract`.</span></span> <span data-ttu-id="dfb0e-128">Come base il **libreria di classi** modello.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-128">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="dfb0e-129">Denominare la soluzione `CalculatorV1`.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-129">Name the solution `CalculatorV1`.</span></span>  
  
## <a name="creating-the-pipeline-directory-structure"></a><span data-ttu-id="dfb0e-130">Creazione della struttura di Directory della Pipeline</span><span class="sxs-lookup"><span data-stu-id="dfb0e-130">Creating the Pipeline Directory Structure</span></span>  
 <span data-ttu-id="dfb0e-131">Il modello di componente aggiuntivo richiede gli assembly dei segmenti della pipeline si trovino in una struttura di directory specificato.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-131">The add-in model requires the pipeline segment assemblies to be placed in a specified directory structure.</span></span> <span data-ttu-id="dfb0e-132">Per ulteriori informazioni sulla struttura della pipeline, vedere [requisiti di sviluppo Pipeline](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="dfb0e-132">For more information about the pipeline structure, see [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
#### <a name="to-create-the-pipeline-directory-structure"></a><span data-ttu-id="dfb0e-133">Per creare la struttura di directory della pipeline</span><span class="sxs-lookup"><span data-stu-id="dfb0e-133">To create the pipeline directory structure</span></span>  
  
1.  <span data-ttu-id="dfb0e-134">Creare una cartella dell'applicazione in un punto qualsiasi nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-134">Create an application folder anywhere on your computer.</span></span>  
  
2.  <span data-ttu-id="dfb0e-135">In tale cartella, creare la struttura seguente:</span><span class="sxs-lookup"><span data-stu-id="dfb0e-135">In that folder, create the following structure:</span></span>  
  
    ```  
    Pipeline  
      AddIns  
        CalcV1  
        CalcV2  
      AddInSideAdapters  
      AddInViews  
      Contracts  
      HostSideAdapters  
    ```  
  
     <span data-ttu-id="dfb0e-136">Non è necessario inserire la struttura di cartelle della pipeline nella cartella dell'applicazione; viene eseguita qui solo per comodità.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-136">It is not necessary to put the pipeline folder structure in your application folder; it is done here only for convenience.</span></span> <span data-ttu-id="dfb0e-137">Nel passaggio appropriato, la procedura dettagliata viene illustrato come modificare il codice se la struttura di cartelle della pipeline si trova in un percorso diverso.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-137">At the appropriate step, the walkthrough explains how to change the code if the pipeline folder structure is in a different location.</span></span> <span data-ttu-id="dfb0e-138">Vedere la sezione requisiti della pipeline directory [requisiti di sviluppo Pipeline](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="dfb0e-138">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dfb0e-139">Il `CalcV2` cartella non viene usata in questa procedura dettagliata, è un segnaposto per [procedura dettagliata: abilitare la compatibilità come le modifiche di Host](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span><span class="sxs-lookup"><span data-stu-id="dfb0e-139">The `CalcV2` folder is not used in this walkthrough; it is a placeholder for [Walkthrough: Enabling Backward Compatibility as Your Host Changes](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="creating-the-contract-and-views"></a><span data-ttu-id="dfb0e-140">Creazione del contratto e viste</span><span class="sxs-lookup"><span data-stu-id="dfb0e-140">Creating the Contract and Views</span></span>  
 <span data-ttu-id="dfb0e-141">Definisce il segmento dei contratti per la pipeline di `ICalc1Contract` interfaccia che definisce i quattro metodi: `add`, `subtract`, `multiply`, e `divide`.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-141">The contract segment for this pipeline defines the `ICalc1Contract` interface, which defines four methods: `add`, `subtract`, `multiply`, and `divide`.</span></span>  
  
#### <a name="to-create-the-contract"></a><span data-ttu-id="dfb0e-142">Per creare il contratto</span><span class="sxs-lookup"><span data-stu-id="dfb0e-142">To create the contract</span></span>  
  
1.  <span data-ttu-id="dfb0e-143">Nella soluzione di Visual Studio denominata `CalculatorV1`, aprire il `Calc1Contract` progetto.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-143">In the Visual Studio solution named `CalculatorV1`, open the `Calc1Contract` project.</span></span>  
  
2.  <span data-ttu-id="dfb0e-144">In **Esplora**, aggiungere riferimenti agli assembly riportati di seguito per il `Calc1Contract` progetto:</span><span class="sxs-lookup"><span data-stu-id="dfb0e-144">In **Solution Explorer**, add references to the following assemblies to the `Calc1Contract` project:</span></span>  
  
     <span data-ttu-id="dfb0e-145">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="dfb0e-145">System.AddIn.Contract.dll</span></span>  
  
     <span data-ttu-id="dfb0e-146">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="dfb0e-146">System.AddIn.dll</span></span>  
  
3.  <span data-ttu-id="dfb0e-147">In **Esplora**, escludere la classe predefinita che viene aggiunto al nuovo **libreria di classi** progetti.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-147">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects.</span></span>  
  
4.  <span data-ttu-id="dfb0e-148">In **Esplora**, aggiungere un nuovo elemento al progetto, tramite il **interfaccia** modello.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-148">In **Solution Explorer**, add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="dfb0e-149">Nel **Aggiungi nuovo elemento** nella finestra di dialogo Nome l'interfaccia `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-149">In the **Add New Item** dialog box, name the interface `ICalc1Contract`.</span></span>  
  
5.  <span data-ttu-id="dfb0e-150">Nel file di interfaccia, aggiungere riferimenti a spazi dei nomi per <xref:System.AddIn.Contract> e <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-150">In the interface file, add namespace references to <xref:System.AddIn.Contract> and <xref:System.AddIn.Pipeline>.</span></span>  
  
6.  <span data-ttu-id="dfb0e-151">Utilizzare il codice seguente per completare questo segmento del contratto.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-151">Use the following code to complete this contract segment.</span></span> <span data-ttu-id="dfb0e-152">Si noti che questa interfaccia deve avere il <xref:System.AddIn.Pipeline.AddInContractAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-152">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInContractAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  <span data-ttu-id="dfb0e-153">Facoltativamente, compilare la soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-153">Optionally, build the Visual Studio solution.</span></span> <span data-ttu-id="dfb0e-154">Impossibile eseguire la soluzione fino a quando la procedura finale, ma la compilazione al termine di ogni procedura garantisce che ogni progetto sia correggere.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-154">The solution cannot be run until the final procedure, but building it after each procedure ensures that each project is correct.</span></span>  
  
 <span data-ttu-id="dfb0e-155">Poiché la vista del componente aggiuntivo e la visualizzazione host del componente aggiuntivo è in genere presentano lo stesso codice, in particolare nella prima versione di un componente aggiuntivo, è possibile creare facilmente le viste nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-155">Because the add-in view and the host view of the add-in usually have the same code, especially in the first version of an add-in, you can easily create the views at the same time.</span></span> <span data-ttu-id="dfb0e-156">Si differenziano per un solo fattore: la vista del componente aggiuntivo richiede il <xref:System.AddIn.Pipeline.AddInBaseAttribute> attributo, mentre la visualizzazione host del componente aggiuntivo non richiede attributi.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-156">They differ by only one factor: the add-in view requires the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute, while the host view of the add-in does not require any attributes.</span></span>  
  
#### <a name="to-create-the-add-in-view"></a><span data-ttu-id="dfb0e-157">Per creare la vista del componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="dfb0e-157">To create the add-in view</span></span>  
  
1.  <span data-ttu-id="dfb0e-158">Aggiungere un nuovo progetto denominato `Calc1AddInView` per il `CalculatorV1` soluzione.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-158">Add a new project named `Calc1AddInView` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="dfb0e-159">Come base il **libreria di classi** modello.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-159">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="dfb0e-160">In **Esplora**, aggiungere un riferimento a System.AddIn.dll per il `Calc1AddInView` progetto.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-160">In **Solution Explorer**, add a reference to System.AddIn.dll to the `Calc1AddInView` project.</span></span>  
  
3.  <span data-ttu-id="dfb0e-161">In **Esplora**, escludere la classe predefinita che viene aggiunto al nuovo **libreria di classi** progetti e aggiungere un nuovo elemento al progetto, tramite il **interfaccia** modello.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-161">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="dfb0e-162">Nel **Aggiungi nuovo elemento** nella finestra di dialogo Nome l'interfaccia `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-162">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
4.  <span data-ttu-id="dfb0e-163">Nel file di interfaccia, aggiungere un riferimento dello spazio dei nomi <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-163">In the interface file, add a namespace reference to <xref:System.AddIn.Pipeline>.</span></span>  
  
5.  <span data-ttu-id="dfb0e-164">Utilizzare il codice seguente per completare questa vista del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-164">Use the following code to complete this add-in view.</span></span> <span data-ttu-id="dfb0e-165">Si noti che questa interfaccia deve avere il <xref:System.AddIn.Pipeline.AddInBaseAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-165">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  <span data-ttu-id="dfb0e-166">Facoltativamente, compilare la soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-166">Optionally, build the Visual Studio solution.</span></span>  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a><span data-ttu-id="dfb0e-167">Per creare la visualizzazione host del componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="dfb0e-167">To create the host view of the add-in</span></span>  
  
1.  <span data-ttu-id="dfb0e-168">Aggiungere un nuovo progetto denominato `Calc1HVA` per il `CalculatorV1` soluzione.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-168">Add a new project named `Calc1HVA` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="dfb0e-169">Come base il **libreria di classi** modello.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-169">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="dfb0e-170">In **Esplora**, escludere la classe predefinita che viene aggiunto al nuovo **libreria di classi** progetti e aggiungere un nuovo elemento al progetto, tramite il **interfaccia** modello.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-170">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="dfb0e-171">Nel **Aggiungi nuovo elemento** nella finestra di dialogo Nome l'interfaccia `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-171">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
3.  <span data-ttu-id="dfb0e-172">Nel file di interfaccia, utilizzare il codice seguente per completare la visualizzazione host del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-172">In the interface file, use the following code to complete the host view of the add-in.</span></span>  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  <span data-ttu-id="dfb0e-173">Facoltativamente, compilare la soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-173">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in-side-adapter"></a><span data-ttu-id="dfb0e-174">Creazione dell'adattatore sul lato componente-</span><span class="sxs-lookup"><span data-stu-id="dfb0e-174">Creating the Add-in-side Adapter</span></span>  
 <span data-ttu-id="dfb0e-175">Questo adattatore sul lato componente-è costituito da una scheda visualizzazione-contratto.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-175">This add-in-side adapter consists of one view-to-contract adapter.</span></span> <span data-ttu-id="dfb0e-176">Questo segmento di pipeline converte i tipi della vista del componente aggiuntivo per il contratto.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-176">This pipeline segment converts the types from the add-in view to the contract.</span></span>  
  
 <span data-ttu-id="dfb0e-177">In questa pipeline, il componente aggiuntivo fornisce un servizio all'host e i tipi di flusso dal componente aggiuntivo per l'host.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-177">In this pipeline, the add-in provides a service to the host, and the types flow from the add-in to the host.</span></span> <span data-ttu-id="dfb0e-178">Poiché non vengono passati tipi dall'host per il componente aggiuntivo, non è necessario includere un adattatore contratto-visualizzazione sul lato componente della pipeline.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-178">Because no types flow from the host to the add-in, you do not have to include a contract-to-view adapter on the add-in side of this pipeline.</span></span>  
  
#### <a name="to-create-the-add-in-side-adapter"></a><span data-ttu-id="dfb0e-179">Per creare l'adattatore lato del componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="dfb0e-179">To create the add-in-side adapter</span></span>  
  
1.  <span data-ttu-id="dfb0e-180">Aggiungere un nuovo progetto denominato `Calc1AddInSideAdapter` per il `CalculatorV1` soluzione.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-180">Add a new project named `Calc1AddInSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="dfb0e-181">Come base il **libreria di classi** modello.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-181">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="dfb0e-182">In **Esplora**, aggiungere riferimenti agli assembly riportati di seguito per il `Calc1AddInSideAdapter` progetto:</span><span class="sxs-lookup"><span data-stu-id="dfb0e-182">In **Solution Explorer**, add references to the following assemblies to the `Calc1AddInSideAdapter` project:</span></span>  
  
     <span data-ttu-id="dfb0e-183">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="dfb0e-183">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="dfb0e-184">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="dfb0e-184">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="dfb0e-185">Aggiungere riferimenti ai progetti per i segmenti della pipeline adiacenti:</span><span class="sxs-lookup"><span data-stu-id="dfb0e-185">Add project references to the projects for the adjacent pipeline segments:</span></span>  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  <span data-ttu-id="dfb0e-186">Selezionare ogni riferimento a progetto e in **proprietà** impostare **Copia localmente** a **False**.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-186">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="dfb0e-187">In Visual Basic, usare il **riferimenti** scheda della **le proprietà del progetto** impostare **Copia localmente** per **False** per i due riferimenti al progetto.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-187">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="dfb0e-188">Rinominare la classe del progetto predefinita `CalculatorViewToContractAddInSideAdapter`.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-188">Rename the project's default class `CalculatorViewToContractAddInSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="dfb0e-189">Nel file di classe, aggiungere riferimenti a spazi dei nomi per <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-189">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="dfb0e-190">Nel file di classe, aggiungere riferimenti a spazi dei nomi per i segmenti adiacenti: `CalcAddInViews` e `CalculatorContracts`.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-190">In the class file, add namespace references for the adjacent segments: `CalcAddInViews` and `CalculatorContracts`.</span></span> <span data-ttu-id="dfb0e-191">(In Visual Basic, questi riferimenti dello spazio dei nomi sono `Calc1AddInView.CalcAddInViews` e `Calc1Contract.CalculatorContracts`, a meno che non è stato disattivato gli spazi dei nomi predefinito nei progetti di Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="dfb0e-191">(In Visual Basic, these namespace references are `Calc1AddInView.CalcAddInViews` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="dfb0e-192">Applicare il <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attributo il `CalculatorViewToContractAddInSideAdapter` (classe), per identificarla come adattatore sul lato del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-192">Apply the <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attribute to the `CalculatorViewToContractAddInSideAdapter` class, to identify it as the add-in-side adapter.</span></span>  
  
9. <span data-ttu-id="dfb0e-193">Rendere il `CalculatorViewToContractAddInSideAdapter` classe ereditare <xref:System.AddIn.Pipeline.ContractBase>, che fornisce un'implementazione predefinita del <xref:System.AddIn.Contract.IContract> di interfaccia e implementare l'interfaccia del contratto per la pipeline, `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-193">Make the `CalculatorViewToContractAddInSideAdapter` class inherit <xref:System.AddIn.Pipeline.ContractBase>, which provides a default implementation of the <xref:System.AddIn.Contract.IContract> interface, and implement the contract interface for the pipeline, `ICalc1Contract`.</span></span>  
  
10. <span data-ttu-id="dfb0e-194">Aggiungere un costruttore pubblico che accetta un `ICalculator`, memorizza nella cache in un campo privato e chiama il costruttore di classe di base.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-194">Add a public constructor that accepts an `ICalculator`, caches it in a private field, and calls the base class constructor.</span></span>  
  
11. <span data-ttu-id="dfb0e-195">Per implementare i membri di `ICalc1Contract`, è sufficiente chiamare i membri corrispondenti del `ICalculator` istanza che viene passato al costruttore e restituisce i risultati.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-195">To implement the members of `ICalc1Contract`, simply call the corresponding members of the `ICalculator` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="dfb0e-196">In questo modo la visualizzazione (`ICalculator`) al contratto (`ICalc1Contract`).</span><span class="sxs-lookup"><span data-stu-id="dfb0e-196">This adapts the view (`ICalculator`) to the contract (`ICalc1Contract`).</span></span>  
  
     <span data-ttu-id="dfb0e-197">Il codice seguente illustra l'adattatore sul lato componente-completato.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-197">The following code shows the completed add-in-side adapter.</span></span>  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. <span data-ttu-id="dfb0e-198">Facoltativamente, compilare la soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-198">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host-side-adapter"></a><span data-ttu-id="dfb0e-199">Creazione dell'adattatore sul lato Host</span><span class="sxs-lookup"><span data-stu-id="dfb0e-199">Creating the Host-side Adapter</span></span>  
 <span data-ttu-id="dfb0e-200">Questo adattatore sul lato host è costituito da una scheda di contratto per visualizzare.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-200">This host-side adapter consists of one contract-to-view adapter.</span></span> <span data-ttu-id="dfb0e-201">Questo segmento adatta il contratto per la visualizzazione host del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-201">This segment adapts the contract to the host view of the add-in.</span></span>  
  
 <span data-ttu-id="dfb0e-202">Nella pipeline, il componente aggiuntivo fornisce un servizio per l'host e il flusso di tipi di componente aggiuntivo per l'host.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-202">In this pipeline, the add-in provides a service to the host and the types flow from the add-in to the host.</span></span> <span data-ttu-id="dfb0e-203">Poiché non vengono passati tipi dall'host per il componente aggiuntivo, non è necessario includere un adattatore visualizzazione-contratto.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-203">Because no types flow from the host to the add-in, you do not have to include a view-to-contract adapter.</span></span>  
  
 <span data-ttu-id="dfb0e-204">Per implementare la gestione della durata, utilizzare un <xref:System.AddIn.Pipeline.ContractHandle> oggetto per associare un token di durata per il contratto.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-204">To implement lifetime management, use a <xref:System.AddIn.Pipeline.ContractHandle> object to attach a lifetime token to the contract.</span></span> <span data-ttu-id="dfb0e-205">È necessario mantenere un riferimento a questo punto di controllo affinché le operazioni di gestione della durata.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-205">You must keep a reference to this handle in order for lifetime management to work.</span></span> <span data-ttu-id="dfb0e-206">Dopo il token viene applicato, alcuna programmazione aggiuntiva non è necessaria perché il sistema del componente aggiuntivo è possibile eliminare gli oggetti quando non è più in uso e renderli disponibili per l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-206">After the token is applied, no additional programming is required because the add-in system can dispose of objects when they are no longer being used and make them available for garbage collection.</span></span> <span data-ttu-id="dfb0e-207">Per altre informazioni, vedere [Gestione della durata](http://msdn.microsoft.com/en-us/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span><span class="sxs-lookup"><span data-stu-id="dfb0e-207">For more information, see [Lifetime Management](http://msdn.microsoft.com/en-us/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
#### <a name="to-create-the-host-side-adapter"></a><span data-ttu-id="dfb0e-208">Per creare l'adattatore sul lato host</span><span class="sxs-lookup"><span data-stu-id="dfb0e-208">To create the host-side adapter</span></span>  
  
1.  <span data-ttu-id="dfb0e-209">Aggiungere un nuovo progetto denominato `Calc1HostSideAdapter` per il `CalculatorV1` soluzione.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-209">Add a new project named `Calc1HostSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="dfb0e-210">Come base il **libreria di classi** modello.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-210">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="dfb0e-211">In **Esplora**, aggiungere riferimenti agli assembly riportati di seguito per il `Calc1HostSideAdapter` progetto:</span><span class="sxs-lookup"><span data-stu-id="dfb0e-211">In **Solution Explorer**, add references to the following assemblies to the `Calc1HostSideAdapter` project:</span></span>  
  
     <span data-ttu-id="dfb0e-212">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="dfb0e-212">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="dfb0e-213">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="dfb0e-213">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="dfb0e-214">Aggiungere riferimenti ai progetti per i segmenti adiacenti:</span><span class="sxs-lookup"><span data-stu-id="dfb0e-214">Add project references to the projects for the adjacent segments:</span></span>  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  <span data-ttu-id="dfb0e-215">Selezionare ogni riferimento a progetto e in **proprietà** impostare **Copia localmente** a **False**.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-215">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="dfb0e-216">In Visual Basic, usare il **riferimenti** scheda della **le proprietà del progetto** impostare **Copia localmente** per **False** per i due riferimenti al progetto.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-216">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="dfb0e-217">Rinominare la classe del progetto predefinita `CalculatorContractToViewHostSideAdapter`.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-217">Rename the project's default class `CalculatorContractToViewHostSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="dfb0e-218">Nel file di classe, aggiungere riferimenti a spazi dei nomi per <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-218">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="dfb0e-219">Nel file di classe, aggiungere riferimenti a spazi dei nomi per i segmenti adiacenti: `CalcHVAs` e `CalculatorContracts`.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-219">In the class file, add namespace references for the adjacent segments: `CalcHVAs` and `CalculatorContracts`.</span></span> <span data-ttu-id="dfb0e-220">(In Visual Basic, questi riferimenti dello spazio dei nomi sono `Calc1HVA.CalcHVAs` e `Calc1Contract.CalculatorContracts`, a meno che non è stato disattivato gli spazi dei nomi predefinito nei progetti di Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="dfb0e-220">(In Visual Basic, these namespace references are `Calc1HVA.CalcHVAs` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="dfb0e-221">Applicare il <xref:System.AddIn.Pipeline.HostAdapterAttribute> attributo il `CalculatorContractToViewHostSideAdapter` (classe), per facilitarne l'identificazione del segmento di adattatore sul lato host.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-221">Apply the <xref:System.AddIn.Pipeline.HostAdapterAttribute> attribute to the `CalculatorContractToViewHostSideAdapter` class, to identify it as the host-side adapter segment.</span></span>  
  
9. <span data-ttu-id="dfb0e-222">Rendere il `CalculatorContractToViewHostSideAdapter` classe implementa l'interfaccia che rappresenta la visualizzazione host del componente aggiuntivo: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="dfb0e-222">Make the `CalculatorContractToViewHostSideAdapter` class implement the interface that represents the host view of the add-in: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).</span></span>  
  
10. <span data-ttu-id="dfb0e-223">Aggiungere un costruttore pubblico che accetta il tipo di contratto della pipeline, `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-223">Add a public constructor that accepts the pipeline contract type, `ICalc1Contract`.</span></span> <span data-ttu-id="dfb0e-224">Il costruttore deve memorizzare nella cache il riferimento al contratto.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-224">The constructor must cache the reference to the contract.</span></span> <span data-ttu-id="dfb0e-225">Inoltre necessario creare e memorizzare nella cache un nuovo <xref:System.AddIn.Pipeline.ContractHandle> per il contratto, per gestire la durata del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-225">It must also create and cache a new <xref:System.AddIn.Pipeline.ContractHandle> for the contract, to manage the lifetime of the add-in.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="dfb0e-226">Il <xref:System.AddIn.Pipeline.ContractHandle> è fondamentale per la gestione della durata.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-226">The <xref:System.AddIn.Pipeline.ContractHandle> is critical to lifetime management.</span></span> <span data-ttu-id="dfb0e-227">Se non si riesce a mantenere un riferimento per il <xref:System.AddIn.Pipeline.ContractHandle> dell'oggetto, quest ' ultimo verrà recuperato dalla procedura di garbage collection e la pipeline verrà interrotta quando il programma non previsto.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-227">If you fail to keep a reference to the <xref:System.AddIn.Pipeline.ContractHandle> object, garbage collection will reclaim it, and the pipeline will shut down when your program does not expect it.</span></span> <span data-ttu-id="dfb0e-228">Questo può causare errori difficili da diagnosticare, ad esempio <xref:System.AppDomainUnloadedException>.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-228">This can lead to errors that are difficult to diagnose, such as <xref:System.AppDomainUnloadedException>.</span></span> <span data-ttu-id="dfb0e-229">L'arresto è una fase normale il ciclo di vita di una pipeline, in modo non è possibile per il codice di gestione del ciclo di vita rilevare che questa condizione è un errore.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-229">Shutdown is a normal stage in the life of a pipeline, so there is no way for the lifetime management code to detect that this condition is an error.</span></span>  
  
11. <span data-ttu-id="dfb0e-230">Per implementare i membri di `ICalculator`, è sufficiente chiamare i membri corrispondenti del `ICalc1Contract` istanza che viene passato al costruttore e restituisce i risultati.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-230">To implement the members of `ICalculator`, simply call the corresponding members of the `ICalc1Contract` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="dfb0e-231">In questo modo il contratto (`ICalc1Contract`) per la visualizzazione (`ICalculator`).</span><span class="sxs-lookup"><span data-stu-id="dfb0e-231">This adapts the contract (`ICalc1Contract`) to the view (`ICalculator`).</span></span>  
  
     <span data-ttu-id="dfb0e-232">Il codice seguente illustra l'adattatore sul lato host completato.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-232">The following code shows the completed host-side adapter.</span></span>  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. <span data-ttu-id="dfb0e-233">Facoltativamente, compilare la soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-233">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host"></a><span data-ttu-id="dfb0e-234">La creazione dell'Host</span><span class="sxs-lookup"><span data-stu-id="dfb0e-234">Creating the Host</span></span>  
 <span data-ttu-id="dfb0e-235">Un'applicazione host interagisce con il componente aggiuntivo tramite la visualizzazione host del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-235">A host application interacts with the add-in through the host view of the add-in.</span></span> <span data-ttu-id="dfb0e-236">Utilizza i metodi di individuazione e attivazione del componente aggiuntivo forniti dal <xref:System.AddIn.Hosting.AddInStore> e <xref:System.AddIn.Hosting.AddInToken> classi per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfb0e-236">It uses add-in discovery and activation methods provided by the <xref:System.AddIn.Hosting.AddInStore> and <xref:System.AddIn.Hosting.AddInToken> classes to do the following:</span></span>  
  
-   <span data-ttu-id="dfb0e-237">Aggiornare la cache di informazioni sulla pipeline e componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-237">Update the cache of pipeline and add-in information.</span></span>  
  
-   <span data-ttu-id="dfb0e-238">Trovare i componenti aggiuntivi del tipo di visualizzazione host, `ICalculator`, nella directory radice della pipeline specificata.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-238">Find add-ins of the host view type, `ICalculator`, under the specified pipeline root directory.</span></span>  
  
-   <span data-ttu-id="dfb0e-239">Richiedere all'utente di specificare il componente aggiuntivo da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-239">Prompt the user to specify which add-in to use.</span></span>  
  
-   <span data-ttu-id="dfb0e-240">Attivare il componente aggiuntivo selezionato in un nuovo dominio applicazione con un livello di attendibilità di sicurezza specificato.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-240">Activate the selected add-in in a new application domain with a specified security trust level.</span></span>  
  
-   <span data-ttu-id="dfb0e-241">Eseguire personalizzata `RunCalculator` metodo, che chiama i metodi del componente aggiuntivo come specificato dalla visualizzazione host del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-241">Run the custom `RunCalculator` method, which calls the add-in's methods as specified by the host view of the add-in.</span></span>  
  
#### <a name="to-create-the-host"></a><span data-ttu-id="dfb0e-242">Per creare l'host</span><span class="sxs-lookup"><span data-stu-id="dfb0e-242">To create the host</span></span>  
  
1.  <span data-ttu-id="dfb0e-243">Aggiungere un nuovo progetto denominato `Calc1Host` per il `CalculatorV1` soluzione.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-243">Add a new project named `Calc1Host` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="dfb0e-244">Come base il **applicazione Console** modello.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-244">Base it on the **Console Application** template.</span></span>  
  
2.  <span data-ttu-id="dfb0e-245">In **Esplora**, aggiungere un riferimento all'assembly System.AddIn.dll per il `Calc1Host` progetto.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-245">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the `Calc1Host` project.</span></span>  
  
3.  <span data-ttu-id="dfb0e-246">Aggiungere un riferimento al progetto il `Calc1HVA` progetto.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-246">Add a project reference to the `Calc1HVA` project.</span></span> <span data-ttu-id="dfb0e-247">Selezionare il riferimento al progetto e in **proprietà** impostare **Copia localmente** a **False**.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-247">Select the project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="dfb0e-248">In Visual Basic, usare il **riferimenti** scheda **le proprietà del progetto** per impostare **Copia localmente** per **False**.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-248">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False**.</span></span>  
  
4.  <span data-ttu-id="dfb0e-249">Rinominare il file di classe (modulo di Visual Basic) `MathHost1`.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-249">Rename the class file (module in Visual Basic) `MathHost1`.</span></span>  
  
5.  <span data-ttu-id="dfb0e-250">In Visual Basic, usare il **applicazione** scheda della finestra di **le proprietà del progetto** la finestra di dialogo per impostare **oggetto di avvio** per **Sub Main**.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-250">In Visual Basic, use the **Application** tab of the **Project Properties** dialog box to set **Startup object** to **Sub Main**.</span></span>  
  
6.  <span data-ttu-id="dfb0e-251">Nel file di classe o modulo, aggiungere un riferimento dello spazio dei nomi a <xref:System.AddIn.Hosting>.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-251">In the class or module file, add a namespace reference to <xref:System.AddIn.Hosting>.</span></span>  
  
7.  <span data-ttu-id="dfb0e-252">Nel file di classe o modulo, aggiungere un riferimento dello spazio dei nomi per la visualizzazione host del componente aggiuntivo: `CalcHVAs`.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-252">In the class or module file, add a namespace reference for the host view of the add-in: `CalcHVAs`.</span></span> <span data-ttu-id="dfb0e-253">(In Visual Basic, questo spazio dei nomi riferimento è `Calc1HVA.CalcHVAs`, a meno che non è stato disattivato gli spazi dei nomi predefinito nei progetti di Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="dfb0e-253">(In Visual Basic, this namespace reference is `Calc1HVA.CalcHVAs`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="dfb0e-254">In **Esplora**, selezionare la soluzione e dal **progetto** dal menu **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-254">In **Solution Explorer**, select the solution and from the **Project** menu choose **Properties**.</span></span> <span data-ttu-id="dfb0e-255">Nel **pagine proprietà soluzione** la finestra di dialogo, impostare il **progetto di avvio singolo** da questo progetto di applicazione host.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-255">In the **Solution Property Pages** dialog box, set the **Single Startup Project** to be this host application project.</span></span>  
  
9. <span data-ttu-id="dfb0e-256">Nel file di classe o modulo, usare il <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> metodo per aggiornare la cache.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-256">In the class or module file, use the <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> method to update the cache.</span></span> <span data-ttu-id="dfb0e-257">Utilizzare il <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> metodo per ottenere una raccolta di token, utilizzare il <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> metodo per attivare un componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-257">Use the <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> method to get a collection of tokens, and use the <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> method to activate an add-in.</span></span>  
  
     <span data-ttu-id="dfb0e-258">Il codice seguente illustra l'applicazione host completata.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-258">The following code shows the completed host application.</span></span>  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="dfb0e-259">Questo codice si presuppone che la struttura di cartelle della pipeline si trova nella cartella dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-259">This code assumes that the pipeline folder structure is located in the application folder.</span></span> <span data-ttu-id="dfb0e-260">Se si trova in un' posizione, modificare la riga di codice che imposta il `addInRoot` variabile, in modo che la variabile contiene il percorso per la struttura di directory della pipeline.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-260">If you located it elsewhere, change the line of code that sets the `addInRoot` variable, so that the variable contains the path to your pipeline directory structure.</span></span>  
  
     <span data-ttu-id="dfb0e-261">Il codice Usa un `ChooseCalculator` metodo per elencare i token e richiedere all'utente di scegliere un componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-261">The code uses a `ChooseCalculator` method to list the tokens and to prompt the user to choose an add-in.</span></span> <span data-ttu-id="dfb0e-262">Il `RunCalculator` metodo richiede l'immissione di espressioni semplici operazioni matematiche, analizza le espressioni utilizzando la `Parser` classe e consente di visualizzare i risultati restituiti dal componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-262">The `RunCalculator` method prompts the user for simple math expressions, parses the expressions using the `Parser` class, and displays the results returned by the add-in.</span></span>  
  
10. <span data-ttu-id="dfb0e-263">Facoltativamente, compilare la soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-263">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in"></a><span data-ttu-id="dfb0e-264">Creare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="dfb0e-264">Creating the Add-In</span></span>  
 <span data-ttu-id="dfb0e-265">Un componente aggiuntivo implementa i metodi specificati da parte della vista del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-265">An add-in implements the methods specified by the add-in view.</span></span> <span data-ttu-id="dfb0e-266">Questo componente aggiuntivo implementa il `Add`, `Subtract`, `Multiply`, e `Divide` operazioni e restituisce i risultati all'host.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-266">This add-in implements the `Add`, `Subtract`, `Multiply`, and `Divide` operations and returns the results to the host.</span></span>  
  
#### <a name="to-create-the-add-in"></a><span data-ttu-id="dfb0e-267">Per creare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="dfb0e-267">To create the add-in</span></span>  
  
1.  <span data-ttu-id="dfb0e-268">Aggiungere un nuovo progetto denominato `AddInCalcV1` per il `CalculatorV1` soluzione.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-268">Add a new project named `AddInCalcV1` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="dfb0e-269">Come base il **libreria di classi** modello.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-269">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="dfb0e-270">In **Esplora**, aggiungere un riferimento all'assembly System.AddIn.dll al progetto.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-270">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the project.</span></span>  
  
3.  <span data-ttu-id="dfb0e-271">Aggiungere un riferimento al progetto il `Calc1AddInView` progetto.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-271">Add a project reference to the `Calc1AddInView` project.</span></span> <span data-ttu-id="dfb0e-272">Selezionare il riferimento al progetto e in **proprietà**, impostare **Copia localmente** a **False**.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-272">Select the project reference, and in **Properties**, set **Copy Local** to **False**.</span></span> <span data-ttu-id="dfb0e-273">In Visual Basic, usare il **riferimenti** scheda **le proprietà del progetto** per impostare **Copia localmente** per **False** per il riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-273">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the project reference.</span></span>  
  
4.  <span data-ttu-id="dfb0e-274">Rinominare la classe `AddInCalcV1`.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-274">Rename the class `AddInCalcV1`.</span></span>  
  
5.  <span data-ttu-id="dfb0e-275">Nel file di classe, aggiungere un riferimento dello spazio dei nomi a <xref:System.AddIn> e il segmento di visualizzazione: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="dfb0e-275">In the class file, add a namespace reference to <xref:System.AddIn> and the add-in view segment: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).</span></span>  
  
6.  <span data-ttu-id="dfb0e-276">Applicare il <xref:System.AddIn.AddInAttribute> attributo il `AddInCalcV1` (classe), per identificare la classe come un componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-276">Apply the <xref:System.AddIn.AddInAttribute> attribute to the `AddInCalcV1` class, to identify the class as an add-in.</span></span>  
  
7.  <span data-ttu-id="dfb0e-277">Rendere il `AddInCalcV1` classe implementa l'interfaccia che rappresenta la vista del componente aggiuntivo: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="dfb0e-277">Make the `AddInCalcV1` class implement the interface that represents the add-in view: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).</span></span>  
  
8.  <span data-ttu-id="dfb0e-278">Implementare i membri di `ICalculator` restituendo i risultati dei calcoli appropriati.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-278">Implement the members of `ICalculator` by returning the results of the appropriate calculations.</span></span>  
  
     <span data-ttu-id="dfb0e-279">Il codice seguente viene illustrato il componente aggiuntivo completato.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-279">The following code shows the completed add-in.</span></span>  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. <span data-ttu-id="dfb0e-280">Facoltativamente, compilare la soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-280">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="deploying-the-pipeline"></a><span data-ttu-id="dfb0e-281">Distribuzione della Pipeline</span><span class="sxs-lookup"><span data-stu-id="dfb0e-281">Deploying the Pipeline</span></span>  
 <span data-ttu-id="dfb0e-282">A questo punto si è pronti compilare e distribuire i segmenti del componente aggiuntivo per la struttura di directory della pipeline richiesta.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-282">You are now ready to build and deploy the add-in segments to the required pipeline directory structure.</span></span>  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a><span data-ttu-id="dfb0e-283">Per distribuire i segmenti della pipeline</span><span class="sxs-lookup"><span data-stu-id="dfb0e-283">To deploy the segments to the pipeline</span></span>  
  
1.  <span data-ttu-id="dfb0e-284">Per ogni progetto nella soluzione, utilizzare il **compilare** scheda della **le proprietà del progetto** (il **compilare** scheda in Visual Basic) per impostare il valore della **percorso di Output**  (il **il percorso di output di compilazione** in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="dfb0e-284">For each project in the solution, use the **Build** tab of **Project Properties** (the **Compile** tab in Visual Basic) to set the value of the **Output path** (the **Build output path** in Visual Basic).</span></span> <span data-ttu-id="dfb0e-285">Se la cartella dell'applicazione denominata `MyApp`, ad esempio, i progetti saranno compilati nelle cartelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfb0e-285">If you named your application folder `MyApp`, for example, your projects would build into the following folders:</span></span>  
  
    |<span data-ttu-id="dfb0e-286">Progetto</span><span class="sxs-lookup"><span data-stu-id="dfb0e-286">Project</span></span>|<span data-ttu-id="dfb0e-287">Path</span><span class="sxs-lookup"><span data-stu-id="dfb0e-287">Path</span></span>|  
    |-------------|----------|  
    |<span data-ttu-id="dfb0e-288">AddInCalcV1</span><span class="sxs-lookup"><span data-stu-id="dfb0e-288">AddInCalcV1</span></span>|<span data-ttu-id="dfb0e-289">MyApp\Pipeline\AddIns\CalcV1</span><span class="sxs-lookup"><span data-stu-id="dfb0e-289">MyApp\Pipeline\AddIns\CalcV1</span></span>|  
    |<span data-ttu-id="dfb0e-290">Calc1AddInSideAdapter</span><span class="sxs-lookup"><span data-stu-id="dfb0e-290">Calc1AddInSideAdapter</span></span>|<span data-ttu-id="dfb0e-291">MyApp\Pipeline\AddInSideAdapters</span><span class="sxs-lookup"><span data-stu-id="dfb0e-291">MyApp\Pipeline\AddInSideAdapters</span></span>|  
    |<span data-ttu-id="dfb0e-292">Calc1AddInView</span><span class="sxs-lookup"><span data-stu-id="dfb0e-292">Calc1AddInView</span></span>|<span data-ttu-id="dfb0e-293">MyApp\Pipeline\AddInViews</span><span class="sxs-lookup"><span data-stu-id="dfb0e-293">MyApp\Pipeline\AddInViews</span></span>|  
    |<span data-ttu-id="dfb0e-294">Calc1Contract</span><span class="sxs-lookup"><span data-stu-id="dfb0e-294">Calc1Contract</span></span>|<span data-ttu-id="dfb0e-295">MyApp\Pipeline\Contracts</span><span class="sxs-lookup"><span data-stu-id="dfb0e-295">MyApp\Pipeline\Contracts</span></span>|  
    |<span data-ttu-id="dfb0e-296">Calc1Host</span><span class="sxs-lookup"><span data-stu-id="dfb0e-296">Calc1Host</span></span>|<span data-ttu-id="dfb0e-297">MyApp</span><span class="sxs-lookup"><span data-stu-id="dfb0e-297">MyApp</span></span>|  
    |<span data-ttu-id="dfb0e-298">Calc1HostSideAdapter</span><span class="sxs-lookup"><span data-stu-id="dfb0e-298">Calc1HostSideAdapter</span></span>|<span data-ttu-id="dfb0e-299">MyApp\Pipeline\HostSideAdapters</span><span class="sxs-lookup"><span data-stu-id="dfb0e-299">MyApp\Pipeline\HostSideAdapters</span></span>|  
    |<span data-ttu-id="dfb0e-300">Calc1HVA</span><span class="sxs-lookup"><span data-stu-id="dfb0e-300">Calc1HVA</span></span>|<span data-ttu-id="dfb0e-301">MyApp</span><span class="sxs-lookup"><span data-stu-id="dfb0e-301">MyApp</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="dfb0e-302">Se si è deciso di inserire la struttura di cartelle della pipeline in un percorso diverso dalla cartella dell'applicazione, è necessario modificare di conseguenza i percorsi mostrati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-302">If you decided to put your pipeline folder structure in a location other than your application folder, you must modify the paths shown in the table accordingly.</span></span> <span data-ttu-id="dfb0e-303">Vedere la sezione requisiti della pipeline directory [requisiti di sviluppo Pipeline](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="dfb0e-303">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
2.  <span data-ttu-id="dfb0e-304">Compilare la soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-304">Build the Visual Studio solution.</span></span>  
  
3.  <span data-ttu-id="dfb0e-305">Controllare le directory della pipeline e di applicazione per assicurarsi che gli assembly sono stati copiati nelle directory corrette e che nessun copie aggiuntive di assembly siano state installate nelle cartelle errate.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-305">Check the application and pipeline directories to ensure that the assemblies were copied to the correct directories and that no extra copies of assemblies were installed in the wrong folders.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dfb0e-306">Se non è stato modificato **Copia localmente** a **False** per il `Calc1AddInView` riferimento nel progetto di `AddInCalcV1` progetto, problemi relativi al contesto del caricatore impedirà il componente aggiuntivo si trovano.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-306">If you did not change **Copy Local** to **False** for the `Calc1AddInView` project reference in the `AddInCalcV1` project, loader context problems will prevent the add-in from being located.</span></span>  
  
     <span data-ttu-id="dfb0e-307">Per informazioni su come distribuire la pipeline, vedere [requisiti di sviluppo Pipeline](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="dfb0e-307">For information about deploying to the pipeline, see [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
## <a name="running-the-host-application"></a><span data-ttu-id="dfb0e-308">Esecuzione dell'applicazione Host</span><span class="sxs-lookup"><span data-stu-id="dfb0e-308">Running the Host Application</span></span>  
 <span data-ttu-id="dfb0e-309">A questo punto si è pronti eseguire l'host e interagire con il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-309">You are now ready to run the host and interact with the add-in.</span></span>  
  
#### <a name="to-run-the-host-application"></a><span data-ttu-id="dfb0e-310">Per eseguire l'applicazione host</span><span class="sxs-lookup"><span data-stu-id="dfb0e-310">To run the host application</span></span>  
  
1.  <span data-ttu-id="dfb0e-311">Al prompt dei comandi, passare alla directory dell'applicazione ed eseguire l'applicazione host, `Calc1Host.exe`.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-311">At the command prompt, go to the application directory and run the host application, `Calc1Host.exe`.</span></span>  
  
2.  <span data-ttu-id="dfb0e-312">L'host consente di individuare tutti i componenti aggiuntivi disponibili del tipo e viene richiesto di selezionare un componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-312">The host finds all available add-ins of its type and prompts you to select an add-in.</span></span> <span data-ttu-id="dfb0e-313">Immettere **1** per il componente aggiuntivo è disponibile solo.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-313">Enter **1** for the only available add-in.</span></span>  
  
3.  <span data-ttu-id="dfb0e-314">Immettere un'equazione per il calcolo, ad esempio **2 + 2**.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-314">Enter an equation for the calculator, such as **2 + 2**.</span></span> <span data-ttu-id="dfb0e-315">Devono essere presenti spazi tra i numeri e l'operatore.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-315">There must be spaces between the numbers and the operator.</span></span>  
  
4.  <span data-ttu-id="dfb0e-316">Tipo **uscire** e premere il **invio** tasto per chiudere l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dfb0e-316">Type **exit** and press the **Enter** key to close the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb0e-317">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfb0e-317">See Also</span></span>  
 [<span data-ttu-id="dfb0e-318">Procedura dettagliata: Consentendo la compatibilità con le versioni precedenti come le modifiche di Host</span><span class="sxs-lookup"><span data-stu-id="dfb0e-318">Walkthrough: Enabling Backward Compatibility as Your Host Changes</span></span>](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
 [<span data-ttu-id="dfb0e-319">Procedura dettagliata: Passaggio di raccolte tra componenti aggiuntivi e host</span><span class="sxs-lookup"><span data-stu-id="dfb0e-319">Walkthrough: Passing Collections Between Hosts and Add-Ins</span></span>](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5)  
 [<span data-ttu-id="dfb0e-320">Requisiti di sviluppo pipeline</span><span class="sxs-lookup"><span data-stu-id="dfb0e-320">Pipeline Development Requirements</span></span>](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
 [<span data-ttu-id="dfb0e-321">Contratti, visualizzazioni e adattatori</span><span class="sxs-lookup"><span data-stu-id="dfb0e-321">Contracts, Views, and Adapters</span></span>](http://msdn.microsoft.com/en-us/a6460173-9507-4b87-8c07-d4ee245d715c)  
 [<span data-ttu-id="dfb0e-322">Sviluppo pipeline</span><span class="sxs-lookup"><span data-stu-id="dfb0e-322">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)

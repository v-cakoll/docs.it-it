---
title: "Procedura dettagliata: creazione di un'applicazione estendibile"
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63780583d035d6fab6b3a79424857b82a910ef09
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183893"
---
# <a name="walkthrough-creating-an-extensible-application"></a><span data-ttu-id="aa5cb-102">Procedura dettagliata: creazione di un'applicazione estendibile</span><span class="sxs-lookup"><span data-stu-id="aa5cb-102">Walkthrough: Creating an Extensible Application</span></span>
<span data-ttu-id="aa5cb-103">Questa procedura dettagliata descrive come creare una pipeline per un componente aggiuntivo che esegue funzioni semplice calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-103">This walkthrough describes how to create a pipeline for an add-in that performs simple calculator functions.</span></span> <span data-ttu-id="aa5cb-104">Se non illustra uno scenario reale; piuttosto, illustra le funzionalità di base di una pipeline e un componente aggiuntivo può come forniscono servizi per un host.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-104">It does not demonstrate a real-world scenario; rather, it demonstrates the basic functionality of a pipeline and how an add-in can provide services for a host.</span></span>  
  
 <span data-ttu-id="aa5cb-105">Questa procedura dettagliata descrive le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa5cb-105">This walkthrough describes the following tasks:</span></span>  
  
-   <span data-ttu-id="aa5cb-106">Creazione di una soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-106">Creating a Visual Studio solution.</span></span>  
  
-   <span data-ttu-id="aa5cb-107">Creazione della struttura di directory della pipeline.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-107">Creating the pipeline directory structure.</span></span>  
  
-   <span data-ttu-id="aa5cb-108">Creazione del contratto e le viste.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-108">Creating the contract and views.</span></span>  
  
-   <span data-ttu-id="aa5cb-109">Creazione dell'adattatore lato componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-109">Creating the add-in-side adapter.</span></span>  
  
-   <span data-ttu-id="aa5cb-110">Creazione dell'adattatore lato host.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-110">Creating the host-side adapter.</span></span>  
  
-   <span data-ttu-id="aa5cb-111">Creazione dell'host.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-111">Creating the host.</span></span>  
  
-   <span data-ttu-id="aa5cb-112">Creare il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-112">Creating the add-in.</span></span>  
  
-   <span data-ttu-id="aa5cb-113">Distribuzione della pipeline.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-113">Deploying the pipeline.</span></span>  
  
-   <span data-ttu-id="aa5cb-114">Esecuzione dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-114">Running the host application.</span></span>  
  
 <span data-ttu-id="aa5cb-115">Questa pipeline passa solo tipi serializzabili (<xref:System.Double> e <xref:System.String>), tra l'host e il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-115">This pipeline passes only serializable types (<xref:System.Double> and <xref:System.String>), between the host and the add-in.</span></span> <span data-ttu-id="aa5cb-116">Per un esempio che illustra come passare raccolte di tipi di dati complessi, vedere [procedura dettagliata: passaggio di raccolte tra host e Add-Ins](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5).</span><span class="sxs-lookup"><span data-stu-id="aa5cb-116">For an example that shows how to pass collections of complex data types, see [Walkthrough: Passing Collections Between Hosts and Add-Ins](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5).</span></span>  
  
 <span data-ttu-id="aa5cb-117">Il contratto per questa pipeline consente di definire un modello a oggetti delle quattro operazioni aritmetiche: aggiunta, sottrazione, moltiplicazione e divisione.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-117">The contract for this pipeline defines an object model of four arithmetic operations: add, subtract, multiply, and divide.</span></span> <span data-ttu-id="aa5cb-118">L'host fornisce il componente aggiuntivo con un'equazione per calcolare, ad esempio 2 + 2, e il componente aggiuntivo restituisce il risultato all'host.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-118">The host provides the add-in with an equation to calculate, such as 2 + 2, and the add-in returns the result to the host.</span></span>  
  
 <span data-ttu-id="aa5cb-119">Versione 2 del componente aggiuntivo per la calcolatrice offre maggiori possibilità di calcolo e viene illustrato il controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-119">Version 2 of the calculator add-in provides more calculating possibilities and demonstrates versioning.</span></span> <span data-ttu-id="aa5cb-120">Viene descritto in [procedura dettagliata: abilitazione della compatibilità con le versioni precedenti come le modifiche di Host](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span><span class="sxs-lookup"><span data-stu-id="aa5cb-120">It is described in [Walkthrough: Enabling Backward Compatibility as Your Host Changes](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aa5cb-121">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="aa5cb-121">Prerequisites</span></span>  
 <span data-ttu-id="aa5cb-122">Per completare questa procedura dettagliata, sono necessari i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="aa5cb-122">You need the following to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="aa5cb-123">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-123">Visual Studio.</span></span>  
  
## <a name="creating-a-visual-studio-solution"></a><span data-ttu-id="aa5cb-124">Creazione di una soluzione di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="aa5cb-124">Creating a Visual Studio Solution</span></span>  
 <span data-ttu-id="aa5cb-125">Usare una soluzione in Visual Studio per contenere i progetti dei segmenti di pipeline.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-125">Use a solution in Visual Studio to contain the projects of your pipeline segments.</span></span>  
  
#### <a name="to-create-the-pipeline-solution"></a><span data-ttu-id="aa5cb-126">Per creare la soluzione della pipeline</span><span class="sxs-lookup"><span data-stu-id="aa5cb-126">To create the pipeline solution</span></span>  
  
1.  <span data-ttu-id="aa5cb-127">In Visual Studio, creare un nuovo progetto denominato `Calc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-127">In Visual Studio, create a new project named `Calc1Contract`.</span></span> <span data-ttu-id="aa5cb-128">Basandosi sul **libreria di classi** modello.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-128">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="aa5cb-129">Assegnare alla soluzione il nome `CalculatorV1`.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-129">Name the solution `CalculatorV1`.</span></span>  
  
## <a name="creating-the-pipeline-directory-structure"></a><span data-ttu-id="aa5cb-130">Creazione della struttura di Directory della Pipeline</span><span class="sxs-lookup"><span data-stu-id="aa5cb-130">Creating the Pipeline Directory Structure</span></span>  
 <span data-ttu-id="aa5cb-131">Il modello di componente aggiuntivo richiede gli assembly di segmenti della pipeline a essere inserito in una struttura di directory specificato.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-131">The add-in model requires the pipeline segment assemblies to be placed in a specified directory structure.</span></span> <span data-ttu-id="aa5cb-132">Per altre informazioni sulla struttura della pipeline, vedere [requisiti di sviluppo delle Pipeline](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="aa5cb-132">For more information about the pipeline structure, see [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
#### <a name="to-create-the-pipeline-directory-structure"></a><span data-ttu-id="aa5cb-133">Per creare la struttura di directory della pipeline</span><span class="sxs-lookup"><span data-stu-id="aa5cb-133">To create the pipeline directory structure</span></span>  
  
1.  <span data-ttu-id="aa5cb-134">Creare una cartella dell'applicazione in un punto qualsiasi nel computer.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-134">Create an application folder anywhere on your computer.</span></span>  
  
2.  <span data-ttu-id="aa5cb-135">In tale cartella, creare la struttura seguente:</span><span class="sxs-lookup"><span data-stu-id="aa5cb-135">In that folder, create the following structure:</span></span>  
  
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
  
     <span data-ttu-id="aa5cb-136">Non è necessario inserire la struttura di cartelle della pipeline nella cartella dell'applicazione; viene eseguita qui solo per comodità.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-136">It is not necessary to put the pipeline folder structure in your application folder; it is done here only for convenience.</span></span> <span data-ttu-id="aa5cb-137">Nel passaggio appropriato, la procedura dettagliata illustra come modificare il codice, se la struttura di cartelle della pipeline si trova in una posizione diversa.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-137">At the appropriate step, the walkthrough explains how to change the code if the pipeline folder structure is in a different location.</span></span> <span data-ttu-id="aa5cb-138">Vedere la discussione dei requisiti di directory della pipeline [requisiti di sviluppo delle Pipeline](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="aa5cb-138">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aa5cb-139">Il `CalcV2` cartella non viene usata in questa procedura dettagliata; è un segnaposto per [questa procedura dettagliata: abilitazione della compatibilità con le versioni precedenti come le modifiche di Host](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span><span class="sxs-lookup"><span data-stu-id="aa5cb-139">The `CalcV2` folder is not used in this walkthrough; it is a placeholder for [Walkthrough: Enabling Backward Compatibility as Your Host Changes](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="creating-the-contract-and-views"></a><span data-ttu-id="aa5cb-140">Creazione del contratto e le viste</span><span class="sxs-lookup"><span data-stu-id="aa5cb-140">Creating the Contract and Views</span></span>  
 <span data-ttu-id="aa5cb-141">Il segmento di contratto per la pipeline definisce i `ICalc1Contract` interfaccia che definisce quattro metodi: `add`, `subtract`, `multiply`, e `divide`.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-141">The contract segment for this pipeline defines the `ICalc1Contract` interface, which defines four methods: `add`, `subtract`, `multiply`, and `divide`.</span></span>  
  
#### <a name="to-create-the-contract"></a><span data-ttu-id="aa5cb-142">Per creare il contratto</span><span class="sxs-lookup"><span data-stu-id="aa5cb-142">To create the contract</span></span>  
  
1.  <span data-ttu-id="aa5cb-143">Nella soluzione di Visual Studio denominata `CalculatorV1`, aprire il `Calc1Contract` progetto.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-143">In the Visual Studio solution named `CalculatorV1`, open the `Calc1Contract` project.</span></span>  
  
2.  <span data-ttu-id="aa5cb-144">Nelle **Esplora soluzioni**, aggiungere i riferimenti agli assembly seguenti per il `Calc1Contract` progetto:</span><span class="sxs-lookup"><span data-stu-id="aa5cb-144">In **Solution Explorer**, add references to the following assemblies to the `Calc1Contract` project:</span></span>  
  
     <span data-ttu-id="aa5cb-145">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="aa5cb-145">System.AddIn.Contract.dll</span></span>  
  
     <span data-ttu-id="aa5cb-146">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="aa5cb-146">System.AddIn.dll</span></span>  
  
3.  <span data-ttu-id="aa5cb-147">Nelle **Esplora soluzioni**, escludere la classe predefinita che viene aggiunto al nuovo **libreria di classi** progetti.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-147">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects.</span></span>  
  
4.  <span data-ttu-id="aa5cb-148">Nelle **Esplora soluzioni**, aggiungere un nuovo elemento al progetto, utilizzando il **interfaccia** modello.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-148">In **Solution Explorer**, add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="aa5cb-149">Nel **Aggiungi nuovo elemento** della finestra di dialogo Nome interfaccia `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-149">In the **Add New Item** dialog box, name the interface `ICalc1Contract`.</span></span>  
  
5.  <span data-ttu-id="aa5cb-150">Nel file di interfaccia, aggiungere i riferimenti di spazio dei nomi per <xref:System.AddIn.Contract> e <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-150">In the interface file, add namespace references to <xref:System.AddIn.Contract> and <xref:System.AddIn.Pipeline>.</span></span>  
  
6.  <span data-ttu-id="aa5cb-151">Usare il codice seguente per completare questo segmento di contratto.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-151">Use the following code to complete this contract segment.</span></span> <span data-ttu-id="aa5cb-152">Si noti che questa interfaccia deve avere il <xref:System.AddIn.Pipeline.AddInContractAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-152">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInContractAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  <span data-ttu-id="aa5cb-153">Facoltativamente, compilare la soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-153">Optionally, build the Visual Studio solution.</span></span> <span data-ttu-id="aa5cb-154">La soluzione non può essere eseguita fino a quando la procedura finale, ma la compilazione al termine di ogni procedura garantisce che ogni progetto è correggere.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-154">The solution cannot be run until the final procedure, but building it after each procedure ensures that each project is correct.</span></span>  
  
 <span data-ttu-id="aa5cb-155">Poiché la visualizzazione componente aggiuntivo e la visualizzazione host del componente aggiuntivo hanno in genere lo stesso codice, in particolare nella prima versione di un componente aggiuntivo, è possibile creare facilmente le viste nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-155">Because the add-in view and the host view of the add-in usually have the same code, especially in the first version of an add-in, you can easily create the views at the same time.</span></span> <span data-ttu-id="aa5cb-156">Si differenziano per un solo fattore: richiede la visualizzazione componente aggiuntivo di <xref:System.AddIn.Pipeline.AddInBaseAttribute> attributo, mentre la visualizzazione host del componente aggiuntivo non richiede tutti gli attributi.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-156">They differ by only one factor: the add-in view requires the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute, while the host view of the add-in does not require any attributes.</span></span>  
  
#### <a name="to-create-the-add-in-view"></a><span data-ttu-id="aa5cb-157">Per creare la visualizzazione componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="aa5cb-157">To create the add-in view</span></span>  
  
1.  <span data-ttu-id="aa5cb-158">Aggiungere un nuovo progetto denominato `Calc1AddInView` per il `CalculatorV1` soluzione.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-158">Add a new project named `Calc1AddInView` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="aa5cb-159">Basandosi sul **libreria di classi** modello.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-159">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="aa5cb-160">Nelle **Esplora soluzioni**, aggiungere un riferimento a System.AddIn.dll per il `Calc1AddInView` progetto.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-160">In **Solution Explorer**, add a reference to System.AddIn.dll to the `Calc1AddInView` project.</span></span>  
  
3.  <span data-ttu-id="aa5cb-161">Nelle **Esplora soluzioni**, escludere la classe predefinita che viene aggiunto al nuovo **libreria di classi** progetti e aggiungere un nuovo elemento al progetto, utilizzando il **interfaccia** modello.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-161">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="aa5cb-162">Nel **Aggiungi nuovo elemento** della finestra di dialogo Nome interfaccia `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-162">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
4.  <span data-ttu-id="aa5cb-163">Nel file di interfaccia, aggiungere un riferimento dello spazio dei nomi a <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-163">In the interface file, add a namespace reference to <xref:System.AddIn.Pipeline>.</span></span>  
  
5.  <span data-ttu-id="aa5cb-164">Usare il codice seguente per completare questa visualizzazione componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-164">Use the following code to complete this add-in view.</span></span> <span data-ttu-id="aa5cb-165">Si noti che questa interfaccia deve avere il <xref:System.AddIn.Pipeline.AddInBaseAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-165">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  <span data-ttu-id="aa5cb-166">Facoltativamente, compilare la soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-166">Optionally, build the Visual Studio solution.</span></span>  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a><span data-ttu-id="aa5cb-167">Per creare la visualizzazione host del componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="aa5cb-167">To create the host view of the add-in</span></span>  
  
1.  <span data-ttu-id="aa5cb-168">Aggiungere un nuovo progetto denominato `Calc1HVA` per il `CalculatorV1` soluzione.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-168">Add a new project named `Calc1HVA` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="aa5cb-169">Basandosi sul **libreria di classi** modello.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-169">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="aa5cb-170">Nelle **Esplora soluzioni**, escludere la classe predefinita che viene aggiunto al nuovo **libreria di classi** progetti e aggiungere un nuovo elemento al progetto, utilizzando il **interfaccia** modello.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-170">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="aa5cb-171">Nel **Aggiungi nuovo elemento** della finestra di dialogo Nome interfaccia `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-171">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
3.  <span data-ttu-id="aa5cb-172">Nel file di interfaccia, usare il codice seguente per completare la visualizzazione host del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-172">In the interface file, use the following code to complete the host view of the add-in.</span></span>  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  <span data-ttu-id="aa5cb-173">Facoltativamente, compilare la soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-173">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in-side-adapter"></a><span data-ttu-id="aa5cb-174">Creazione dell'adattatore sul lato del componente:</span><span class="sxs-lookup"><span data-stu-id="aa5cb-174">Creating the Add-in-side Adapter</span></span>  
 <span data-ttu-id="aa5cb-175">Questo adapter in-sul lato del componente è costituito da un adattatore visualizzazione-contratto.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-175">This add-in-side adapter consists of one view-to-contract adapter.</span></span> <span data-ttu-id="aa5cb-176">Questo segmento di pipeline converte i tipi dalla visualizzazione componente aggiuntivo per il contratto.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-176">This pipeline segment converts the types from the add-in view to the contract.</span></span>  
  
 <span data-ttu-id="aa5cb-177">In questa pipeline, il componente aggiuntivo fornisce un servizio all'host e i tipi di flusso dal componente aggiuntivo all'host.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-177">In this pipeline, the add-in provides a service to the host, and the types flow from the add-in to the host.</span></span> <span data-ttu-id="aa5cb-178">Poiché nessun tipo di flusso dall'host al componente aggiuntivo, non è necessario includere un adattatore contratto-visualizzazione sul lato componente aggiuntivo della pipeline.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-178">Because no types flow from the host to the add-in, you do not have to include a contract-to-view adapter on the add-in side of this pipeline.</span></span>  
  
#### <a name="to-create-the-add-in-side-adapter"></a><span data-ttu-id="aa5cb-179">Per creare l'adattatore lato componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="aa5cb-179">To create the add-in-side adapter</span></span>  
  
1.  <span data-ttu-id="aa5cb-180">Aggiungere un nuovo progetto denominato `Calc1AddInSideAdapter` per il `CalculatorV1` soluzione.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-180">Add a new project named `Calc1AddInSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="aa5cb-181">Basandosi sul **libreria di classi** modello.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-181">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="aa5cb-182">Nelle **Esplora soluzioni**, aggiungere i riferimenti agli assembly seguenti per il `Calc1AddInSideAdapter` progetto:</span><span class="sxs-lookup"><span data-stu-id="aa5cb-182">In **Solution Explorer**, add references to the following assemblies to the `Calc1AddInSideAdapter` project:</span></span>  
  
     <span data-ttu-id="aa5cb-183">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="aa5cb-183">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="aa5cb-184">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="aa5cb-184">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="aa5cb-185">Aggiungere riferimenti al progetto per i progetti per i segmenti di pipeline adiacente:</span><span class="sxs-lookup"><span data-stu-id="aa5cb-185">Add project references to the projects for the adjacent pipeline segments:</span></span>  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  <span data-ttu-id="aa5cb-186">Selezionare ogni riferimento al progetto e nella **delle proprietà** impostare **Copia localmente** al **False**.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-186">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="aa5cb-187">In Visual Basic, usare il **riferimenti** scheda della finestra **le proprietà del progetto** impostare **Copia localmente** a **False** per i due riferimenti al progetto.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-187">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="aa5cb-188">Rinominare la classe del progetto predefinita `CalculatorViewToContractAddInSideAdapter`.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-188">Rename the project's default class `CalculatorViewToContractAddInSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="aa5cb-189">Nel file di classe, aggiungere i riferimenti di spazio dei nomi a <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-189">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="aa5cb-190">Nel file di classe, aggiungere i riferimenti di spazio dei nomi per i segmenti adiacenti: `CalcAddInViews` e `CalculatorContracts`.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-190">In the class file, add namespace references for the adjacent segments: `CalcAddInViews` and `CalculatorContracts`.</span></span> <span data-ttu-id="aa5cb-191">(In Visual Basic, sono questi riferimenti dello spazio dei nomi `Calc1AddInView.CalcAddInViews` e `Calc1Contract.CalculatorContracts`, a meno che non siano stati disattivati gli spazi dei nomi predefinito nei progetti Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="aa5cb-191">(In Visual Basic, these namespace references are `Calc1AddInView.CalcAddInViews` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="aa5cb-192">Si applicano i <xref:System.AddIn.Pipeline.AddInAdapterAttribute> dell'attributo di `CalculatorViewToContractAddInSideAdapter` (classe), venga identificato come l'adattatore lato componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-192">Apply the <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attribute to the `CalculatorViewToContractAddInSideAdapter` class, to identify it as the add-in-side adapter.</span></span>  
  
9. <span data-ttu-id="aa5cb-193">Rendere la `CalculatorViewToContractAddInSideAdapter` classe ereditare <xref:System.AddIn.Pipeline.ContractBase>, che fornisce un'implementazione predefinita delle <xref:System.AddIn.Contract.IContract> interfaccia e implementare l'interfaccia del contratto per la pipeline `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-193">Make the `CalculatorViewToContractAddInSideAdapter` class inherit <xref:System.AddIn.Pipeline.ContractBase>, which provides a default implementation of the <xref:System.AddIn.Contract.IContract> interface, and implement the contract interface for the pipeline, `ICalc1Contract`.</span></span>  
  
10. <span data-ttu-id="aa5cb-194">Aggiungere un costruttore pubblico che accetta un `ICalculator`, memorizza nella cache in un campo privato e chiama il costruttore di classe di base.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-194">Add a public constructor that accepts an `ICalculator`, caches it in a private field, and calls the base class constructor.</span></span>  
  
11. <span data-ttu-id="aa5cb-195">Per implementare i membri del `ICalc1Contract`, è sufficiente chiamare i membri corrispondenti del `ICalculator` istanza che viene passato al costruttore e restituirà i risultati.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-195">To implement the members of `ICalc1Contract`, simply call the corresponding members of the `ICalculator` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="aa5cb-196">In questo modo la visualizzazione (`ICalculator`) al contratto (`ICalc1Contract`).</span><span class="sxs-lookup"><span data-stu-id="aa5cb-196">This adapts the view (`ICalculator`) to the contract (`ICalc1Contract`).</span></span>  
  
     <span data-ttu-id="aa5cb-197">Il codice seguente illustra l'adattatore sul lato del componente-completato.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-197">The following code shows the completed add-in-side adapter.</span></span>  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. <span data-ttu-id="aa5cb-198">Facoltativamente, compilare la soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-198">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host-side-adapter"></a><span data-ttu-id="aa5cb-199">Creazione dell'adattatore sul lato Host</span><span class="sxs-lookup"><span data-stu-id="aa5cb-199">Creating the Host-side Adapter</span></span>  
 <span data-ttu-id="aa5cb-200">Questo adattatore lato host è costituito da un adattatore contratto-vista.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-200">This host-side adapter consists of one contract-to-view adapter.</span></span> <span data-ttu-id="aa5cb-201">Il segmento si adatta al contratto per la visualizzazione host del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-201">This segment adapts the contract to the host view of the add-in.</span></span>  
  
 <span data-ttu-id="aa5cb-202">In questa pipeline, il componente aggiuntivo fornisce un servizio per l'host e il flusso di tipi dal componente aggiuntivo all'host.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-202">In this pipeline, the add-in provides a service to the host and the types flow from the add-in to the host.</span></span> <span data-ttu-id="aa5cb-203">Poiché nessun tipo di flusso dall'host al componente aggiuntivo, non è necessario includere un adattatore visualizzazione-contratto.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-203">Because no types flow from the host to the add-in, you do not have to include a view-to-contract adapter.</span></span>  
  
 <span data-ttu-id="aa5cb-204">Per implementare la gestione della durata, usare un <xref:System.AddIn.Pipeline.ContractHandle> oggetto da associare un token di durata per il contratto.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-204">To implement lifetime management, use a <xref:System.AddIn.Pipeline.ContractHandle> object to attach a lifetime token to the contract.</span></span> <span data-ttu-id="aa5cb-205">È necessario mantenere un riferimento a questo handle in ordine per la gestione della durata a funzionare.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-205">You must keep a reference to this handle in order for lifetime management to work.</span></span> <span data-ttu-id="aa5cb-206">Dopo il token viene applicato, alcuna programmazione aggiuntiva non è necessaria perché il sistema del componente aggiuntivo possa eliminare gli oggetti quando non sono più in uso e renderli disponibili per l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-206">After the token is applied, no additional programming is required because the add-in system can dispose of objects when they are no longer being used and make them available for garbage collection.</span></span> <span data-ttu-id="aa5cb-207">Per altre informazioni, vedere [Gestione della durata](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span><span class="sxs-lookup"><span data-stu-id="aa5cb-207">For more information, see [Lifetime Management](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
#### <a name="to-create-the-host-side-adapter"></a><span data-ttu-id="aa5cb-208">Per creare l'adattatore lato host</span><span class="sxs-lookup"><span data-stu-id="aa5cb-208">To create the host-side adapter</span></span>  
  
1.  <span data-ttu-id="aa5cb-209">Aggiungere un nuovo progetto denominato `Calc1HostSideAdapter` per il `CalculatorV1` soluzione.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-209">Add a new project named `Calc1HostSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="aa5cb-210">Basandosi sul **libreria di classi** modello.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-210">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="aa5cb-211">Nelle **Esplora soluzioni**, aggiungere i riferimenti agli assembly seguenti per il `Calc1HostSideAdapter` progetto:</span><span class="sxs-lookup"><span data-stu-id="aa5cb-211">In **Solution Explorer**, add references to the following assemblies to the `Calc1HostSideAdapter` project:</span></span>  
  
     <span data-ttu-id="aa5cb-212">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="aa5cb-212">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="aa5cb-213">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="aa5cb-213">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="aa5cb-214">Aggiungere riferimenti al progetto per i progetti per i segmenti adiacenti:</span><span class="sxs-lookup"><span data-stu-id="aa5cb-214">Add project references to the projects for the adjacent segments:</span></span>  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  <span data-ttu-id="aa5cb-215">Selezionare ogni riferimento al progetto e nella **delle proprietà** impostare **Copia localmente** al **False**.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-215">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="aa5cb-216">In Visual Basic, usare il **riferimenti** scheda della finestra **le proprietà del progetto** impostare **Copia localmente** a **False** per i due riferimenti al progetto.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-216">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="aa5cb-217">Rinominare la classe del progetto predefinita `CalculatorContractToViewHostSideAdapter`.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-217">Rename the project's default class `CalculatorContractToViewHostSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="aa5cb-218">Nel file di classe, aggiungere i riferimenti di spazio dei nomi a <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-218">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="aa5cb-219">Nel file di classe, aggiungere i riferimenti di spazio dei nomi per i segmenti adiacenti: `CalcHVAs` e `CalculatorContracts`.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-219">In the class file, add namespace references for the adjacent segments: `CalcHVAs` and `CalculatorContracts`.</span></span> <span data-ttu-id="aa5cb-220">(In Visual Basic, sono questi riferimenti dello spazio dei nomi `Calc1HVA.CalcHVAs` e `Calc1Contract.CalculatorContracts`, a meno che non siano stati disattivati gli spazi dei nomi predefinito nei progetti Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="aa5cb-220">(In Visual Basic, these namespace references are `Calc1HVA.CalcHVAs` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="aa5cb-221">Si applicano i <xref:System.AddIn.Pipeline.HostAdapterAttribute> dell'attributo di `CalculatorContractToViewHostSideAdapter` (classe), per facilitarne l'identificazione del segmento di adattatore lato host.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-221">Apply the <xref:System.AddIn.Pipeline.HostAdapterAttribute> attribute to the `CalculatorContractToViewHostSideAdapter` class, to identify it as the host-side adapter segment.</span></span>  
  
9. <span data-ttu-id="aa5cb-222">Verificare i `CalculatorContractToViewHostSideAdapter` classe implementare l'interfaccia che rappresenta la visualizzazione host del componente aggiuntivo: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="aa5cb-222">Make the `CalculatorContractToViewHostSideAdapter` class implement the interface that represents the host view of the add-in: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).</span></span>  
  
10. <span data-ttu-id="aa5cb-223">Aggiungere un costruttore pubblico che accetta il tipo di contratto di pipeline, `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-223">Add a public constructor that accepts the pipeline contract type, `ICalc1Contract`.</span></span> <span data-ttu-id="aa5cb-224">Il costruttore deve memorizzare nella cache il riferimento al contratto.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-224">The constructor must cache the reference to the contract.</span></span> <span data-ttu-id="aa5cb-225">Anche necessario creare e memorizzare nella cache un nuovo <xref:System.AddIn.Pipeline.ContractHandle> per il contratto, per gestire la durata del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-225">It must also create and cache a new <xref:System.AddIn.Pipeline.ContractHandle> for the contract, to manage the lifetime of the add-in.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="aa5cb-226">Il <xref:System.AddIn.Pipeline.ContractHandle> è fondamentale per la gestione della durata.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-226">The <xref:System.AddIn.Pipeline.ContractHandle> is critical to lifetime management.</span></span> <span data-ttu-id="aa5cb-227">Se non si riesce a mantenere un riferimento al <xref:System.AddIn.Pipeline.ContractHandle> dell'oggetto, quest ' ultimo verrà recuperato dalla procedura di garbage collection, e la pipeline si arresterà quando il programma non previsto.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-227">If you fail to keep a reference to the <xref:System.AddIn.Pipeline.ContractHandle> object, garbage collection will reclaim it, and the pipeline will shut down when your program does not expect it.</span></span> <span data-ttu-id="aa5cb-228">Questo può causare errori difficili da diagnosticare, ad esempio <xref:System.AppDomainUnloadedException>.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-228">This can lead to errors that are difficult to diagnose, such as <xref:System.AppDomainUnloadedException>.</span></span> <span data-ttu-id="aa5cb-229">Istruzione SHUTDOWN è una fase normale in tutta la durata di una pipeline, in modo che non è possibile per il codice di gestione di durata rilevare che questa condizione è un errore.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-229">Shutdown is a normal stage in the life of a pipeline, so there is no way for the lifetime management code to detect that this condition is an error.</span></span>  
  
11. <span data-ttu-id="aa5cb-230">Per implementare i membri del `ICalculator`, è sufficiente chiamare i membri corrispondenti del `ICalc1Contract` istanza che viene passato al costruttore e restituirà i risultati.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-230">To implement the members of `ICalculator`, simply call the corresponding members of the `ICalc1Contract` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="aa5cb-231">In questo modo il contratto (`ICalc1Contract`) per la visualizzazione (`ICalculator`).</span><span class="sxs-lookup"><span data-stu-id="aa5cb-231">This adapts the contract (`ICalc1Contract`) to the view (`ICalculator`).</span></span>  
  
     <span data-ttu-id="aa5cb-232">Il codice seguente illustra l'adattatore lato host completato.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-232">The following code shows the completed host-side adapter.</span></span>  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. <span data-ttu-id="aa5cb-233">Facoltativamente, compilare la soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-233">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host"></a><span data-ttu-id="aa5cb-234">Creazione dell'Host</span><span class="sxs-lookup"><span data-stu-id="aa5cb-234">Creating the Host</span></span>  
 <span data-ttu-id="aa5cb-235">Un'applicazione host interagisce con il componente aggiuntivo tramite la visualizzazione host del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-235">A host application interacts with the add-in through the host view of the add-in.</span></span> <span data-ttu-id="aa5cb-236">Utilizza i metodi di individuazione e attivazione del componente aggiuntivo forniti dal <xref:System.AddIn.Hosting.AddInStore> e <xref:System.AddIn.Hosting.AddInToken> classi per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa5cb-236">It uses add-in discovery and activation methods provided by the <xref:System.AddIn.Hosting.AddInStore> and <xref:System.AddIn.Hosting.AddInToken> classes to do the following:</span></span>  
  
-   <span data-ttu-id="aa5cb-237">Aggiornare la cache di informazioni sulla pipeline e componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-237">Update the cache of pipeline and add-in information.</span></span>  
  
-   <span data-ttu-id="aa5cb-238">Trovare i componenti aggiuntivi del tipo di visualizzazione host, `ICalculator`, nella directory radice della pipeline specificata.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-238">Find add-ins of the host view type, `ICalculator`, under the specified pipeline root directory.</span></span>  
  
-   <span data-ttu-id="aa5cb-239">Richiedere all'utente di specificare quale componente aggiuntivo da usare.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-239">Prompt the user to specify which add-in to use.</span></span>  
  
-   <span data-ttu-id="aa5cb-240">Attivare il componente aggiuntivo selezionato in un nuovo dominio applicazione con un livello di attendibilità di sicurezza specificato.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-240">Activate the selected add-in in a new application domain with a specified security trust level.</span></span>  
  
-   <span data-ttu-id="aa5cb-241">Eseguire l'oggetto personalizzato `RunCalculator` metodo, che chiama i metodi del componente aggiuntivo come specificato dalla visualizzazione host del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-241">Run the custom `RunCalculator` method, which calls the add-in's methods as specified by the host view of the add-in.</span></span>  
  
#### <a name="to-create-the-host"></a><span data-ttu-id="aa5cb-242">Per creare l'host</span><span class="sxs-lookup"><span data-stu-id="aa5cb-242">To create the host</span></span>  
  
1.  <span data-ttu-id="aa5cb-243">Aggiungere un nuovo progetto denominato `Calc1Host` per il `CalculatorV1` soluzione.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-243">Add a new project named `Calc1Host` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="aa5cb-244">Basandosi sul **applicazione Console** modello.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-244">Base it on the **Console Application** template.</span></span>  
  
2.  <span data-ttu-id="aa5cb-245">Nelle **Esplora soluzioni**, aggiungere un riferimento all'assembly System.AddIn.dll al `Calc1Host` progetto.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-245">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the `Calc1Host` project.</span></span>  
  
3.  <span data-ttu-id="aa5cb-246">Aggiungere un riferimento al progetto il `Calc1HVA` progetto.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-246">Add a project reference to the `Calc1HVA` project.</span></span> <span data-ttu-id="aa5cb-247">Selezionare il riferimento al progetto e nella **delle proprietà** impostare **Copia localmente** al **False**.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-247">Select the project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="aa5cb-248">In Visual Basic, usare il **riferimenti** scheda della finestra **le proprietà del progetto** impostare **Copia localmente** a **False**.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-248">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False**.</span></span>  
  
4.  <span data-ttu-id="aa5cb-249">Rinominare il file di classe (modulo di Visual Basic) `MathHost1`.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-249">Rename the class file (module in Visual Basic) `MathHost1`.</span></span>  
  
5.  <span data-ttu-id="aa5cb-250">In Visual Basic, usare il **applicazione** scheda della finestra di **le proprietà del progetto** la finestra di dialogo per impostare **oggetto di avvio** per **Sub Main**.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-250">In Visual Basic, use the **Application** tab of the **Project Properties** dialog box to set **Startup object** to **Sub Main**.</span></span>  
  
6.  <span data-ttu-id="aa5cb-251">Nel file di classe o modulo, aggiungere un riferimento dello spazio dei nomi a <xref:System.AddIn.Hosting>.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-251">In the class or module file, add a namespace reference to <xref:System.AddIn.Hosting>.</span></span>  
  
7.  <span data-ttu-id="aa5cb-252">Nel file di classe o modulo, aggiungere un riferimento dello spazio dei nomi per la visualizzazione host del componente aggiuntivo: `CalcHVAs`.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-252">In the class or module file, add a namespace reference for the host view of the add-in: `CalcHVAs`.</span></span> <span data-ttu-id="aa5cb-253">(In Visual Basic, il riferimento dello spazio dei nomi è `Calc1HVA.CalcHVAs`, a meno che non siano stati disattivati gli spazi dei nomi predefinito nei progetti Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="aa5cb-253">(In Visual Basic, this namespace reference is `Calc1HVA.CalcHVAs`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="aa5cb-254">In **Esplora soluzioni**, selezionare la soluzione e dal **Project** dal menu **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-254">In **Solution Explorer**, select the solution and from the **Project** menu choose **Properties**.</span></span> <span data-ttu-id="aa5cb-255">Nel **pagine proprietà soluzione** finestra di dialogo, impostare il **progetto di avvio singolo** da questo progetto di applicazione host.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-255">In the **Solution Property Pages** dialog box, set the **Single Startup Project** to be this host application project.</span></span>  
  
9. <span data-ttu-id="aa5cb-256">Nel file di classe o modulo, usare il <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> metodo per aggiornare la cache.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-256">In the class or module file, use the <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> method to update the cache.</span></span> <span data-ttu-id="aa5cb-257">Usare la <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> metodo per ottenere una raccolta di token e usare il <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> metodo per attivare un componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-257">Use the <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> method to get a collection of tokens, and use the <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> method to activate an add-in.</span></span>  
  
     <span data-ttu-id="aa5cb-258">Il codice seguente illustra l'applicazione host completata.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-258">The following code shows the completed host application.</span></span>  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="aa5cb-259">Questo codice presuppone che la struttura di cartelle della pipeline si trova nella cartella dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-259">This code assumes that the pipeline folder structure is located in the application folder.</span></span> <span data-ttu-id="aa5cb-260">Se si trova in un' posizione, modificare la riga di codice che imposta il `addInRoot` variabile, in modo che la variabile contiene il percorso per la struttura di directory della pipeline.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-260">If you located it elsewhere, change the line of code that sets the `addInRoot` variable, so that the variable contains the path to your pipeline directory structure.</span></span>  
  
     <span data-ttu-id="aa5cb-261">Il codice Usa un `ChooseCalculator` metodo per elencare i token e per richiedere all'utente di scegliere un componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-261">The code uses a `ChooseCalculator` method to list the tokens and to prompt the user to choose an add-in.</span></span> <span data-ttu-id="aa5cb-262">Il `RunCalculator` metodo richiede l'immissione di espressioni matematiche semplici, analizza le espressioni che usano il `Parser` classe e visualizza i risultati restituiti dal componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-262">The `RunCalculator` method prompts the user for simple math expressions, parses the expressions using the `Parser` class, and displays the results returned by the add-in.</span></span>  
  
10. <span data-ttu-id="aa5cb-263">Facoltativamente, compilare la soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-263">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in"></a><span data-ttu-id="aa5cb-264">Creazione del componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="aa5cb-264">Creating the Add-In</span></span>  
 <span data-ttu-id="aa5cb-265">Un componente aggiuntivo implementa i metodi specificati dalla visualizzazione componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-265">An add-in implements the methods specified by the add-in view.</span></span> <span data-ttu-id="aa5cb-266">Questo componente aggiuntivo implementa il `Add`, `Subtract`, `Multiply`, e `Divide` operazioni e restituisce i risultati per l'host.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-266">This add-in implements the `Add`, `Subtract`, `Multiply`, and `Divide` operations and returns the results to the host.</span></span>  
  
#### <a name="to-create-the-add-in"></a><span data-ttu-id="aa5cb-267">Per creare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="aa5cb-267">To create the add-in</span></span>  
  
1.  <span data-ttu-id="aa5cb-268">Aggiungere un nuovo progetto denominato `AddInCalcV1` per il `CalculatorV1` soluzione.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-268">Add a new project named `AddInCalcV1` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="aa5cb-269">Basandosi sul **libreria di classi** modello.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-269">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="aa5cb-270">Nelle **Esplora soluzioni**, aggiungere un riferimento all'assembly System.AddIn.dll al progetto.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-270">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the project.</span></span>  
  
3.  <span data-ttu-id="aa5cb-271">Aggiungere un riferimento al progetto il `Calc1AddInView` progetto.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-271">Add a project reference to the `Calc1AddInView` project.</span></span> <span data-ttu-id="aa5cb-272">Selezionare il riferimento al progetto e nella **delle proprietà**, impostare **Copia localmente** al **False**.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-272">Select the project reference, and in **Properties**, set **Copy Local** to **False**.</span></span> <span data-ttu-id="aa5cb-273">In Visual Basic, usare il **riferimenti** scheda della finestra **le proprietà del progetto** impostare **Copia localmente** a **False** per il riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-273">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the project reference.</span></span>  
  
4.  <span data-ttu-id="aa5cb-274">Rinominare la classe `AddInCalcV1`.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-274">Rename the class `AddInCalcV1`.</span></span>  
  
5.  <span data-ttu-id="aa5cb-275">Nel file di classe, aggiungere un riferimento dello spazio dei nomi <xref:System.AddIn> e il segmento di visualizzazione componente aggiuntivo: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="aa5cb-275">In the class file, add a namespace reference to <xref:System.AddIn> and the add-in view segment: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).</span></span>  
  
6.  <span data-ttu-id="aa5cb-276">Si applicano i <xref:System.AddIn.AddInAttribute> dell'attributo di `AddInCalcV1` (classe), per identificare la classe come un componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-276">Apply the <xref:System.AddIn.AddInAttribute> attribute to the `AddInCalcV1` class, to identify the class as an add-in.</span></span>  
  
7.  <span data-ttu-id="aa5cb-277">Verificare i `AddInCalcV1` classe implementare l'interfaccia che rappresenta la visualizzazione componente aggiuntivo: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="aa5cb-277">Make the `AddInCalcV1` class implement the interface that represents the add-in view: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).</span></span>  
  
8.  <span data-ttu-id="aa5cb-278">Implementare i membri di `ICalculator` restituendo i risultati dei calcoli appropriati.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-278">Implement the members of `ICalculator` by returning the results of the appropriate calculations.</span></span>  
  
     <span data-ttu-id="aa5cb-279">Il codice seguente illustra il componente aggiuntivo completato.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-279">The following code shows the completed add-in.</span></span>  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. <span data-ttu-id="aa5cb-280">Facoltativamente, compilare la soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-280">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="deploying-the-pipeline"></a><span data-ttu-id="aa5cb-281">Distribuzione della Pipeline</span><span class="sxs-lookup"><span data-stu-id="aa5cb-281">Deploying the Pipeline</span></span>  
 <span data-ttu-id="aa5cb-282">A questo punto si è pronti compilare e distribuire i segmenti del componente aggiuntivo per la struttura di directory della pipeline richiesta.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-282">You are now ready to build and deploy the add-in segments to the required pipeline directory structure.</span></span>  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a><span data-ttu-id="aa5cb-283">Per distribuire i segmenti della pipeline</span><span class="sxs-lookup"><span data-stu-id="aa5cb-283">To deploy the segments to the pipeline</span></span>  
  
1.  <span data-ttu-id="aa5cb-284">Per ogni progetto nella soluzione, usare il **compilare** scheda della finestra **le proprietà del progetto** (la **compilare** scheda in Visual Basic) per impostare il valore del **percorso di Output**  (la **percorso di output di compilazione** in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="aa5cb-284">For each project in the solution, use the **Build** tab of **Project Properties** (the **Compile** tab in Visual Basic) to set the value of the **Output path** (the **Build output path** in Visual Basic).</span></span> <span data-ttu-id="aa5cb-285">Se la cartella dell'applicazione denominata `MyApp`, ad esempio, i progetti saranno compilati nelle cartelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa5cb-285">If you named your application folder `MyApp`, for example, your projects would build into the following folders:</span></span>  
  
    |<span data-ttu-id="aa5cb-286">Progetto</span><span class="sxs-lookup"><span data-stu-id="aa5cb-286">Project</span></span>|<span data-ttu-id="aa5cb-287">Path</span><span class="sxs-lookup"><span data-stu-id="aa5cb-287">Path</span></span>|  
    |-------------|----------|  
    |<span data-ttu-id="aa5cb-288">AddInCalcV1</span><span class="sxs-lookup"><span data-stu-id="aa5cb-288">AddInCalcV1</span></span>|<span data-ttu-id="aa5cb-289">MyApp\Pipeline\AddIns\CalcV1</span><span class="sxs-lookup"><span data-stu-id="aa5cb-289">MyApp\Pipeline\AddIns\CalcV1</span></span>|  
    |<span data-ttu-id="aa5cb-290">Calc1AddInSideAdapter</span><span class="sxs-lookup"><span data-stu-id="aa5cb-290">Calc1AddInSideAdapter</span></span>|<span data-ttu-id="aa5cb-291">MyApp\Pipeline\AddInSideAdapters</span><span class="sxs-lookup"><span data-stu-id="aa5cb-291">MyApp\Pipeline\AddInSideAdapters</span></span>|  
    |<span data-ttu-id="aa5cb-292">Calc1AddInView</span><span class="sxs-lookup"><span data-stu-id="aa5cb-292">Calc1AddInView</span></span>|<span data-ttu-id="aa5cb-293">MyApp\Pipeline\AddInViews</span><span class="sxs-lookup"><span data-stu-id="aa5cb-293">MyApp\Pipeline\AddInViews</span></span>|  
    |<span data-ttu-id="aa5cb-294">Calc1Contract</span><span class="sxs-lookup"><span data-stu-id="aa5cb-294">Calc1Contract</span></span>|<span data-ttu-id="aa5cb-295">MyApp\Pipeline\Contracts</span><span class="sxs-lookup"><span data-stu-id="aa5cb-295">MyApp\Pipeline\Contracts</span></span>|  
    |<span data-ttu-id="aa5cb-296">Calc1Host</span><span class="sxs-lookup"><span data-stu-id="aa5cb-296">Calc1Host</span></span>|<span data-ttu-id="aa5cb-297">MyApp</span><span class="sxs-lookup"><span data-stu-id="aa5cb-297">MyApp</span></span>|  
    |<span data-ttu-id="aa5cb-298">Calc1HostSideAdapter</span><span class="sxs-lookup"><span data-stu-id="aa5cb-298">Calc1HostSideAdapter</span></span>|<span data-ttu-id="aa5cb-299">MyApp\Pipeline\HostSideAdapters</span><span class="sxs-lookup"><span data-stu-id="aa5cb-299">MyApp\Pipeline\HostSideAdapters</span></span>|  
    |<span data-ttu-id="aa5cb-300">Calc1HVA</span><span class="sxs-lookup"><span data-stu-id="aa5cb-300">Calc1HVA</span></span>|<span data-ttu-id="aa5cb-301">MyApp</span><span class="sxs-lookup"><span data-stu-id="aa5cb-301">MyApp</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="aa5cb-302">Se si è deciso di mettere la struttura di cartelle di pipeline in un percorso diverso dalla cartella dell'applicazione, è necessario modificare i percorsi visualizzati nella tabella di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-302">If you decided to put your pipeline folder structure in a location other than your application folder, you must modify the paths shown in the table accordingly.</span></span> <span data-ttu-id="aa5cb-303">Vedere la discussione dei requisiti di directory della pipeline [requisiti di sviluppo delle Pipeline](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="aa5cb-303">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
2.  <span data-ttu-id="aa5cb-304">Compilare la soluzione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-304">Build the Visual Studio solution.</span></span>  
  
3.  <span data-ttu-id="aa5cb-305">Controllare le directory dell'applicazione e la pipeline per garantire che gli assembly sono stati copiati nelle directory corrette e che nessun copie aggiuntive di assembly siano state installate nelle cartelle non corrette.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-305">Check the application and pipeline directories to ensure that the assemblies were copied to the correct directories and that no extra copies of assemblies were installed in the wrong folders.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aa5cb-306">Se non è stato modificato **Copia localmente** al **False** per il `Calc1AddInView` riferimento nel progetto di `AddInCalcV1` progetti, problemi di contesto del caricatore impedirà il componente aggiuntivo che si trova.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-306">If you did not change **Copy Local** to **False** for the `Calc1AddInView` project reference in the `AddInCalcV1` project, loader context problems will prevent the add-in from being located.</span></span>  
  
     <span data-ttu-id="aa5cb-307">Per informazioni sulla distribuzione per la pipeline, vedere [requisiti di sviluppo delle Pipeline](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="aa5cb-307">For information about deploying to the pipeline, see [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
## <a name="running-the-host-application"></a><span data-ttu-id="aa5cb-308">Esecuzione dell'applicazione Host</span><span class="sxs-lookup"><span data-stu-id="aa5cb-308">Running the Host Application</span></span>  
 <span data-ttu-id="aa5cb-309">A questo punto si è pronti eseguire l'host e interagire con il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-309">You are now ready to run the host and interact with the add-in.</span></span>  
  
#### <a name="to-run-the-host-application"></a><span data-ttu-id="aa5cb-310">Per eseguire l'applicazione host</span><span class="sxs-lookup"><span data-stu-id="aa5cb-310">To run the host application</span></span>  
  
1.  <span data-ttu-id="aa5cb-311">Al prompt dei comandi, passare alla directory dell'applicazione ed eseguire l'applicazione host, `Calc1Host.exe`.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-311">At the command prompt, go to the application directory and run the host application, `Calc1Host.exe`.</span></span>  
  
2.  <span data-ttu-id="aa5cb-312">L'host consente di trovare tutti i componenti aggiuntivi disponibili del tipo e viene richiesto di selezionare un componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-312">The host finds all available add-ins of its type and prompts you to select an add-in.</span></span> <span data-ttu-id="aa5cb-313">Immettere **1** per il componente aggiuntivo è disponibile solo.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-313">Enter **1** for the only available add-in.</span></span>  
  
3.  <span data-ttu-id="aa5cb-314">Immettere un'equazione per la Calcolatrice, ad esempio **2 + 2**.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-314">Enter an equation for the calculator, such as **2 + 2**.</span></span> <span data-ttu-id="aa5cb-315">Devono essere presenti spazi tra i numeri e l'operatore.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-315">There must be spaces between the numbers and the operator.</span></span>  
  
4.  <span data-ttu-id="aa5cb-316">Tipo di **uscire** e premere il **invio** un tasto per chiudere l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="aa5cb-316">Type **exit** and press the **Enter** key to close the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa5cb-317">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa5cb-317">See Also</span></span>  
- [<span data-ttu-id="aa5cb-318">Procedura dettagliata: Abilitazione della compatibilità con le versioni precedenti in base alle modifiche dell'Host</span><span class="sxs-lookup"><span data-stu-id="aa5cb-318">Walkthrough: Enabling Backward Compatibility as Your Host Changes</span></span>](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
-  [<span data-ttu-id="aa5cb-319">Procedura dettagliata: Passaggio di raccolte tra host e componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="aa5cb-319">Walkthrough: Passing Collections Between Hosts and Add-Ins</span></span>](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
-  [<span data-ttu-id="aa5cb-320">Requisiti di sviluppo delle pipeline</span><span class="sxs-lookup"><span data-stu-id="aa5cb-320">Pipeline Development Requirements</span></span>](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
-  [<span data-ttu-id="aa5cb-321">Contratti, viste e adattatori</span><span class="sxs-lookup"><span data-stu-id="aa5cb-321">Contracts, Views, and Adapters</span></span>](https://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c)  
-  [<span data-ttu-id="aa5cb-322">Sviluppo pipeline</span><span class="sxs-lookup"><span data-stu-id="aa5cb-322">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)

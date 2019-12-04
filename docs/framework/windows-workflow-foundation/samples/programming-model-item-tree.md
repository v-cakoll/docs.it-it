---
title: Programmazione dell'albero degli elementi del modello
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: efda69ac568b0ad9c5fdcf4d42722c5b7dadd3f3
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715671"
---
# <a name="programming-model-item-tree"></a><span data-ttu-id="a8664-102">Programmazione dell'albero degli elementi del modello</span><span class="sxs-lookup"><span data-stu-id="a8664-102">Programming Model Item Tree</span></span>
<span data-ttu-id="a8664-103">In questo esempio viene illustrato come spostarsi nell'albero <xref:System.Activities.Presentation.Model.ModelItem> utilizzando data binding dichiarativo dalla visualizzazione albero Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="a8664-103">This sample demonstrates how to navigate the <xref:System.Activities.Presentation.Model.ModelItem> tree using declarative data binding from the Windows Presentation Foundation (WPF) Tree View.</span></span>

## <a name="sample-details"></a><span data-ttu-id="a8664-104">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="a8664-104">Sample Details</span></span>
 <span data-ttu-id="a8664-105">L'albero <xref:System.Activities.Presentation.Model.ModelItem> è l'astrazione usata dall'infrastruttura di Windows Progettazione flussi di lavoro per esporre i dati sull'istanza sottostante in fase di modifica.</span><span class="sxs-lookup"><span data-stu-id="a8664-105">The <xref:System.Activities.Presentation.Model.ModelItem> tree is the abstraction that is used by the Windows Workflow Designer infrastructure to expose the data about the underlying instance being edited.</span></span> <span data-ttu-id="a8664-106">La figura seguente illustra i diversi livelli di infrastruttura all'interno del Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a8664-106">The following illustration is a depiction of the various layers of infrastructure within the Workflow Designer.</span></span>

 ![Diagramma che illustra l'architettura del Progettazione flussi di lavoro.](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 <span data-ttu-id="a8664-108">Un oggetto <xref:System.Activities.Presentation.Model.ModelItem> è costituito da un puntatore al valore sottostante e da una raccolta di oggetti <xref:System.Activities.Presentation.Model.ModelProperty>.</span><span class="sxs-lookup"><span data-stu-id="a8664-108">A <xref:System.Activities.Presentation.Model.ModelItem> consists of a pointer to the underlying value, as well as a collection of <xref:System.Activities.Presentation.Model.ModelProperty> objects.</span></span> <span data-ttu-id="a8664-109">Un oggetto <xref:System.Activities.Presentation.Model.ModelProperty> è costituito, a sua volta, da dati quali il nome e il tipo della proprietà e quindi da un puntatore al valore che, a sua volta, è un altro <xref:System.Activities.Presentation.Model.ModelItem>.</span><span class="sxs-lookup"><span data-stu-id="a8664-109">A <xref:System.Activities.Presentation.Model.ModelProperty> object in turn, consists of data such as the name and type of the property and then a pointer to the value, which in turn, is another <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="a8664-110">Un convertitore di valori viene usato per modificare alcuni oggetti <xref:System.Activities.Presentation.Model.ModelItem>restituiti da <xref:System.Activities.Presentation.Model.ModelProperty> in modo che siano riportati correttamente nella visualizzazione albero.</span><span class="sxs-lookup"><span data-stu-id="a8664-110">A value converter is used to manipulate some of the <xref:System.Activities.Presentation.Model.ModelItem>s returned from a <xref:System.Activities.Presentation.Model.ModelProperty> to make them appear correctly in the tree view.</span></span> <span data-ttu-id="a8664-111">Nell'esempio viene dimostrato quindi come programmare in modo imperativo rispetto all'albero <xref:System.Activities.Presentation.Model.ModelItem> usando la sintassi imperativa, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a8664-111">The sample then demonstrates how to imperatively program against the <xref:System.Activities.Presentation.Model.ModelItem> tree using the imperative syntax, as seen in the following example.</span></span>

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="a8664-112">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="a8664-112">To use this sample</span></span>

1. <span data-ttu-id="a8664-113">Aprire la soluzione ProgrammingModelItemTree. sln in Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="a8664-113">Open the ProgrammingModelItemTree.sln solution in Visual Studio 2010.</span></span>

2. <span data-ttu-id="a8664-114">Compilare la soluzione scegliendo **Compila soluzione** dal menu **Compila** .</span><span class="sxs-lookup"><span data-stu-id="a8664-114">Build the solution by selecting **Build Solution** from the **Build** menu.</span></span>

3. <span data-ttu-id="a8664-115">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a8664-115">Press F5 to run the application.</span></span> <span data-ttu-id="a8664-116">Il form WPF viene quindi visualizzato.</span><span class="sxs-lookup"><span data-stu-id="a8664-116">The WPF form is then displayed.</span></span>

4. <span data-ttu-id="a8664-117">Fare clic sul pulsante **Load WF** per caricare il <xref:System.Activities.Presentation.Model.ModelItem> e associarlo alla visualizzazione albero.</span><span class="sxs-lookup"><span data-stu-id="a8664-117">Click the **Load WF** button to load the <xref:System.Activities.Presentation.Model.ModelItem> and bind it to the tree view.</span></span>

5. <span data-ttu-id="a8664-118">Facendo clic sul pulsante **modifica albero degli elementi del modello** viene eseguito il codice precedente per aggiungere un elemento nell'albero e impostare una proprietà.</span><span class="sxs-lookup"><span data-stu-id="a8664-118">Clicking the **Change Model Item Tree** button executes the preceding code to add an item into the tree and set a property.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8664-119">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="a8664-119">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a8664-120">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a8664-120">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="a8664-121">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="a8664-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a8664-122">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="a8664-122">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a><span data-ttu-id="a8664-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8664-123">See also</span></span>

- <xref:System.Windows.Data.IValueConverter>

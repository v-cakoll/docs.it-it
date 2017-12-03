---
title: Servizio casella degli strumenti
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 742212d0-445e-41ed-9739-9ee848ce7f1b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 294c530072b2d694f9aeb54d04b36d72bb6da637
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="toolbox-service"></a><span data-ttu-id="72ede-102">Servizio casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="72ede-102">Toolbox Service</span></span>
<span data-ttu-id="72ede-103">In questo esempio viene illustrato come aggiornare le attività della casella degli strumenti di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] in base al contesto del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72ede-103">This sample demonstrates how to update the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] Toolbox activities based on the context of the workflow.</span></span> <span data-ttu-id="72ede-104">L'esempio contiene un flusso di lavoro che modifica il contenuto della casella degli strumenti in base alla selezione o meno di un'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="72ede-104">The sample contains a workflow that changes the toolbox contents based on whether a custom activity is selected.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="72ede-105">Discussione</span><span class="sxs-lookup"><span data-stu-id="72ede-105">Discussion</span></span>  
 <span data-ttu-id="72ede-106">Durante la creazione di flussi di lavoro, i clienti generalmente desiderano che Casella degli strumenti sia sensibile al contesto.</span><span class="sxs-lookup"><span data-stu-id="72ede-106">During workflow authoring, customers generally want their Toolbox to be context sensitive.</span></span> <span data-ttu-id="72ede-107">Ad esempio, l'utente può volersi assicurare che nella Casella degli strumenti siano visualizzate alcune attività aggiuntive quando un'attività specifica viene aggiunta al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72ede-107">For example, the user may want to ensure that the Toolbox shows a few additional activities when a specific activity is added to the workflow.</span></span> <span data-ttu-id="72ede-108">Se le attività vengono rimosse dal flusso di lavoro, la casella degli strumenti deve riflettere in modo appropriato i requisiti del dominio.</span><span class="sxs-lookup"><span data-stu-id="72ede-108">If the activities are removed from the workflow, the toolbox should react appropriately based on the domain requirements.</span></span>  
  
 <span data-ttu-id="72ede-109">In una finestra di progettazione del flusso di lavoro riallocata è possibile verificare il controllo Casella degli strumenti e assicurarsi che in base alle modifiche del Modello nel flusso di lavoro, l'host attivi modifiche appropriate nel controllo Casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="72ede-109">In a re-hosted workflow designer, you control the Toolbox control and can ensure that based on the Model changes in the workflow, the host triggers appropriate changes in the Toolbox control.</span></span> <span data-ttu-id="72ede-110">Tuttavia, in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], la casella degli strumenti non viene controllata dall'utente e quindi per modificarne il contenuto è necessaria un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="72ede-110">However, in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], the toolbox is not controlled by the user and thus an interface is required to modify its contents.</span></span> <span data-ttu-id="72ede-111">`IActivityToolboxService` è l'interfaccia necessaria.</span><span class="sxs-lookup"><span data-stu-id="72ede-111">`IActivityToolboxService` is that interface.</span></span>  
  
 <span data-ttu-id="72ede-112">L'API fornisce i quattro metodi seguenti.</span><span class="sxs-lookup"><span data-stu-id="72ede-112">The API provides the following four methods.</span></span>  
  
```  
public interface IActivityToolboxService   
{   
        void AddCategory(string categoryName);   
        void RemoveCategory(string categoryName);   
        void AddItem(string qualifiedTypeName, string categoryName);   
        void RemoveItem(string qualifiedTypeName, string categoryName);   
        IList<string> EnumCategories();   
        IList<string> EnumItems(string categoryName);   
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="72ede-113">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="72ede-113">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="72ede-114">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione WorkflowSimulator.sln.</span><span class="sxs-lookup"><span data-stu-id="72ede-114">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WorkflowSimulator.sln solution file.</span></span>  
  
2.  <span data-ttu-id="72ede-115">Premere CTRL+MAIUSC+B per compilare la soluzione,</span><span class="sxs-lookup"><span data-stu-id="72ede-115">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="72ede-116">Aprire il file Workflow.xaml.</span><span class="sxs-lookup"><span data-stu-id="72ede-116">Open the Workflow.xaml file.</span></span>  
  
4.  <span data-ttu-id="72ede-117">Aggiungere un **CustomActivity** trascinando e rilasciandolo dalla casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="72ede-117">Add a **CustomActivity** by dragging and dropping it from the toolbox.</span></span> <span data-ttu-id="72ede-118">Si noti che una categoria della casella degli strumenti aggiuntiva denominata: **nuova categoria WF** con un'attività aggiuntiva **assegnare**.</span><span class="sxs-lookup"><span data-stu-id="72ede-118">Notice that an additional Toolbox category called: **New WF Category** with an additional activity **Assign**.</span></span>  
  
5.  <span data-ttu-id="72ede-119">Deselezionare la **CustomActivity** trascinandovi un'altra attività.</span><span class="sxs-lookup"><span data-stu-id="72ede-119">Now unselect the **CustomActivity** by dragging another activity into it.</span></span>  
  
6.  <span data-ttu-id="72ede-120">L'elemento **assegnare** nella categoria **nuova categoria WF** nella casella degli strumenti viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="72ede-120">The item **Assign** in the category **New WF Category** under Toolbox is now removed.</span></span> <span data-ttu-id="72ede-121">Inoltre, poiché non sono rimasti elementi nella categoria, questa viene anch'essa rimossa.</span><span class="sxs-lookup"><span data-stu-id="72ede-121">Also, because there are no more items left in the category, the category is removed as well.</span></span>  
  
7.  <span data-ttu-id="72ede-122">Selezionare il **CustomActivity** nuovamente e la categoria e **assegnare** attività vengono nuovamente aggiunte.</span><span class="sxs-lookup"><span data-stu-id="72ede-122">Select the **CustomActivity** again and the category and **Assign** activity is added back.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="72ede-123">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="72ede-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="72ede-124">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="72ede-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="72ede-125">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="72ede-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="72ede-126">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="72ede-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\IActivityToolboxService`

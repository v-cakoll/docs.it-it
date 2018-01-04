---
title: "Creazione di attività del flusso di lavoro tramite la classe Activity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 52d29f9cbed65932b3f9e97f0e9275861953b5d0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="bf8f9-102">Creazione di attività del flusso di lavoro tramite la classe Activity</span><span class="sxs-lookup"><span data-stu-id="bf8f9-102">Workflow Activity Authoring Using the Activity Class</span></span>
<span data-ttu-id="bf8f9-103">Il modo più semplice per creare un'attività usando [!INCLUDE[wf](../../../includes/wf-md.md)] in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] consiste nel creare una classe che eredita da <xref:System.Activities.Activity> che crea la funzionalità assemblando personalizzato attività o attività dal [libreria attività incorporata ](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).</span><span class="sxs-lookup"><span data-stu-id="bf8f9-103">The most basic way to create an activity using [!INCLUDE[wf](../../../includes/wf-md.md)] in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="bf8f9-104">In questo argomento viene illustrato come creare un'attività che consente di scrivere due messaggi nella console.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>  
  
### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="bf8f9-105">Per creare un'attività personalizzata usando ActivityDesigner</span><span class="sxs-lookup"><span data-stu-id="bf8f9-105">To create a custom Activity using the activity designer</span></span>  
  
1.  <span data-ttu-id="bf8f9-106">Aprire [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf8f9-106">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="bf8f9-107">Scegliere File, Nuovo, Progetto.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-107">Select File, New, Project.</span></span> <span data-ttu-id="bf8f9-108">Selezionare **Workflow 4.0** in **Visual c#** nel **tipi di progetto** window e selezionare il **v2010** nodo.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="bf8f9-109">Selezionare **libreria attività** nel **modelli** finestra.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="bf8f9-110">Assegnare al nuovo progetto il nome HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-110">Name the new project HelloActivity.</span></span>  
  
3.  <span data-ttu-id="bf8f9-111">Aprire la nuova attività.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-111">Open the new activity.</span></span>  <span data-ttu-id="bf8f9-112">Trascinare un'attività <xref:System.Activities.Statements.Sequence> dalla casella degli strumenti nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>  
  
4.  <span data-ttu-id="bf8f9-113">Trascinare un'attività <xref:System.Activities.Statements.WriteLine> nell'attività <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="bf8f9-114">Immettere `"Hello World"` (con le virgolette) nei **testo** campo.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>  
  
5.  <span data-ttu-id="bf8f9-115">Trascinare una seconda attività <xref:System.Activities.Statements.WriteLine> nell'attività <xref:System.Activities.Statements.Sequence>, al di sotto della prima.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="bf8f9-116">Immettere `"Goodbye"` (con le virgolette) nei **testo** campo.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>

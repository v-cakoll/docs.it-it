---
title: Tipi deprecati in Windows Workflow Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 422e95a105978749cc56dfe6601fb4518cc11509
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a><span data-ttu-id="89614-102">Tipi deprecati in Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="89614-102">Deprecated types in Windows Workflow Foundation</span></span>
<span data-ttu-id="89614-103">In .NET 4 team del flusso di lavoro ha rilasciato un motore del flusso di lavoro totalmente nuovo nello spazio dei nomi <xref:System.Activities>.</span><span class="sxs-lookup"><span data-stu-id="89614-103">In .NET 4 the Workflow Team released an all new Workflow engine in the <xref:System.Activities> namespace.</span></span> <span data-ttu-id="89614-104">La maggior parte dei tipi in "WF 3" vengono contrassegnati con la versione di .NET 4.5 Beta <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, e <xref:System.Workflow.Runtime> gli spazi dei nomi come obsoleto.</span><span class="sxs-lookup"><span data-stu-id="89614-104">With the release of .NET 4.5 Beta we are marking most of the types in the "WF 3" <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, and  <xref:System.Workflow.Runtime> namespaces as obsolete.</span></span>  
  
## <a name="obsolete-namespaces-and-tools"></a><span data-ttu-id="89614-105">Spazi dei nomi e strumenti obsoleti</span><span class="sxs-lookup"><span data-stu-id="89614-105">Obsolete namespaces and tools</span></span>  
 <span data-ttu-id="89614-106">Gli assembly seguenti includono uno o più tipi pubblici che saranno deprecati:</span><span class="sxs-lookup"><span data-stu-id="89614-106">The following assemblies have one or more public types that will be deprecated:</span></span>  
  
-   <span data-ttu-id="89614-107">System.Workflow.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="89614-107">System.Workflow.Activities.dll</span></span>  
  
-   <span data-ttu-id="89614-108">System.Workflow.ComponentModel.dll</span><span class="sxs-lookup"><span data-stu-id="89614-108">System.Workflow.ComponentModel.dll</span></span>  
  
-   <span data-ttu-id="89614-109">System.Workflow.Runtime.dll</span><span class="sxs-lookup"><span data-stu-id="89614-109">System.Workflow.Runtime.dll</span></span>  
  
-   <span data-ttu-id="89614-110">System.WorkflowServices.dll</span><span class="sxs-lookup"><span data-stu-id="89614-110">System.WorkflowServices.dll</span></span>  
  
-   <span data-ttu-id="89614-111">Microsoft.Workflow.DebugController.dll</span><span class="sxs-lookup"><span data-stu-id="89614-111">Microsoft.Workflow.DebugController.dll</span></span>  
  
-   <span data-ttu-id="89614-112">Microsoft.Workflow.Compiler.exe</span><span class="sxs-lookup"><span data-stu-id="89614-112">Microsoft.Workflow.Compiler.exe</span></span>  
  
-   <span data-ttu-id="89614-113">Wfc.exe</span><span class="sxs-lookup"><span data-stu-id="89614-113">Wfc.exe</span></span>  
  
 <span data-ttu-id="89614-114">Di conseguenza, i clienti che usano le API di WF 3 deprecate riceveranno avvisi di compilazione con un messaggio simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="89614-114">As a result, customers who are using the deprecated WF 3 APIs will encounter build warnings with a message similar to the following:</span></span>  
  
 <span data-ttu-id="89614-115">**Avviso BC40000: X è obsoleto: tipi di WF 3 sono deprecati. Usare WF 4.**</span><span class="sxs-lookup"><span data-stu-id="89614-115">**Warning BC40000: X is obsolete: WF 3 types are deprecated. Please use WF 4 instead.**</span></span> <span data-ttu-id="89614-116">I tipi verranno rimossi da .NET Framework in una versione futura, ma non è stato ancora determinato l'arco di tempo (non in 4.5).</span><span class="sxs-lookup"><span data-stu-id="89614-116">We will remove the types from the .NET Framework in a future release, but we have not yet determined that timeframe (not in 4.5).</span></span> <span data-ttu-id="89614-117">L'attuale passaggio intende comunicare la direttiva ai clienti concedendo loro il tempo sufficiente per passare al nuovo modello WF4.</span><span class="sxs-lookup"><span data-stu-id="89614-117">This current step allows us to communicate our direction to our customers and allow them plenty of time to move to the new WF4 model.</span></span> <span data-ttu-id="89614-118">È, naturalmente, continuerà a supportare questi tipi in WF 3 il [ciclo di vita del supporto Microsoft](http://aka.ms/MicrosoftSupportLifecycle).</span><span class="sxs-lookup"><span data-stu-id="89614-118">We will, of course, continue to support these WF 3 types under the [Microsoft Support Lifecycle Policy](http://aka.ms/MicrosoftSupportLifecycle).</span></span> <span data-ttu-id="89614-119">Le applicazioni in WF3 esistenti verranno eseguite senza problemi in .NET 4.5 e [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] supporterà le nuove e soluzioni esistenti basate su WF3.</span><span class="sxs-lookup"><span data-stu-id="89614-119">Existing WF3 applications will run without issue on .NET 4.5, and [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] will support new and existing WF3-based solutions.</span></span>  
  
 <span data-ttu-id="89614-120">I tipi relativi alle regole nello spazio dei nomi <xref:System.Workflow.Activities.Rules>, che non hanno una sostituzione in WF 4.5, non sono stati deprecati.</span><span class="sxs-lookup"><span data-stu-id="89614-120">Rules related types in the <xref:System.Workflow.Activities.Rules> namespace, which do not have a replacement in WF 4.5, have not been deprecated.</span></span>  
  
 <span data-ttu-id="89614-121">I clienti che desiderano eseguire la migrazione delle applicazioni a WF 4 troverà la Guida in linea di [Guida alla migrazione del flusso di lavoro 4](migration-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="89614-121">Customers who want to migrate their applications to WF 4 will find help in the [Workflow 4 Migration Guidance](migration-guidance.md).</span></span>

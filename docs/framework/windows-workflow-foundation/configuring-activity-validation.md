---
title: "Configurazione della convalida di attività"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d17a640db012730ae8f5329f4e625823a4f5bff2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="configuring-activity-validation"></a><span data-ttu-id="55634-102">Configurazione della convalida di attività</span><span class="sxs-lookup"><span data-stu-id="55634-102">Configuring Activity Validation</span></span>
<span data-ttu-id="55634-103">La convalida delle attività consente agli autori e agli utenti di attività di identificare e segnalare errori nella configurazione di un'attività prima della relativa esecuzione.</span><span class="sxs-lookup"><span data-stu-id="55634-103">Activity validation enables activity authors and users to identify and report errors in an activity’s configuration prior to its execution.</span></span> [!INCLUDE[wf](../../../includes/wf-md.md)]<span data-ttu-id="55634-104"> offre i seguenti tre tipi di convalida delle attività:</span><span class="sxs-lookup"><span data-stu-id="55634-104"> provides the following three types of activity validation:</span></span>  
  
-   <span data-ttu-id="55634-105">Attributi `RequiredArgument` e `OverloadGroup`.</span><span class="sxs-lookup"><span data-stu-id="55634-105">`RequiredArgument` and `OverloadGroup` attributes.</span></span>  
  
-   <span data-ttu-id="55634-106">Convalida basata su codice imperativo.</span><span class="sxs-lookup"><span data-stu-id="55634-106">Imperative code-based validation.</span></span>  
  
-   <span data-ttu-id="55634-107">Vincoli dichiarativi.</span><span class="sxs-lookup"><span data-stu-id="55634-107">Declarative constraints.</span></span>  
  
 <span data-ttu-id="55634-108">Gli attributi `RequiredArgument` e `OverloadGroup` indicano che determinati argomenti di un'attività sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="55634-108">`RequiredArgument` and `OverloadGroup` attributes indicate that certain arguments on an activity are required.</span></span> <span data-ttu-id="55634-109">La convalida basata su codice imperativo fornisce un modo semplice per la convalida automatica di un'attività mentre i vincoli dichiarativi abilitano la convalida dell'attività e della relativa relazione con il flusso di lavoro contenitore.</span><span class="sxs-lookup"><span data-stu-id="55634-109">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and declarative constraints enable validation about the activity and its relationship with the containing workflow.</span></span> <span data-ttu-id="55634-110">Se un'attività non viene configurata correttamente in base ai requisiti di convalida, vengono restituiti errori e avvisi di convalida.</span><span class="sxs-lookup"><span data-stu-id="55634-110">If an activity is not configured properly according to the validation requirements, validation errors and warnings are returned.</span></span> <span data-ttu-id="55634-111">Se il flusso di lavoro contenitore viene creato tramite l'utilità di progettazione del flusso di lavoro, gli eventuali errori e avvisi di convalida vengono visualizzati nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="55634-111">If the containing workflow is created using the workflow designer, any validation errors and warnings are displayed in the designer.</span></span> <span data-ttu-id="55634-112">Se il flusso di lavoro viene creato al di fuori dell'utilità di progettazione del flusso di lavoro, gli eventuali errori di convalida vengono restituiti quando il flusso di lavoro viene richiamato.</span><span class="sxs-lookup"><span data-stu-id="55634-112">If the workflow is created outside of the workflow designer any validation errors are returned when the workflow is invoked.</span></span> <span data-ttu-id="55634-113">Indipendentemente dalla modalità con la quale il flusso di lavoro viene creato, se con errori di convalida, un flusso di lavoro non può mai essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="55634-113">Regardless of how the workflow was created, a workflow with validation errors is never allowed to execute.</span></span> <span data-ttu-id="55634-114">Contenuto della sezione viene fornita una panoramica su questi tipi di convalida delle attività e su come viene richiamata la convalida delle attività.</span><span class="sxs-lookup"><span data-stu-id="55634-114">This section provides an overview of these types of activity validation and how activity validation is invoked.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55634-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="55634-115">In This Section</span></span>  
 [<span data-ttu-id="55634-116">Argomenti obbligatori e gruppi di overload</span><span class="sxs-lookup"><span data-stu-id="55634-116">Required Arguments and Overload Groups</span></span>](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md)  
 <span data-ttu-id="55634-117">Viene descritto come usare gli attributi `RequiredArgument` e `OverloadGroup` per fornire la convalida.</span><span class="sxs-lookup"><span data-stu-id="55634-117">Describes how to use the `RequiredArgument` and `OverloadGroup` attributes to provide validation.</span></span>  
  
 [<span data-ttu-id="55634-118">Convalida basata su codice imperativo</span><span class="sxs-lookup"><span data-stu-id="55634-118">Imperative Code-Based Validation</span></span>](../../../docs/framework/windows-workflow-foundation/imperative-code-based-validation.md)  
 <span data-ttu-id="55634-119">Viene descritto come usare la convalida basata su codice per attività basate sugli oggetti <xref:System.Activities.CodeActivity> e <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="55634-119">Describes how to use code-based validation for <xref:System.Activities.CodeActivity> and <xref:System.Activities.NativeActivity> based activities.</span></span>  
  
 [<span data-ttu-id="55634-120">Vincoli dichiarativi</span><span class="sxs-lookup"><span data-stu-id="55634-120">Declarative Constraints</span></span>](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md)  
 <span data-ttu-id="55634-121">Viene descritto come usare vincoli dichiarativi per fornire la convalida delle attività complessa.</span><span class="sxs-lookup"><span data-stu-id="55634-121">Describes how to use declarative constraints to provide complex activity validation.</span></span>  
  
 [<span data-ttu-id="55634-122">Richiamo della convalida di attività</span><span class="sxs-lookup"><span data-stu-id="55634-122">Invoking Activity Validation</span></span>](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md)  
 <span data-ttu-id="55634-123">Viene illustrato quando la convalida delle attività viene richiamata automaticamente e come richiamare la convalida in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="55634-123">Discusses when activity validation is invoked automatically and how to explicitly invoke validation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="55634-124">Riferimento</span><span class="sxs-lookup"><span data-stu-id="55634-124">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="55634-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="55634-125">Related Sections</span></span>

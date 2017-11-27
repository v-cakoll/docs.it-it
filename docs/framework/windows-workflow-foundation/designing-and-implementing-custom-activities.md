---
title: "Progettazione e implementazione di attività personalizzate"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
caps.latest.revision: "22"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f9243761803bc8b68ce37b3d3ad310e8bb7f93d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="designing-and-implementing-custom-activities"></a><span data-ttu-id="dc326-102">Progettazione e implementazione di attività personalizzate</span><span class="sxs-lookup"><span data-stu-id="dc326-102">Designing and Implementing Custom Activities</span></span>
<span data-ttu-id="dc326-103">Le attività personalizzate in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] vengono create assemblando le attività fornite dal sistema nelle attività composte o creando nuovi tipi che derivano dall'oggetto <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> o <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="dc326-103">Custom activities in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] are created by either assembling system-provided activities into composite activities or by creating new types that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="dc326-104">Contenuto della sezione viene illustrato come creare attività personalizzate con uno dei metodi.</span><span class="sxs-lookup"><span data-stu-id="dc326-104">This section describes how to create custom activities with either method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dc326-105">Le attività personalizzate vengono visualizzate per impostazione predefinita nella finestra di progettazione del flusso di lavoro come un semplice rettangolo con il nome dell'attività.</span><span class="sxs-lookup"><span data-stu-id="dc326-105">Custom activities by default display within the workflow designer as a simple rectangle with the activity’s name.</span></span> <span data-ttu-id="dc326-106">Per fornire una rappresentazione visiva personalizzata dell'attività nella finestra di progettazione del flusso di lavoro è inoltre necessario creare una finestra di progettazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="dc326-106">To provide a custom visual representation of your activity in the workflow designer you must also create a custom designer.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="dc326-107">[Tramite gli ActivityDesigner personalizzati e modelli](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="dc326-107"> [Using Custom Activity Designers and Templates](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dc326-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="dc326-108">In This Section</span></span>  
 [<span data-ttu-id="dc326-109">Opzioni di creazione di attività</span><span class="sxs-lookup"><span data-stu-id="dc326-109">Activity Authoring Options</span></span>](../../../docs/framework/windows-workflow-foundation/activity-authoring-options-in-wf.md)  
 <span data-ttu-id="dc326-110">Viene illustrata la creazione di stili disponibili in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc326-110">Discusses the authoring styles available in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="dc326-111">Uso di un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="dc326-111">Using a custom activity</span></span>](../../../docs/framework/windows-workflow-foundation/using-a-custom-activity.md)  
 <span data-ttu-id="dc326-112">Viene descritto come aggiungere un'attività personalizzata a un progetto flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dc326-112">Describes how to add a custom activity to a workflow project.</span></span>  
  
  [<span data-ttu-id="dc326-113">Creazione di attività asincrone</span><span class="sxs-lookup"><span data-stu-id="dc326-113">Creating Asynchronous Activities</span></span>](../../../docs/framework/windows-workflow-foundation/creating-asynchronous-activities-in-wf.md)  
 <span data-ttu-id="dc326-114">Viene illustrato come creare attività asincrone.</span><span class="sxs-lookup"><span data-stu-id="dc326-114">Describes how to create asynchronous activities.</span></span>  
  
 [<span data-ttu-id="dc326-115">Configurazione della convalida di attività</span><span class="sxs-lookup"><span data-stu-id="dc326-115">Configuring Activity Validation</span></span>](../../../docs/framework/windows-workflow-foundation/configuring-activity-validation.md)  
 <span data-ttu-id="dc326-116">Viene illustrato come usare la convalida delle attività per identificare e segnalare errori nella configurazione di un'attività prima della relativa esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dc326-116">Describes how activity validation can be used to identify and report errors in an activity’s configuration prior to its execution.</span></span>  
  
 [<span data-ttu-id="dc326-117">Creazione di un'attività in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="dc326-117">Creating an Activity at Runtime</span></span>](../../../docs/framework/windows-workflow-foundation/creating-an-activity-at-runtime-with-dynamicactivity.md)  
 <span data-ttu-id="dc326-118">Viene illustrato come creare attività in fase di esecuzione usando <xref:System.Activities.DynamicActivity>.</span><span class="sxs-lookup"><span data-stu-id="dc326-118">Discusses how to create activities at runtime using <xref:System.Activities.DynamicActivity>.</span></span>  
  
 [<span data-ttu-id="dc326-119">Proprietà di esecuzione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dc326-119">Workflow Execution Properties</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-execution-properties.md)  
 <span data-ttu-id="dc326-120">Viene illustrato come usare le proprietà di esecuzione del flusso di lavoro per aggiungere proprietà specifiche del contesto all'ambiente di un'attività.</span><span class="sxs-lookup"><span data-stu-id="dc326-120">Describes how to use workflow execution properties to add context specific properties to an activity’s environment</span></span>  
  
 [<span data-ttu-id="dc326-121">Uso di delegati di attività</span><span class="sxs-lookup"><span data-stu-id="dc326-121">Using Activity Delegates</span></span>](../../../docs/framework/windows-workflow-foundation/using-activity-delegates.md)  
 <span data-ttu-id="dc326-122">Viene illustrato come creare e usare attività che contengono delegati di attività.</span><span class="sxs-lookup"><span data-stu-id="dc326-122">Discusses how to author and use activities that contain activity delegates.</span></span>  
  
 [<span data-ttu-id="dc326-123">Localizzazione di attività</span><span class="sxs-lookup"><span data-stu-id="dc326-123">Activity Localization</span></span>](../../../docs/framework/windows-workflow-foundation/activity-localization.md)  
 <span data-ttu-id="dc326-124">Viene illustrato come usare la localizzazione di risorse di tipo stringa nelle attività.</span><span class="sxs-lookup"><span data-stu-id="dc326-124">Describes how to use localization of string resources in activities.</span></span>  
  
 [<span data-ttu-id="dc326-125">Uso di estensioni di attività</span><span class="sxs-lookup"><span data-stu-id="dc326-125">Using Activity Extensions</span></span>](../../../docs/framework/windows-workflow-foundation/using-activity-extensions.md)  
 <span data-ttu-id="dc326-126">Viene descritto come creare e usare le estensioni di attività.</span><span class="sxs-lookup"><span data-stu-id="dc326-126">Describes how to author and use activity extensions.</span></span>  
  
 [<span data-ttu-id="dc326-127">Utilizzo di feed OData da un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dc326-127">Consuming OData Feeds from a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/consuming-odata-feeds-from-a-workflow.md)  
 <span data-ttu-id="dc326-128">Vengono descritti i diversi metodi per chiamare WCF Data Services da un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dc326-128">Describes several methods for calling a WCF Data Service from a workflow.</span></span>  
  
 [<span data-ttu-id="dc326-129">Ambito e visibilità della definizione di attività</span><span class="sxs-lookup"><span data-stu-id="dc326-129">Activity Definition Scoping and Visibility</span></span>](../../../docs/framework/windows-workflow-foundation/activity-definition-scoping-and-visibility.md)  
 <span data-ttu-id="dc326-130">Vengono descritte le opzioni e le regole per definire l'ambito dei dati e la visibilità dei membri per le attività.</span><span class="sxs-lookup"><span data-stu-id="dc326-130">Describes the options and rules for defining data scoping and member visibility for activities.</span></span>

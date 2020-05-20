---
title: Progettazione e implementazione di attività personalizzate
description: Questo articolo fornisce le risorse per la creazione di attività personalizzate in Workflow Foundation creando attività composite o creando nuovi tipi di attività.
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: 9c184bff9518bb5581f3bf4cd408db224736192b
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419993"
---
# <a name="designing-and-implementing-custom-activities"></a><span data-ttu-id="8f0e5-103">Progettazione e implementazione di attività personalizzate</span><span class="sxs-lookup"><span data-stu-id="8f0e5-103">Designing and Implementing Custom Activities</span></span>
<span data-ttu-id="8f0e5-104">Le attività personalizzate in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] vengono create assemblando le attività fornite dal sistema nelle attività composte o creando nuovi tipi che derivano dall'oggetto <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> o <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="8f0e5-104">Custom activities in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] are created by either assembling system-provided activities into composite activities or by creating new types that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="8f0e5-105">Contenuto della sezione viene illustrato come creare attività personalizzate con uno dei metodi.</span><span class="sxs-lookup"><span data-stu-id="8f0e5-105">This section describes how to create custom activities with either method.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8f0e5-106">Le attività personalizzate vengono visualizzate per impostazione predefinita nella finestra di progettazione del flusso di lavoro come un semplice rettangolo con il nome dell'attività.</span><span class="sxs-lookup"><span data-stu-id="8f0e5-106">Custom activities by default display within the workflow designer as a simple rectangle with the activity’s name.</span></span> <span data-ttu-id="8f0e5-107">Per fornire una rappresentazione visiva personalizzata dell'attività nella finestra di progettazione del flusso di lavoro è inoltre necessario creare una finestra di progettazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="8f0e5-107">To provide a custom visual representation of your activity in the workflow designer you must also create a custom designer.</span></span> <span data-ttu-id="8f0e5-108">Per altre informazioni, vedere [uso di ActivityDesigner e modelli personalizzati](using-custom-activity-designers-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="8f0e5-108">For more information, see [Using Custom Activity Designers and Templates](using-custom-activity-designers-and-templates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f0e5-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="8f0e5-109">In This Section</span></span>  
 [<span data-ttu-id="8f0e5-110">Opzioni di creazione di attività</span><span class="sxs-lookup"><span data-stu-id="8f0e5-110">Activity Authoring Options</span></span>](activity-authoring-options-in-wf.md)  
 <span data-ttu-id="8f0e5-111">Viene illustrata la creazione di stili disponibili in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f0e5-111">Discusses the authoring styles available in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="8f0e5-112">Uso di un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="8f0e5-112">Using a custom activity</span></span>](using-a-custom-activity.md)  
 <span data-ttu-id="8f0e5-113">Viene descritto come aggiungere un'attività personalizzata a un progetto flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8f0e5-113">Describes how to add a custom activity to a workflow project.</span></span>  
  
  [<span data-ttu-id="8f0e5-114">Creazione di attività asincrone</span><span class="sxs-lookup"><span data-stu-id="8f0e5-114">Creating Asynchronous Activities</span></span>](creating-asynchronous-activities-in-wf.md)  
 <span data-ttu-id="8f0e5-115">Viene illustrato come creare attività asincrone.</span><span class="sxs-lookup"><span data-stu-id="8f0e5-115">Describes how to create asynchronous activities.</span></span>  
  
 [<span data-ttu-id="8f0e5-116">Configurazione della convalida di attività</span><span class="sxs-lookup"><span data-stu-id="8f0e5-116">Configuring Activity Validation</span></span>](configuring-activity-validation.md)  
 <span data-ttu-id="8f0e5-117">Viene illustrato come usare la convalida delle attività per identificare e segnalare errori nella configurazione di un'attività prima della relativa esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8f0e5-117">Describes how activity validation can be used to identify and report errors in an activity’s configuration prior to its execution.</span></span>  
  
 [<span data-ttu-id="8f0e5-118">Creazione di un'attività in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="8f0e5-118">Creating an Activity at Runtime</span></span>](creating-an-activity-at-runtime-with-dynamicactivity.md)  
 <span data-ttu-id="8f0e5-119">Viene illustrato come creare attività in fase di esecuzione usando <xref:System.Activities.DynamicActivity>.</span><span class="sxs-lookup"><span data-stu-id="8f0e5-119">Discusses how to create activities at runtime using <xref:System.Activities.DynamicActivity>.</span></span>  
  
 [<span data-ttu-id="8f0e5-120">Proprietà di esecuzione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8f0e5-120">Workflow Execution Properties</span></span>](workflow-execution-properties.md)  
 <span data-ttu-id="8f0e5-121">Viene illustrato come usare le proprietà di esecuzione del flusso di lavoro per aggiungere proprietà specifiche del contesto all'ambiente di un'attività.</span><span class="sxs-lookup"><span data-stu-id="8f0e5-121">Describes how to use workflow execution properties to add context specific properties to an activity’s environment</span></span>  
  
 [<span data-ttu-id="8f0e5-122">Uso di delegati di attività</span><span class="sxs-lookup"><span data-stu-id="8f0e5-122">Using Activity Delegates</span></span>](using-activity-delegates.md)  
 <span data-ttu-id="8f0e5-123">Viene illustrato come creare e usare attività che contengono delegati di attività.</span><span class="sxs-lookup"><span data-stu-id="8f0e5-123">Discusses how to author and use activities that contain activity delegates.</span></span>
  
 [<span data-ttu-id="8f0e5-124">Uso di estensioni di attività</span><span class="sxs-lookup"><span data-stu-id="8f0e5-124">Using Activity Extensions</span></span>](using-activity-extensions.md)  
 <span data-ttu-id="8f0e5-125">Viene descritto come creare e usare le estensioni di attività.</span><span class="sxs-lookup"><span data-stu-id="8f0e5-125">Describes how to author and use activity extensions.</span></span>  
  
 [<span data-ttu-id="8f0e5-126">Utilizzo di feed OData da un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8f0e5-126">Consuming OData Feeds from a Workflow</span></span>](consuming-odata-feeds-from-a-workflow.md)  
 <span data-ttu-id="8f0e5-127">Vengono descritti i diversi metodi per chiamare WCF Data Services da un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8f0e5-127">Describes several methods for calling a WCF Data Service from a workflow.</span></span>  
  
 [<span data-ttu-id="8f0e5-128">Ambito e visibilità della definizione di attività</span><span class="sxs-lookup"><span data-stu-id="8f0e5-128">Activity Definition Scoping and Visibility</span></span>](activity-definition-scoping-and-visibility.md)  
 <span data-ttu-id="8f0e5-129">Vengono descritte le opzioni e le regole per definire l'ambito dei dati e la visibilità dei membri per le attività.</span><span class="sxs-lookup"><span data-stu-id="8f0e5-129">Describes the options and rules for defining data scoping and member visibility for activities.</span></span>

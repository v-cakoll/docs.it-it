---
title: Progettazione e implementazione di attività personalizzate
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: 673145c856e950c8648a87cb3dcb9665ffa51ba9
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216715"
---
# <a name="designing-and-implementing-custom-activities"></a><span data-ttu-id="5fda0-102">Progettazione e implementazione di attività personalizzate</span><span class="sxs-lookup"><span data-stu-id="5fda0-102">Designing and Implementing Custom Activities</span></span>
<span data-ttu-id="5fda0-103">Le attività personalizzate in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] vengono create assemblando le attività fornite dal sistema nelle attività composte o creando nuovi tipi che derivano dall'oggetto <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> o <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="5fda0-103">Custom activities in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] are created by either assembling system-provided activities into composite activities or by creating new types that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="5fda0-104">Contenuto della sezione viene illustrato come creare attività personalizzate con uno dei metodi.</span><span class="sxs-lookup"><span data-stu-id="5fda0-104">This section describes how to create custom activities with either method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5fda0-105">Le attività personalizzate vengono visualizzate per impostazione predefinita nella finestra di progettazione del flusso di lavoro come un semplice rettangolo con il nome dell'attività.</span><span class="sxs-lookup"><span data-stu-id="5fda0-105">Custom activities by default display within the workflow designer as a simple rectangle with the activity’s name.</span></span> <span data-ttu-id="5fda0-106">Per fornire una rappresentazione visiva personalizzata dell'attività nella finestra di progettazione del flusso di lavoro è inoltre necessario creare una finestra di progettazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5fda0-106">To provide a custom visual representation of your activity in the workflow designer you must also create a custom designer.</span></span> <span data-ttu-id="5fda0-107">Per altre informazioni, vedere [usando gli ActivityDesigner personalizzati e modelli](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="5fda0-107">For more information, see [Using Custom Activity Designers and Templates](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5fda0-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="5fda0-108">In This Section</span></span>  
 [<span data-ttu-id="5fda0-109">Opzioni di creazione di attività</span><span class="sxs-lookup"><span data-stu-id="5fda0-109">Activity Authoring Options</span></span>](../../../docs/framework/windows-workflow-foundation/activity-authoring-options-in-wf.md)  
 <span data-ttu-id="5fda0-110">Viene illustrata la creazione di stili disponibili in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fda0-110">Discusses the authoring styles available in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="5fda0-111">Uso di un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="5fda0-111">Using a custom activity</span></span>](../../../docs/framework/windows-workflow-foundation/using-a-custom-activity.md)  
 <span data-ttu-id="5fda0-112">Viene descritto come aggiungere un'attività personalizzata a un progetto flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5fda0-112">Describes how to add a custom activity to a workflow project.</span></span>  
  
  [<span data-ttu-id="5fda0-113">Creazione di attività asincrone</span><span class="sxs-lookup"><span data-stu-id="5fda0-113">Creating Asynchronous Activities</span></span>](../../../docs/framework/windows-workflow-foundation/creating-asynchronous-activities-in-wf.md)  
 <span data-ttu-id="5fda0-114">Viene illustrato come creare attività asincrone.</span><span class="sxs-lookup"><span data-stu-id="5fda0-114">Describes how to create asynchronous activities.</span></span>  
  
 [<span data-ttu-id="5fda0-115">Configurazione della convalida di attività</span><span class="sxs-lookup"><span data-stu-id="5fda0-115">Configuring Activity Validation</span></span>](../../../docs/framework/windows-workflow-foundation/configuring-activity-validation.md)  
 <span data-ttu-id="5fda0-116">Viene illustrato come usare la convalida delle attività per identificare e segnalare errori nella configurazione di un'attività prima della relativa esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5fda0-116">Describes how activity validation can be used to identify and report errors in an activity’s configuration prior to its execution.</span></span>  
  
 [<span data-ttu-id="5fda0-117">Creazione di un'attività in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="5fda0-117">Creating an Activity at Runtime</span></span>](../../../docs/framework/windows-workflow-foundation/creating-an-activity-at-runtime-with-dynamicactivity.md)  
 <span data-ttu-id="5fda0-118">Viene illustrato come creare attività in fase di esecuzione usando <xref:System.Activities.DynamicActivity>.</span><span class="sxs-lookup"><span data-stu-id="5fda0-118">Discusses how to create activities at runtime using <xref:System.Activities.DynamicActivity>.</span></span>  
  
 [<span data-ttu-id="5fda0-119">Proprietà di esecuzione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="5fda0-119">Workflow Execution Properties</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-execution-properties.md)  
 <span data-ttu-id="5fda0-120">Viene illustrato come usare le proprietà di esecuzione del flusso di lavoro per aggiungere proprietà specifiche del contesto all'ambiente di un'attività.</span><span class="sxs-lookup"><span data-stu-id="5fda0-120">Describes how to use workflow execution properties to add context specific properties to an activity’s environment</span></span>  
  
 [<span data-ttu-id="5fda0-121">Uso di delegati di attività</span><span class="sxs-lookup"><span data-stu-id="5fda0-121">Using Activity Delegates</span></span>](../../../docs/framework/windows-workflow-foundation/using-activity-delegates.md)  
 <span data-ttu-id="5fda0-122">Viene illustrato come creare e usare attività che contengono delegati di attività.</span><span class="sxs-lookup"><span data-stu-id="5fda0-122">Discusses how to author and use activities that contain activity delegates.</span></span>
  
 [<span data-ttu-id="5fda0-123">Uso di estensioni di attività</span><span class="sxs-lookup"><span data-stu-id="5fda0-123">Using Activity Extensions</span></span>](../../../docs/framework/windows-workflow-foundation/using-activity-extensions.md)  
 <span data-ttu-id="5fda0-124">Viene descritto come creare e usare le estensioni di attività.</span><span class="sxs-lookup"><span data-stu-id="5fda0-124">Describes how to author and use activity extensions.</span></span>  
  
 [<span data-ttu-id="5fda0-125">Utilizzo di feed OData da un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="5fda0-125">Consuming OData Feeds from a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/consuming-odata-feeds-from-a-workflow.md)  
 <span data-ttu-id="5fda0-126">Vengono descritti i diversi metodi per chiamare WCF Data Services da un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5fda0-126">Describes several methods for calling a WCF Data Service from a workflow.</span></span>  
  
 [<span data-ttu-id="5fda0-127">Ambito e visibilità della definizione di attività</span><span class="sxs-lookup"><span data-stu-id="5fda0-127">Activity Definition Scoping and Visibility</span></span>](../../../docs/framework/windows-workflow-foundation/activity-definition-scoping-and-visibility.md)  
 <span data-ttu-id="5fda0-128">Vengono descritte le opzioni e le regole per definire l'ambito dei dati e la visibilità dei membri per le attività.</span><span class="sxs-lookup"><span data-stu-id="5fda0-128">Describes the options and rules for defining data scoping and member visibility for activities.</span></span>

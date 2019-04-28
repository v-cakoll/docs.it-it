---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: 98bc1b24da6e65a11a39d133057c1bb55b003a58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613455"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="ae805-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="ae805-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="ae805-102">Comportamento del servizio che consente di specificare impostazioni che controllano la modalità di esecuzione delle istanze del flusso di lavoro, inclusa la persistenza, il comportamento delle eccezioni non gestite e il comportamento di inattività.</span><span class="sxs-lookup"><span data-stu-id="ae805-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="ae805-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ae805-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ae805-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ae805-104">\<behaviors></span></span>  
<span data-ttu-id="ae805-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ae805-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="ae805-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ae805-106">\<behavior></span></span>  
<span data-ttu-id="ae805-107">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="ae805-107">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae805-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae805-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae805-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ae805-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ae805-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ae805-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae805-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="ae805-111">Attributes</span></span>  
  
|<span data-ttu-id="ae805-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="ae805-112">Attribute</span></span>|<span data-ttu-id="ae805-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae805-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ae805-114">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="ae805-114">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="ae805-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ae805-115">Child Elements</span></span>  
 <span data-ttu-id="ae805-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ae805-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae805-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ae805-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ae805-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="ae805-118">Element</span></span>|<span data-ttu-id="ae805-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae805-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae805-120">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ae805-120">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="ae805-121">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="ae805-121">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae805-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae805-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>

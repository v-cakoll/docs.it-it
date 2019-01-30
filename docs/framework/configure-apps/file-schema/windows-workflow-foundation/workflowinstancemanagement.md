---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: baa1ccbe0accd2db701fac9ef53cdc6357713c5d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257421"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="90dde-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="90dde-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="90dde-102">Comportamento del servizio che consente di specificare impostazioni che controllano la modalità di esecuzione delle istanze del flusso di lavoro, inclusa la persistenza, il comportamento delle eccezioni non gestite e il comportamento di inattività.</span><span class="sxs-lookup"><span data-stu-id="90dde-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="90dde-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="90dde-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="90dde-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="90dde-104">\<behaviors></span></span>  
<span data-ttu-id="90dde-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="90dde-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="90dde-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="90dde-106">\<behavior></span></span>  
<span data-ttu-id="90dde-107">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="90dde-107">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90dde-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90dde-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90dde-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="90dde-109">Attributes and Elements</span></span>  
 <span data-ttu-id="90dde-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="90dde-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90dde-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="90dde-111">Attributes</span></span>  
  
|<span data-ttu-id="90dde-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="90dde-112">Attribute</span></span>|<span data-ttu-id="90dde-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90dde-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="90dde-114">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="90dde-114">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="90dde-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="90dde-115">Child Elements</span></span>  
 <span data-ttu-id="90dde-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="90dde-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90dde-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="90dde-117">Parent Elements</span></span>  
  
|<span data-ttu-id="90dde-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="90dde-118">Element</span></span>|<span data-ttu-id="90dde-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90dde-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90dde-120">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="90dde-120">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="90dde-121">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="90dde-121">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90dde-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90dde-122">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>

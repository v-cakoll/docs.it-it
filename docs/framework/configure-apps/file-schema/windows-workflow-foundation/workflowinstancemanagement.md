---
title: '&lt;workflowInstanceManagement&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: ba3d9415efc21012b470fd2e9a7f426ca8f3aad1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662062"
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="ca0c3-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="ca0c3-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="ca0c3-103">Comportamento del servizio che consente di specificare impostazioni che controllano la modalità di esecuzione delle istanze del flusso di lavoro, inclusa la persistenza, il comportamento delle eccezioni non gestite e il comportamento di inattività.</span><span class="sxs-lookup"><span data-stu-id="ca0c3-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="ca0c3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ca0c3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ca0c3-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ca0c3-105">\<behaviors></span></span>  
<span data-ttu-id="ca0c3-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ca0c3-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="ca0c3-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ca0c3-107">\<behavior></span></span>  
<span data-ttu-id="ca0c3-108">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="ca0c3-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca0c3-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca0c3-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca0c3-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ca0c3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ca0c3-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ca0c3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca0c3-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="ca0c3-112">Attributes</span></span>  
  
|<span data-ttu-id="ca0c3-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="ca0c3-113">Attribute</span></span>|<span data-ttu-id="ca0c3-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca0c3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca0c3-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="ca0c3-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="ca0c3-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ca0c3-116">Child Elements</span></span>  
 <span data-ttu-id="ca0c3-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ca0c3-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca0c3-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ca0c3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ca0c3-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="ca0c3-119">Element</span></span>|<span data-ttu-id="ca0c3-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca0c3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca0c3-121">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ca0c3-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="ca0c3-122">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="ca0c3-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca0c3-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca0c3-123">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>

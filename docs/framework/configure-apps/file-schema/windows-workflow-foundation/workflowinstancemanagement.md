---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: aa2edafd9adc0317ed0023ad46688025dcecad67
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397526"
---
# \<workflowInstanceManagement>
<span data-ttu-id="99200-101">Comportamento del servizio che consente di specificare impostazioni che controllano la modalità di esecuzione delle istanze del flusso di lavoro, inclusa la persistenza, il comportamento delle eccezioni non gestite e il comportamento di inattività.</span><span class="sxs-lookup"><span data-stu-id="99200-101">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**  
  
## <a name="syntax"></a><span data-ttu-id="99200-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99200-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99200-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="99200-103">Attributes and Elements</span></span>  
 <span data-ttu-id="99200-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="99200-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99200-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="99200-105">Attributes</span></span>  
  
|<span data-ttu-id="99200-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="99200-106">Attribute</span></span>|<span data-ttu-id="99200-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99200-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99200-108">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="99200-108">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="99200-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="99200-109">Child Elements</span></span>  
 <span data-ttu-id="99200-110">No.</span><span class="sxs-lookup"><span data-stu-id="99200-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99200-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="99200-111">Parent Elements</span></span>  
  
|<span data-ttu-id="99200-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="99200-112">Element</span></span>|<span data-ttu-id="99200-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99200-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99200-114">\<behavior>di\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="99200-114">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="99200-115">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="99200-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99200-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99200-116">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>

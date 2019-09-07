---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: aa2edafd9adc0317ed0023ad46688025dcecad67
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397526"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="ccdb2-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="ccdb2-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="ccdb2-102">Comportamento del servizio che consente di specificare impostazioni che controllano la modalità di esecuzione delle istanze del flusso di lavoro, inclusa la persistenza, il comportamento delle eccezioni non gestite e il comportamento di inattività.</span><span class="sxs-lookup"><span data-stu-id="ccdb2-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="ccdb2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ccdb2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ccdb2-104">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ccdb2-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="ccdb2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ccdb2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="ccdb2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ccdb2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="ccdb2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ccdb2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="ccdb2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> workflowInstanceManagement**</span><span class="sxs-lookup"><span data-stu-id="ccdb2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccdb2-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ccdb2-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccdb2-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ccdb2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ccdb2-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ccdb2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccdb2-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="ccdb2-112">Attributes</span></span>  
  
|<span data-ttu-id="ccdb2-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="ccdb2-113">Attribute</span></span>|<span data-ttu-id="ccdb2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ccdb2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ccdb2-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="ccdb2-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="ccdb2-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ccdb2-116">Child Elements</span></span>  
 <span data-ttu-id="ccdb2-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ccdb2-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ccdb2-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ccdb2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ccdb2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="ccdb2-119">Element</span></span>|<span data-ttu-id="ccdb2-120">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="ccdb2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccdb2-121">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ccdb2-121">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="ccdb2-122">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="ccdb2-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ccdb2-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccdb2-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>

---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 29b6d8982e712a0fa595b3103803f1795adea892
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398559"
---
# \<workflowUnhandledException>
<span data-ttu-id="4d27c-101">Comportamento del servizio che consente di specificare l'azione da intraprendere quando si verifica un'eccezione non gestita all'interno di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4d27c-101">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**  
  
## <a name="syntax"></a><span data-ttu-id="4d27c-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d27c-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d27c-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4d27c-103">Attributes and Elements</span></span>  
 <span data-ttu-id="4d27c-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4d27c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d27c-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="4d27c-105">Attributes</span></span>  
  
|<span data-ttu-id="4d27c-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="4d27c-106">Attribute</span></span>|<span data-ttu-id="4d27c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d27c-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d27c-108">action</span><span class="sxs-lookup"><span data-stu-id="4d27c-108">action</span></span>|<span data-ttu-id="4d27c-109">Stringa che specifica l'azione da intraprendere quando si verifica un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="4d27c-109">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="4d27c-110">L'attributo è di tipo <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="4d27c-110">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d27c-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4d27c-111">Child Elements</span></span>  
 <span data-ttu-id="4d27c-112">No.</span><span class="sxs-lookup"><span data-stu-id="4d27c-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d27c-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4d27c-113">Parent Elements</span></span>  
  
|<span data-ttu-id="4d27c-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d27c-114">Element</span></span>|<span data-ttu-id="4d27c-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d27c-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d27c-116">\<behavior>di\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4d27c-116">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="4d27c-117">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="4d27c-117">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d27c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d27c-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>

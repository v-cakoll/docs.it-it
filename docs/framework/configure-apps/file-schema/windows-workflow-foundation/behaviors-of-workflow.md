---
title: '&lt;i comportamenti&gt; del flusso di lavoro'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 40278c0a3d99dd5c37df1d642b8a2e13e9f62633
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltbehaviorsgt-of-workflow"></a><span data-ttu-id="9636d-102">&lt;i comportamenti&gt; del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9636d-102">&lt;behaviors&gt; of workflow</span></span>
<span data-ttu-id="9636d-103">Questo elemento contiene il **serviceBehaviors** insieme.</span><span class="sxs-lookup"><span data-stu-id="9636d-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="9636d-104">Ogni elemento della raccolta definisce elementi di comportamento utilizzati dai servizi flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9636d-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="9636d-105">Ogni elemento di comportamento è identificato dal relativo univoco **nome** attributo.</span><span class="sxs-lookup"><span data-stu-id="9636d-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="9636d-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9636d-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9636d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9636d-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9636d-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9636d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9636d-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9636d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9636d-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="9636d-110">Attributes</span></span>  
 <span data-ttu-id="9636d-111">Nessuna</span><span class="sxs-lookup"><span data-stu-id="9636d-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9636d-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9636d-112">Child Elements</span></span>  
  
|<span data-ttu-id="9636d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="9636d-113">Element</span></span>|<span data-ttu-id="9636d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9636d-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9636d-115">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9636d-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="9636d-116">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio flusso di lavoro specifico.</span><span class="sxs-lookup"><span data-stu-id="9636d-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9636d-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9636d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9636d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="9636d-118">Element</span></span>|<span data-ttu-id="9636d-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9636d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9636d-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9636d-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="9636d-121">Elemento radice di tutti gli elementi di configurazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9636d-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9636d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9636d-122">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="9636d-123">La configurazione e l'estensione del Runtime dei comportamenti</span><span class="sxs-lookup"><span data-stu-id="9636d-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 83c1bf4beb244b72d2fe3d82d749ff6ae6723baf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltbehaviorsgt-of-workflow"></a><span data-ttu-id="d90ff-102">&lt;i comportamenti&gt; del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d90ff-102">&lt;behaviors&gt; of workflow</span></span>
<span data-ttu-id="d90ff-103">Questo elemento contiene il **serviceBehaviors** insieme.</span><span class="sxs-lookup"><span data-stu-id="d90ff-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="d90ff-104">Ogni elemento della raccolta definisce elementi di comportamento utilizzati dai servizi flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d90ff-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="d90ff-105">Ogni elemento di comportamento è identificato dal relativo univoco **nome** attributo.</span><span class="sxs-lookup"><span data-stu-id="d90ff-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="d90ff-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d90ff-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d90ff-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d90ff-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d90ff-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d90ff-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d90ff-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d90ff-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d90ff-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="d90ff-110">Attributes</span></span>  
 <span data-ttu-id="d90ff-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="d90ff-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d90ff-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d90ff-112">Child Elements</span></span>  
  
|<span data-ttu-id="d90ff-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="d90ff-113">Element</span></span>|<span data-ttu-id="d90ff-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d90ff-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d90ff-115">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d90ff-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="d90ff-116">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio flusso di lavoro specifico.</span><span class="sxs-lookup"><span data-stu-id="d90ff-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d90ff-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d90ff-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d90ff-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="d90ff-118">Element</span></span>|<span data-ttu-id="d90ff-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d90ff-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d90ff-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d90ff-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="d90ff-121">Elemento radice di tutti gli elementi di configurazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d90ff-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d90ff-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d90ff-122">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="d90ff-123">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="d90ff-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

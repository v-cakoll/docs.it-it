---
title: '&lt;i comportamenti&gt; del flusso di lavoro'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 762fd1ff0de7980848ac3921706f406932c7f35d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltbehaviorsgt-of-workflow"></a><span data-ttu-id="2c4c6-102">&lt;i comportamenti&gt; del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2c4c6-102">&lt;behaviors&gt; of workflow</span></span>
<span data-ttu-id="2c4c6-103">Questo elemento contiene il **serviceBehaviors** insieme.</span><span class="sxs-lookup"><span data-stu-id="2c4c6-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="2c4c6-104">Ogni elemento della raccolta definisce elementi di comportamento utilizzati dai servizi flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2c4c6-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="2c4c6-105">Ogni elemento di comportamento è identificato dal relativo univoco **nome** attributo.</span><span class="sxs-lookup"><span data-stu-id="2c4c6-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="2c4c6-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2c4c6-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c4c6-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c4c6-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c4c6-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2c4c6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2c4c6-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2c4c6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c4c6-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="2c4c6-110">Attributes</span></span>  
 <span data-ttu-id="2c4c6-111">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2c4c6-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2c4c6-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2c4c6-112">Child Elements</span></span>  
  
|<span data-ttu-id="2c4c6-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="2c4c6-113">Element</span></span>|<span data-ttu-id="2c4c6-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c4c6-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c4c6-115">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2c4c6-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="2c4c6-116">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio flusso di lavoro specifico.</span><span class="sxs-lookup"><span data-stu-id="2c4c6-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c4c6-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2c4c6-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2c4c6-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="2c4c6-118">Element</span></span>|<span data-ttu-id="2c4c6-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c4c6-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c4c6-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2c4c6-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="2c4c6-121">Elemento radice di tutti gli elementi di configurazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2c4c6-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c4c6-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c4c6-122">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="2c4c6-123">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="2c4c6-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

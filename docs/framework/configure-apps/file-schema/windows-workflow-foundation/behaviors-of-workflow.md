---
title: <behaviors> del flusso di lavoro
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: b7c5cf93a82ac88c25f9c478ad52cf41eb6f6d65
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790299"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="502b9-102">\<i comportamenti > del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="502b9-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="502b9-103">Questo elemento contiene il **serviceBehaviors** raccolta.</span><span class="sxs-lookup"><span data-stu-id="502b9-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="502b9-104">Ogni elemento della raccolta definisce elementi di comportamento utilizzati dai servizi flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="502b9-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="502b9-105">Ogni elemento di comportamento è identificato dal relativo univoco **nome** attributo.</span><span class="sxs-lookup"><span data-stu-id="502b9-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="502b9-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="502b9-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="502b9-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="502b9-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="502b9-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="502b9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="502b9-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="502b9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="502b9-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="502b9-110">Attributes</span></span>  
 <span data-ttu-id="502b9-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="502b9-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="502b9-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="502b9-112">Child Elements</span></span>  
  
|<span data-ttu-id="502b9-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="502b9-113">Element</span></span>|<span data-ttu-id="502b9-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="502b9-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="502b9-115">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="502b9-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="502b9-116">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio flusso di lavoro specifico.</span><span class="sxs-lookup"><span data-stu-id="502b9-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="502b9-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="502b9-117">Parent Elements</span></span>  
  
|<span data-ttu-id="502b9-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="502b9-118">Element</span></span>|<span data-ttu-id="502b9-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="502b9-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="502b9-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="502b9-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="502b9-121">Elemento radice di tutti gli elementi di configurazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="502b9-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="502b9-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="502b9-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="502b9-123">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="502b9-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

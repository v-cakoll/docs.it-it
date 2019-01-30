---
title: <behaviors> del flusso di lavoro
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: e61a2078c5989a3b100e77e6b2f753b0ee5dd934
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271786"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="6de1e-102">\<i comportamenti > del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6de1e-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="6de1e-103">Questo elemento contiene il **serviceBehaviors** raccolta.</span><span class="sxs-lookup"><span data-stu-id="6de1e-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="6de1e-104">Ogni elemento della raccolta definisce elementi di comportamento utilizzati dai servizi flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6de1e-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="6de1e-105">Ogni elemento di comportamento è identificato dal relativo univoco **nome** attributo.</span><span class="sxs-lookup"><span data-stu-id="6de1e-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="6de1e-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6de1e-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6de1e-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6de1e-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6de1e-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6de1e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6de1e-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6de1e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6de1e-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="6de1e-110">Attributes</span></span>  
 <span data-ttu-id="6de1e-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="6de1e-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6de1e-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6de1e-112">Child Elements</span></span>  
  
|<span data-ttu-id="6de1e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="6de1e-113">Element</span></span>|<span data-ttu-id="6de1e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6de1e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6de1e-115">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="6de1e-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="6de1e-116">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio flusso di lavoro specifico.</span><span class="sxs-lookup"><span data-stu-id="6de1e-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6de1e-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6de1e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6de1e-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="6de1e-118">Element</span></span>|<span data-ttu-id="6de1e-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6de1e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6de1e-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6de1e-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="6de1e-121">Elemento radice di tutti gli elementi di configurazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6de1e-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6de1e-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6de1e-122">See also</span></span>
- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="6de1e-123">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="6de1e-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

---
title: <behaviors>del flusso di lavoro
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 05a15cdf5c043eb5d94b36028324310d2b7a8413
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398871"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="03fe6-102">\<comportamenti > del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="03fe6-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="03fe6-103">Questo elemento contiene la raccolta **serviceBehaviors** .</span><span class="sxs-lookup"><span data-stu-id="03fe6-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="03fe6-104">Ogni elemento della raccolta definisce elementi di comportamento utilizzati dai servizi flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="03fe6-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="03fe6-105">Ogni elemento di comportamento è identificato dall'attributo del **nome** univoco.</span><span class="sxs-lookup"><span data-stu-id="03fe6-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
<span data-ttu-id="03fe6-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="03fe6-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="03fe6-107">&nbsp;&nbsp;[ **\<sistema. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="03fe6-107">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="03fe6-108">&nbsp;&nbsp;&nbsp;&nbsp; **\<comportamenti >**</span><span class="sxs-lookup"><span data-stu-id="03fe6-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03fe6-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03fe6-109">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03fe6-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="03fe6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="03fe6-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="03fe6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03fe6-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="03fe6-112">Attributes</span></span>  
 <span data-ttu-id="03fe6-113">Nessuna</span><span class="sxs-lookup"><span data-stu-id="03fe6-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="03fe6-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="03fe6-114">Child Elements</span></span>  
  
|<span data-ttu-id="03fe6-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="03fe6-115">Element</span></span>|<span data-ttu-id="03fe6-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03fe6-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03fe6-117">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="03fe6-117">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="03fe6-118">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio flusso di lavoro specifico.</span><span class="sxs-lookup"><span data-stu-id="03fe6-118">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03fe6-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="03fe6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="03fe6-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="03fe6-120">Element</span></span>|<span data-ttu-id="03fe6-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03fe6-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03fe6-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="03fe6-122">\<system.serviceModel></span></span>](../wcf/system-servicemodel.md)|<span data-ttu-id="03fe6-123">Elemento radice di tutti gli elementi di configurazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="03fe6-123">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03fe6-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03fe6-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="03fe6-125">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="03fe6-125">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

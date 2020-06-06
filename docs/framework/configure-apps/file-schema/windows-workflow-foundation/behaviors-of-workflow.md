---
title: <behaviors>del flusso di lavoro
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 05a15cdf5c043eb5d94b36028324310d2b7a8413
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398871"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="26c34-102">\<behaviors>del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="26c34-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="26c34-103">Questo elemento contiene la raccolta **serviceBehaviors** .</span><span class="sxs-lookup"><span data-stu-id="26c34-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="26c34-104">Ogni elemento della raccolta definisce elementi di comportamento utilizzati dai servizi flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="26c34-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="26c34-105">Ogni elemento di comportamento è identificato dall'attributo del **nome** univoco.</span><span class="sxs-lookup"><span data-stu-id="26c34-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="26c34-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26c34-106">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26c34-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="26c34-107">Attributes and Elements</span></span>  
 <span data-ttu-id="26c34-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="26c34-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26c34-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="26c34-109">Attributes</span></span>  
 <span data-ttu-id="26c34-110">nessuno</span><span class="sxs-lookup"><span data-stu-id="26c34-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="26c34-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="26c34-111">Child Elements</span></span>  
  
|<span data-ttu-id="26c34-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="26c34-112">Element</span></span>|<span data-ttu-id="26c34-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="26c34-113">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="26c34-114">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio flusso di lavoro specifico.</span><span class="sxs-lookup"><span data-stu-id="26c34-114">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="26c34-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="26c34-115">Parent Elements</span></span>  
  
|<span data-ttu-id="26c34-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="26c34-116">Element</span></span>|<span data-ttu-id="26c34-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="26c34-117">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](../wcf/system-servicemodel.md)|<span data-ttu-id="26c34-118">Elemento radice di tutti gli elementi di configurazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="26c34-118">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26c34-119">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="26c34-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="26c34-120">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="26c34-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

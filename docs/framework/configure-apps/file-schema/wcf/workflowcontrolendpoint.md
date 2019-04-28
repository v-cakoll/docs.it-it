---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: a9c16d1036a8177120cd152d4ac211ad084d588e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769642"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="bb0be-101">\<workflowControlEndpoint></span><span class="sxs-lookup"><span data-stu-id="bb0be-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="bb0be-102">Questo elemento di configurazione definisce un endpoint standard per il controllo dell'esecuzione di istanze del flusso di lavoro (creazione, esecuzione, sospensione, terminazione e così via).</span><span class="sxs-lookup"><span data-stu-id="bb0be-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="bb0be-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bb0be-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="bb0be-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="bb0be-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb0be-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb0be-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb0be-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bb0be-106">Attributes and Elements</span></span>  
 <span data-ttu-id="bb0be-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bb0be-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb0be-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="bb0be-108">Attributes</span></span>  
  
|<span data-ttu-id="bb0be-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="bb0be-109">Attribute</span></span>|<span data-ttu-id="bb0be-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb0be-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bb0be-111">name</span><span class="sxs-lookup"><span data-stu-id="bb0be-111">name</span></span>|<span data-ttu-id="bb0be-112">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="bb0be-112">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="bb0be-113">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="bb0be-113">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb0be-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bb0be-114">Child Elements</span></span>  
 <span data-ttu-id="bb0be-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="bb0be-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bb0be-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bb0be-116">Parent Elements</span></span>  
  
|<span data-ttu-id="bb0be-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="bb0be-117">Element</span></span>|<span data-ttu-id="bb0be-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb0be-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb0be-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="bb0be-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="bb0be-120">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="bb0be-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb0be-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb0be-121">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>

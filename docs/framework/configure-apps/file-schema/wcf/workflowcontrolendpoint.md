---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: de0a51ed6f2a878ab3a6ebe15863f1f2925034ce
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272585"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="cee94-101">\<workflowControlEndpoint></span><span class="sxs-lookup"><span data-stu-id="cee94-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="cee94-102">Questo elemento di configurazione definisce un endpoint standard per il controllo dell'esecuzione di istanze del flusso di lavoro (creazione, esecuzione, sospensione, terminazione e così via).</span><span class="sxs-lookup"><span data-stu-id="cee94-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="cee94-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cee94-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="cee94-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="cee94-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cee94-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cee94-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cee94-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cee94-106">Attributes and Elements</span></span>  
 <span data-ttu-id="cee94-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cee94-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cee94-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="cee94-108">Attributes</span></span>  
  
|<span data-ttu-id="cee94-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="cee94-109">Attribute</span></span>|<span data-ttu-id="cee94-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cee94-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cee94-111">name</span><span class="sxs-lookup"><span data-stu-id="cee94-111">name</span></span>|<span data-ttu-id="cee94-112">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="cee94-112">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="cee94-113">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="cee94-113">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cee94-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cee94-114">Child Elements</span></span>  
 <span data-ttu-id="cee94-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cee94-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cee94-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cee94-116">Parent Elements</span></span>  
  
|<span data-ttu-id="cee94-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="cee94-117">Element</span></span>|<span data-ttu-id="cee94-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cee94-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cee94-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="cee94-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="cee94-120">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="cee94-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cee94-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cee94-121">See also</span></span>
- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>

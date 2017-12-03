---
title: '&lt;oggetto workflowControlEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 741968e160683ab38f79effdfa0bdf56053cfb93
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowcontrolendpointgt"></a><span data-ttu-id="7d138-102">&lt;oggetto workflowControlEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="7d138-102">&lt;workflowControlEndpoint&gt;</span></span>
<span data-ttu-id="7d138-103">Questo elemento di configurazione definisce un endpoint standard per il controllo dell'esecuzione di istanze del flusso di lavoro (creazione, esecuzione, sospensione, terminazione e così via).</span><span class="sxs-lookup"><span data-stu-id="7d138-103">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="7d138-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7d138-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7d138-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="7d138-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d138-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d138-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d138-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7d138-107">Attributes and Elements</span></span>  
 <span data-ttu-id="7d138-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7d138-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d138-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="7d138-109">Attributes</span></span>  
  
|<span data-ttu-id="7d138-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="7d138-110">Attribute</span></span>|<span data-ttu-id="7d138-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d138-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d138-112">name</span><span class="sxs-lookup"><span data-stu-id="7d138-112">name</span></span>|<span data-ttu-id="7d138-113">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="7d138-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="7d138-114">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="7d138-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d138-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7d138-115">Child Elements</span></span>  
 <span data-ttu-id="7d138-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7d138-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d138-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7d138-117">Parent Elements</span></span>  
  
|<span data-ttu-id="7d138-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d138-118">Element</span></span>|<span data-ttu-id="7d138-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d138-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d138-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="7d138-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="7d138-121">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="7d138-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d138-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d138-122">See Also</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>

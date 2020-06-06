---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 670c1573fe4378a18c19d0a58fe58241745725bd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854792"
---
# \<workflowControlEndpoint>
<span data-ttu-id="62df2-101">Questo elemento di configurazione definisce un endpoint standard per il controllo dell'esecuzione di istanze del flusso di lavoro (creazione, esecuzione, sospensione, terminazione e così via).</span><span class="sxs-lookup"><span data-stu-id="62df2-101">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="62df2-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62df2-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62df2-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="62df2-103">Attributes and Elements</span></span>  
 <span data-ttu-id="62df2-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="62df2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62df2-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="62df2-105">Attributes</span></span>  
  
|<span data-ttu-id="62df2-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="62df2-106">Attribute</span></span>|<span data-ttu-id="62df2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62df2-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="62df2-108">name</span><span class="sxs-lookup"><span data-stu-id="62df2-108">name</span></span>|<span data-ttu-id="62df2-109">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="62df2-109">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="62df2-110">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="62df2-110">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62df2-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="62df2-111">Child Elements</span></span>  
 <span data-ttu-id="62df2-112">No.</span><span class="sxs-lookup"><span data-stu-id="62df2-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62df2-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="62df2-113">Parent Elements</span></span>  
  
|<span data-ttu-id="62df2-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="62df2-114">Element</span></span>|<span data-ttu-id="62df2-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62df2-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="62df2-116">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="62df2-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62df2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62df2-117">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>

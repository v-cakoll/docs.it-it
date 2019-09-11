---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 670c1573fe4378a18c19d0a58fe58241745725bd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854792"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="1cc7f-101">\<workflowControlEndpoint></span><span class="sxs-lookup"><span data-stu-id="1cc7f-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="1cc7f-102">Questo elemento di configurazione definisce un endpoint standard per il controllo dell'esecuzione di istanze del flusso di lavoro (creazione, esecuzione, sospensione, terminazione e così via).</span><span class="sxs-lookup"><span data-stu-id="1cc7f-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="1cc7f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1cc7f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1cc7f-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1cc7f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1cc7f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="1cc7f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="1cc7f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> workflowControlEndpoint**</span><span class="sxs-lookup"><span data-stu-id="1cc7f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cc7f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1cc7f-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1cc7f-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1cc7f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1cc7f-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1cc7f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1cc7f-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="1cc7f-110">Attributes</span></span>  
  
|<span data-ttu-id="1cc7f-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="1cc7f-111">Attribute</span></span>|<span data-ttu-id="1cc7f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cc7f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1cc7f-113">name</span><span class="sxs-lookup"><span data-stu-id="1cc7f-113">name</span></span>|<span data-ttu-id="1cc7f-114">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="1cc7f-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="1cc7f-115">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="1cc7f-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1cc7f-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1cc7f-116">Child Elements</span></span>  
 <span data-ttu-id="1cc7f-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1cc7f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1cc7f-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1cc7f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1cc7f-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="1cc7f-119">Element</span></span>|<span data-ttu-id="1cc7f-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cc7f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cc7f-121">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="1cc7f-121">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="1cc7f-122">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="1cc7f-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1cc7f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cc7f-123">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>

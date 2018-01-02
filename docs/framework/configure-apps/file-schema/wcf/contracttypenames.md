---
title: '&lt;contractTypeNames&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5ac3a4af54d9f470a1cbd50096731b23d28b0c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltcontracttypenamesgt"></a><span data-ttu-id="e3392-102">&lt;contractTypeNames&gt;</span><span class="sxs-lookup"><span data-stu-id="e3392-102">&lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="e3392-103">Sezione di configurazione che specifica un elenco di nomi di tipi di contratto che costituiscono i nomi di contratto dei servizi ricercati, nonché i criteri usati in genere durante la ricerca di un servizio.</span><span class="sxs-lookup"><span data-stu-id="e3392-103">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="e3392-104">Se si specificano più nomi di contratto, risponderanno solo gli endpoint del servizio corrispondenti a tutti i contratti.</span><span class="sxs-lookup"><span data-stu-id="e3392-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="e3392-105">Si noti che in [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] un endpoint può supportare un solo contratto.</span><span class="sxs-lookup"><span data-stu-id="e3392-105">Note that in [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="e3392-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e3392-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="e3392-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="e3392-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3392-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3392-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan" 
                        maxResults="Integer" 
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String" namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3392-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e3392-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e3392-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e3392-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3392-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="e3392-111">Attributes</span></span>  
 <span data-ttu-id="e3392-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e3392-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e3392-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e3392-113">Child Elements</span></span>  
  
|<span data-ttu-id="e3392-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3392-114">Element</span></span>|<span data-ttu-id="e3392-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3392-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3392-116">\<add></span><span class="sxs-lookup"><span data-stu-id="e3392-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="e3392-117">Un nome del tipo di contratto è una proprietà che fa riferimento al set di criteri usato in genere durante la ricerca di un servizio.</span><span class="sxs-lookup"><span data-stu-id="e3392-117">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e3392-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e3392-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e3392-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3392-119">Element</span></span>|<span data-ttu-id="e3392-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3392-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3392-121">\<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="e3392-121">\<findCriteria></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|<span data-ttu-id="e3392-122">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="e3392-122">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="e3392-123">I criteri possono essere raggruppati nei criteri di ricerca (specificando i servizi da cercare) e i criteri di terminazione (quanto tempo deve durare la ricerca).</span><span class="sxs-lookup"><span data-stu-id="e3392-123">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3392-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3392-124">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>

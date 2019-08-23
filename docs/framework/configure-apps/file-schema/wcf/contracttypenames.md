---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: 12f9d4eca02ae3b306646826667c4eafef51a95c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919369"
---
# <a name="contracttypenames"></a><span data-ttu-id="f5e8e-101">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="f5e8e-101">\<contractTypeNames></span></span>
<span data-ttu-id="f5e8e-102">Sezione di configurazione che specifica un elenco di nomi di tipi di contratto che costituiscono i nomi di contratto dei servizi ricercati, nonché i criteri usati in genere durante la ricerca di un servizio.</span><span class="sxs-lookup"><span data-stu-id="f5e8e-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="f5e8e-103">Se si specificano più nomi di contratto, risponderanno solo gli endpoint del servizio corrispondenti a tutti i contratti.</span><span class="sxs-lookup"><span data-stu-id="f5e8e-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="f5e8e-104">Si noti che in Windows Communication Foundation (WCF) un endpoint può supportare un solo contratto.</span><span class="sxs-lookup"><span data-stu-id="f5e8e-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="f5e8e-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f5e8e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="f5e8e-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="f5e8e-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5e8e-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5e8e-107">Syntax</span></span>  
  
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
              <add name="String"
                   namespace="String" />
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5e8e-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f5e8e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f5e8e-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f5e8e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5e8e-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="f5e8e-110">Attributes</span></span>  
 <span data-ttu-id="f5e8e-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f5e8e-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f5e8e-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f5e8e-112">Child Elements</span></span>  
  
|<span data-ttu-id="f5e8e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5e8e-113">Element</span></span>|<span data-ttu-id="f5e8e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5e8e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5e8e-115">\<add></span><span class="sxs-lookup"><span data-stu-id="f5e8e-115">\<add></span></span>](contracttypenames.md)|<span data-ttu-id="f5e8e-116">Un nome del tipo di contratto è una proprietà che fa riferimento al set di criteri usato in genere durante la ricerca di un servizio.</span><span class="sxs-lookup"><span data-stu-id="f5e8e-116">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f5e8e-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f5e8e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f5e8e-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5e8e-118">Element</span></span>|<span data-ttu-id="f5e8e-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5e8e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5e8e-120">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="f5e8e-120">\<findCriteria></span></span>](findcriteria.md)|<span data-ttu-id="f5e8e-121">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="f5e8e-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="f5e8e-122">I criteri possono essere raggruppati in criteri di ricerca (specificando i servizi desiderati) e individuare i criteri di terminazione (durata della ricerca).</span><span class="sxs-lookup"><span data-stu-id="f5e8e-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5e8e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5e8e-123">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>

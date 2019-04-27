---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: b1cec9272a1de029ab72ea4d5f36c74630e5b93a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673199"
---
# <a name="contracttypenames"></a><span data-ttu-id="3505b-101">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="3505b-101">\<contractTypeNames></span></span>
<span data-ttu-id="3505b-102">Sezione di configurazione che specifica un elenco di nomi di tipi di contratto che costituiscono i nomi di contratto dei servizi ricercati, nonché i criteri usati in genere durante la ricerca di un servizio.</span><span class="sxs-lookup"><span data-stu-id="3505b-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="3505b-103">Se si specificano più nomi di contratto, risponderanno solo gli endpoint del servizio corrispondenti a tutti i contratti.</span><span class="sxs-lookup"><span data-stu-id="3505b-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="3505b-104">Si noti che in Windows Communication Foundation (WCF), un endpoint può supportare un solo contratto.</span><span class="sxs-lookup"><span data-stu-id="3505b-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="3505b-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3505b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="3505b-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="3505b-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3505b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3505b-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3505b-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3505b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3505b-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3505b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3505b-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="3505b-110">Attributes</span></span>  
 <span data-ttu-id="3505b-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3505b-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3505b-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3505b-112">Child Elements</span></span>  
  
|<span data-ttu-id="3505b-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="3505b-113">Element</span></span>|<span data-ttu-id="3505b-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3505b-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3505b-115">\<add></span><span class="sxs-lookup"><span data-stu-id="3505b-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="3505b-116">Un nome del tipo di contratto è una proprietà che fa riferimento al set di criteri usato in genere durante la ricerca di un servizio.</span><span class="sxs-lookup"><span data-stu-id="3505b-116">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3505b-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3505b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3505b-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="3505b-118">Element</span></span>|<span data-ttu-id="3505b-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3505b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3505b-120">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="3505b-120">\<findCriteria></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|<span data-ttu-id="3505b-121">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="3505b-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="3505b-122">I criteri possono essere raggruppati in Criteri di ricerca (specificando i servizi desiderati) e trovare i criteri di terminazione (quanto tempo deve durare la ricerca).</span><span class="sxs-lookup"><span data-stu-id="3505b-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3505b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3505b-123">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>

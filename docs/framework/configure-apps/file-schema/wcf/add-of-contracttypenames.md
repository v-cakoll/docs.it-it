---
title: <add> di <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 856298cb0639cf19b941f326b5b9a25aa6663088
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701190"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="a7890-102">\<aggiungere > di \<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="a7890-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="a7890-103">Elemento di configurazione che specifica il nome del contratto dei servizi ricercati e i criteri usati in genere durante la ricerca di un servizio.</span><span class="sxs-lookup"><span data-stu-id="a7890-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="a7890-104">Se si specificano più nomi di contratto, risponderanno solo gli endpoint del servizio corrispondenti a tutti i contratti.</span><span class="sxs-lookup"><span data-stu-id="a7890-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="a7890-105">Si noti che in Windows Communication Foundation (WCF), un endpoint può supportare un solo contratto.</span><span class="sxs-lookup"><span data-stu-id="a7890-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="a7890-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a7890-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="a7890-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="a7890-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7890-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7890-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7890-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a7890-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a7890-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a7890-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7890-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="a7890-111">Attributes</span></span>  
  
|<span data-ttu-id="a7890-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="a7890-112">Attribute</span></span>|<span data-ttu-id="a7890-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a7890-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7890-114">name</span><span class="sxs-lookup"><span data-stu-id="a7890-114">name</span></span>|<span data-ttu-id="a7890-115">Stringa che specifica il nome del tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="a7890-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="a7890-116">namespace</span><span class="sxs-lookup"><span data-stu-id="a7890-116">namespace</span></span>|<span data-ttu-id="a7890-117">Stringa che specifica lo spazio dei nomi del tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="a7890-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7890-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a7890-118">Child Elements</span></span>  
 <span data-ttu-id="a7890-119">nessuno</span><span class="sxs-lookup"><span data-stu-id="a7890-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a7890-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a7890-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a7890-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="a7890-121">Element</span></span>|<span data-ttu-id="a7890-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a7890-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7890-123">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="a7890-123">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="a7890-124">Raccolta di nomi di tipi di contratto.</span><span class="sxs-lookup"><span data-stu-id="a7890-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7890-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7890-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>

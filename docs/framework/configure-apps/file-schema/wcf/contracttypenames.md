---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: c67e5b9e82b96e27ce73512680bd4236b26ef4dd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855447"
---
# <a name="contracttypenames"></a><span data-ttu-id="57af3-101">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="57af3-101">\<contractTypeNames></span></span>
<span data-ttu-id="57af3-102">Sezione di configurazione che specifica un elenco di nomi di tipi di contratto che costituiscono i nomi di contratto dei servizi ricercati, nonché i criteri usati in genere durante la ricerca di un servizio.</span><span class="sxs-lookup"><span data-stu-id="57af3-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="57af3-103">Se si specificano più nomi di contratto, risponderanno solo gli endpoint del servizio corrispondenti a tutti i contratti.</span><span class="sxs-lookup"><span data-stu-id="57af3-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="57af3-104">Si noti che in Windows Communication Foundation (WCF) un endpoint può supportare un solo contratto.</span><span class="sxs-lookup"><span data-stu-id="57af3-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
<span data-ttu-id="57af3-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="57af3-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="57af3-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="57af3-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="57af3-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="57af3-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="57af3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dynamicEndpoint**](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="57af3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="57af3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> standardEndpoint**</span><span class="sxs-lookup"><span data-stu-id="57af3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="57af3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> discoveryClientSettings**](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="57af3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="57af3-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> findCriteria**](findcriteria.md)</span><span class="sxs-lookup"><span data-stu-id="57af3-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)</span></span>\
<span data-ttu-id="57af3-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> contractTypeNames**</span><span class="sxs-lookup"><span data-stu-id="57af3-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<contractTypeNames>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57af3-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57af3-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57af3-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="57af3-114">Attributes and Elements</span></span>  
 <span data-ttu-id="57af3-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="57af3-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57af3-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="57af3-116">Attributes</span></span>  
 <span data-ttu-id="57af3-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="57af3-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="57af3-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="57af3-118">Child Elements</span></span>  
  
|<span data-ttu-id="57af3-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="57af3-119">Element</span></span>|<span data-ttu-id="57af3-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57af3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57af3-121">\<add></span><span class="sxs-lookup"><span data-stu-id="57af3-121">\<add></span></span>](contracttypenames.md)|<span data-ttu-id="57af3-122">Un nome del tipo di contratto è una proprietà che fa riferimento al set di criteri usato in genere durante la ricerca di un servizio.</span><span class="sxs-lookup"><span data-stu-id="57af3-122">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="57af3-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="57af3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="57af3-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="57af3-124">Element</span></span>|<span data-ttu-id="57af3-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57af3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57af3-126">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="57af3-126">\<findCriteria></span></span>](findcriteria.md)|<span data-ttu-id="57af3-127">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="57af3-127">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="57af3-128">I criteri possono essere raggruppati in criteri di ricerca (specificando i servizi desiderati) e individuare i criteri di terminazione (durata della ricerca).</span><span class="sxs-lookup"><span data-stu-id="57af3-128">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="57af3-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57af3-129">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>

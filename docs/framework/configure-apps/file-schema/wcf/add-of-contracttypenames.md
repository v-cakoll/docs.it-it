---
title: <add> di <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 696752470aa39c2bcc66a1337f84119031742ae9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850540"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="101cf-102">\<aggiungere > di \<ContractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="101cf-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="101cf-103">Elemento di configurazione che specifica il nome del contratto dei servizi ricercati e i criteri usati in genere durante la ricerca di un servizio.</span><span class="sxs-lookup"><span data-stu-id="101cf-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="101cf-104">Se si specificano più nomi di contratto, risponderanno solo gli endpoint del servizio corrispondenti a tutti i contratti.</span><span class="sxs-lookup"><span data-stu-id="101cf-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="101cf-105">Si noti che in Windows Communication Foundation (WCF) un endpoint può supportare un solo contratto.</span><span class="sxs-lookup"><span data-stu-id="101cf-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
<span data-ttu-id="101cf-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="101cf-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="101cf-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="101cf-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="101cf-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="101cf-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="101cf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dynamicEndpoint**](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="101cf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="101cf-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> standardEndpoint**</span><span class="sxs-lookup"><span data-stu-id="101cf-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="101cf-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> discoveryClientSettings**](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="101cf-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="101cf-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> findCriteria**](findcriteria.md)</span><span class="sxs-lookup"><span data-stu-id="101cf-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)</span></span>\
<span data-ttu-id="101cf-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> contractTypeNames**](contracttypenames.md)</span><span class="sxs-lookup"><span data-stu-id="101cf-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<contractTypeNames>**](contracttypenames.md)</span></span>\
<span data-ttu-id="101cf-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="101cf-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="101cf-115">Sintassi</span><span class="sxs-lookup"><span data-stu-id="101cf-115">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="101cf-116">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="101cf-116">Attributes and Elements</span></span>  
 <span data-ttu-id="101cf-117">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="101cf-117">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="101cf-118">Attributi</span><span class="sxs-lookup"><span data-stu-id="101cf-118">Attributes</span></span>  
  
|<span data-ttu-id="101cf-119">Attributo</span><span class="sxs-lookup"><span data-stu-id="101cf-119">Attribute</span></span>|<span data-ttu-id="101cf-120">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="101cf-120">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="101cf-121">name</span><span class="sxs-lookup"><span data-stu-id="101cf-121">name</span></span>|<span data-ttu-id="101cf-122">Stringa che specifica il nome del tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="101cf-122">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="101cf-123">namespace</span><span class="sxs-lookup"><span data-stu-id="101cf-123">namespace</span></span>|<span data-ttu-id="101cf-124">Stringa che specifica lo spazio dei nomi del tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="101cf-124">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="101cf-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="101cf-125">Child Elements</span></span>  
 <span data-ttu-id="101cf-126">Nessuna</span><span class="sxs-lookup"><span data-stu-id="101cf-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="101cf-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="101cf-127">Parent Elements</span></span>  
  
|<span data-ttu-id="101cf-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="101cf-128">Element</span></span>|<span data-ttu-id="101cf-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="101cf-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="101cf-130">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="101cf-130">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="101cf-131">Raccolta di nomi di tipi di contratto.</span><span class="sxs-lookup"><span data-stu-id="101cf-131">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="101cf-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="101cf-132">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>

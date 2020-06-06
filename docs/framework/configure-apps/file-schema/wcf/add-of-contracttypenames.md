---
title: <add> di <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 696752470aa39c2bcc66a1337f84119031742ae9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850540"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="3a2ce-102">\<add> di \<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="3a2ce-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="3a2ce-103">Elemento di configurazione che specifica il nome del contratto dei servizi ricercati e i criteri usati in genere durante la ricerca di un servizio.</span><span class="sxs-lookup"><span data-stu-id="3a2ce-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="3a2ce-104">Se si specificano più nomi di contratto, risponderanno solo gli endpoint del servizio corrispondenti a tutti i contratti.</span><span class="sxs-lookup"><span data-stu-id="3a2ce-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="3a2ce-105">Si noti che in Windows Communication Foundation (WCF) un endpoint può supportare un solo contratto.</span><span class="sxs-lookup"><span data-stu-id="3a2ce-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<contractTypeNames>**](contracttypenames.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="3a2ce-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a2ce-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a2ce-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3a2ce-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3a2ce-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3a2ce-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a2ce-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="3a2ce-109">Attributes</span></span>  
  
|<span data-ttu-id="3a2ce-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="3a2ce-110">Attribute</span></span>|<span data-ttu-id="3a2ce-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a2ce-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a2ce-112">name</span><span class="sxs-lookup"><span data-stu-id="3a2ce-112">name</span></span>|<span data-ttu-id="3a2ce-113">Stringa che specifica il nome del tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="3a2ce-113">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="3a2ce-114">namespace</span><span class="sxs-lookup"><span data-stu-id="3a2ce-114">namespace</span></span>|<span data-ttu-id="3a2ce-115">Stringa che specifica lo spazio dei nomi del tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="3a2ce-115">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a2ce-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3a2ce-116">Child Elements</span></span>  
 <span data-ttu-id="3a2ce-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="3a2ce-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a2ce-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3a2ce-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3a2ce-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a2ce-119">Element</span></span>|<span data-ttu-id="3a2ce-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a2ce-120">Description</span></span>|  
|-------------|-----------------|  
|[\<contractTypeNames>](contracttypenames.md)|<span data-ttu-id="3a2ce-121">Raccolta di nomi di tipi di contratto.</span><span class="sxs-lookup"><span data-stu-id="3a2ce-121">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a2ce-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a2ce-122">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>

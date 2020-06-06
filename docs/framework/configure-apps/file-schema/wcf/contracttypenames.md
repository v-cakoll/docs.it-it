---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: c67e5b9e82b96e27ce73512680bd4236b26ef4dd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855447"
---
# \<contractTypeNames>
<span data-ttu-id="389b2-101">Sezione di configurazione che specifica un elenco di nomi di tipi di contratto che costituiscono i nomi di contratto dei servizi ricercati, nonché i criteri usati in genere durante la ricerca di un servizio.</span><span class="sxs-lookup"><span data-stu-id="389b2-101">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="389b2-102">Se si specificano più nomi di contratto, risponderanno solo gli endpoint del servizio corrispondenti a tutti i contratti.</span><span class="sxs-lookup"><span data-stu-id="389b2-102">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="389b2-103">Si noti che in Windows Communication Foundation (WCF) un endpoint può supportare un solo contratto.</span><span class="sxs-lookup"><span data-stu-id="389b2-103">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<contractTypeNames>**  
  
## <a name="syntax"></a><span data-ttu-id="389b2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="389b2-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="389b2-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="389b2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="389b2-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="389b2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="389b2-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="389b2-107">Attributes</span></span>  
 <span data-ttu-id="389b2-108">No.</span><span class="sxs-lookup"><span data-stu-id="389b2-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="389b2-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="389b2-109">Child Elements</span></span>  
  
|<span data-ttu-id="389b2-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="389b2-110">Element</span></span>|<span data-ttu-id="389b2-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="389b2-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](contracttypenames.md)|<span data-ttu-id="389b2-112">Un nome del tipo di contratto è una proprietà che fa riferimento al set di criteri usato in genere durante la ricerca di un servizio.</span><span class="sxs-lookup"><span data-stu-id="389b2-112">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="389b2-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="389b2-113">Parent Elements</span></span>  
  
|<span data-ttu-id="389b2-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="389b2-114">Element</span></span>|<span data-ttu-id="389b2-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="389b2-115">Description</span></span>|  
|-------------|-----------------|  
|[\<findCriteria>](findcriteria.md)|<span data-ttu-id="389b2-116">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="389b2-116">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="389b2-117">I criteri possono essere raggruppati nei criteri di ricerca (specificando i servizi da cercare) e nei criteri di terminazione della ricerca (durata della ricerca).</span><span class="sxs-lookup"><span data-stu-id="389b2-117">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="389b2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="389b2-118">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>

---
title: '&lt;add&gt; di &lt;contractTypeNames&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bebea15e6d1f24c95905355dbced33aa9c5150f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltcontracttypenamesgt"></a><span data-ttu-id="66568-102">&lt;add&gt; di &lt;contractTypeNames&gt;</span><span class="sxs-lookup"><span data-stu-id="66568-102">&lt;add&gt; of &lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="66568-103">Elemento di configurazione che specifica il nome del contratto dei servizi ricercati e i criteri usati in genere durante la ricerca di un servizio.</span><span class="sxs-lookup"><span data-stu-id="66568-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="66568-104">Se si specificano più nomi di contratto, risponderanno solo gli endpoint del servizio corrispondenti a tutti i contratti.</span><span class="sxs-lookup"><span data-stu-id="66568-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="66568-105">Si noti che in [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] un endpoint può supportare un solo contratto.</span><span class="sxs-lookup"><span data-stu-id="66568-105">Note that in [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="66568-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="66568-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="66568-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="66568-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66568-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66568-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>       <dynamicEndpoint>           <standardEndpoint>             <discoveryClientSettings discoveryEndpoint="String" >               <findCriteria duration="TimeSpan"                  maxResults="Integer"                   scopeMatchBy="Uri" >                  <contractTypeNames>                     <add name="String" namespace="String" />                  <contractTypeNames>                  <extensions />                  <scopes>                    <add scope="URI"/>                  </scopes>               </findCriteria>             </discoveryClientSettings>          <standardEndpoint>       </dynamicEndpoint>            </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66568-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="66568-109">Attributes and Elements</span></span>  
 <span data-ttu-id="66568-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="66568-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66568-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="66568-111">Attributes</span></span>  
  
|<span data-ttu-id="66568-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="66568-112">Attribute</span></span>|<span data-ttu-id="66568-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66568-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="66568-114">name</span><span class="sxs-lookup"><span data-stu-id="66568-114">name</span></span>|<span data-ttu-id="66568-115">Stringa che specifica il nome del tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="66568-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="66568-116">namespace</span><span class="sxs-lookup"><span data-stu-id="66568-116">namespace</span></span>|<span data-ttu-id="66568-117">Stringa che specifica lo spazio dei nomi del tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="66568-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66568-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="66568-118">Child Elements</span></span>  
 <span data-ttu-id="66568-119">None</span><span class="sxs-lookup"><span data-stu-id="66568-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="66568-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="66568-120">Parent Elements</span></span>  
  
|<span data-ttu-id="66568-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="66568-121">Element</span></span>|<span data-ttu-id="66568-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66568-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66568-123">\<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="66568-123">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="66568-124">Raccolta di nomi di tipi di contratto.</span><span class="sxs-lookup"><span data-stu-id="66568-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="66568-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66568-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>

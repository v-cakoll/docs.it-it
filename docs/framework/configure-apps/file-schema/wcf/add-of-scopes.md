---
title: <add> di <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: bcde6b18c34dccf1716c809dddeb45b1b4da90f0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398298"
---
# <a name="add-of-scopes"></a><span data-ttu-id="d071d-102">\<add> di \<scopes></span><span class="sxs-lookup"><span data-stu-id="d071d-102">\<add> of \<scopes></span></span>
<span data-ttu-id="d071d-103">Aggiunge URI di ambito personalizzato che è possibile usare per filtrare gli endpoint di servizio durante l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="d071d-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="d071d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d071d-104">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d071d-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d071d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d071d-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d071d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d071d-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="d071d-107">Attributes</span></span>  
  
|<span data-ttu-id="d071d-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="d071d-108">Attribute</span></span>|<span data-ttu-id="d071d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d071d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d071d-110">ambito</span><span class="sxs-lookup"><span data-stu-id="d071d-110">scope</span></span>|<span data-ttu-id="d071d-111">URI contenente informazioni sull'ambito per l'endpoint che è possibile usare nei criteri di corrispondenza per la ricerca di servizi.</span><span class="sxs-lookup"><span data-stu-id="d071d-111">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d071d-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d071d-112">Child Elements</span></span>  
 <span data-ttu-id="d071d-113">No.</span><span class="sxs-lookup"><span data-stu-id="d071d-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d071d-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d071d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="d071d-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="d071d-115">Element</span></span>|<span data-ttu-id="d071d-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d071d-116">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="d071d-117">Contiene una raccolta di elementi di configurazione che specificano URI di ambito personalizzati che è possibile usare per filtrare gli endpoint del servizio durante l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="d071d-117">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d071d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d071d-118">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>

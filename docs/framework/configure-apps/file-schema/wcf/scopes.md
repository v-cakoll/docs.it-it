---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 57e9e19025db5e1fa588f073fdf30de09837a25d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399944"
---
# \<scopes>
<span data-ttu-id="c18eb-101">Contiene una raccolta di elementi di configurazione che specificano URI di ambito personalizzati che è possibile usare per filtrare gli endpoint del servizio durante l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="c18eb-101">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopes>**  
  
## <a name="syntax"></a><span data-ttu-id="c18eb-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c18eb-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c18eb-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c18eb-103">Attributes and Elements</span></span>  
 <span data-ttu-id="c18eb-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c18eb-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c18eb-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="c18eb-105">Attributes</span></span>  
 <span data-ttu-id="c18eb-106">No.</span><span class="sxs-lookup"><span data-stu-id="c18eb-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c18eb-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c18eb-107">Child Elements</span></span>  
  
|<span data-ttu-id="c18eb-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="c18eb-108">Attribute</span></span>|<span data-ttu-id="c18eb-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c18eb-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-scopes.md)|<span data-ttu-id="c18eb-110">Aggiunge le informazioni sull'ambito per l'endpoint che è possibile usare nei criteri di corrispondenza per la ricerca di servizi.</span><span class="sxs-lookup"><span data-stu-id="c18eb-110">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c18eb-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c18eb-111">Parent Elements</span></span>  
  
|<span data-ttu-id="c18eb-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c18eb-112">Element</span></span>|<span data-ttu-id="c18eb-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c18eb-113">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointDiscovery>](endpointdiscovery.md)|<span data-ttu-id="c18eb-114">Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.</span><span class="sxs-lookup"><span data-stu-id="c18eb-114">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c18eb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c18eb-115">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>

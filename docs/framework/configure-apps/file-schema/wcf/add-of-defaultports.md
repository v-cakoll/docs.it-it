---
title: <add> di <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: f5de2aa897a3bc37d08932451a2c7b94bc603b9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400646"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="b3bd4-102">\<add> di \<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="b3bd4-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="b3bd4-103">Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="b3bd4-103">A default communications endpoint that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultPorts>**](defaultports.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="b3bd4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3bd4-104">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3bd4-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b3bd4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b3bd4-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b3bd4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3bd4-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="b3bd4-107">Attributes</span></span>  
  
|<span data-ttu-id="b3bd4-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="b3bd4-108">Attribute</span></span>|<span data-ttu-id="b3bd4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3bd4-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b3bd4-110">port</span><span class="sxs-lookup"><span data-stu-id="b3bd4-110">port</span></span>|<span data-ttu-id="b3bd4-111">Integer che specifica il numero della porta di comunicazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b3bd4-111">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="b3bd4-112">scheme</span><span class="sxs-lookup"><span data-stu-id="b3bd4-112">scheme</span></span>|<span data-ttu-id="b3bd4-113">Stringa che specifica il gruppo di impostazioni del protocollo associato a una porta di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="b3bd4-113">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3bd4-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b3bd4-114">Child Elements</span></span>  
 <span data-ttu-id="b3bd4-115">No.</span><span class="sxs-lookup"><span data-stu-id="b3bd4-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b3bd4-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b3bd4-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b3bd4-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="b3bd4-117">Element</span></span>|<span data-ttu-id="b3bd4-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3bd4-118">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="b3bd4-119">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="b3bd4-119">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3bd4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3bd4-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>

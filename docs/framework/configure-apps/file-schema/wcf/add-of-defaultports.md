---
title: <add> di <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: f5de2aa897a3bc37d08932451a2c7b94bc603b9e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400646"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="4ea41-102">\<aggiungere > di \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="4ea41-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="4ea41-103">Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="4ea41-103">A default communications endpoint that the client application listens to.</span></span>  
  
<span data-ttu-id="4ea41-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4ea41-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4ea41-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4ea41-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4ea41-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4ea41-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="4ea41-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4ea41-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="4ea41-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4ea41-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="4ea41-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> useRequestHeadersForMetadataAddress**](userequestheadersformetadataaddress.md)</span><span class="sxs-lookup"><span data-stu-id="4ea41-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)</span></span>\
<span data-ttu-id="4ea41-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> defaultPorts**](defaultports.md)</span><span class="sxs-lookup"><span data-stu-id="4ea41-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultPorts>**](defaultports.md)</span></span>\
<span data-ttu-id="4ea41-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="4ea41-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ea41-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ea41-112">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ea41-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4ea41-113">Attributes and Elements</span></span>  
 <span data-ttu-id="4ea41-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4ea41-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ea41-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="4ea41-115">Attributes</span></span>  
  
|<span data-ttu-id="4ea41-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="4ea41-116">Attribute</span></span>|<span data-ttu-id="4ea41-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ea41-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ea41-118">port</span><span class="sxs-lookup"><span data-stu-id="4ea41-118">port</span></span>|<span data-ttu-id="4ea41-119">Integer che specifica il numero della porta di comunicazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4ea41-119">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="4ea41-120">scheme</span><span class="sxs-lookup"><span data-stu-id="4ea41-120">scheme</span></span>|<span data-ttu-id="4ea41-121">Stringa che specifica il gruppo di impostazioni del protocollo associato a una porta di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="4ea41-121">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ea41-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4ea41-122">Child Elements</span></span>  
 <span data-ttu-id="4ea41-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4ea41-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ea41-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4ea41-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4ea41-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="4ea41-125">Element</span></span>|<span data-ttu-id="4ea41-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ea41-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ea41-127">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="4ea41-127">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="4ea41-128">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="4ea41-128">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ea41-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ea41-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>

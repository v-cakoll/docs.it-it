---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: cc5ebcf36a10e88d48ed14f1f10dac6396d7b242
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399713"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="7f390-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="7f390-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="7f390-102">Fornisce un elemento di configurazione del flusso di lavoro che stabilisce a livello di servizio la validità di una trasmissione, un messaggio o un'origine.</span><span class="sxs-lookup"><span data-stu-id="7f390-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="7f390-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7f390-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7f390-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7f390-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7f390-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7f390-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="7f390-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7f390-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="7f390-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7f390-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="7f390-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> serviceAuthenticationManager**</span><span class="sxs-lookup"><span data-stu-id="7f390-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f390-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f390-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f390-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7f390-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7f390-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7f390-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f390-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="7f390-112">Attributes</span></span>  
  
|<span data-ttu-id="7f390-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="7f390-113">Attribute</span></span>|<span data-ttu-id="7f390-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f390-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f390-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="7f390-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="7f390-116">Stringa che specifica il tipo del criterio di autenticazione per il comportamento corrente.</span><span class="sxs-lookup"><span data-stu-id="7f390-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f390-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7f390-117">Child Elements</span></span>  
 <span data-ttu-id="7f390-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7f390-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f390-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7f390-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7f390-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f390-120">Element</span></span>|<span data-ttu-id="7f390-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f390-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f390-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7f390-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="7f390-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="7f390-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f390-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f390-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>

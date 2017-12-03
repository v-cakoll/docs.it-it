---
title: '&lt;serviceAuthenticationManager&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 077878ae1746008532c3bee6b12913f98afc343f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="11720-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="11720-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="11720-103">Fornisce un elemento di configurazione del flusso di lavoro che stabilisce a livello di servizio la validità di una trasmissione, di un messaggio o di un creatore.</span><span class="sxs-lookup"><span data-stu-id="11720-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>  
  
<span data-ttu-id="11720-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="11720-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="11720-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="11720-105">\<behaviors></span></span>  
<span data-ttu-id="11720-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="11720-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="11720-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="11720-107">\<behavior></span></span>  
<span data-ttu-id="11720-108">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="11720-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11720-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11720-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11720-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="11720-110">Attributes and Elements</span></span>  
 <span data-ttu-id="11720-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="11720-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11720-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="11720-112">Attributes</span></span>  
  
|<span data-ttu-id="11720-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="11720-113">Attribute</span></span>|<span data-ttu-id="11720-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11720-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="11720-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="11720-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="11720-116">Stringa che specifica il tipo del criterio di autenticazione per il comportamento corrente.</span><span class="sxs-lookup"><span data-stu-id="11720-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11720-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="11720-117">Child Elements</span></span>  
 <span data-ttu-id="11720-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="11720-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="11720-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="11720-119">Parent Elements</span></span>  
  
|<span data-ttu-id="11720-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="11720-120">Element</span></span>|<span data-ttu-id="11720-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11720-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11720-122">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="11720-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="11720-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="11720-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11720-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11720-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>

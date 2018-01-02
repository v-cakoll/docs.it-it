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
ms.workload: dotnet
ms.openlocfilehash: b46df4f069259ae4bb2d2769e20c6ad9e6090c00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="1bbc2-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="1bbc2-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="1bbc2-103">Fornisce un elemento di configurazione del flusso di lavoro che stabilisce a livello di servizio la validità di una trasmissione, di un messaggio o di un creatore.</span><span class="sxs-lookup"><span data-stu-id="1bbc2-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>  
  
<span data-ttu-id="1bbc2-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1bbc2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1bbc2-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="1bbc2-105">\<behaviors></span></span>  
<span data-ttu-id="1bbc2-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1bbc2-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1bbc2-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="1bbc2-107">\<behavior></span></span>  
<span data-ttu-id="1bbc2-108">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="1bbc2-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bbc2-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1bbc2-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bbc2-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1bbc2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1bbc2-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1bbc2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bbc2-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="1bbc2-112">Attributes</span></span>  
  
|<span data-ttu-id="1bbc2-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="1bbc2-113">Attribute</span></span>|<span data-ttu-id="1bbc2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bbc2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1bbc2-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="1bbc2-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="1bbc2-116">Stringa che specifica il tipo del criterio di autenticazione per il comportamento corrente.</span><span class="sxs-lookup"><span data-stu-id="1bbc2-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bbc2-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1bbc2-117">Child Elements</span></span>  
 <span data-ttu-id="1bbc2-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1bbc2-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1bbc2-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1bbc2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1bbc2-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="1bbc2-120">Element</span></span>|<span data-ttu-id="1bbc2-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bbc2-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1bbc2-122">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="1bbc2-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="1bbc2-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="1bbc2-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1bbc2-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bbc2-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>

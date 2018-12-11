---
title: '&lt;serviceAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 34c50e0e8c259190d3f66aa7ad1369befc629d44
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154079"
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="d1b76-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="d1b76-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="d1b76-103">Fornisce un elemento di configurazione del flusso di lavoro che stabilisce a livello di servizio la validità di una trasmissione, un messaggio o un'origine.</span><span class="sxs-lookup"><span data-stu-id="d1b76-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="d1b76-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d1b76-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d1b76-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="d1b76-105">\<behaviors></span></span>  
<span data-ttu-id="d1b76-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="d1b76-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d1b76-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="d1b76-107">\<behavior></span></span>  
<span data-ttu-id="d1b76-108">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="d1b76-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1b76-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d1b76-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1b76-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d1b76-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d1b76-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d1b76-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1b76-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="d1b76-112">Attributes</span></span>  
  
|<span data-ttu-id="d1b76-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="d1b76-113">Attribute</span></span>|<span data-ttu-id="d1b76-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d1b76-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d1b76-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="d1b76-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="d1b76-116">Stringa che specifica il tipo del criterio di autenticazione per il comportamento corrente.</span><span class="sxs-lookup"><span data-stu-id="d1b76-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1b76-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d1b76-117">Child Elements</span></span>  
 <span data-ttu-id="d1b76-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d1b76-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d1b76-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d1b76-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d1b76-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="d1b76-120">Element</span></span>|<span data-ttu-id="d1b76-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d1b76-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1b76-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d1b76-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d1b76-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="d1b76-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1b76-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1b76-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>

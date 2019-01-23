---
title: '&lt;serviceAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: fd04b10c0ac0bef4087daa1012a1b8bd3a5880e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493638"
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="756b1-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="756b1-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="756b1-103">Fornisce un elemento di configurazione del flusso di lavoro che stabilisce a livello di servizio la validità di una trasmissione, un messaggio o un'origine.</span><span class="sxs-lookup"><span data-stu-id="756b1-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="756b1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="756b1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="756b1-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="756b1-105">\<behaviors></span></span>  
<span data-ttu-id="756b1-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="756b1-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="756b1-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="756b1-107">\<behavior></span></span>  
<span data-ttu-id="756b1-108">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="756b1-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="756b1-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="756b1-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="756b1-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="756b1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="756b1-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="756b1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="756b1-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="756b1-112">Attributes</span></span>  
  
|<span data-ttu-id="756b1-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="756b1-113">Attribute</span></span>|<span data-ttu-id="756b1-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="756b1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="756b1-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="756b1-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="756b1-116">Stringa che specifica il tipo del criterio di autenticazione per il comportamento corrente.</span><span class="sxs-lookup"><span data-stu-id="756b1-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="756b1-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="756b1-117">Child Elements</span></span>  
 <span data-ttu-id="756b1-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="756b1-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="756b1-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="756b1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="756b1-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="756b1-120">Element</span></span>|<span data-ttu-id="756b1-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="756b1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="756b1-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="756b1-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="756b1-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="756b1-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="756b1-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="756b1-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>

---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 7708dd8a572dd24c2852410b1781fce2807efab9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263485"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="fd617-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="fd617-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="fd617-102">Fornisce un elemento di configurazione del flusso di lavoro che stabilisce a livello di servizio la validità di una trasmissione, un messaggio o un'origine.</span><span class="sxs-lookup"><span data-stu-id="fd617-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="fd617-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fd617-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fd617-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="fd617-104">\<behaviors></span></span>  
<span data-ttu-id="fd617-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="fd617-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="fd617-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fd617-106">\<behavior></span></span>  
<span data-ttu-id="fd617-107">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="fd617-107">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd617-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd617-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd617-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fd617-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fd617-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fd617-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd617-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="fd617-111">Attributes</span></span>  
  
|<span data-ttu-id="fd617-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="fd617-112">Attribute</span></span>|<span data-ttu-id="fd617-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd617-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fd617-114">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="fd617-114">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="fd617-115">Stringa che specifica il tipo del criterio di autenticazione per il comportamento corrente.</span><span class="sxs-lookup"><span data-stu-id="fd617-115">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd617-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fd617-116">Child Elements</span></span>  
 <span data-ttu-id="fd617-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fd617-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd617-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fd617-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fd617-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="fd617-119">Element</span></span>|<span data-ttu-id="fd617-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd617-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd617-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fd617-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="fd617-122">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="fd617-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd617-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd617-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>

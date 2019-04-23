---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 0940248364488bb38a329c5e461d72463c574e74
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192044"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="7e06c-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="7e06c-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="7e06c-102">Fornisce un elemento di configurazione del flusso di lavoro che stabilisce a livello di servizio la validità di una trasmissione, un messaggio o un'origine.</span><span class="sxs-lookup"><span data-stu-id="7e06c-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="7e06c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7e06c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="7e06c-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="7e06c-104">\<behaviors></span></span>  
<span data-ttu-id="7e06c-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="7e06c-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="7e06c-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7e06c-106">\<behavior></span></span>  
<span data-ttu-id="7e06c-107">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="7e06c-107">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e06c-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e06c-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e06c-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7e06c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7e06c-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7e06c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e06c-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="7e06c-111">Attributes</span></span>  
  
|<span data-ttu-id="7e06c-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="7e06c-112">Attribute</span></span>|<span data-ttu-id="7e06c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e06c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e06c-114">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="7e06c-114">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="7e06c-115">Stringa che specifica il tipo del criterio di autenticazione per il comportamento corrente.</span><span class="sxs-lookup"><span data-stu-id="7e06c-115">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e06c-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7e06c-116">Child Elements</span></span>  
 <span data-ttu-id="7e06c-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7e06c-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e06c-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7e06c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7e06c-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="7e06c-119">Element</span></span>|<span data-ttu-id="7e06c-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e06c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e06c-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7e06c-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="7e06c-122">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="7e06c-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e06c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e06c-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>

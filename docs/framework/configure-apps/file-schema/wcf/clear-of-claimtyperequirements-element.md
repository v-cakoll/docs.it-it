---
title: <clear> di <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 35d0391951204bd352918d3004f0cc4f9480b0e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704271"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="18d0a-102">\<clear > di \<claimTypeRequirements > elemento</span><span class="sxs-lookup"><span data-stu-id="18d0a-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="18d0a-103">Specifica tutti i tipi di attestazioni da rimuovere nella credenziale federativa.</span><span class="sxs-lookup"><span data-stu-id="18d0a-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="18d0a-104">Ciò consente di assicurare che la raccolta sia inizialmente vuota.</span><span class="sxs-lookup"><span data-stu-id="18d0a-104">This ensures that the collection starts empty.</span></span>  
  
 <span data-ttu-id="18d0a-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="18d0a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="18d0a-106">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="18d0a-106">\<bindings></span></span>  
<span data-ttu-id="18d0a-107">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="18d0a-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="18d0a-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="18d0a-108">\<binding></span></span>  
<span data-ttu-id="18d0a-109">\<security></span><span class="sxs-lookup"><span data-stu-id="18d0a-109">\<security></span></span>  
<span data-ttu-id="18d0a-110">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="18d0a-110">\<message></span></span>  
<span data-ttu-id="18d0a-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="18d0a-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18d0a-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18d0a-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18d0a-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="18d0a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="18d0a-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="18d0a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18d0a-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="18d0a-115">Attributes</span></span>  
 <span data-ttu-id="18d0a-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="18d0a-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="18d0a-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="18d0a-117">Child Elements</span></span>  
 <span data-ttu-id="18d0a-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="18d0a-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18d0a-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="18d0a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="18d0a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="18d0a-120">Element</span></span>|<span data-ttu-id="18d0a-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18d0a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18d0a-122">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="18d0a-122">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="18d0a-123">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="18d0a-123">Specifies a collection of required claim types.</span></span> <span data-ttu-id="18d0a-124">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="18d0a-124">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="18d0a-125">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="18d0a-125">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="18d0a-126">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="18d0a-126">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="18d0a-127">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="18d0a-127">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18d0a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18d0a-128">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>

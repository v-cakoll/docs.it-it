---
title: <remove> di <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 8058a90d61d8f94944d98a26c59bfbe225f611d5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259503"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="c5ee2-102">\<rimuovere > di \<claimTypeRequirements > elemento</span><span class="sxs-lookup"><span data-stu-id="c5ee2-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="c5ee2-103">Specifica i tipi di attestazioni da rimuovere nella credenziale federativa.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
 <span data-ttu-id="c5ee2-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c5ee2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c5ee2-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="c5ee2-105">\<bindings></span></span>  
<span data-ttu-id="c5ee2-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="c5ee2-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="c5ee2-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="c5ee2-107">\<binding></span></span>  
<span data-ttu-id="c5ee2-108">\<security></span><span class="sxs-lookup"><span data-stu-id="c5ee2-108">\<security></span></span>  
<span data-ttu-id="c5ee2-109">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="c5ee2-109">\<message></span></span>  
<span data-ttu-id="c5ee2-110">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="c5ee2-110">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5ee2-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5ee2-111">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5ee2-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c5ee2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c5ee2-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5ee2-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="c5ee2-114">Attributes</span></span>  
  
|<span data-ttu-id="c5ee2-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="c5ee2-115">Attribute</span></span>|<span data-ttu-id="c5ee2-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5ee2-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c5ee2-117">claimType</span><span class="sxs-lookup"><span data-stu-id="c5ee2-117">claimType</span></span>|<span data-ttu-id="c5ee2-118">URI che definisce il tipo di un'attestazione da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-118">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5ee2-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c5ee2-119">Child Elements</span></span>  
 <span data-ttu-id="c5ee2-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c5ee2-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c5ee2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c5ee2-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="c5ee2-122">Element</span></span>|<span data-ttu-id="c5ee2-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5ee2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5ee2-124">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="c5ee2-124">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="c5ee2-125">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="c5ee2-126">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="c5ee2-127">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="c5ee2-128">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="c5ee2-129">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="c5ee2-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5ee2-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5ee2-130">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>

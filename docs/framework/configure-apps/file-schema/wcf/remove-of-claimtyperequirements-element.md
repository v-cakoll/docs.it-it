---
title: <remove> di <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 9ab1162ff5d86b8a9d43dae79ebf9c9321119206
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119704"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="c9fc7-102">\<rimuovere > di \<claimTypeRequirements > elemento</span><span class="sxs-lookup"><span data-stu-id="c9fc7-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="c9fc7-103">Specifica i tipi di attestazioni da rimuovere nella credenziale federativa.</span><span class="sxs-lookup"><span data-stu-id="c9fc7-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
 <span data-ttu-id="c9fc7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c9fc7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c9fc7-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="c9fc7-105">\<bindings></span></span>  
<span data-ttu-id="c9fc7-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="c9fc7-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="c9fc7-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="c9fc7-107">\<binding></span></span>  
<span data-ttu-id="c9fc7-108">\<security></span><span class="sxs-lookup"><span data-stu-id="c9fc7-108">\<security></span></span>  
<span data-ttu-id="c9fc7-109">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="c9fc7-109">\<message></span></span>  
<span data-ttu-id="c9fc7-110">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="c9fc7-110">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9fc7-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9fc7-111">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9fc7-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c9fc7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c9fc7-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c9fc7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9fc7-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="c9fc7-114">Attributes</span></span>  
  
|<span data-ttu-id="c9fc7-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="c9fc7-115">Attribute</span></span>|<span data-ttu-id="c9fc7-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9fc7-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9fc7-117">claimType</span><span class="sxs-lookup"><span data-stu-id="c9fc7-117">claimType</span></span>|<span data-ttu-id="c9fc7-118">URI che definisce il tipo di un'attestazione da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="c9fc7-118">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9fc7-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c9fc7-119">Child Elements</span></span>  
 <span data-ttu-id="c9fc7-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c9fc7-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c9fc7-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c9fc7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c9fc7-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="c9fc7-122">Element</span></span>|<span data-ttu-id="c9fc7-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9fc7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9fc7-124">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="c9fc7-124">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="c9fc7-125">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="c9fc7-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="c9fc7-126">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="c9fc7-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="c9fc7-127">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="c9fc7-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="c9fc7-128">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="c9fc7-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="c9fc7-129">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="c9fc7-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9fc7-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9fc7-130">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>

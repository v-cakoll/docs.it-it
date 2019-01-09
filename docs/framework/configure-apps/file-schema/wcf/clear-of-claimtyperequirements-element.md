---
title: Elemento &lt;clear&gt; di &lt;claimTypeRequirements&gt;
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 1e77e3c978c1e385aec983d5e2d4bea64697c43e
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145289"
---
# <a name="ltcleargt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="ec057-102">Elemento &lt;clear&gt; di &lt;claimTypeRequirements&gt;</span><span class="sxs-lookup"><span data-stu-id="ec057-102">&lt;clear&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="ec057-103">Specifica tutti i tipi di attestazioni da rimuovere nella credenziale federativa.</span><span class="sxs-lookup"><span data-stu-id="ec057-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="ec057-104">Ciò consente di assicurare che la raccolta sia inizialmente vuota.</span><span class="sxs-lookup"><span data-stu-id="ec057-104">This ensures that the collection starts empty.</span></span>  
  
 <span data-ttu-id="ec057-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ec057-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="ec057-106">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="ec057-106">\<bindings></span></span>  
<span data-ttu-id="ec057-107">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="ec057-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="ec057-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="ec057-108">\<binding></span></span>  
<span data-ttu-id="ec057-109">\<security></span><span class="sxs-lookup"><span data-stu-id="ec057-109">\<security></span></span>  
<span data-ttu-id="ec057-110">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="ec057-110">\<message></span></span>  
<span data-ttu-id="ec057-111">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="ec057-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec057-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec057-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec057-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ec057-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ec057-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ec057-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec057-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="ec057-115">Attributes</span></span>  
 <span data-ttu-id="ec057-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ec057-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ec057-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ec057-117">Child Elements</span></span>  
 <span data-ttu-id="ec057-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ec057-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec057-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ec057-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ec057-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="ec057-120">Element</span></span>|<span data-ttu-id="ec057-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec057-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec057-122">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="ec057-122">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="ec057-123">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="ec057-123">Specifies a collection of required claim types.</span></span> <span data-ttu-id="ec057-124">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="ec057-124">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="ec057-125">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="ec057-125">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="ec057-126">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="ec057-126">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="ec057-127">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="ec057-127">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec057-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec057-128">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>

---
title: <add> di <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: 65398c5afa9750f215c95899bb6004cae671123a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920265"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="91983-102">\<aggiungere > di \<AuthorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="91983-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="91983-103">Specifica i criteri di autorizzazione per la trasformazione di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="91983-103">Specifies an authorization policy for claim transformation.</span></span>  
  
 <span data-ttu-id="91983-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="91983-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="91983-105">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="91983-105">\<behaviors></span></span>  
<span data-ttu-id="91983-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="91983-106">\<behavior></span></span>  
<span data-ttu-id="91983-107">\<serviceAuthorization></span><span class="sxs-lookup"><span data-stu-id="91983-107">\<serviceAuthorization></span></span>  
<span data-ttu-id="91983-108">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="91983-108">\<authorizationPolicies></span></span>  
<span data-ttu-id="91983-109">\<add></span><span class="sxs-lookup"><span data-stu-id="91983-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91983-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91983-110">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="91983-111">Type</span><span class="sxs-lookup"><span data-stu-id="91983-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91983-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="91983-112">Attributes and Elements</span></span>  
 <span data-ttu-id="91983-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="91983-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91983-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="91983-114">Attributes</span></span>  
  
|<span data-ttu-id="91983-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="91983-115">Attribute</span></span>|<span data-ttu-id="91983-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="91983-116">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="91983-117">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="91983-117">A required String attribute.</span></span><br /><br /> <span data-ttu-id="91983-118">Il modello di controllo di accesso Windows Communication Foundation (WCF) supporta il provisioning di un set di criteri di autorizzazione come tipi.</span><span class="sxs-lookup"><span data-stu-id="91983-118">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="91983-119">Questo attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="91983-119">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="91983-120">Su questa base può essere concesso o negato il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="91983-120">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91983-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="91983-121">Child Elements</span></span>  
 <span data-ttu-id="91983-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="91983-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91983-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="91983-123">Parent Elements</span></span>  
  
|<span data-ttu-id="91983-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="91983-124">Element</span></span>|<span data-ttu-id="91983-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="91983-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91983-126">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="91983-126">\<authorizationPolicies></span></span>](authorizationpolicies.md)|<span data-ttu-id="91983-127">Specifica una raccolta di tipi di criteri di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="91983-127">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91983-128">Note</span><span class="sxs-lookup"><span data-stu-id="91983-128">Remarks</span></span>  
 <span data-ttu-id="91983-129">Ciascun criterio di autorizzazione contiene un solo attributo `policyType` obbligatorio che è una stringa.</span><span class="sxs-lookup"><span data-stu-id="91983-129">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="91983-130">L'attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="91983-130">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="91983-131">Su questa base può essere concesso o negato il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="91983-131">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="91983-132">Per ulteriori informazioni sul funzionamento di un criterio di autorizzazione, <xref:System.IdentityModel.Policy.IAuthorizationPolicy> vedere e [criteri di autorizzazione](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="91983-132">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91983-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91983-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="91983-134">Autorizzazione dell'accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="91983-134">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="91983-135">Procedura: Creazione di un gestore autorizzazioni personalizzato per un servizio</span><span class="sxs-lookup"><span data-stu-id="91983-135">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="91983-136">\<add></span><span class="sxs-lookup"><span data-stu-id="91983-136">\<add></span></span>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="91983-137">Criteri di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="91983-137">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)

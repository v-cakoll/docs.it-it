---
title: <add> di <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: 6a1a7d6b1ef9732e015536d8a78c058fe348113f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255497"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="ca649-102">\<aggiungere > di \<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="ca649-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="ca649-103">Specifica i criteri di autorizzazione per la trasformazione di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="ca649-103">Specifies an authorization policy for claim transformation.</span></span>  
  
 <span data-ttu-id="ca649-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ca649-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ca649-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ca649-105">\<behaviors></span></span>  
<span data-ttu-id="ca649-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ca649-106">\<behavior></span></span>  
<span data-ttu-id="ca649-107">\<serviceAuthorization></span><span class="sxs-lookup"><span data-stu-id="ca649-107">\<serviceAuthorization></span></span>  
<span data-ttu-id="ca649-108">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="ca649-108">\<authorizationPolicies></span></span>  
<span data-ttu-id="ca649-109">\<add></span><span class="sxs-lookup"><span data-stu-id="ca649-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca649-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca649-110">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="ca649-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="ca649-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca649-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ca649-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ca649-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ca649-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca649-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="ca649-114">Attributes</span></span>  
  
|<span data-ttu-id="ca649-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="ca649-115">Attribute</span></span>|<span data-ttu-id="ca649-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca649-116">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="ca649-117">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ca649-117">A required String attribute.</span></span><br /><br /> <span data-ttu-id="ca649-118">Il modello di controllo di accesso di Windows Communication Foundation (WCF) supporta il provisioning di un set di criteri di autorizzazione come tipi.</span><span class="sxs-lookup"><span data-stu-id="ca649-118">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="ca649-119">Questo attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="ca649-119">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="ca649-120">Su questa base può essere concesso o negato il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="ca649-120">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca649-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ca649-121">Child Elements</span></span>  
 <span data-ttu-id="ca649-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ca649-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca649-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ca649-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ca649-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="ca649-124">Element</span></span>|<span data-ttu-id="ca649-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca649-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca649-126">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="ca649-126">\<authorizationPolicies></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|<span data-ttu-id="ca649-127">Specifica una raccolta di tipi di criteri di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="ca649-127">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca649-128">Note</span><span class="sxs-lookup"><span data-stu-id="ca649-128">Remarks</span></span>  
 <span data-ttu-id="ca649-129">Ciascun criterio di autorizzazione contiene un solo attributo `policyType` obbligatorio che è una stringa.</span><span class="sxs-lookup"><span data-stu-id="ca649-129">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="ca649-130">L'attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="ca649-130">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="ca649-131">Su questa base può essere concesso o negato il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="ca649-131">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="ca649-132">Per altre informazioni sul funzionamento dei criteri di autorizzazione, vedere <xref:System.IdentityModel.Policy.IAuthorizationPolicy> e [criteri di autorizzazione](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="ca649-132">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca649-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca649-133">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="ca649-134">Autorizzazione dell'accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="ca649-134">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="ca649-135">Procedura: Creare un gestore autorizzazioni personalizzato per un servizio</span><span class="sxs-lookup"><span data-stu-id="ca649-135">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="ca649-136">\<add></span><span class="sxs-lookup"><span data-stu-id="ca649-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)
- [<span data-ttu-id="ca649-137">Criteri di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ca649-137">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)

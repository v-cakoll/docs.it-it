---
title: <add> di <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: 532f7f1a74cb3af24d7a1bc26046be901f3cf025
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59205238"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="f707f-102">\<aggiungere > di \<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="f707f-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="f707f-103">Specifica i criteri di autorizzazione per la trasformazione di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="f707f-103">Specifies an authorization policy for claim transformation.</span></span>  
  
 <span data-ttu-id="f707f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f707f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f707f-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f707f-105">\<behaviors></span></span>  
<span data-ttu-id="f707f-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f707f-106">\<behavior></span></span>  
<span data-ttu-id="f707f-107">\<serviceAuthorization></span><span class="sxs-lookup"><span data-stu-id="f707f-107">\<serviceAuthorization></span></span>  
<span data-ttu-id="f707f-108">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="f707f-108">\<authorizationPolicies></span></span>  
<span data-ttu-id="f707f-109">\<add></span><span class="sxs-lookup"><span data-stu-id="f707f-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f707f-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f707f-110">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="f707f-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="f707f-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f707f-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f707f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f707f-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f707f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f707f-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="f707f-114">Attributes</span></span>  
  
|<span data-ttu-id="f707f-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="f707f-115">Attribute</span></span>|<span data-ttu-id="f707f-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f707f-116">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="f707f-117">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f707f-117">A required String attribute.</span></span><br /><br /> <span data-ttu-id="f707f-118">Il modello di controllo di accesso di Windows Communication Foundation (WCF) supporta il provisioning di un set di criteri di autorizzazione come tipi.</span><span class="sxs-lookup"><span data-stu-id="f707f-118">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="f707f-119">Questo attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="f707f-119">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="f707f-120">Su questa base può essere concesso o negato il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="f707f-120">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f707f-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f707f-121">Child Elements</span></span>  
 <span data-ttu-id="f707f-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f707f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f707f-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f707f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f707f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="f707f-124">Element</span></span>|<span data-ttu-id="f707f-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f707f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f707f-126">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="f707f-126">\<authorizationPolicies></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|<span data-ttu-id="f707f-127">Specifica una raccolta di tipi di criteri di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="f707f-127">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f707f-128">Note</span><span class="sxs-lookup"><span data-stu-id="f707f-128">Remarks</span></span>  
 <span data-ttu-id="f707f-129">Ciascun criterio di autorizzazione contiene un solo attributo `policyType` obbligatorio che è una stringa.</span><span class="sxs-lookup"><span data-stu-id="f707f-129">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="f707f-130">L'attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="f707f-130">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="f707f-131">Su questa base può essere concesso o negato il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="f707f-131">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="f707f-132">Per altre informazioni sul funzionamento dei criteri di autorizzazione, vedere <xref:System.IdentityModel.Policy.IAuthorizationPolicy> e [criteri di autorizzazione](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f707f-132">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f707f-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f707f-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="f707f-134">Autorizzazione dell'accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="f707f-134">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="f707f-135">Procedura: Creare un gestore autorizzazioni personalizzato per un servizio</span><span class="sxs-lookup"><span data-stu-id="f707f-135">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="f707f-136">\<add></span><span class="sxs-lookup"><span data-stu-id="f707f-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)
- [<span data-ttu-id="f707f-137">Criteri di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="f707f-137">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)

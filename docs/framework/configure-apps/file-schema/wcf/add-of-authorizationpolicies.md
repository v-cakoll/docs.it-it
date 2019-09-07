---
title: <add> di <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: e2597bc51e788c919bfe3ce3422ae2911cc6b33b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400691"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="3f475-102">\<aggiungere > di \<AuthorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="3f475-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="3f475-103">Specifica i criteri di autorizzazione per la trasformazione di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="3f475-103">Specifies an authorization policy for claim transformation.</span></span>  
  
<span data-ttu-id="3f475-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3f475-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3f475-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3f475-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3f475-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3f475-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="3f475-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3f475-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="3f475-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3f475-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="3f475-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceAuthorization**](serviceauthorization-element.md)</span><span class="sxs-lookup"><span data-stu-id="3f475-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceAuthorization>**](serviceauthorization-element.md)</span></span>\
<span data-ttu-id="3f475-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> authorizationPolicies**](authorizationpolicies.md)</span><span class="sxs-lookup"><span data-stu-id="3f475-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<authorizationPolicies>**](authorizationpolicies.md)</span></span>\
<span data-ttu-id="3f475-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="3f475-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f475-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f475-112">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="3f475-113">Type</span><span class="sxs-lookup"><span data-stu-id="3f475-113">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f475-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3f475-114">Attributes and Elements</span></span>  
 <span data-ttu-id="3f475-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3f475-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f475-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="3f475-116">Attributes</span></span>  
  
|<span data-ttu-id="3f475-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="3f475-117">Attribute</span></span>|<span data-ttu-id="3f475-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f475-118">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="3f475-119">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3f475-119">A required String attribute.</span></span><br /><br /> <span data-ttu-id="3f475-120">Il modello di controllo di accesso Windows Communication Foundation (WCF) supporta il provisioning di un set di criteri di autorizzazione come tipi.</span><span class="sxs-lookup"><span data-stu-id="3f475-120">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="3f475-121">Questo attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="3f475-121">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="3f475-122">Su questa base può essere concesso o negato il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="3f475-122">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f475-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3f475-123">Child Elements</span></span>  
 <span data-ttu-id="3f475-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3f475-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f475-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3f475-125">Parent Elements</span></span>  
  
|<span data-ttu-id="3f475-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="3f475-126">Element</span></span>|<span data-ttu-id="3f475-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f475-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f475-128">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="3f475-128">\<authorizationPolicies></span></span>](authorizationpolicies.md)|<span data-ttu-id="3f475-129">Specifica una raccolta di tipi di criteri di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="3f475-129">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f475-130">Note</span><span class="sxs-lookup"><span data-stu-id="3f475-130">Remarks</span></span>  
 <span data-ttu-id="3f475-131">Ciascun criterio di autorizzazione contiene un solo attributo `policyType` obbligatorio che è una stringa.</span><span class="sxs-lookup"><span data-stu-id="3f475-131">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="3f475-132">L'attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="3f475-132">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="3f475-133">Su questa base può essere concesso o negato il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="3f475-133">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="3f475-134">Per ulteriori informazioni sul funzionamento di un criterio di autorizzazione, <xref:System.IdentityModel.Policy.IAuthorizationPolicy> vedere e [criteri di autorizzazione](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="3f475-134">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f475-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f475-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="3f475-136">Autorizzazione dell'accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="3f475-136">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="3f475-137">Procedura: Creazione di un gestore autorizzazioni personalizzato per un servizio</span><span class="sxs-lookup"><span data-stu-id="3f475-137">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="3f475-138">\<add></span><span class="sxs-lookup"><span data-stu-id="3f475-138">\<add></span></span>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="3f475-139">Criteri di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3f475-139">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)

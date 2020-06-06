---
title: <add> di <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: e2597bc51e788c919bfe3ce3422ae2911cc6b33b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400691"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="4ca4c-102">\<add> di \<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="4ca4c-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="4ca4c-103">Specifica i criteri di autorizzazione per la trasformazione di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="4ca4c-103">Specifies an authorization policy for claim transformation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceAuthorization>**](serviceauthorization-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<authorizationPolicies>**](authorizationpolicies.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="4ca4c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ca4c-104">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="4ca4c-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="4ca4c-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ca4c-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4ca4c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="4ca4c-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4ca4c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ca4c-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="4ca4c-108">Attributes</span></span>  
  
|<span data-ttu-id="4ca4c-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="4ca4c-109">Attribute</span></span>|<span data-ttu-id="4ca4c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ca4c-110">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="4ca4c-111">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4ca4c-111">A required String attribute.</span></span><br /><br /> <span data-ttu-id="4ca4c-112">Il modello di controllo di accesso Windows Communication Foundation (WCF) supporta il provisioning di un set di criteri di autorizzazione come tipi.</span><span class="sxs-lookup"><span data-stu-id="4ca4c-112">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="4ca4c-113">Questo attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="4ca4c-113">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="4ca4c-114">Su questa base può essere concesso o negato il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="4ca4c-114">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ca4c-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4ca4c-115">Child Elements</span></span>  
 <span data-ttu-id="4ca4c-116">No.</span><span class="sxs-lookup"><span data-stu-id="4ca4c-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ca4c-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4ca4c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4ca4c-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="4ca4c-118">Element</span></span>|<span data-ttu-id="4ca4c-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ca4c-119">Description</span></span>|  
|-------------|-----------------|  
|[\<authorizationPolicies>](authorizationpolicies.md)|<span data-ttu-id="4ca4c-120">Specifica una raccolta di tipi di criteri di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="4ca4c-120">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ca4c-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="4ca4c-121">Remarks</span></span>  
 <span data-ttu-id="4ca4c-122">Ciascun criterio di autorizzazione contiene un solo attributo `policyType` obbligatorio che è una stringa.</span><span class="sxs-lookup"><span data-stu-id="4ca4c-122">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="4ca4c-123">L'attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="4ca4c-123">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="4ca4c-124">Su questa base può essere concesso o negato il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="4ca4c-124">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="4ca4c-125">Per ulteriori informazioni sul funzionamento di un criterio di autorizzazione, vedere <xref:System.IdentityModel.Policy.IAuthorizationPolicy> e [criteri di autorizzazione](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="4ca4c-125">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca4c-126">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4ca4c-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="4ca4c-127">Autorizzazione dell'accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="4ca4c-127">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="4ca4c-128">Procedura: Creare un gestore autorizzazioni personalizzato per un servizio</span><span class="sxs-lookup"><span data-stu-id="4ca4c-128">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [\<add>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="4ca4c-129">Criteri di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4ca4c-129">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)

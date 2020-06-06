---
title: <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 38d123a53b344ff1e4d781115093d0d1de5ae679
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "69926456"
---
# \<authorizationPolicies>
<span data-ttu-id="4f8aa-101">Questa sezione di configurazione contiene una raccolta di tipi di criteri di autorizzazione che possono essere aggiunti mediante la parola chiave `add`.</span><span class="sxs-lookup"><span data-stu-id="4f8aa-101">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="4f8aa-102">Ciascun criterio di autorizzazione contiene un solo attributo `policyType` obbligatorio che è una stringa.</span><span class="sxs-lookup"><span data-stu-id="4f8aa-102">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="4f8aa-103">L'attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="4f8aa-103">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="4f8aa-104">Su questa base può essere concesso o negato il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="4f8aa-104">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="4f8aa-105">Per ulteriori informazioni sul funzionamento di un criterio di autorizzazione, vedere <xref:System.IdentityModel.Policy.IAuthorizationPolicy> e [criteri di autorizzazione](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="4f8aa-105">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f8aa-106">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4f8aa-106">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="4f8aa-107">Autorizzazione dell'accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="4f8aa-107">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="4f8aa-108">Procedura: Creare un gestore autorizzazioni personalizzato per un servizio</span><span class="sxs-lookup"><span data-stu-id="4f8aa-108">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [\<add>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="4f8aa-109">Criteri di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4f8aa-109">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)

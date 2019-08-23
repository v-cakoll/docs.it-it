---
title: <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 38d123a53b344ff1e4d781115093d0d1de5ae679
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926456"
---
# <a name="authorizationpolicies"></a><span data-ttu-id="e5280-101">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="e5280-101">\<authorizationPolicies></span></span>
<span data-ttu-id="e5280-102">Questa sezione di configurazione contiene una raccolta di tipi di criteri di autorizzazione che possono essere aggiunti mediante la parola chiave `add`.</span><span class="sxs-lookup"><span data-stu-id="e5280-102">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="e5280-103">Ciascun criterio di autorizzazione contiene un solo attributo `policyType` obbligatorio che è una stringa.</span><span class="sxs-lookup"><span data-stu-id="e5280-103">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="e5280-104">L'attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="e5280-104">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="e5280-105">Su questa base può essere concesso o negato il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="e5280-105">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="e5280-106">Per ulteriori informazioni sul funzionamento di un criterio di autorizzazione, <xref:System.IdentityModel.Policy.IAuthorizationPolicy> vedere e [criteri di autorizzazione](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="e5280-106">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5280-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5280-107">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="e5280-108">Autorizzazione dell'accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="e5280-108">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="e5280-109">Procedura: Creazione di un gestore autorizzazioni personalizzato per un servizio</span><span class="sxs-lookup"><span data-stu-id="e5280-109">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="e5280-110">\<add></span><span class="sxs-lookup"><span data-stu-id="e5280-110">\<add></span></span>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="e5280-111">Criteri di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e5280-111">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)

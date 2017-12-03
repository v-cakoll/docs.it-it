---
title: '&lt;authorizationPolicies&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 94bbf10ad093c6b99d586f9aaacb7faffc097cee
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltauthorizationpoliciesgt"></a><span data-ttu-id="dcb11-102">&lt;authorizationPolicies&gt;</span><span class="sxs-lookup"><span data-stu-id="dcb11-102">&lt;authorizationPolicies&gt;</span></span>
<span data-ttu-id="dcb11-103">Questa sezione di configurazione contiene una raccolta di tipi di criteri di autorizzazione che possono essere aggiunti mediante la parola chiave `add`.</span><span class="sxs-lookup"><span data-stu-id="dcb11-103">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="dcb11-104">Ciascun criterio di autorizzazione contiene un solo attributo `policyType` obbligatorio che è una stringa.</span><span class="sxs-lookup"><span data-stu-id="dcb11-104">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="dcb11-105">L'attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="dcb11-105">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="dcb11-106">Su questa base può essere concesso o negato il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="dcb11-106">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="dcb11-107">Per ulteriori informazioni sul funzionamento di un criterio di autorizzazione, vedere <xref:System.IdentityModel.Policy.IAuthorizationPolicy> e [criteri di autorizzazione](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="dcb11-107">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcb11-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcb11-108">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>  
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>  
 [<span data-ttu-id="dcb11-109">Autorizzazione dell'accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="dcb11-109">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="dcb11-110">Procedura: creare un gestore autorizzazioni personalizzato per un servizio</span><span class="sxs-lookup"><span data-stu-id="dcb11-110">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [<span data-ttu-id="dcb11-111">\<add></span><span class="sxs-lookup"><span data-stu-id="dcb11-111">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)  
 [<span data-ttu-id="dcb11-112">Criteri di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="dcb11-112">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)

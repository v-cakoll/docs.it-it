---
title: Elemento &lt;claimTypeRequirements&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 187fedc6f81e1cc4a022bfe3b6c68e2c12d09022
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltclaimtyperequirementsgt-element"></a><span data-ttu-id="d0721-102">Elemento &lt;claimTypeRequirements&gt;</span><span class="sxs-lookup"><span data-stu-id="d0721-102">&lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="d0721-103">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="d0721-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="d0721-104">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="d0721-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="d0721-105">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="d0721-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="d0721-106">Ogni elemento figlio di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="d0721-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="d0721-107">Un requisito del tipo di attestazione è costituito da un URI del tipo di attestazione necessario nel token rilasciato e da un parametro booleano che indica se il tipo attestazione specifico è necessario nel token rilasciato o è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d0721-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0721-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0721-108">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="d0721-109">L'autenticazione e identità del servizio</span><span class="sxs-lookup"><span data-stu-id="d0721-109">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="d0721-110">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="d0721-110">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="d0721-111">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="d0721-111">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="d0721-112">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="d0721-112">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="d0721-113">\<add></span><span class="sxs-lookup"><span data-stu-id="d0721-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md)  
 [<span data-ttu-id="d0721-114">Associazioni</span><span class="sxs-lookup"><span data-stu-id="d0721-114">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d0721-115">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="d0721-115">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="d0721-116">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="d0721-116">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="d0721-117">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d0721-117">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="d0721-118">Procedura: creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d0721-118">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="d0721-119">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="d0721-119">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)

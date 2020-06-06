---
title: Elemento <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
ms.openlocfilehash: b4d8479dd9a24774afbd0549caf9e261f55fa147
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "69926149"
---
# <a name="claimtyperequirements-element"></a><span data-ttu-id="ac3e4-102">Elemento \<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="ac3e4-102">\<claimTypeRequirements> element</span></span>
<span data-ttu-id="ac3e4-103">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="ac3e4-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="ac3e4-104">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="ac3e4-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="ac3e4-105">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="ac3e4-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="ac3e4-106">Ogni elemento figlio di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="ac3e4-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="ac3e4-107">Un requisito del tipo di attestazione è costituito da un URI del tipo di attestazione necessario nel token rilasciato e da un parametro booleano che indica se il tipo attestazione specifico è necessario nel token rilasciato o è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ac3e4-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac3e4-108">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ac3e4-108">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ac3e4-109">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="ac3e4-109">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ac3e4-110">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="ac3e4-110">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ac3e4-111">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="ac3e4-111">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="ac3e4-112">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="ac3e4-112">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](add-of-claimtyperequirements.md)
- [<span data-ttu-id="ac3e4-113">Binding</span><span class="sxs-lookup"><span data-stu-id="ac3e4-113">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ac3e4-114">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="ac3e4-114">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ac3e4-115">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="ac3e4-115">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="ac3e4-116">Procedura: creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ac3e4-116">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="ac3e4-117">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="ac3e4-117">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)

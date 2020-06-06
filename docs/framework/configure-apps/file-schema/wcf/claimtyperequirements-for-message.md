---
title: <claimTypeRequirements> per <message>
ms.date: 03/30/2017
ms.assetid: f95c5ecd-abb6-4b77-a6d7-a38727f4a142
ms.openlocfilehash: db6717022bf3af0c4922818668595dd3937e9c71
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "61704407"
---
# <a name="claimtyperequirements-for-message"></a><span data-ttu-id="49840-102">\<claimTypeRequirements> per \<message></span><span class="sxs-lookup"><span data-stu-id="49840-102">\<claimTypeRequirements> for \<message></span></span>
<span data-ttu-id="49840-103">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="49840-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="49840-104">La raccolta viene usata dal servizio per specificare tutte le attestazioni obbligatorie e facoltative che devono essere presenti nel token rilasciato usato dal client per accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="49840-104">The collection is used by the service to specify any required and optional claims which must be in the issued token the client uses to access the service.</span></span> <span data-ttu-id="49840-105">Se la pubblicazione WSDL è attiva, il servizio espone i tipi di attestazione obbligatori nei metadati. Tuttavia, WCF non richiede che il token emesso contenga i tipi di attestazione specificati.</span><span class="sxs-lookup"><span data-stu-id="49840-105">The service exposes the required claim types in metadata if WSDL publishing is enabled but WCF does not require the issued token contain the specified claim types.</span></span> <span data-ttu-id="49840-106">I servizi che desiderano imporre la presenza di tipi di attestazione obbligatori devono ricorrere ai criteri di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="49840-106">Services wishing to enforce required claim types are present should do using authorization policy.</span></span>  
  
 <span data-ttu-id="49840-107">Nei client federati, questa raccolta contiene l'elenco delle attestazioni obbligatorie e facoltative inviato al servizio token di sicurezza nella richiesta del client per un token rilasciato.</span><span class="sxs-lookup"><span data-stu-id="49840-107">On federated clients, this collection contains the list of required and optional claims which is sent to the security token service in the client’s request for an issued token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49840-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49840-108">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>

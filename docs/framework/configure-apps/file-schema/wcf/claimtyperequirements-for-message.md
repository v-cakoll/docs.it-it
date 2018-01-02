---
title: '&lt;claimTypeRequirements&gt; di &lt;message&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f95c5ecd-abb6-4b77-a6d7-a38727f4a142
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5497156862859b2a797f27150362ed3a0498849a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltclaimtyperequirementsgt-for-ltmessagegt"></a><span data-ttu-id="044d2-102">&lt;claimTypeRequirements&gt; di &lt;message&gt;</span><span class="sxs-lookup"><span data-stu-id="044d2-102">&lt;claimTypeRequirements&gt; for &lt;message&gt;</span></span>
<span data-ttu-id="044d2-103">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="044d2-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="044d2-104">La raccolta viene usata dal servizio per specificare tutte le attestazioni obbligatorie e facoltative che devono essere presenti nel token rilasciato usato dal client per accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="044d2-104">The collection is used by the service to specify any required and optional claims which must be in the issued token the client uses to access the service.</span></span> <span data-ttu-id="044d2-105">Se la pubblicazione WSDL è attiva, il servizio espone i tipi di attestazione obbligatori nei metadati. Tuttavia, WCF non richiede che il token emesso contenga i tipi di attestazione specificati.</span><span class="sxs-lookup"><span data-stu-id="044d2-105">The service exposes the required claim types in metadata if WSDL publishing is enabled but WCF does not require the issued token contain the specified claim types.</span></span> <span data-ttu-id="044d2-106">I servizi che desiderano imporre la presenza di tipi di attestazione obbligatori devono ricorrere ai criteri di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="044d2-106">Services wishing to enforce required claim types are present should do using authorization policy.</span></span>  
  
 <span data-ttu-id="044d2-107">Nei client federati, questa raccolta contiene l'elenco delle attestazioni obbligatorie e facoltative inviato al servizio token di sicurezza nella richiesta del client per un token rilasciato.</span><span class="sxs-lookup"><span data-stu-id="044d2-107">On federated clients, this collection contains the list of required and optional claims which is sent to the security token service in the client’s request for an issued token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="044d2-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="044d2-108">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>

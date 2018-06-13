---
title: '&lt;claimTypeRequirements&gt; di &lt;message&gt;'
ms.date: 03/30/2017
ms.assetid: f95c5ecd-abb6-4b77-a6d7-a38727f4a142
ms.openlocfilehash: f4460311f5478f441b819bc8a48540d6feea69b1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754545"
---
# <a name="ltclaimtyperequirementsgt-for-ltmessagegt"></a>&lt;claimTypeRequirements&gt; di &lt;message&gt;
Specifica una raccolta di tipi di attestazione obbligatori.  
  
 La raccolta viene usata dal servizio per specificare tutte le attestazioni obbligatorie e facoltative che devono essere presenti nel token rilasciato usato dal client per accedere al servizio. Se la pubblicazione WSDL è attiva, il servizio espone i tipi di attestazione obbligatori nei metadati. Tuttavia, WCF non richiede che il token emesso contenga i tipi di attestazione specificati. I servizi che desiderano imporre la presenza di tipi di attestazione obbligatori devono ricorrere ai criteri di autorizzazione.  
  
 Nei client federati, questa raccolta contiene l'elenco delle attestazioni obbligatorie e facoltative inviato al servizio token di sicurezza nella richiesta del client per un token rilasciato.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>

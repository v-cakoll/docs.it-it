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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 747ac641f8602010819baa00033f3663e2e5f678
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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

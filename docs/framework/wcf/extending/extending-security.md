---
title: Estensione della protezione
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: 698d65d951ed7adad5aa32e874befb15a3b24d12
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261427"
---
# <a name="extending-security"></a>Estensione della protezione
Per supportare nuovi tipi di attestazioni e token personalizzati, è possibile estendere l'infrastruttura di sicurezza di Windows Communication Foundation (WCF). Questa operazione viene descritta negli argomenti di questa sezione.  
  
## <a name="in-this-section"></a>In questa sezione  
  
 [Credenziali personalizzate e convalida delle credenziali](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 Viene spiegato il modo in cui il modello di identità viene utilizzato durante la convalida di credenziali personalizzate.  
  
 [Token personalizzati](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 I token rilasciati da un servizio token di sicurezza (STS) sono in genere token SAML. In questo argomento viene spiegato come creare un tipo di token personalizzato.  
  
 [Autorizzazione personalizzata](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 Viene spiegato come implementare un'autorizzazione personalizzata.  
  
 [Override dell'identità di un servizio per l'autenticazione](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 Viene descritto come eseguire l'override dell'identità di un servizio per l'autenticazione.  
  
 [Procedura: Creare un verificatore di identità Client personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 Viene dimostrato come convalidare l'identità di un endpoint personalizzato.  
  
 [Procedura: Usare certificati X.509 separati per la firma e crittografia](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 I messaggi vengono in genere firmati e crittografati con un solo certificato. In questo argomento viene spiegato come sia possibile utilizzare due certificati, se necessario.  
  
 [Procedura: Modificare il Provider di crittografia per la chiave privata di un certificato X.509](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 Viene illustrato come modificare il provider di crittografia utilizzato per fornire la chiave privata di un certificato X.509 e come integrare il provider nel framework di Windows Communication Foundation (WCF).  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Sicurezza](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [Programmazione WCF di base](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica della sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md)

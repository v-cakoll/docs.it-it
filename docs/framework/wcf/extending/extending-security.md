---
title: Estensione della protezione
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: 45216493a3afa23f24a085964a2c43e19b197d4b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797127"
---
# <a name="extending-security"></a>Estensione della protezione
Per supportare nuovi tipi di attestazione e token personalizzati, è possibile estendere l'infrastruttura di sicurezza di Windows Communication Foundation (WCF). Questa operazione viene descritta negli argomenti di questa sezione.  
  
## <a name="in-this-section"></a>In questa sezione  
  
 [Credenziali personalizzate e convalida delle credenziali](custom-credential-and-credential-validation.md)  
 Viene spiegato il modo in cui il modello di identità viene utilizzato durante la convalida di credenziali personalizzate.  
  
 [Token personalizzati](custom-tokens.md)  
 I token rilasciati da un servizio token di sicurezza (STS) sono in genere token SAML. In questo argomento viene spiegato come creare un tipo di token personalizzato.  
  
 [Autorizzazione personalizzata](custom-authorization.md)  
 Viene spiegato come implementare un'autorizzazione personalizzata.  
  
 [Override dell'identità di un servizio per l'autenticazione](overriding-the-identity-of-a-service-for-authentication.md)  
 Viene descritto come eseguire l'override dell'identità di un servizio per l'autenticazione.  
  
 [Procedura: Creare un verificatore di identità client personalizzato](how-to-create-a-custom-client-identity-verifier.md)  
 Viene dimostrato come convalidare l'identità di un endpoint personalizzato.  
  
 [Procedura: Usare certificati X. 509 distinti per la firma e la crittografia](how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 I messaggi vengono in genere firmati e crittografati con un solo certificato. In questo argomento viene spiegato come sia possibile utilizzare due certificati, se necessario.  
  
 [Procedura: Modificare il provider di crittografia per la chiave privata di un certificato X. 509](change-cryptographic-provider-x509-certificate-private-key.md)  
 Viene illustrato come modificare il provider di crittografia utilizzato per fornire la chiave privata di un certificato X. 509 e come integrare il provider nel Framework Windows Communication Foundation (WCF).  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Sicurezza](../feature-details/security.md)  
  
 [Programmazione WCF di base](../basic-wcf-programming.md)  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della sicurezza](../feature-details/security-overview.md)

---
title: Credenziale personalizzata e convalida della credenziale
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bdfd50253c71bfc9edd737964e771546cb797b9e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="custom-credential-and-credential-validation"></a>Credenziale personalizzata e convalida della credenziale
La protezione in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] si basa sullo scambio di credenziali tra servizi e client. La maggior parte degli scenari di sicurezza può essere soddisfatta usando tipi di credenziali comuni, ad esempio Windows (Kerberos), nome utente e password e certificati. Tuttavia, se è necessario un nuovo tipo di credenziale, negli argomenti di questa sezione viene illustrato come gestire e convalidare nuovi tipi.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Creare un servizio che usi un validator del certificato personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 Viene illustrato come personalizzare la convalida [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ereditando dalla classe <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  
  
 [Procedura dettagliata: creazione di credenziali client e del servizio personalizzate](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 Viene illustrato come estendere il <xref:System.ServiceModel.Description.ClientCredentials> e <xref:System.ServiceModel.Description.ServiceCredentials> classi per accogliere nuovi tipi di credenziali. Si tratta del primo di una serie di argomenti sulla creazione di tipi di credenziali personalizzati.  
  
 [Procedura: Creare un provider di token di sicurezza personalizzati](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 Viene illustrato come creare un provider di token di sicurezza per gestire nuovi tipi di credenziali e restituire nuovi token per la credenziale. Si tratta del secondo argomento della serie.  
  
 [Procedura: Creare un autenticatore del token di sicurezza personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 Viene illustrato come creare un autenticatore personalizzato per autenticare un nuovo tipo di credenziale. Si tratta del terzo argomento della serie.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Autenticazione](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [Federazione e token rilasciati](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [Autorizzazione](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Sicurezza](../../../../docs/framework/wcf/feature-details/security.md)

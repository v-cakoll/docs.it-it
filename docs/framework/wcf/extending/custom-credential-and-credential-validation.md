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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c3ca7726f3a6a0c5faaab1cbbd0b31125ce0c1d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="custom-credential-and-credential-validation"></a>Credenziale personalizzata e convalida della credenziale
La protezione in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] si basa sullo scambio di credenziali tra servizi e client. La maggior parte degli scenari di sicurezza può essere soddisfatta usando tipi di credenziali comuni, ad esempio Windows (Kerberos), nome utente e password e certificati. Tuttavia, se è necessario un nuovo tipo di credenziale, negli argomenti di questa sezione viene illustrato come gestire e convalidare nuovi tipi.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: creare un servizio che usa un Validator del certificato personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 Viene illustrato come personalizzare la convalida [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ereditando dalla classe <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  
  
 [Procedura dettagliata: Creazione di Client personalizzate e le credenziali del servizio](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 Viene illustrato come estendere il <xref:System.ServiceModel.Description.ClientCredentials> e <xref:System.ServiceModel.Description.ServiceCredentials> classi per accogliere nuovi tipi di credenziali. Si tratta del primo di una serie di argomenti sulla creazione di tipi di credenziali personalizzati.  
  
 [Procedura: creare un Provider di Token di sicurezza personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 Viene illustrato come creare un provider di token di sicurezza per gestire nuovi tipi di credenziali e restituire nuovi token per la credenziale. Si tratta del secondo argomento della serie.  
  
 [Procedura: creare un autenticatore del Token di sicurezza personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 Viene illustrato come creare un autenticatore personalizzato per autenticare un nuovo tipo di credenziale. Si tratta del terzo argomento della serie.  
  
## <a name="reference"></a>Riferimento  
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
  
 [Federazione e token emessi](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [Autorizzazione](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Sicurezza](../../../../docs/framework/wcf/feature-details/security.md)

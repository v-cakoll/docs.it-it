---
title: Credenziale personalizzata e convalida della credenziale
ms.date: 03/30/2017
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
ms.openlocfilehash: 1418d4155bc7f2fefc9f3e6caf4d3a264747a667
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795810"
---
# <a name="custom-credential-and-credential-validation"></a>Credenziale personalizzata e convalida della credenziale
La sicurezza in Windows Communication Foundation (WCF) è basata sullo scambio di credenziali tra servizi e client. La maggior parte degli scenari di sicurezza può essere soddisfatta usando tipi di credenziali comuni, ad esempio Windows (Kerberos), nome utente e password e certificati. Tuttavia, se è necessario un nuovo tipo di credenziale, negli argomenti di questa sezione viene illustrato come gestire e convalidare nuovi tipi.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Creare un servizio che usa un validator del certificato personalizzato](how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 Viene illustrato come personalizzare la <xref:System.IdentityModel.Selectors.X509CertificateValidator> convalida WCF ereditando dalla classe.  
  
 [Procedura dettagliata: Creazione di credenziali client e del servizio personalizzate](walkthrough-creating-custom-client-and-service-credentials.md)  
 Viene illustrato come estendere le <xref:System.ServiceModel.Description.ClientCredentials> classi <xref:System.ServiceModel.Description.ServiceCredentials> e per supportare nuovi tipi di credenziali. Si tratta del primo di una serie di argomenti sulla creazione di tipi di credenziali personalizzati.  
  
 [Procedura: Creare un provider di token di sicurezza personalizzato](how-to-create-a-custom-security-token-provider.md)  
 Viene illustrato come creare un provider di token di sicurezza per gestire nuovi tipi di credenziali e restituire nuovi token per la credenziale. Si tratta del secondo argomento della serie.  
  
 [Procedura: Creare un autenticatore del token di sicurezza personalizzato](how-to-create-a-custom-security-token-authenticator.md)  
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
 [Autenticazione](../feature-details/authentication-in-wcf.md)  
  
 [Federazione e token rilasciati](../feature-details/federation-and-issued-tokens.md)  
  
 [Autorizzazione](../feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza](../feature-details/security.md)

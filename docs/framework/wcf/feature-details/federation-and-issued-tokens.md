---
title: Federazione e token emessi
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
ms.openlocfilehash: d566388279f9210f70ebdb5c42512aea0425a47e
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964586"
---
# <a name="federation-and-issued-tokens"></a>Federazione e token emessi
Con Windows Communication Foundation (WCF) è possibile creare client che comunicano in modo sicuro con servizi che implementano le specifiche WS-Federation e WS-Trust. Le specifiche utilizzano XML, SOAP e Web Services Description Language (WSDL) per fornire meccanismi che consentano l'autenticazione e l'autorizzazione in diverse aree di attendibilità.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Federazione](../../../../docs/framework/wcf/feature-details/federation.md)  
 Fornisce una panoramica della federazione.  
  
 [Federazione e attendibilità](../../../../docs/framework/wcf/feature-details/federation-and-trust.md)  
 Elenca i problemi di progettazione da tenere in considerazione durante la creazione di servizi o di client federati.  
  
 [Procedura: Creare un client federato](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 Vengono descritte le nozioni di base sulla creazione di un client federato con WCF.  
  
 [Procedura: Configurare le credenziali in un servizio federativo](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 Descrive i passaggi necessari per la creazione di un servizio federato.  
  
 [Procedura: Creare una classe WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 Descrive come configurare client e servizi che utilizzano `WSFederationHttpBinding`.  
  
 [Procedura: Creare un servizio token di sicurezza](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-token-service.md)  
 Descrive i passaggi necessari per la creazione di un servizio token di sicurezza.  
  
 [Attestazioni e token SAML (Security Assertions Markup Language)](../../../../docs/framework/wcf/feature-details/saml-tokens-and-claims.md)  
 Descrive i token Security Assertions Markup Language (SAML) che sono flessibili e consentono di creare tipi di attestazione dettagliati.  
  
 [Procedura: Configurare un emittente locale](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 Descrive come creare un emittente locale di token di sicurezza.  
  
 [Procedura: Disabilitare sessioni sicure in un'associazione WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 Descrive come disattivare sessioni protette in `WSFederationHttpBinding`. La disattivazione di sessioni protette è necessaria in caso di creazione di una Web farm che richiede una sessione per ogni client.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a>Vedere anche

- [Autorizzazione](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)
- [Token personalizzati](../../../../docs/framework/wcf/extending/custom-tokens.md)
- [Modello di sicurezza per Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))

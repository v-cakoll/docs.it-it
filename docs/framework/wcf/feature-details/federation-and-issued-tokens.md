---
title: Federazione e token emessi
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
ms.openlocfilehash: aeffc1e2a7b61dfd9406b9f06678064533ea61ec
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595505"
---
# <a name="federation-and-issued-tokens"></a>Federazione e token emessi
Con Windows Communication Foundation (WCF) è possibile creare client che comunicano in modo sicuro con servizi che implementano le specifiche WS-Federation e WS-Trust. Le specifiche utilizzano XML, SOAP e Web Services Description Language (WSDL) per fornire meccanismi che consentano l'autenticazione e l'autorizzazione in diverse aree di attendibilità.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Federazione](federation.md)  
 Fornisce una panoramica della federazione.  
  
 [Federazione e attendibilità](federation-and-trust.md)  
 Elenca i problemi di progettazione da tenere in considerazione durante la creazione di servizi o di client federati.  
  
 [Procedura: creare un client federato](how-to-create-a-federated-client.md)  
 Vengono descritte le nozioni di base sulla creazione di un client federato con WCF.  
  
 [Procedura: configurare le credenziali in un servizio federativo](how-to-configure-credentials-on-a-federation-service.md)  
 Descrive i passaggi necessari per la creazione di un servizio federato.  
  
 [Procedura: Creare una classe WSFederationHttpBinding](how-to-create-a-wsfederationhttpbinding.md)  
 Descrive come configurare client e servizi che utilizzano `WSFederationHttpBinding`.  
  
 [Procedura: creare un servizio token di sicurezza](how-to-create-a-security-token-service.md)  
 Descrive i passaggi necessari per la creazione di un servizio token di sicurezza.  
  
 [Attestazioni e token SAML (Security Assertions Markup Language)](saml-tokens-and-claims.md)  
 Descrive i token Security Assertions Markup Language (SAML) che sono flessibili e consentono di creare tipi di attestazione dettagliati.  
  
 [Procedura: configurare un emittente locale](how-to-configure-a-local-issuer.md)  
 Descrive come creare un emittente locale di token di sicurezza.  
  
 [Procedura: disattivare sessioni protette in un'associazione WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 Descrive come disattivare sessioni protette in `WSFederationHttpBinding`. La disattivazione di sessioni protette è necessaria in caso di creazione di una Web farm che richiede una sessione per ogni client.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a>Vedere anche

- [Autorizzazione](authorization-in-wcf.md)
- [Token personalizzati](../extending/custom-tokens.md)
- [Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))

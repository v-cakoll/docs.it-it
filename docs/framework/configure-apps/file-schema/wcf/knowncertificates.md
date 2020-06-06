---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 23fe19258e09e9e8a5e05a94ccef0e40ee1cb5fd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400327"
---
# \<knownCertificates>
Rappresenta una raccolta di certificati X.509 che vengono forniti per autenticare credenziali di sicurezza pubblicate da un servizio token di sicurezza (STS, Security Token Service).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownCertificates>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<add>](add-of-knowncertificates.md)|Aggiunge un certificato X.509 alla raccolta.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|Specifica un token emesso da una credenziale del servizio.|  
  
## <a name="remarks"></a>Commenti  
 L'emissione di un token di autenticazione prevede tre fasi. Nella prima fase, un client che tenta di accedere a un servizio viene fatto riferimento a un *servizio token di sicurezza*. Nella seconda fase, il servizio token di sicurezza autentica il client e quindi rilascia a quest'ultimo un token, in genere un token SAML (Security Assertions Markup Language), che il client restituisce in seguito al servizio. Nella terza fase, il servizio ricerca nel token appena ricevuto i dati da usare per autenticare il token stesso e, pertanto, il client. Affinché il token venga autenticato è necessario che il servizio riconosca il certificato usato dal servizio token di sicurezza.  
  
 L' [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) elemento è il repository per i certificati del servizio token di sicurezza. Per aggiungere certificati, utilizzare l' [ \<knownCertificates> elemento](knowncertificates.md). Inserire un [\<add>](add-of-knowncertificates.md) per ogni certificato, come illustrato nell'esempio seguente.  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 Per impostazione predefinita, i certificati devono essere ottenuti da un servizio token di sicurezza. Questi certificati "riconosciuti" garantiscono che solo i client autorizzati siano in grado di accedere a un determinato servizio.  
  
 Per esaminare le condizioni necessarie per l'autenticazione di un client da un servizio federato, nonché altre informazioni sull'uso di questo elemento di configurazione, vedere [procedura: configurare le credenziali in un servizio federativo](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md). Per ulteriori informazioni sugli scenari federati, vedere [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md).  
  
 Per un esempio in cui viene illustrato come popolare la raccolta nella configurazione, vedere [\<add>](add-of-knowncertificates.md) .  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<add>](add-of-knowncertificates.md)
- [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)
- [Comportamenti di sicurezza](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Procedura: configurare le credenziali in un servizio federativo](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)
- [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](add-of-knowncertificates.md)
- [Securing Services and Clients](../../../wcf/feature-details/securing-services-and-clients.md)

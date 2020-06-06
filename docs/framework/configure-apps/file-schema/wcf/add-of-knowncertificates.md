---
title: <add> di <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 29b067e6ec20992084f9ab3bab087222bdd56da2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400615"
---
# <a name="add-of-knowncertificates"></a>\<add> di \<knownCertificates>
Aggiunge un certificato X.509 alla raccolta di certificati conosciuti.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|findValue|Stringa. Valore da cercare.|  
|storeLocation|Enumerazione. Uno di due percorsi dell'archivio in cui cercare.|  
|storeName|Enumerazione. Uno degli archivi di sistema in cui cercare.|  
|x509FindType|Enumerazione. Uno dei campi certificato in cui cercare.|  
  
## <a name="findvalue-attribute"></a>Attributo findValue  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|string|Il valore dipende dal campo di ricerca specificato dall'attributo X509FindType. Ad esempio, se viene eseguita la ricerca di un'identificazione digitale, il valore deve essere una stringa di numeri esadecimali.|  
  
## <a name="x509findtype-attribute"></a>Attributo x509FindType  
  
|Valore|Description|  
|-----------|-----------------|  
|Enumerazione|I valori includono: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.|  
  
## <a name="storelocation-attribute"></a>Attributo storeLocation  
  
|Valore|Description|  
|-----------|-----------------|  
|Enumerazione|CurrentUser o LocalMachine.|  
  
## <a name="storename-attribute"></a>Attributo storeName  
  
|Valore|Description|  
|-----------|-----------------|  
|Enumerazione|I valori includono: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople e TrustedPublisher.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<knownCertificates>](knowncertificates.md)|Rappresenta una raccolta di certificati X.509 forniti da un servizio token di sicurezza (STS, Security Token Service) per la convalida dei token di sicurezza.|  
  
## <a name="remarks"></a>Commenti  
 L'emissione di un token di autenticazione prevede tre fasi. Nella prima fase, un client che tenta di accedere a un servizio viene fatto riferimento a un *servizio token di sicurezza*. Nella seconda fase, il servizio token di sicurezza autentica il client e quindi rilascia a quest'ultimo un token, in genere un token SAML (Security Assertions Markup Language), che il client restituisce in seguito al servizio. Nella terza fase, il servizio ricerca nel token appena ricevuto i dati da usare per autenticare il token stesso e, pertanto, il client. Affinché il token venga autenticato è necessario che il servizio riconosca il certificato usato dal servizio token di sicurezza.  
  
 L' [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) elemento è il repository per i certificati del servizio token di sicurezza. Per aggiungere certificati, utilizzare [\<knownCertificates>](knowncertificates.md) . Inserire un [ \<add> \<knownCertificates> elemento element](add-of-knowncertificates.md) per ogni certificato, come illustrato nell'esempio seguente.  
  
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
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene aggiunto il certificato al repository per i certificati STS.  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <serviceCredentials>
      <issuedTokenAuthentication>
        <knownCertificates>
          <add findValue="www.contoso.com"
               storeLocation="LocalMachine"
               storeName="CertificateAuthority"
               x509FindType="FindByIssuerName" />
        </knownCertificates>
      </issuedTokenAuthentication>
    </serviceCredentials>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<knownCertificates>](knowncertificates.md)
- [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)
- [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Procedura: configurare le credenziali in un servizio federativo](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Securing Services and Clients](../../../wcf/feature-details/securing-services-and-clients.md)

---
title: <add> di <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 3eb5bf74f909e6036154b7f5f7c6181b09fefbff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077719"
---
# <a name="add-of-knowncertificates"></a>\<aggiungere > di \<knownCertificates >
Aggiunge un certificato X.509 alla raccolta di certificati conosciuti.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceCredentials>  
\<issuedTokenAuthentication>  
\<knownCertificates>  
\<add>  
  
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
  
|Value|Descrizione|  
|-----------|-----------------|  
|Stringa|Il valore dipende dal campo di ricerca specificato dall'attributo X509FindType. Ad esempio, se viene eseguita la ricerca di un'identificazione digitale, il valore deve essere una stringa di numeri esadecimali.|  
  
## <a name="x509findtype-attribute"></a>Attributo x509FindType  
  
|Value|Descrizione|  
|-----------|-----------------|  
|Enumerazione|I valori includono: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.|  
  
## <a name="storelocation-attribute"></a>Attributo storeLocation  
  
|Value|Descrizione|  
|-----------|-----------------|  
|Enumerazione|CurrentUser o LocalMachine.|  
  
## <a name="storename-attribute"></a>Attributo storeName  
  
|Value|Descrizione|  
|-----------|-----------------|  
|Enumerazione|I valori includono: AddressBook, AuthRoot, CertificateAuthority, disattivati, My, Root, TrustedPeople e TrustedPublisher.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)|Rappresenta una raccolta di certificati X.509 forniti da un servizio token di sicurezza (STS, Security Token Service) per la convalida dei token di sicurezza.|  
  
## <a name="remarks"></a>Note  
 L'emissione di un token di autenticazione prevede tre fasi. Nella prima fase, un client tenta di accedere a un servizio viene reindirizzato a un *servizio token di sicurezza*. Nella seconda fase, il servizio token di sicurezza autentica il client e quindi rilascia a quest'ultimo un token, in genere un token SAML (Security Assertions Markup Language), che il client restituisce in seguito al servizio. Nella terza fase, il servizio ricerca nel token appena ricevuto i dati da usare per autenticare il token stesso e, pertanto, il client. Affinché il token venga autenticato è necessario che il servizio riconosca il certificato usato dal servizio token di sicurezza.  
  
 Il [ \<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) elemento è il repository per tutti questi certificati di servizio token di sicurezza. Per aggiungere i certificati, usare il [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md). Inserire un [ \<Aggiungi > elemento \<knownCertificates > elemento](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) per ogni certificato, come illustrato nell'esempio seguente.  
  
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
  
 Per le condizioni necessarie per un client da autenticare presso un servizio federato, nonché altre informazioni sull'uso di questo elemento di configurazione, vedere [come: Configurare le credenziali in un servizio federativo](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md). Per altre informazioni sugli scenari federati, vedere [federazione e token emessi](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)
- [Uso di certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Federazione e token rilasciati](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [Procedura: Configurare le credenziali in un servizio federativo](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

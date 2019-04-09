---
title: <clientCertificate> di <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
ms.openlocfilehash: 5abf0a99beff1b9fb3655cb82d74484f3b88237f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216457"
---
# <a name="clientcertificate-of-clientcredentials-element"></a>\<clientCertificate > di \<clientCredentials > elemento
Definisce un certificato X.509 utilizzato dal client per autenticare un servizio.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<clientCredentials>  
\<clientCertificate>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<clientCertificate findValue="String"
                   storeLocation="LocalMachine/CurrentUser"
                   storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                   X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`findValue`|Stringa che contiene il valore da cercare nell'archivio certificati X.509. Il tipo contenuto in questo attributo deve soddisfare i requisiti del valore `X509FindType` specificato. Il valore predefinito è una stringa vuota.|  
|`storeLocation`|Specifica il percorso del certificato X.509 usato dal client per autenticarsi presso il servizio. Di seguito vengono elencati i valori validi:<br /><br /> -LocalMachine: l'archivio certificati assegnato al computer locale.<br />-CurrentUser: l'archivio certificati assegnato all'utente corrente.<br /><br /> L'impostazione predefinita è LocalMachine. L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|`storeName`|Specifica il nome dell'archivio certificati X.509 in cui eseguire la ricerca. Di seguito vengono elencati i valori validi:<br /><br /> -AddressBook: Archivio certificati per altri utenti.<br />-AuthRoot: Archivio certificati per autorità di certificazione di terze parti (CA).<br />-CertificateAuthority: Archivio certificati per autorità di certificazione intermedie (CA).<br />-Non consentito: Archivio certificati per certificati revocati.<br />-Personali: Archivio certificati per certificati personali.<br />-Root: Archivio certificati per autorità di certificazione radice attendibile (CA).<br />-TrustedPeople: Archivio certificati per le risorse e persone direttamente attendibili.<br />-   TrustedPublisher: Archivio certificati per autori direttamente attendibili.<br /><br /> L'impostazione predefinita è My. L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Definisce il tipo di ricerca X.509 da eseguire. Il tipo contenuto nell'attributo `findValue` deve soddisfare i requisiti di questo attributo. Di seguito vengono elencati i valori validi:<br /><br /> -   FindByThumbPrint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> L'impostazione predefinita è FindBySubjectDistinguishedName. L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Specifica le credenziali usate per autenticare il client presso un servizio.|  
  
## <a name="remarks"></a>Note  
 Questo elemento di configurazione specifica il certificato usato per autenticare il client con questo elemento. Per altre informazioni, vedere [Procedura: Specificare i valori di credenziale Client](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [Comportamenti di sicurezza](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Procedura: Specificare valori di credenziali client](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)
- [Protezione di client](../../../../../docs/framework/wcf/securing-clients.md)
- [Utilizzo dei certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

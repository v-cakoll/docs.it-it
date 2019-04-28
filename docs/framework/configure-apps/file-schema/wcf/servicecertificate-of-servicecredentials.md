---
title: <serviceCertificate> di <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
ms.openlocfilehash: 086b700b94198aa36e61289178ebbed75d33da98
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670313"
---
# <a name="servicecertificate-of-servicecredentials"></a>\<serviceCertificate > di \<serviceCredentials >
Specifica un certificato X.509 che verrà usato dai client per autenticare il servizio tramite la modalità di sicurezza dei messaggi.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceCredentials>  
\<serviceCertificate>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<serviceCertificate findValue="String"
                    storeLocation="LocalMachine/CurrentUser"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`findValue`|Stringa che contiene il valore da cercare nell'archivio certificati X.509. Il tipo contenuto in questo attributo deve soddisfare i requisiti del valore X509FindType specificato. Il valore predefinito è una stringa vuota.|  
|`storeLocation`|Specifica il percorso dell'archivio certificati X.509 usato dal client per convalidare il certificato sul server. Di seguito vengono elencati i valori validi:<br /><br /> -LocalMachine: l'archivio certificati assegnato al computer locale.<br />-CurrentUser: l'archivio certificati assegnato all'utente corrente.<br /><br /> L'impostazione predefinita è LocalMachine.|  
|`storeName`|Specifica il nome dell'archivio certificati X.509 da aprire. Di seguito vengono elencati i valori validi:<br /><br /> -AddressBook: Archivio certificati per altri utenti.<br />-AuthRoot: Archivio certificati per autorità di certificazione di terze parti (CA).<br />-CertificateAuthority: Archivio certificati per autorità di certificazione intermedie (CA).<br />-Non consentito: Archivio certificati per certificati revocati.<br />-Personali: Archivio certificati per certificati personali.<br />-Root: Archivio certificati per autorità di certificazione radice attendibile (CA).<br />-TrustedPeople: Archivio certificati per le risorse e persone direttamente attendibili.<br />-   TrustedPublisher: Archivio certificati per autori direttamente attendibili.<br /><br /> L'impostazione predefinita è My.|  
|`x509FindType`|Definisce il tipo di ricerca X.509 da eseguire. Di seguito vengono elencati i valori validi:<br /><br /> -   FindByThumbprint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> Il tipo contenuto nell'attributo `findValue` deve soddisfare i requisiti del valore X509FindType specificato.<br /><br /> L'impostazione predefinita è FindBySubjectDistinguishedName.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<serviceCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.|  
  
## <a name="remarks"></a>Note  
 Questo elemento consente di specificare il certificato X.509 usato dai client per autenticare il servizio tramite la modalità di sicurezza Messaggio. L'identificazione personale di un certificato che viene rinnovato periodicamente viene anch'essa aggiornata periodicamente di conseguenza. In questo caso, poiché il certificato può essere rilasciato nuovamente con lo stesso nome del soggetto, usare quest'ultimo come tipo `x509FindType`.  
  
 Per altre informazioni sull'utilizzo dell'elemento, vedere [come: Specificare i valori di credenziale Client](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>
- [Procedura: Specificare i valori di credenziale Client](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)
- [Comportamenti di sicurezza](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)

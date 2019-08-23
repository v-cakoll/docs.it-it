---
title: <add>dell' <scopedCertificates> elemento
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: 9756d37527fcf888cad930b24677ae8e6a2c8fba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920050"
---
# <a name="add-of-scopedcertificates-element"></a>\<Aggiungi > dell' \<elemento > scopedCertificates
Aggiunge un certificato X.509 alla raccolta di certificati con ambito.  
  
 \<system.ServiceModel>  
\<comportamenti >  
sezione endpointBehaviors  
\<comportamento >  
\<clientCredentials>  
\<serviceCertificate>  
\<> scopedCertificates  
\<aggiungere > elemento per \<scopedCertificates >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|targetUri|Stringa. Specifica l'URI del servizio associato al certificato.|  
|findValue|Stringa. Valore da cercare.|  
|x509FindType|Enumerazione. Uno dei campi certificato in cui cercare.|  
|storeLocation|Enumerazione. Uno di due percorsi dell'archivio in cui cercare.|  
|storeName|Enumerazione. Uno degli archivi di sistema in cui cercare.|  
  
## <a name="findvalue-attribute"></a>Attributo findValue  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|String|Il valore dipende dal campo di ricerca specificato dall'attributo X509FindType. Ad esempio, se viene eseguita la ricerca di un'identificazione digitale, il valore deve essere una stringa di numeri esadecimali.|  
  
## <a name="x509findtype-attribute"></a>Attributo x509FindType  
  
|Value|Descrizione|  
|-----------|-----------------|  
|Enumerazione|I valori includono: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.|  
  
## <a name="storelocation-attribute"></a>Attributo storeLocation  
  
|Value|DESCRIZIONE|  
|-----------|-----------------|  
|Enumerazione|CurrentUser o LocalMachine.|  
  
## <a name="storename-attribute"></a>Attributo storeName  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|Enumerazione|I valori includono: AddressBook, AuthRoot, CertificateAuthority, non consentito, My, root, TrustedPeople e TrustedPublisher.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<scopedCertificates>](scopedcertificates-element.md)|Rappresenta una raccolta di certificati X.509 fornita da servizi specifici (con ambito) per l'autenticazione.|  
  
## <a name="remarks"></a>Note  
 Questo elemento consente al client di configurare un certificato del servizio da usare in base all'URL del servizio con cui comunica. Questa soluzione è particolarmente utile negli scenari di token pubblicati in cui un client comunica con più servizi (il servizio finale e i servizi token di sicurezza intermedi). Per le associazioni che usano sistemi di sicurezza dei messaggi basati sui certificati, questo certificato viene usato per crittografare i messaggi inviati al servizio ed è previsto che venga usato dal servizio per firmare le risposte al client.  
  
 Se per un'associazione è necessario un certificato per il servizio e non vengono individuati certificati specifici per l'URL del servizio in ScopedCertificates, verrà usato il certificato predefinito.  
  
 Per ulteriori informazioni, vedere la sezione "certificati con ambito" di [procedura: Creare un client](../../../wcf/feature-details/how-to-create-a-federated-client.md)federato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente un certificato X.509 viene aggiunto alla raccolta.  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <serviceCertificate>
          <scopedCertificates>
            <add targetUri="http://www.contoso.com"
                 findValue="www.Contoso.com"
                 storeLocation="LocalMachine"
                 storeName="Root"
                 x509FindType="FindByIssuerName" />
          </scopedCertificates>
        </serviceCertificate>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [Procedura: Creazione di un client federato](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [Uso di certificati](../../../wcf/feature-details/working-with-certificates.md)
- [Protezione di client](../../../wcf/securing-clients.md)
- [Protezione di servizi e client](../../../wcf/feature-details/securing-services-and-clients.md)

---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 6c9c77f96ff6032de43d9b5a257bc0796a19b858
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269341"
---
# <a name="certificatereference"></a>\<certificateReference>
Specifica le impostazioni che consentono di trovare e convalidare un certificato X.509 in un archivio certificati.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<serviceCertificate>  
\<certificateReference>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference   
        storeName="AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher"  
        storeLocation="CurrentUser||LocalMachine"  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|storeName|Il nome dell'archivio certificati X.509. Il valore predefinito è "My". Facoltativo.|  
|storeLocation|Oggetto <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valore che specifica il percorso dell'archivio certificati X.509. Il valore predefinito è "LocalMachine". Facoltativo.|  
|x509FindType|Un <xref:System.Security.Cryptography.X509Certificates.X509FindType> valore che specifica il tipo di ricerca che deve essere eseguito. Il valore predefinito è "FindBySubjectDistinguishedName". Facoltativo.|  
|findValue|Valore da cercare nell'archivio certificati X.509. Facoltativo.|  
|isChainIncluded|Specifica se la convalida deve essere eseguita usando la catena di certificati. Il valore predefinito è "true". la convalida viene eseguita usando la catena di certificati. Facoltativo.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<serviceCertificate>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Configura il certificato utilizzato per crittografare e decrittografare i token.|  
  
## <a name="remarks"></a>Note  
 Il `<certificateReference>` elemento specifica le impostazioni che vengono usate per trovare e convalidare un certificato X.509 in un archivio certificati. Quando viene specificato come elemento figlio del `<serviceCertficate>` elemento, specifica la posizione e verifica le impostazioni del certificato X.509 utilizzato per crittografare e decrittografare i token. Il `<certificateReference>` elemento è rappresentato dal <xref:System.ServiceModel.Configuration.CertificateReferenceElement> classe.

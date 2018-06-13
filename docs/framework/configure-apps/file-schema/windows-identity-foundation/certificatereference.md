---
title: '&lt;certificateReference&gt;'
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e0f9a826a4c8d292346d9efee7970a82b88fb612
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756839"
---
# <a name="ltcertificatereferencegt"></a>&lt;certificateReference&gt;
Specifica le impostazioni che consentono di trovare e convalidare un certificato x. 509 nell'archivio certificati.  
  
 \<IdentityModel >  
\<federationConfiguration >  
\<elemento serviceCertificate >  
\<certificateReference >  
  
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
|storeName|Il nome dell'archivio certificati x. 509. Il valore predefinito è "My". Facoltativo.|  
|storeLocation|Oggetto <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valore che specifica il percorso dell'archivio certificati x. 509. Il valore predefinito è "LocalMachine". Facoltativo.|  
|x509FindType|Un <xref:System.Security.Cryptography.X509Certificates.X509FindType> valore che specifica il tipo di ricerca che deve essere eseguito. Il valore predefinito è "FindBySubjectDistinguishedName". Facoltativo.|  
|findValue|Valore da cercare nell'archivio certificati X.509. Facoltativo.|  
|isChainIncluded|Specifica se la convalida deve essere eseguita usando la catena di certificati. Il valore predefinito è "true". la convalida viene eseguita usando la catena di certificati. Facoltativo.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<elemento serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Consente di configurare il certificato utilizzato per crittografare e decrittografare i token.|  
  
## <a name="remarks"></a>Note  
 Il `<certificateReference>` elemento specifica impostazioni che consentono di trovare e convalidare un certificato x. 509 nell'archivio certificati. Quando viene specificato come elemento figlio del `<serviceCertficate>` elemento, specifica la posizione e verifica le impostazioni del certificato x. 509 utilizzato per crittografare e decrittografare i token. Il `<certificateReference>` elemento è rappresentato dalla <xref:System.ServiceModel.Configuration.CertificateReferenceElement> classe.

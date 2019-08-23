---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: da8ea128466457409334cd0b4ee3246a923f969a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941924"
---
# <a name="certificatereference"></a>\<certificateReference>
Specifica le impostazioni utilizzate per individuare e convalidare un certificato X. 509 in un archivio certificati.  
  
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
|storeName|Nome dell'archivio certificati X. 509. Il valore predefinito è "My". facoltativo.|  
|storeLocation|<xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valore che specifica la posizione dell'archivio certificati X. 509. Il valore predefinito è "LocalMachine". facoltativo.|  
|x509FindType|<xref:System.Security.Cryptography.X509Certificates.X509FindType> Valore che specifica il tipo di ricerca da eseguire. Il valore predefinito è "FindBySubjectDistinguishedName". facoltativo.|  
|findValue|Valore da cercare nell'archivio certificati X.509. facoltativo.|  
|isChainIncluded|Specifica se la convalida deve essere eseguita utilizzando la catena di certificati. Il valore predefinito è "true"; la convalida viene eseguita tramite la catena di certificati. facoltativo.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|Configura il certificato usato per crittografare e decrittografare i token.|  
  
## <a name="remarks"></a>Note  
 L' `<certificateReference>` elemento specifica le impostazioni utilizzate per individuare e convalidare un certificato X. 509 in un archivio certificati. Quando viene specificato come elemento figlio dell' `<serviceCertificate>` elemento, specifica il percorso e le impostazioni di verifica del certificato X. 509 usato per crittografare e decrittografare i token. L' `<certificateReference>` elemento è rappresentato <xref:System.ServiceModel.Configuration.CertificateReferenceElement> dalla classe.

---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 47d432a84d070476ddffd9b98a4ba46d8163bdc3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152814"
---
# <a name="certificatereference"></a>\<> di riferimento
Specifica le impostazioni utilizzate per trovare e convalidare un certificato X.509 in un archivio certificati.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di configurazione**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>serviceCertificate**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>di riferimento**  
  
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
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|storeName|Nome dell'archivio certificati X.509. Il valore predefinito è "My". Facoltativa.|  
|storeLocation|Valore <xref:System.Security.Cryptography.X509Certificates.StoreLocation> che specifica il percorso dell'archivio certificati X.509. Il valore predefinito è "LocalMachine". Facoltativa.|  
|x509FindType|Valore <xref:System.Security.Cryptography.X509Certificates.X509FindType> che specifica il tipo di ricerca da eseguire. Il valore predefinito è "FindBySubjectDistinguishedName". Facoltativa.|  
|findValue|Valore da cercare nell'archivio certificati X.509. Facoltativa.|  
|isChainIncluded|Specifica se la convalida deve essere eseguita utilizzando la catena di certificati. Il valore predefinito è "true"; la convalida viene eseguita utilizzando la catena di certificati. Facoltativa.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>serviceCertificate](servicecertificate.md)|Configura il certificato utilizzato per crittografare e decrittografare i token.|  
  
## <a name="remarks"></a>Osservazioni  
 L'elemento `<certificateReference>` specifica le impostazioni utilizzate per trovare e convalidare un certificato X.509 in un archivio certificati. Quando viene specificato come elemento `<serviceCertificate>` figlio dell'elemento, specifica il percorso e le impostazioni di verifica del certificato X.509 utilizzato per crittografare e decrittografare i token. L'elemento `<certificateReference>` è <xref:System.ServiceModel.Configuration.CertificateReferenceElement> rappresentato dalla classe .

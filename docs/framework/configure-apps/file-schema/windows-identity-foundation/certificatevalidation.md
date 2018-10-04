---
title: '&lt;certificateValidation&gt;'
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 29881be43f02d275ad135efd97dc8b25a7409beb
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48778169"
---
# <a name="ltcertificatevalidationgt"></a>&lt;certificateValidation&gt;
Controllare le impostazioni che utilizzano i gestori di token per convalidare i certificati. Queste impostazioni vengono ignorate se un gestore specifico è configurato con il proprio validator.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<certificateValidation >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|certificateValidationMode|Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valore che specifica la modalità di convalida da utilizzare per il certificato X.509. Il valore predefinito è "PeerOrChainTrust". Per specificare un validator personalizzato, impostare questo attributo su "Custom" e specificare il validator mediante la [ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) elemento. Facoltativo.|  
|revocationMode|Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valore che specifica la modalità di revoche di certificati da utilizzare per il certificato X.509. Il valore predefinito è "Online". Facoltativo.|  
|trustedStoreLocation|Oggetto <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valore che specifica l'archivio certificati X.509. Il valore predefinito è "LocalMachine". Facoltativo.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|Specifica un tipo personalizzato per la convalida del certificato. Questo tipo viene usato solo se il `certificateValidationMode` attributo del [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) elemento è impostato su "Custom".|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Specifica le impostazioni di identità a livello di servizio.|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di sicurezza i gestori di token.|  
  
## <a name="remarks"></a>Note  
 Oggetto `<certificateValidation>` elemento può essere specificato a livello di servizio con il `<identityConfiguration>` elemento o a livello di raccolta gestori di token di sicurezza nel `<securityTokenHandlerConfiguration>` elemento. Le impostazioni in una raccolta di gestori di token sostituiscono quelle specificate nel servizio. Alcuni gestori di token consentono di specificare le impostazioni di convalida di certificati nella configurazione. Le impostazioni ai singoli gestori di token sostituiscono quelle specificate a livello di servizio e la raccolta di gestori di token di sicurezza.  
  
## <a name="example"></a>Esempio  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```

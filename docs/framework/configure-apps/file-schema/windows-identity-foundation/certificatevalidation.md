---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: c2d1a5d36cb5616ef06eedc093dd70a68a164a81
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252128"
---
# \<certificateValidation>
Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati. Queste impostazioni vengono sostituite se un gestore specifico è configurato con il proprio validator.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**  
  
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
|certificateValidationMode|<xref:System.ServiceModel.Security.X509CertificateValidationMode>Valore che specifica la modalità di convalida da utilizzare per il certificato X. 509. Il valore predefinito è "PeerOrChainTrust". Per specificare un validator personalizzato, impostare questo attributo su "Custom" e specificare il validator usando l' [\<certificateValidator>](certificatevalidator.md) elemento. Facoltativa.|  
|revocationMode|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>Valore che specifica la modalità di revoca da utilizzare per il certificato X. 509. Il valore predefinito è "online". Facoltativa.|  
|trustedStoreLocation|<xref:System.Security.Cryptography.X509Certificates.StoreLocation>Valore che specifica l'archivio certificati X. 509. Il valore predefinito è "LocalMachine". Facoltativa.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<certificateValidator>](certificatevalidator.md)|Specifica un tipo personalizzato per la convalida del certificato. Questo tipo viene utilizzato solo se l' `certificateValidationMode` attributo dell' [\<certificateValidation>](certificatevalidation.md) elemento è impostato su "Custom".|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Specifica le impostazioni di identità a livello di servizio.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di gestori di token di sicurezza.|  
  
## <a name="remarks"></a>Commenti  
 Un `<certificateValidation>` elemento può essere specificato a livello di servizio nell' `<identityConfiguration>` elemento o nel livello di raccolta del gestore del token di sicurezza sotto l' `<securityTokenHandlerConfiguration>` elemento. Le impostazioni in una raccolta di gestori di token eseguono l'override di quelle specificate nel servizio. Alcuni gestori di token consentono di specificare le impostazioni di convalida del certificato nella configurazione. Le impostazioni nei singoli gestori di token eseguono l'override di quelle specificate sia a livello di servizio che nella raccolta di gestori di token di sicurezza.  
  
## <a name="example"></a>Esempio  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```

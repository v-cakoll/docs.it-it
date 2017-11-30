---
title: '&lt;certificateValidation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 778088f2e0508f5a80c29ae027b2442a80286795
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltcertificatevalidationgt"></a>&lt;certificateValidation&gt;
Controlla le impostazioni che utilizzano gestori di token per convalidare i certificati. Queste impostazioni vengono ignorate se un gestore specifico è configurato con il proprio servizio di convalida.  
  
 \<System. IdentityModel >  
\<identityConfiguration >  
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
|certificateValidationMode|Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valore che specifica la modalità di convalida da utilizzare per il certificato x. 509. Il valore predefinito è "PeerOrChainTrust". Per specificare un validator personalizzato, impostare questo attributo su "Custom" e specificare il servizio di convalida utilizzando il [ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) elemento. Parametro facoltativo.|  
|revocationMode|Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valore che specifica la modalità di revoche di certificati da utilizzare per il certificato x. 509. Il valore predefinito è "Online". Parametro facoltativo.|  
|trustedStoreLocation|Oggetto <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valore che specifica l'archivio certificati x. 509. Il valore predefinito è "LocalMachine". Parametro facoltativo.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|Specifica un tipo personalizzato per la convalida del certificato. Questo tipo viene utilizzato solo se il `certificateValidationMode` attributo del [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) viene impostato su "Custom".|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Specifica le impostazioni di identità a livello di servizio.|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di sicurezza gestori di token.|  
  
## <a name="remarks"></a>Note  
 A `<certificateValidation>` elemento può essere specificato a livello di servizio sotto il `<identityConfiguration>` elemento o a livello di raccolta gestore dei token di sicurezza nel `<securityTokenHandlerConfiguration>` elemento. Le impostazioni in una raccolta di gestore del token sostituiscono quelle specificate nel servizio. Alcuni gestori di token consentono di specificare impostazioni di convalida dei certificati nella configurazione. Le impostazioni ai gestori di token singoli sostituiscono quelle specificate a livello di servizio e la raccolta di gestore del token di sicurezza.  
  
## <a name="example"></a>Esempio  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```

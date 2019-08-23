---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 2851820460a34d62175929b48ad57914df557059
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945174"
---
# <a name="x509securitytokenhandlerrequirement"></a>\<x509SecurityTokenHandlerRequirement>
Fornisce la configurazione facoltativa <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> per la classe o le classi derivate.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<add>  
\<x509SecurityTokenHandlerRequirement>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|certificateValidationMode|<xref:System.ServiceModel.Security.X509CertificateValidationMode> Valore che specifica la modalità di convalida da utilizzare per il certificato X. 509. Il valore predefinito è "PeerOrChainTrust".|  
|mapToWindows|Specifica se il gestore di token deve eseguire il mapping del token di convalida a un account di Windows tramite l'attestazione UPN in ingresso. Il valore predefinito è "false".|  
|revocationMode|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Valore che specifica la modalità di revoca da utilizzare per il certificato X. 509. Il valore predefinito è "online".|  
|trustedStoreLocation|<xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valore che specifica l'archivio certificati X. 509. Il valore predefinito è "LocalMachine".|  
|certificateValidator|Tipo personalizzato che deriva da <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Se l' `certificateValidationMode` attributo è "Custom", un'istanza di questo tipo viene utilizzata per la convalida del certificato dell'autorità emittente.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<add>](add.md)|Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.|  
  
## <a name="example"></a>Esempio  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```

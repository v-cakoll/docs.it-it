---
title: '&lt;x509SecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 994677904cada71dbc7cce4b6ca0de1d4dc65014
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47085662"
---
# <a name="ltx509securitytokenhandlerrequirementgt"></a>&lt;x509SecurityTokenHandlerRequirement&gt;
Fornisce una configurazione facoltativa per il <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> classe o le classi derivate.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<add>  
\<x509SecurityTokenHandlerRequirement >  
  
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
|certificateValidationMode|Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valore che specifica la modalità di convalida da utilizzare per il certificato X.509. Il valore predefinito è "PeerOrChainTrust".|  
|mapToWindows|Specifica se il gestore di token deve mappare il token di convalida a un account di Windows usando l'attestazione UPN in ingresso. Il valore predefinito è "false".|  
|revocationMode|Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valore che specifica la modalità di revoche di certificati da utilizzare per il certificato X.509. Il valore predefinito è "Online".|  
|trustedStoreLocation|Oggetto <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valore che specifica l'archivio certificati X.509. Il valore predefinito è "LocalMachine".|  
|certificateValidator|Un tipo personalizzato che deriva da <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Se il `certificateValidationMode` attributo è "Custom", un'istanza di questo tipo viene usata per la convalida del certificato dell'autorità di certificazione.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Aggiunge il gestore di token di sicurezza specificato nella raccolta di gestori di token.|  
  
## <a name="example"></a>Esempio  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```

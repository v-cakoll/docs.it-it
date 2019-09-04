---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: cab7572518a7a6dc26f8bbcf67cd424fa1c01085
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251895"
---
# <a name="samlsecuritytokenrequirement"></a>\<samlSecurityTokenRequirement>
Fornisce la configurazione per <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la classe, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la classe o una classe derivata di una di queste classi. Rappresentata dalla <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> classe.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Aggiungi >** ](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> samlSecurityTokenRequirement**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement   
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
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
|mapToWindows|Specifica se il gestore di token deve eseguire il mapping del token di convalida a un account di Windows tramite l'attestazione UPN in ingresso. Il valore predefinito è "false".|  
|issuerCertificateRevocationMode|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Valore che specifica la modalità di revoca da utilizzare per il certificato X. 509. Il valore predefinito è "online".|  
|issuerCertificateValidationMode|<xref:System.ServiceModel.Security.X509CertificateValidationMode> Valore che specifica la modalità di convalida da utilizzare per il certificato X. 509. Il valore predefinito è "PeerOrChainTrust".|  
|issuerCertificateTrustedStoreLocation|<xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valore che specifica l'archivio certificati X. 509. Il valore predefinito è "LocalMachine".|  
|issuerCertificateValidator|Tipo personalizzato che deriva da <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Se l' `issuerCertificateValidationMode` attributo è "Custom", un'istanza di questo tipo viene utilizzata per la convalida del certificato dell'autorità emittente.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<nameClaimType>](nameclaimtype.md)|Imposta il tipo di attestazione che <xref:System.Security.Principal.IIdentity.Name%2A> specifica la proprietà.|  
|[\<roleClaimType>](roleclaimtype.md)|Specifica il tipo di attestazione che definisce le attestazioni del tipo di <xref:System.Security.Claims.ClaimsIdentity> ruolo nella raccolta di <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> oggetti restituiti dal metodo del gestore del token.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<add>](add.md)|Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.|  
  
## <a name="remarks"></a>Note  
 L' `<samlSecurityTokenRequirement>` elemento è rappresentato <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> dalla classe nel modello a oggetti e viene usato per configurare la `SamlSecurityTokenRequirement` proprietà in un <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> oggetto o <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.  
  
## <a name="example"></a>Esempio  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```

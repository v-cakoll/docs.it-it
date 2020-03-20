---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152632"
---
# <a name="samlsecuritytokenrequirement"></a>\<> samlSecurityTokenRequirement
Fornisce la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> configurazione per <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la classe, la classe o una classe derivata di una di queste classi. Rappresentato <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> dalla classe.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.identityModel**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di identitàConfigurazione**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<aggiungere>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>samlSecurityTokenRequirement**  
  
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
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|MapToWindows (finestra di lavoro su MapToWindows|Specifica se il gestore di token deve eseguire il mapping del token di convalida a un account Windows utilizzando l'attestazione UPN in ingresso. Il valore predefinito è "false".|  
|issuerCertificateRevocationMode|Valore <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> che specifica la modalità di revoca da utilizzare per il certificato X.509. Il valore predefinito è "Online".|  
|issuerCertificateValidationMode|Valore <xref:System.ServiceModel.Security.X509CertificateValidationMode> che specifica la modalità di convalida da utilizzare per il certificato X.509. Il valore predefinito è "PeerOrChainTrust".|  
|issuerCertificatoTrustedStoreLocation|Valore <xref:System.Security.Cryptography.X509Certificates.StoreLocation> che specifica l'archivio certificati X.509. Il valore predefinito è "LocalMachine".|  
|issuerCertificateValidator|Tipo personalizzato che deriva <xref:System.IdentityModel.Selectors.X509CertificateValidator>da . Se `issuerCertificateValidationMode` l'attributo è "Custom", un'istanza di questo tipo viene utilizzata per la convalida del certificato dell'autorità emittente.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>nameClaimType](nameclaimtype.md)|Imposta il tipo di <xref:System.Security.Principal.IIdentity.Name%2A> attestazione che specifica la proprietà.|  
|[\<>roleClaimType](roleclaimtype.md)|Specifica il tipo di attestazione che definisce <xref:System.Security.Claims.ClaimsIdentity> le attestazioni <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> del tipo di ruolo nella raccolta di oggetti restituiti dal metodo del gestore di token.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<aggiungere>](add.md)|Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.|  
  
## <a name="remarks"></a>Osservazioni  
 `<samlSecurityTokenRequirement>` L'elemento <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> è rappresentato dalla classe nel modello `SamlSecurityTokenRequirement` a oggetti <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> e <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>viene utilizzato per configurare la proprietà in un oggetto o un oggetto .  
  
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

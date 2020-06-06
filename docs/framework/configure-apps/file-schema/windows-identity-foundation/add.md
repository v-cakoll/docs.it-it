---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 83ba51cbbd5100bf7412f9914a270cac88f7faa1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73973808"
---
# \<add>
Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
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
|type|Nome del tipo CLR del gestore di token da aggiungere. Per ulteriori informazioni su come specificare l' `type` attributo, vedere [riferimenti ai tipi personalizzati](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|Fornisce la configurazione per la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> classe, la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe o una classe derivata di una di queste classi.|  
|[\<sessionTokenRequirement>](sessiontokenrequirement.md)|Fornisce la configurazione per la <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> classe o le classi derivate.|  
|[\<userNameSecurityTokenHandlerRequirement>](usernamesecuritytokenhandlerrequirement.md)|Fornisce la configurazione per la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> classe o le classi derivate.|  
|[\<x509SecurityTokenHandlerRequirement>](x509securitytokenhandlerrequirement.md)|Fornisce la configurazione facoltativa per la <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> classe o le classi derivate.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.|  
  
## <a name="remarks"></a>Commenti  
 L' `<add>` elemento può assumere un singolo elemento figlio che specifica la configurazione per il gestore del token. Questo dipende dal fatto che la classe del gestore a cui viene fatto riferimento tramite l' `type` attributo dell' `<add>` elemento fornisca il supporto per questa funzionalità. Le classi del gestore di token che forniscono questa funzionalità devono esporre un costruttore che accetta un <xref:System.Xml.XmlElement> oggetto.  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 Diverse classi del gestore del token di sicurezza predefinite forniscono questa funzionalità. Queste classi sono <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> ,,, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> e <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> .  
  
> [!IMPORTANT]
> La raccolta di gestori di token può contenere solo un singolo gestore di qualsiasi tipo specificato. Ciò significa, ad esempio, che se si desidera aggiungere un gestore derivato dalla <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe alla raccolta, è necessario innanzitutto rimuovere <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , che è presente per impostazione predefinita, dalla raccolta. È possibile utilizzare l' [\<remove>](remove.md) elemento per rimuovere un singolo gestore dalla raccolta oppure utilizzare l' [\<clear>](clear.md) elemento per rimuovere tutti i gestori dalla raccolta.  
  
 Le impostazioni specificate in un gestore eseguono l'override di impostazioni equivalenti specificate nella raccolta di gestori di token nell' [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) elemento e quelle specificate a livello di servizio nell' [\<identityConfiguration>](identityconfiguration.md) elemento.  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrato l'utilizzo `<add>` degli `<remove>` elementi e per sostituire il gestore del token di sessione predefinito con un gestore di token di sessione personalizzato. Il codice XML viene tratto dall' `ClaimsAwareWebFarm` esempio.  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```

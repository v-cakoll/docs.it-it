---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 83ba51cbbd5100bf7412f9914a270cac88f7faa1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973808"
---
# <a name="add"></a>\<add>
Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<IdentityConfiguration**](identityconfiguration.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**securityTokenHandlers**](securitytokenhandlers.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**aggiungi >**  
  
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
|tipo|Nome del tipo CLR del gestore di token da aggiungere. Per ulteriori informazioni su come specificare l'attributo `type`, vedere [riferimenti ai tipi personalizzati](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement >](samlsecuritytokenrequirement.md)|Fornisce la configurazione per la classe <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, la classe <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> o una classe derivata di una di queste classi.|  
|[\<sessionTokenRequirement >](sessiontokenrequirement.md)|Fornisce la configurazione per la classe <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> o le classi derivate.|  
|[\<userNameSecurityTokenHandlerRequirement >](usernamesecuritytokenhandlerrequirement.md)|Fornisce la configurazione per la classe <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> o le classi derivate.|  
|[\<x509SecurityTokenHandlerRequirement >](x509securitytokenhandlerrequirement.md)|Fornisce la configurazione facoltativa per la classe <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> o le classi derivate.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<securityTokenHandlers >](securitytokenhandlers.md)|Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.|  
  
## <a name="remarks"></a>Note  
 L'elemento `<add>` può assumere un singolo elemento figlio che specifica la configurazione per il gestore del token. Questo dipende dal fatto che la classe del gestore a cui viene fatto riferimento tramite l'attributo `type` dell'elemento `<add>` fornisca supporto per questa funzionalità. Le classi del gestore di token che forniscono questa funzionalità devono esporre un costruttore che accetta un oggetto <xref:System.Xml.XmlElement>.  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 Diverse classi del gestore del token di sicurezza predefinite forniscono questa funzionalità. Queste classi sono <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>e <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.  
  
> [!IMPORTANT]
> La raccolta di gestori di token può contenere solo un singolo gestore di qualsiasi tipo specificato. Ciò significa, ad esempio, che se si desidera aggiungere un gestore derivato dalla classe <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> alla raccolta, è necessario innanzitutto rimuovere l'<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, che è presente per impostazione predefinita, dalla raccolta. È possibile utilizzare l'elemento [\<remove >](remove.md) per rimuovere un singolo gestore dalla raccolta oppure utilizzare l'elemento [\<Clear >](clear.md) per rimuovere tutti i gestori dalla raccolta.  
  
 Le impostazioni specificate in un gestore eseguono l'override delle impostazioni equivalenti specificate nella raccolta di gestori di token nell'elemento [\<securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md) e quelle specificate a livello di servizio nell'elemento [\<IdentityConfiguration >](identityconfiguration.md) .  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrato l'utilizzo degli elementi `<add>` e `<remove>` per sostituire il gestore del token di sessione predefinito con un gestore di token di sessione personalizzato. Il codice XML viene tratto dall'esempio `ClaimsAwareWebFarm`.  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```

---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 67d7e0aa5b6b05bfe8b17a1b1efebb1fbddbb0eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152671"
---
# <a name="issuertokenresolver"></a>\<IssuerTokenResolver>
Registra il resolver di token dell'autorità di certificazione utilizzato dai gestori nella raccolta di gestori di token. Il resolver del token dell'autorità emittente viene utilizzato per risolvere il token di firma nei token e nei messaggi in ingresso.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.identityModel**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di identitàConfigurazione**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|type|Specifica il tipo di resolver del token dell'autorità emittente. Deve essere <xref:System.IdentityModel.Tokens.IssuerTokenResolver> la classe o un tipo <xref:System.IdentityModel.Tokens.IssuerTokenResolver> che deriva dalla classe. Obbligatorio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>securityTokenHandlerConfiguration](securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di gestori di token di sicurezza.|  
  
## <a name="remarks"></a>Osservazioni  
 Il resolver del token dell'autorità emittente viene utilizzato per risolvere il token di firma nei token e nei messaggi in ingresso. Viene utilizzato per recuperare il materiale crittografico utilizzato per controllare la firma. È necessario `type` specificare l'attributo. Il tipo specificato <xref:System.IdentityModel.Tokens.IssuerTokenResolver> può essere o un tipo <xref:System.IdentityModel.Tokens.IssuerTokenResolver> personalizzato che deriva dalla classe .  
  
 Alcuni gestori di token consentono di specificare le impostazioni del resolver del token dell'autorità di certificazione nella configurazione. Le impostazioni nei singoli gestori di token eseguono l'override di quelle specificate nella raccolta di gestori di token di sicurezza.  
  
> [!NOTE]
> Specificare `<issuerTokenResolver>` l'elemento come elemento figlio dell'elemento [ \<identityConfiguration>](identityconfiguration.md) è deprecato, ma è comunque supportato per la compatibilità con le versioni precedenti. Le impostazioni `<securityTokenHandlerConfiguration>` dell'elemento `<identityConfiguration>` sostituiscono quelle dell'elemento.  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrata la configurazione per un resolver <xref:System.IdentityModel.Tokens.IssuerTokenResolver>di token dell'autorità emittente basata su una classe personalizzata che deriva da . Il resolver di token gestisce un dizionario di coppie audience-chiave inizializzato da un elemento di configurazione personalizzato (`<AddAudienceKeyPair>`) definito per la classe. La classe esegue <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> l'override del metodo per elaborare questo elemento. L'override è illustrato nell'esempio seguente. tuttavia, i metodi che chiama non vengono visualizzati per brevità. Per l'esempio completo, vedere l'esempio. `CustomToken`  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a>Esempio
  
```csharp
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
```
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>

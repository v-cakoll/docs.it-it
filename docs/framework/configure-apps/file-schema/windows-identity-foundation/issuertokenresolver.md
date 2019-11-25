---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 451750a1facd9a886b53427a8d54580d1a939fa5
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968516"
---
# <a name="issuertokenresolver"></a>\<issuerTokenResolver >
Registra il resolver dei token dell'autorità emittente utilizzato dai gestori nella raccolta di gestori di token. Il resolver dei token dell'autorità emittente viene usato per risolvere il token di firma sui token e i messaggi in ingresso.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<IdentityConfiguration**](identityconfiguration.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**securityTokenHandlers**](securitytokenhandlers.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerTokenResolver >**  
  
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
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|tipo|Specifica il tipo del resolver dei token dell'autorità emittente. Deve essere la classe <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o un tipo che deriva dalla classe <xref:System.IdentityModel.Tokens.IssuerTokenResolver>. Obbligatorio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di gestori di token di sicurezza.|  
  
## <a name="remarks"></a>Note  
 Il resolver dei token dell'autorità emittente viene usato per risolvere il token di firma sui token e i messaggi in ingresso. Viene utilizzato per recuperare il materiale crittografico utilizzato per il controllo della firma. È necessario specificare l'attributo `type`. Il tipo specificato può essere <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o un tipo personalizzato che deriva dalla classe <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.  
  
 Alcuni gestori di token consentono di specificare le impostazioni del resolver dei token dell'autorità emittente nella configurazione. Le impostazioni sui singoli gestori di token eseguono l'override di quelle specificate nella raccolta di gestori di token di sicurezza.  
  
> [!NOTE]
> La specifica dell'elemento `<issuerTokenResolver>` come elemento figlio dell'elemento [\<IdentityConfiguration](identityconfiguration.md) è stata deprecata, ma è ancora supportata per la compatibilità con le versioni precedenti. Le impostazioni sull'elemento `<securityTokenHandlerConfiguration>` eseguono l'override di quelle nell'elemento `<identityConfiguration>`.  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrata la configurazione di un resolver dei token dell'autorità emittente basato su una classe personalizzata che deriva da <xref:System.IdentityModel.Tokens.IssuerTokenResolver>. Il resolver di token mantiene un dizionario di coppie di chiavi di audience inizializzate da un elemento di configurazione personalizzato (`<AddAudienceKeyPair>`) definito per la classe. La classe esegue l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> per elaborare questo elemento. L'override è illustrato nell'esempio seguente: Tuttavia, i metodi che chiama non vengono visualizzati per brevità. Per l'esempio completo, vedere l'esempio `CustomToken`.  
  
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

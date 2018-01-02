---
title: '&lt;issuerTokenResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: e859f99768eae5c931618d5902caf40dfad95d54
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltissuertokenresolvergt"></a>&lt;issuerTokenResolver&gt;
Registra il resolver del token dell'autorità di certificazione che viene utilizzato dai gestori nella raccolta di gestori di token. Il resolver del token dell'autorità di certificazione viene utilizzato per risolvere il token di firma di token in arrivo e messaggi.  
  
 \<System. IdentityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration >  
\<issuerTokenResolver >  
  
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
|tipo|Specifica il tipo di resolver del token dell'autorità di certificazione. Deve essere il <xref:System.IdentityModel.Tokens.IssuerTokenResolver> classe o un tipo che deriva dalla <xref:System.IdentityModel.Tokens.IssuerTokenResolver> classe. Obbligatorio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 None  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di sicurezza gestori di token.|  
  
## <a name="remarks"></a>Note  
 Il resolver del token dell'autorità di certificazione viene utilizzato per risolvere il token di firma di token in arrivo e messaggi. Consente di recuperare il materiale di crittografia che viene utilizzato per controllare la firma. È necessario specificare il `type` attributo. Il tipo specificato può essere <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o un tipo personalizzato da cui deriva il <xref:System.IdentityModel.Tokens.IssuerTokenResolver> classe.  
  
 Alcuni gestori di token consentono di specificare le impostazioni di resolver del token dell'autorità di certificazione nella configurazione. Le impostazioni ai gestori di token singoli sostituiscono quelle specificate nella raccolta di gestore del token di sicurezza.  
  
> [!NOTE]
>  Specifica il `<issuerTokenResolver>` come un elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportato per compatibilità con le versioni precedenti. Impostazioni di `<securityTokenHandlerConfiguration>` elemento prevalgono su quelle nel `<identityConfiguration>` elemento.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente mostra la configurazione per un resolver del token dell'autorità di certificazione basata su una classe personalizzata che deriva da <xref:System.IdentityModel.Tokens.IssuerTokenResolver>. Il resolver del token gestisce un dizionario di coppie di chiavi di gruppo di destinatari che viene inizializzato da un elemento di configurazione personalizzato (`<AddAudienceKeyPair>`) definito per la classe. La classe esegue l'override di <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> metodo per l'elaborazione di questo elemento. La sostituzione è illustrata nell'esempio riportato di seguito; Tuttavia, i metodi che chiama non vengono visualizzati per motivi di brevità. Per un esempio completo, vedere il `CustomToken` esempio.  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a>Esempio  
  
```  
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
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>

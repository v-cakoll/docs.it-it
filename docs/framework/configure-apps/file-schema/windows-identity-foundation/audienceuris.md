---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: bd04e4ebdf5c58adaeea0ff0ca5993d7d9ce38f1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252174"
---
# <a name="audienceuris"></a>\<audienceUris>
Specifica il set di URI che sono identificatori accettabili del relying party (RP). I token non verranno accettati a meno che non siano limitati a uno degli URI del gruppo di destinatari consentiti.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> audienceUris**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|modalità|<xref:System.IdentityModel.Selectors.AudienceUriMode> Valore che specifica se la restrizione dei destinatari deve essere applicata a un token in ingresso. I valori possibili sono "Always", "Never" e "BearerKeyOnly". Il valore predefinito è "Always". facoltativo.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`<add value=xs:string>`|Aggiunge l'URI specificato dall' `value` attributo alla raccolta audienceUris. L'attributo `value` è obbligatorio. L'URI fa distinzione tra maiuscole e minuscole.|  
|`<clear>`|Cancella la raccolta audienceUris. Tutti gli identificatori vengono rimossi dalla raccolta.|  
|`<remove value=xs:string>`|Rimuove l'URI specificato dall' `value` attributo dalla raccolta audienceUris. L'attributo `value` è obbligatorio. L'URI fa distinzione tra maiuscole e minuscole.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di gestori di token di sicurezza.|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, la raccolta è vuota; utilizzare `<add>`gli `<clear>`elementi, `<remove>` e per modificare la raccolta. <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>gli <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> oggetti e usano i valori nella raccolta di URI dei destinatari per configurare eventuali restrizioni degli URI <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> dei destinatari consentiti negli oggetti.  
  
 L' `<audienceUris>` elemento è rappresentato <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> dalla classe. Un singolo URI aggiunto alla raccolta è rappresentato dalla <xref:System.IdentityModel.Configuration.AudienceUriElement> classe.  
  
> [!NOTE]
> L'uso dell'elemento `<audienceUris>` come elemento figlio [ \<dell'elemento > IdentityConfiguration](identityconfiguration.md) è stato deprecato, ma è ancora supportato per la compatibilità con le versioni precedenti. Le impostazioni sull' `<securityTokenHandlerConfiguration>` elemento eseguono l'override `<identityConfiguration>` di quelle nell'elemento.  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrato come configurare gli URI di audience accettabili per un'applicazione. Questo esempio Mostra come configurare un singolo URI. I token con ambito per questo URI verranno accettati, tutti gli altri verranno rifiutati.  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```

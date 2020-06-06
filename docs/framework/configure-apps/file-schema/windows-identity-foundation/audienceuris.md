---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: bd04e4ebdf5c58adaeea0ff0ca5993d7d9ce38f1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252174"
---
# \<audienceUris>
Specifica il set di URI che sono identificatori accettabili del relying party (RP). I token non verranno accettati se non hanno come ambito uno degli URI dei gruppi di destinatari consentiti.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**  
  
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
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|mode|<xref:System.IdentityModel.Selectors.AudienceUriMode>Valore che specifica se la restrizione dei destinatari deve essere applicata a un token in ingresso. I valori possibili sono "Always", "Never" e "BearerKeyOnly". Il valore predefinito è "Always". Facoltativa.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`<add value=xs:string>`|Aggiunge l'URI specificato dall' `value` attributo alla raccolta audienceUris. L'attributo `value` è obbligatorio. L'URI fa distinzione tra maiuscole e minuscole.|  
|`<clear>`|Cancella la raccolta audienceUris. Tutti gli identificatori vengono rimossi dalla raccolta.|  
|`<remove value=xs:string>`|Rimuove l'URI specificato dall' `value` attributo dalla raccolta audienceUris. L'attributo `value` è obbligatorio. L'URI fa distinzione tra maiuscole e minuscole.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di gestori di token di sicurezza.|  
  
## <a name="remarks"></a>Commenti  
 Per impostazione predefinita, la raccolta è vuota; utilizzare `<add>` `<clear>` `<remove>` gli elementi, e per modificare la raccolta. <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler><xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>gli oggetti e usano i valori nella raccolta di URI dei destinatari per configurare eventuali restrizioni degli URI dei destinatari consentiti negli <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetti.  
  
 L' `<audienceUris>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> classe. Un singolo URI aggiunto alla raccolta è rappresentato dalla <xref:System.IdentityModel.Configuration.AudienceUriElement> classe.  
  
> [!NOTE]
> L'uso dell' `<audienceUris>` elemento come elemento figlio dell' [\<identityConfiguration>](identityconfiguration.md) elemento è stato deprecato, ma è ancora supportato per la compatibilità con le versioni precedenti. Le impostazioni sull' `<securityTokenHandlerConfiguration>` elemento eseguono l'override di quelle nell' `<identityConfiguration>` elemento.  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrato come configurare gli URI di audience accettabili per un'applicazione. Questo esempio Mostra come configurare un singolo URI. I token con ambito per questo URI verranno accettati, tutti gli altri verranno rifiutati.  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```

---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 556c444d5e48e27036c4b49338f6e70de7ef5c5d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750748"
---
# <a name="audienceuris"></a>\<audienceUris>
Specifica il set di URI accettabili identificatori della relying party (RP). I token non verranno accettati, a meno che hanno come ambito per uno dei gruppi di destinatari consentiti gli URI.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration>  
\<audienceUris>  
  
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
|modalità|Un <xref:System.IdentityModel.Selectors.AudienceUriMode> valore che specifica se la restrizione di gruppo di destinatari deve essere applicata a un token in ingresso. I valori possibili sono "Sempre", "Mai" e "BearerKeyOnly". Il valore predefinito è "Sempre". Facoltativo.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`<add value=xs:string>`|Aggiunge l'URI specificato da di `value` attributo alla raccolta di audienceUris. L'attributo `value` è obbligatorio. L'URI è tra maiuscole e minuscole.|  
|`<clear>`|Cancella la raccolta di audienceUris. Tutti gli identificatori vengono rimossi dalla raccolta.|  
|`<remove value=xs:string>`|Rimuove l'URI specificato da di `value` attributo dalla raccolta di audienceUris. L'attributo `value` è obbligatorio. L'URI è tra maiuscole e minuscole.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di sicurezza i gestori di token.|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, la raccolta è vuota. usare `<add>`, `<clear>`, e `<remove>` elementi per modificare la raccolta. <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> e <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> agli oggetti usano i valori nel gruppo di destinatari raccolta di URI per configurare qualsiasi consentito audience le restrizioni di URI in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetti.  
  
 Il `<audienceUris>` elemento è rappresentato dal <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> classe. Un singolo URI aggiunto alla raccolta è rappresentato dal <xref:System.IdentityModel.Configuration.AudienceUriElement> classe.  
  
> [!NOTE]
>  L'utilizzo dei `<audienceUris>` come elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportata per la compatibilità con le versioni precedenti. Le impostazioni nel `<securityTokenHandlerConfiguration>` elemento sostituiscono quelle di `<identityConfiguration>` elemento.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrato come configurare il "audience" accettabili gli URI per un'applicazione. Questo esempio mostra come configurare un singolo URI. I token con ambiti per questo URI verranno accettati, tutte le altre verranno rifiutate.  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```

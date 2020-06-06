---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: 017309436660991c69da569e9cc4219e842ecaa3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251867"
---
# \<securityTokenHandlers>
Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlers>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|name|Specifica il nome di una raccolta di gestori di token. Gli unici valori riconosciuti dal Framework sono "ActAs" e "OnBehalfOf". Se le raccolte di gestori di token vengono specificate con uno di questi nomi, l'insieme verrà usato per l'elaborazione rispettivamente dei token ActAs o OnBehalfOf.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<add>](add.md)|Aggiunge un gestore del token di sicurezza alla raccolta di gestori di token.|  
|[\<clear>](clear.md)|Cancella tutti i gestori dei token di sicurezza dalla raccolta di gestori di token.|  
|[\<remove>](remove.md)|Rimuove un gestore del token di sicurezza dalla raccolta di gestori di token.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Fornisce la configurazione per la raccolta di gestori di token.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Specifica le impostazioni di identità a livello di servizio.|  
  
## <a name="remarks"></a>Commenti  
 È possibile specificare una o più raccolte denominate di gestori di token di sicurezza in una configurazione del servizio. È possibile specificare un nome per una raccolta usando l' `name` attributo. Gli unici nomi gestiti dal Framework sono "ActAs" e "OnBehalfOf". Se i gestori sono presenti in queste raccolte, vengono utilizzati da un servizio token di sicurezza (STS) invece dei gestori predefiniti durante l'elaborazione `ActAs` e i `OnBehalfOf` token.  
  
 Per impostazione predefinita, la raccolta viene popolata con i tipi di gestore seguenti: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> ,, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> e <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler> . È possibile modificare la raccolta usando gli `<add>` elementi, `<remove>` e `<clear>` . È necessario assicurarsi che nella raccolta sia presente solo un singolo gestore di un determinato tipo. Se, ad esempio, si deriva un gestore dalla <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe, il gestore o l'oggetto <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> può essere configurato in una singola raccolta, ma non in entrambi i casi.  
  
 Utilizzare l' `<securityTokenHandlerConfiguration>` elemento per specificare le impostazioni di configurazione per i gestori nella raccolta. Le impostazioni specificate tramite questo elemento eseguono l'override di quelle specificate nel servizio tramite l' [\<identityConfiguration>](identityconfiguration.md) elemento. Alcuni gestori (inclusi diversi tipi di gestori incorporati) possono supportare una configurazione aggiuntiva tramite un elemento figlio dell' `<add>` elemento. Le impostazioni specificate in un gestore eseguono l'override delle impostazioni equivalenti specificate nella raccolta o nel servizio.

---
title: '&lt;securityTokenHandlers&gt;'
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: e63f02add81495e474b59b6c5cc090bd69add3d2
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47082987"
---
# <a name="ltsecuritytokenhandlersgt"></a>&lt;securityTokenHandlers&gt;
Specifica una raccolta di gestori di token di sicurezza che sono registrati con l'endpoint.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
  
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
|name|Specifica il nome di una raccolta di gestori di token. Gli unici valori riconosciuti dal framework sono "ActAs" e "OnBehalfOf". Se le raccolte di gestori di token vengono specificate con uno di questi nomi, la raccolta verrà utilizzata durante l'elaborazione ActAs o OnBehalfOf token rispettivamente.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Aggiunge un gestore di token di sicurezza per la raccolta di gestori di token.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|Cancella tutti i gestori di token di sicurezza dalla raccolta di gestori di token.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|Rimuove un gestore di token di sicurezza dalla raccolta di gestori di token.|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Fornisce la configurazione per la raccolta di gestori di token.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Specifica le impostazioni di identità a livello di servizio.|  
  
## <a name="remarks"></a>Note  
 È possibile specificare uno o più raccolte denominate di gestori di token di sicurezza in una configurazione del servizio. È possibile specificare un nome per una raccolta usando il `name` attributo. Gli unici nomi che gestisce il framework sono "ActAs" e "OnBehalfOf". Se presenti dei gestori in tali raccolte, verranno utilizzate da un servizio token di sicurezza (STS) anziché i gestori predefiniti quando si elaborano `ActAs` e `OnBehalfOf` i token.  
  
 Per impostazione predefinita, la raccolta viene popolata con i seguenti tipi di gestore: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, e <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>. È possibile modificare la raccolta usando il `<add>`, `<remove>`, e `<clear>` elementi. È necessario assicurarsi che solo un singolo gestore di qualsiasi tipo specifico è presente nella raccolta. Ad esempio, se si deriva un gestore dal <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe, ovvero il gestore o <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> può essere configurato in una singola raccolta, ma non entrambi.  
  
 Uso di `<securityTokenHandlerConfiguration>` elemento per specificare le impostazioni di configurazione per i gestori nella raccolta. Le impostazioni specificate tramite questo elemento sostituiscono quelle specificate nel servizio tramite il [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento. Alcuni gestori (compresi alcuni dei tipi di gestore predefinito) possono supportare altre configurazione tramite un elemento figlio del `<add>` elemento. Le impostazioni specificate in un gestore sostituiscono le impostazioni equivalenti specificate nella raccolta o il servizio.

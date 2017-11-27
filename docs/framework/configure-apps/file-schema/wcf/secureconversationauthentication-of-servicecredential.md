---
title: '&lt;secureConversationAuthentication&gt; di &lt;serviceCredential&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 0fb9ff476812b6b889750e8eb7b80efce801f041
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecureconversationauthenticationgt-of-ltservicecredentialgt"></a>&lt;secureConversationAuthentication&gt; di &lt;serviceCredential&gt;
Specifica le impostazioni per un servizio di conversazione protetta.  
  
 \<System. ServiceModel >  
\<i comportamenti >  
\<serviceBehaviors >  
\<comportamento >  
\<serviceCredentials >  
\<secureConversationAuthentication >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`securityStateEncoderType`|Stringa che specifica il tipo di <xref:System.ServiceModel.Security.SecurityStateEncoder> da usare.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<serviceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.|  
  
## <a name="remarks"></a>Note  
 Usare questo elemento di configurazione per specificare un elenco di tipi di attestazione noti per la serializzazione dei cookie del token del contesto di sicurezza (SCT, Security Context Token), oltre a un codificatore per la codifica e la sicurezza delle informazioni sui cookie. Per altre informazioni su SCT, vedere <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>

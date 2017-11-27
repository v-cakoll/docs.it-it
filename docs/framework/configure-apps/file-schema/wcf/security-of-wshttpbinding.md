---
title: '&lt;security&gt; di &lt;wsHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 7dfadcbb120f55232ea2375e880a5edb17caf045
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltwshttpbindinggt"></a>&lt;security&gt; di &lt;wsHttpBinding&gt;
Rappresenta le funzionalità di sicurezza di [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
 \<System. ServiceModel >  
\<associazioni >  
\<wsHttpBinding >  
\<associazione >  
\<sicurezza >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">  
   <transport  
         clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string"   
      defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      defaultRealm="string" />  
   <message  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
       establishSecurityContext="Boolean"   
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|modalità|-Facoltativo. Specifica il tipo di sicurezza applicata. Il valore predefinito è `Message`.<br />-L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.|  
  
## <a name="mode-attribute"></a>Attributo mode  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|None|La sicurezza è disabilitata.|  
|Trasporto|La sicurezza è fornita mediante HTTPS. Può essere necessario che il servizio sia configurato con certificati SSL. Il messaggio è interamente protetto usando HTTPS e viene autenticato dal client usando il certificato SSL del servizio. L'autenticazione client è controllata tramite l'attributo `ClientCredentials`. del [ \<trasporto >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).|  
|Messaggio|La sicurezza è fornita mediante la sicurezza dei messaggi SOAP. Per impostazione predefinita, il corpo SOAP viene crittografato e firmato. Questa modalità offre varie funzionalità, ad esempio la disponibilità o meno delle credenziali del servizio per il client fuori banda, la suite di algoritmi da usare e il livello di protezione da applicare al corpo del messaggio tramite la proprietà Security.Message. L'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.|  
|TransportWithMessageCredential|In questa modalità, HTTPS fornisce l'integrità, la riservatezza e l'autenticazione server e client, mentre la sicurezza dei messaggi SOAP fornisce l'autenticazione client. Per impostazione predefinita, l'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<trasporto >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)|Definisce le impostazioni di sicurezza del trasporto. Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.|  
|[\<messaggio >](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)|Definisce le impostazioni di sicurezza per il messaggio. Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Associazione protetta per applicazioni di trasporto HTTP.|  
  
## <a name="remarks"></a>Note  
 La classe WSHttpBinding è progettata per essere interoperabile con i servizi che implementano le specifiche WS-*. La sicurezza basata sul trasporto di questa associazione è SSL (Secure Sockets Layer) su HTTP, ovvero HTTPS.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Configurazione di associazioni fornite dal sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Uso di associazioni per configurare i client e servizi Windows Communication Foundation](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<associazione >](../../../../../docs/framework/misc/binding.md)

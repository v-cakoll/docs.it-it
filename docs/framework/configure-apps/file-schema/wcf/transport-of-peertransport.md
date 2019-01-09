---
title: '&lt;transport&gt; di &lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: c82e91543920522f0ed6232036ec1b5a94189fa8
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148943"
---
# <a name="lttransportgt-of-ltpeertransportgt"></a>&lt;transport&gt; di &lt;peerTransport&gt;
Specifica il tipo di trasporto per messaggi protetti inviati dai peer configurati con questa associazione.  
  
 \<system.serviceModel>  
\<le associazioni >  
\<customBinding>  
\<binding>  
\<peerTransport >  
\<security>  
\<trasporto >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|credentialType|Parametro facoltativo. Specifica il tipo di credenziali usate per verificare messaggi inviati con il trasporto peer. L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.|  
  
## <a name="credentialtype-attribute"></a>Attributo credentialType  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|Certificato|L'autenticazione del trasporto del canale peer richiede un certificato X509.|  
|Password|L'autenticazione del trasporto del canale peer richiede una password corretta.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|Definisce le impostazioni di sicurezza di un trasporto peer.|  
  
## <a name="remarks"></a>Note  
 Questo elemento viene impostato solo se l'attributo mode di [ \<sicurezza >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) è impostata su `Transport` o `TransportWithMessageCredential`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Sicurezza del trasporto](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [Trasporti](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [Scelta di un trasporto](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

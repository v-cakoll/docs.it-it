---
title: <transport> di <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 5dbc55db25c0c49d72ec2cd8dd1041a3f8705d8e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940640"
---
# <a name="transport-of-peertransport"></a>\<> di trasporto \<di peerTransport >
Specifica il tipo di trasporto per messaggi protetti inviati dai peer configurati con questa associazione.  
  
 \<system.serviceModel>  
\<Binding >  
\<customBinding>  
\<binding>  
\<peerTransport>  
\<security>  
\<> di trasporto  
  
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
|credentialType|facoltativo. Specifica il tipo di credenziali usate per verificare messaggi inviati con il trasporto peer. L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.|  
  
## <a name="credentialtype-attribute"></a>Attributo credentialType  
  
|Value|Descrizione|  
|-----------|-----------------|  
|Certificato|L'autenticazione del trasporto del canale peer richiede un certificato X509.|  
|Password|L'autenticazione del trasporto del canale peer richiede una password corretta.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|Definisce le impostazioni di sicurezza di un trasporto peer.|  
  
## <a name="remarks"></a>Note  
 Questo elemento viene impostato solo se l'attributo mode del [ \<> di sicurezza](security-of-peertransport.md) è impostato `Transport` su `TransportWithMessageCredential`o su.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Sicurezza del trasporto](../../../wcf/feature-details/transport-security.md)
- [Trasporti](../../../wcf/feature-details/transports.md)
- [Scelta di un trasporto](../../../wcf/feature-details/choosing-a-transport.md)
- [Associazioni](../../../wcf/bindings.md)
- [Estensione delle associazioni](../../../wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)

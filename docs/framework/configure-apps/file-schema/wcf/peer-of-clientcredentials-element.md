---
title: <peer> di <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 8970100b1ad3019ff4a639d835d1db1430968008
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275142"
---
# <a name="peer-of-clientcredentials-element"></a>\<peer > di \<clientCredentials > elemento
Specifica le credenziali usate per l'autenticazione di client peer-to-peer.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<clientCredentials>  
\<peer>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di client peer-to-peer. .|  
|[\<peerAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|Specifica le opzioni di autenticazione dei client peer.|  
|[\<messageSenderAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|Specifica le opzioni di autenticazione dei mittenti di messaggi.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Specifica le credenziali usate per autenticare un client presso un servizio.|  
  
## <a name="remarks"></a>Note  
 Questo elemento di configurazione specifica le credenziali che un nodo peer usa per autenticare se stesso agli altri nodi della rete, nonché le impostazioni di autenticazione usate da un nodo peer per autenticare altri nodi peer. Per altre informazioni, vedere [l'autenticazione dei messaggi del canale Peer](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) e [protezione di applicazioni del canale Peer](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [Reti peer-to-peer](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [Protezione di client](../../../../../docs/framework/wcf/securing-clients.md)
- [Autenticazione dei messaggi del canale peer](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)
- [Autenticazione personalizzata del canale peer](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)
- [Protezione di applicazioni del canale peer](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

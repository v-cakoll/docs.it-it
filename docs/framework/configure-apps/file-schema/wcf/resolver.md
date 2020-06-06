---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 0dc667f392595d895bd4f2773ab69777d7369446
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738734"
---
# \<resolver>
Specifica un resolver peer usato per risolvere un ID della rete di peer in un insieme di indirizzi di nodo peer che rappresenta alcuni nodi che partecipano nella rete.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<resolver>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`mode`|Stringa che specifica se l'istanza del resolver peer associata a questo servizio è specifica di PNRP, un resolver personalizzato o viene determinata automaticamente. L'attributo è di tipo <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.|  
|`referralPolicy`|Una stringa che specifica la modalità di condivisione dei riferimenti fra peer. L'attributo è di tipo <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<headers>](headers.md)|Specifica le impostazioni di un servizio resolver peer personalizzato.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Definisce tutte le funzionalità di associazione di [\<netPeerTcpBinding>](netpeertcpbinding.md) .|  
  
## <a name="remarks"></a>Commenti  
 Un resolver di nomi peer è un servizio di individuazione usato dai canali peer per trovare i nodi che partecipano a una rete peer. Un resolver di nomi peer consente inoltre di "registrare" un nodo in una rete di peer, ovvero di renderlo individuabile e disponibile all'interno della rete. Per ulteriori informazioni sui resolver del peer, vedere [resolver](../../../wcf/feature-details/peer-resolvers.md)del peer.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [Resolver del peer](../../../wcf/feature-details/peer-resolvers.md)
- [Aggiunta di un resolver personalizzato a un'applicazione PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))

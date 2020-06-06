---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 26537980a6be5c0fe12661d93a6ba5fe862ceb4e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398165"
---
# \<channelPoolSettings>
Specifica le impostazioni del pool di canali per un'associazione personalizzata.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oneWay>**](oneway.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelPoolSettings>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`idleTimeout`|Oggetto <xref:System.TimeSpan> positivo che specifica il periodo massimo di inattività dei canali nel pool prima della disconnessione. L'impostazione predefinita è 00:02:00.|  
|`leaseTimeout`|Oggetto <xref:System.TimeSpan> che specifica l'intervallo di tempo trascorso il quale un canale, dopo essere stato restituito al pool, viene chiuso. L'impostazione predefinita è 00:10:00.|  
|`maxOutboundChannelsPerEndpoint`|Numero intero positivo che specifica il numero massimo di canali che possono essere memorizzati nel pool per ogni endpoint remoto. Il valore predefinito è 10.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<oneWay>](oneway.md)|Attiva il routing dei pacchetti per un'associazione personalizzata.|  
  
## <a name="remarks"></a>Commenti  
 Le quote sono usate come meccanismo di criterio per impedire un consumo eccessivo di risorse. Impediscono attacchi di tipo Denial of Service (DoS), dannosi o non intenzionali. Usare questo elemento durante l'impostazione delle quote dei canali in un canale personalizzato.  
  
 `ChannelPoolSettings` specifica tre quote:  
  
- La quota `idleTimeout` viene usata per ridurre il rischio di attacchi di tipo Denial of Service (DoS) nel server basati sul blocco di risorse per periodi di tempo prolungati. Nel client, l'impostazione del valore corretto può aumentare l'affidabilità della connessione con il servizio. Il valore predefinito è basato su un'allocazione conservativamente modesta di risorse. È adatto per un ambiente di sviluppo e in scenari con installazioni di piccole dimensioni. Gli amministratori del servizio devono rivedere il valore se un'installazione sta esaurendo le risorse o se le connessioni sono limitate nonostante la disponibilità di risorse aggiuntive.  
  
- La quota `leaseTimeout` viene usata per l'integrazione con i servizi di bilanciamento del carico e per migliorare l'affidabilità. Il valore predefinito è basato su un'allocazione conservativa di risorse. È adatto per un ambiente di sviluppo e in scenari con installazioni di piccole dimensioni. Gli amministratori del servizio devono rivedere il valore se un'installazione sta esaurendo le risorse o se le connessioni sono limitate nonostante la disponibilità di risorse aggiuntive.  
  
- La quota `maxOutboundChannelsPerEndpoint` imposta limiti della cache sia nel server che nel client ed è usata per migliorare l'affidabilità. Il valore predefinito è basato su un'allocazione conservativamente modesta di risorse idonee per ambienti di sviluppo e scenari con installazioni di piccole dimensioni. Gli amministratori del servizio devono rivedere il valore se un'installazione sta esaurendo le risorse o se le connessioni sono limitate nonostante la disponibilità di risorse aggiuntive.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<oneWay>](oneway.md)
- [Binding](../../../wcf/bindings.md)
- [Estensione delle associazioni](../../../wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)

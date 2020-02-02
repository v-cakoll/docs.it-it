---
title: Resolver del peer
ms.date: 03/30/2017
ms.assetid: d86d12a1-7358-450f-9727-b6afb95adb9c
ms.openlocfilehash: 3bcdeffac3673c1c464a35d8b6e089efd7394907
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76919237"
---
# <a name="peer-resolvers"></a>Resolver del peer
Per connettersi a una mesh, un nodo peer necessita dell'indirizzo IP di altri nodi. Gli indirizzi IP si ottengono contattando un servizio resolver, che accetta l'ID della rete e restituisce un elenco di indirizzi corrispondenti ai nodi registrati con quel particolare ID di rete. Il resolver mantiene un elenco di indirizzi registrati, creato facendo in modo che ogni nodo nella mesh venga registrato con il servizio.  
  
 È possibile specificare il servizio PeerResolver da usare tramite la proprietà `Resolver` di <xref:System.ServiceModel.NetPeerTcpBinding>.  
  
## <a name="supported-peer-resolvers"></a>Resolver peer supportati  
 Il canale peer supporta due tipi di resolver, il protocollo PNRP (Peer Name Resolution Protocol) e i servizi resolver personalizzati.  
  
 Per impostazione predefinita, il canale peer usa il servizio resolver peer PNRP per l'individuazione di peer e di elementi adiacenti nella rete. Per situazioni/piattaforme in cui PNRP non è disponibile o fattibile, Windows Communication Foundation (WCF) fornisce un servizio di individuazione alternativo basato su server, ovvero l'<xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>. È possibile definire anche in modo esplicito un servizio resolver personalizzato scrivendo una classe che implementa l'interfaccia <xref:System.ServiceModel.PeerResolvers.IPeerResolverContract>.  
  
### <a name="peer-name-resolution-protocol-pnrp"></a>Protocollo PNRP (Peer Name Resolution Protocol)  
 PNRP, il sistema di risoluzione predefinito per Windows Vista, è un servizio di risoluzione dei nomi distribuito senza server. PNRP può essere utilizzato anche in Windows XP SP2 installando Advanced Networking Pack. Due client qualsiasi che eseguono la stessa versione di PNRP possono individuarsi reciprocamente usando questo protocollo, a condizione di soddisfare determinate condizioni, ad esempio il mancato intervento di un firewall aziendale. Si noti che la versione di PNRP fornita con Windows Vista è più recente della versione inclusa in Advanced Networking Pack. Controllare l'area download Microsoft per gli aggiornamenti di PNRP per Windows XP SP2.  
  
### <a name="custom-resolver-services"></a>Servizi resolver personalizzati  
 Quando il servizio PNRP non è disponibile o si desidera disporre del controllo completo sulla definizione della rete, è possibile usare un servizio resolver basato su server personalizzato. È possibile definire questo servizio in modo esplicito scrivendo una classe resolver che implementi l'interfaccia <xref:System.ServiceModel.PeerResolvers.IPeerResolverContract> o usando l'implementazione predefinita inclusa <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>.  
  
 Nell'implementazione predefinita del servizio, le registrazioni client scadono dopo un determinato periodo di tempo se non vengono esplicitamente aggiornate. I client che usano il servizio resolver devono conoscere il limite superiore della latenza client-server per poter aggiornare correttamente le registrazioni entro il periodo di tempo previsto. Questo implica la scelta di un timeout di aggiornamento appropriato (`RefreshInterval`) sul servizio resolver. (Per altre informazioni, vedere [all'interno di CustomPeerResolverService: registrazioni client](../../../../docs/framework/wcf/feature-details/inside-the-custompeerresolverservice-client-registrations.md)).  
  
 L'autore dell'applicazione deve prendere in considerazione anche la protezione della connessione tra i client e il servizio resolver personalizzato. A questo scopo è possibile usare impostazioni di sicurezza sulla classe <xref:System.ServiceModel.NetTcpBinding> usata dai client per contattare il servizio resolver. È necessario specificare credenziali (se usate) sulla classe `ChannelFactory` usata per creare il canale peer. Queste credenziali vengono passate alla classe `ChannelFactory` usa per creare canali per il resolver personalizzato.  
  
> [!NOTE]
> Quando si usano reti locali e improvvisate con un resolver personalizzato, è consigliabile che le applicazioni che usano o supportano reti improvvisate e locali rispetto al collegamento includano la logica per la selezione di un solo indirizzo locale rispetto al collegamento da usare per la connessione. Ciò evita la confusione che può essere causata da computer con più indirizzi locali rispetto al collegamento. In conformità a quanto sopra, il canale peer supporta l'uso di un solo indirizzo di collegamento locale alla volta. È possibile specificare questo indirizzo con la proprietà `ListenIpAddress` sulla classe <xref:System.ServiceModel.NetPeerTcpBinding>.  
  
 Per una dimostrazione di come implementare un sistema di risoluzione personalizzato, vedere [Peer Channel resolver peer personalizzato](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751466(v=vs.90)).  
  
## <a name="in-this-section"></a>In questa sezione  
 [CustomPeerResolverService: registrazioni client](../../../../docs/framework/wcf/feature-details/inside-the-custompeerresolverservice-client-registrations.md)  
  
## <a name="see-also"></a>Vedere anche

- [Concetti relativi al canale peer](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md)
- [Sicurezza del canale peer](../../../../docs/framework/wcf/feature-details/peer-channel-security.md)
- [Creazione di un'applicazione del canale peer](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)

---
title: Limitazione della distribuzione di messaggi
ms.date: 03/30/2017
ms.assetid: 8b5ec4b8-1ce9-45ef-bb90-2c840456bcc1
ms.openlocfilehash: 188d7bd365caad7d4cd438744c78ae8e7cd95e7e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84586312"
---
# <a name="limiting-message-distribution"></a>Limitazione della distribuzione di messaggi

In base alla progettazione, il canale peer è una rete di trasmissione. Il relativo modello di flooding di base prevede la distribuzione di ogni messaggio inviato da qualsiasi membro di una rete a tutti gli altri membri di quella stessa rete. Questa soluzione è ideale nelle situazioni in cui tutti i messaggi generati da un membro sono attinenti e utili a tutti gli altri membri, ad esempio in una chat. Tuttavia, molte applicazioni hanno occasionalmente la necessità di limitare la distribuzione dei messaggi. Ad esempio, se un nuovo membro si aggiunge a una rete e desidera recuperare l'ultimo messaggio inviato attraverso di essa, non è necessario che questa richiesta venga propagata a ogni membro della rete. La richiesta può essere limitata a vicini adiacenti oppure i messaggi generati localmente possono essere esclusi. I messaggi possono essere inviati anche a un singolo nodo della rete. In questo argomento viene illustrato come utilizzare il conteggio hop, un filtro di propagazione dei messaggi, un filtro locale o una connessione diretta per controllare il modo in cui i messaggi vengono inoltrati attraverso la rete. Vengono inoltre fornite linee guida generali per la scelta dell'approccio più appropriato.

## <a name="hop-counts"></a>Conteggi hop

Il concetto di `PeerHopCount` è simile a quello di durata (TTL, Time-To-Live) utilizzato nel protocollo IP. Il valore di `PeerHopCount` viene collegato a un'istanza del messaggio e specifica il numero di volte in cui un messaggio deve essere inoltrato prima di essere rilasciato. Ogni volta che un messaggio viene ricevuto da un client del canale peer, il client esamina il messaggio per verificare se `PeerHopCount` è specificato. In caso affermativo, il client diminuisce il valore del conteggio hop di uno prima di inoltrare il messaggio ai nodi adiacenti. Quando un client riceve un messaggio con un valore del conteggio hop pari a zero, il client elabora il messaggio, ma non lo inoltra ai router adiacenti.

Il conteggio hop può essere inserito in un messaggio aggiungendo `PeerHopCount` come attributo alla proprietà o al campo pertinente nell'implementazione della classe del messaggio. È possibile impostarlo su un valore specifico prima di inviare il messaggio nella rete. Il conteggio hop consente quindi di limitare la distribuzione dei messaggi nella rete in caso di necessità, evitando potenzialmente la duplicazione non necessaria dei messaggi. Ciò si rivela utile nei casi in cui la rete contiene una quantità elevata di dati ridondanti oppure per l'invio di un messaggio a router immediatamente adiacenti o all'interno di un numero ridotto di hop.

- Per i frammenti di codice e le informazioni correlate, vedere il post relativo all' [attributo PeerHopCount: controllo della distribuzione dei messaggi](https://docs.microsoft.com/archive/blogs/peerchan/the-peerhopcount-attribute-controlling-message-distribution) nel Blog Peer Channel.

## <a name="message-propagation-filter"></a>Filtro di propagazione dei messaggi

`MessagePropagationFilter` può essere utilizzato per il controllo personalizzato del flood di messaggi, in particolare quando il contenuto del messaggio o altri scenari specifici determinano una propagazione. Il filtro è responsabile delle decisioni sulla propagazione di ogni messaggio che passa attraverso il nodo. Questa situazione si verifica sia per i messaggi creati in altri punti della rete e ricevuti dal nodo sia per i messaggi creati dall'applicazione. Il filtro accede sia al messaggio che alla sua origine, pertanto le decisioni relative all'inoltro o all'eliminazione del messaggio possono basarsi sulle informazioni complete disponibili.

<xref:System.ServiceModel.PeerMessagePropagationFilter> è una classe astratta di base con una sola funzione, <xref:System.ServiceModel.PeerMessagePropagationFilter.ShouldMessagePropagate%2A>. Il primo argomento della chiamata al metodo passa una copia completa del messaggio. Qualsiasi modifica apportata al messaggio non influisce sul messaggio effettivo. L'ultimo argomento della chiamata al metodo identifica l'origine del messaggio (`PeerMessageOrigination.Local` o `PeerMessageOrigination.Remote`). Le implementazioni concrete di questo metodo devono restituire una costante dall'enumerazione <xref:System.ServiceModel.PeerMessagePropagation> che indica che il messaggio deve essere inoltrato all'applicazione locale (`Local`), a client remoti (`Remote`), a entrambi (`LocalAndRemote`) o a nessuna delle parti (`None`). È possibile applicare questo filtro accedendo all'oggetto `PeerNode` corrispondente e specificando un'istanza della classe del filtro di propagazione derivata nella proprietà `PeerNode.MessagePropagationFilter`. Assicurarsi che il filtro di propagazione sia collegato prima di aprire il canale peer.

- Per i frammenti di codice e le informazioni correlate, vedere il post [Peer Channel e MessagePropagationFilter](https://docs.microsoft.com/archive/blogs/peerchan/peer-channel-and-messagepropagationfilter) nel Blog Peer Channel.

## <a name="contacting-an-individual-node-in-the-mesh"></a>Contatto di un singolo nodo nella rete

È possibile contattare un singolo nodo in una rete configurando un filtro locale o una connessione diretta.

Se ogni nodo di una rete dispone di un ID singolo, è possibile specificare un ID di destinazione nell'implementazione del messaggio. È possibile configurare un filtro locale scrivendo una funzione nel contratto di messaggio che consenta la visualizzazione del messaggio solo al nodo corrente se l'ID corrisponde a all'ID di destinazione specificato. La rete trasporta il messaggio, di conseguenza è possibile evitare il sovraccarico della configurazione di una nuova connessione. Viene tuttavia registrata una perdita di efficienza poiché il messaggio viene inviato molte volte attraverso la rete. Questa soluzione è adeguata per l'invio di messaggi a singoli membri di una rete, a condizione che i messaggi non siano di dimensioni eccessive o troppo frequenti.

Per connessioni durevoli e a larghezza di banda elevata, sono preferibili le connessioni dirette. È possibile inviare informazioni sulla connessione sulla rete e successivamente configurare una connessione diretta a scelta per inviare e ricevere messaggi.

## <a name="choosing-an-approach-for-limiting-message-distribution"></a>Scelta di un approccio per limitare la distribuzione di messaggi

Quando si rileva uno scenario in cui è necessario limitare la distribuzione di messaggi, è opportuno porsi le seguenti domande:

- **Chi** deve ricevere il messaggio? Solo un nodo adiacente? Un nodo in un'altra posizione della rete? Metà della rete?

- Con **quale frequenza** viene inviato questo messaggio?

- Quale tipo di **larghezza di banda** verrà usato da questo messaggio?

Le risposte a queste domande possono essere utili per stabilire se utilizzare un conteggio hop, un filtro di propagazione dei messaggi, un filtro locale o una connessione diretta. Si considerino le seguenti linee guida generali:

- **Che**

  - *Singolo nodo*: filtro locale o connessione diretta.

  - *Adiacenti entro una certa vicinanza*: PeerHopCount.

  - *Subset complesso della mesh*: MessagePropagationFilter.

- **Con quale frequenza**

  - *Molto frequente*: connessione diretta, PeerHopCount, MessagePropagationFilter.

  - *Occasionale*: filtro locale.

- **Utilizzo della larghezza di banda**

  - *Alta*: connessione diretta, meno consigliabile per l'uso di MessagePropagationFilter o di un filtro locale.

  - *Bassa*: qualsiasi connessione diretta probabilmente non necessaria.

## <a name="see-also"></a>Vedere anche

- [Creazione di un'applicazione del canale peer](building-a-peer-channel-application.md)

---
title: Procedure consigliate per le sessioni affidabili
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b94f6e01-8070-40b6-aac7-a2cb7b4cb4f2
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c022db62103826aa89e9035fd36c050d1f7c0f84
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="best-practices-for-reliable-sessions"></a>Procedure consigliate per le sessioni affidabili

In questo argomento illustra le procedure consigliate per le sessioni affidabili.

## <a name="setting-maxtransferwindowsize"></a>Impostazione di MaxTransferWindowSize

Le sessioni affidabili in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] usano una finestra di trasferimento per contenere i messaggi nel client e nel servizio. La proprietà configurabile <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> indica quanti messaggi può contenere la finestra di trasferimento.

Sul lato mittente, questo indica quanti messaggi può contenere la finestra di trasferimento mentre attende gli acknowledgement; sul ricevitore, indica il numero di messaggi da memorizzare nel buffer per il servizio.

Scelta della dimensione giusta influisce sull'efficienza della rete e la capacità ottimale del servizio. Nelle sezioni seguenti in dettaglio cosa considerare quando si sceglie un valore per questa proprietà e l'impatto del valore.

La dimensione predefinita della finestra di trasferimento è otto messaggi.

### <a name="efficient-use-of-the-network"></a>Utilizzo efficiente della rete

In questo contesto, il termine *rete* corrisponde a tutte le risorse utilizzate come base per la comunicazione tra un client (mittente) e un servizio (destinatario). Ciò include le connessioni di trasporto e qualsiasi intermediari o bridge tra, compresi i router SOAP o proxy/firewall HTTP.

L'uso efficiente della rete assicura che la capacità della rete sia pienamente usata. Sia la quantità di dati che possono essere trasferiti in rete al secondo (*velocità dati*) e il tempo impiegato per trasferire i dati dal mittente al destinatario (*latenza*) impatto sull'efficienza della rete viene utilizzato.

Sul lato mittente, la proprietà <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> indica quanti messaggi può contenere la finestra di trasferimento durante l'attesa di acknowledgement. Se la latenza di rete è elevata e per assicurare un mittente reattiva e un efficace uso della rete, è necessario aumentare le dimensioni di finestra di trasferimento.

Ad esempio anche se il mittente mantiene con la velocità dati, la latenza potrebbe essere elevata se sono presenti diversi intermediari tra il mittente e ricevitore o i dati devono passare tramite un intermediario di perdita di dati o in rete. Di conseguenza, il mittente deve rimanere in attesa per i riconoscimenti per i messaggi nella finestra di trasferimento prima di accettare nuovi messaggi da inviare in rete. Minore è il buffer con latenza elevata, il meno efficace l'uso della rete. D'altra parte, un trasferimento finestra dimensioni eccessive possono incidere il servizio perché il servizio potrebbe essere necessario risincronizzare l'elevata velocità dei dati inviati dal client.

### <a name="running-the-service-to-capacity"></a>Esecuzione del servizio alla capacità

Come viene usata la rete in modo efficiente, in teoria è possibile l'esecuzione alla capacità ottimale del servizio. La proprietà della dimensione della finestra di trasferimento indica quanti messaggi il destinatario può memorizzare nel buffer. La memorizzazione dei messaggi nel buffer non solo agevola il controllo del flusso di rete ma consente anche l'esecuzione del servizio alla capacità completa. Ad esempio se il buffer è un messaggio e i messaggi arrivano più velocemente di quanto il servizio possa elaborarli, quindi la rete può rilasciare messaggi e capacità potrebbe essere sprecata o sottoutilizzata.

Usando un buffer aumenta la disponibilità del servizio come contemporaneamente riceve e memorizza nel buffer un messaggio durante l'elaborazione dei messaggi ricevuti in precedenza.

Si consiglia di utilizzare lo stesso `MaxTransferWindowSize` sul mittente e destinatario.

### <a name="enabling-flow-control"></a>Abilitazione del controllo di flusso

*Controllo di flusso* è un meccanismo che assicura che il mittente e il destinatario stiano reciprocamente, vale a dire i messaggi vengono utilizzati e intervenire stessa velocità con cui sta generati. La dimensione della finestra di trasferimento sul client e sul servizio assicura che tra il mittente e il destinatario ci sia un intervallo di sincronizzazione accettabile.

È consigliabile impostare la proprietà <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled%2A> a `true` quando si utilizza una sessione affidabile tra un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client e un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servizio.

## <a name="setting-maxpendingchannels"></a>Impostazione di MaxPendingChannels

Quando si scrive un servizio che consente la comunicazione della sessione affidabile da client diversi, è possibile che molti client di stabilire una sessione affidabile per il servizio nello stesso momento. La risposta del servizio in queste situazioni dipende dalla proprietà `MaxPendingChannels`.

Quando il mittente crea un canale di sessione affidabile per un destinatario, un handshake tra di loro stabilisce una sessione affidabile. Dopo la creazione della sessione affidabile, il canale viene inserito in una coda di canali in sospeso per l'accettazione da parte del servizio. La proprietà `MaxPendingChannels` indica quanti canali possono trovarsi in questo stato.

È possibile che il servizio sia in uno stato in cui non può accettare più canali. Se la coda è piena, viene rifiutato un tentativo di stabilire una sessione affidabile e il client deve ripetere.

È anche possibile che i canali in sospeso nella coda di restano nella coda per molto tempo. Nel frattempo, può verificarsi un timeout di inattività della sessione affidabile, causando il canale per la transizione a uno stato di errore.

Durante la scrittura di un servizio che fornisce servizi di più client contemporaneamente, è necessario impostare un valore adatto alle proprie esigenze. L'impostazione di un valore troppo alto per il `MaxPendingChannels` proprietà influisce sul working set.

Il valore predefinito per <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxPendingChannels%2A> è quattro canali.

## <a name="reliable-sessions-and-hosting"></a>Sessioni affidabili e hosting

Quando web che ospita un servizio che usa sessioni affidabili, è necessario tenere presente le importanti considerazioni seguenti:

- Le sessioni affidabili hanno uno stato, che viene conservato nel dominio dell'applicazione. Questo significa che tutti i messaggi di una sessione affidabile devono essere elaborati nello stesso dominio dell'applicazione. Web farm e i web garden in cui le dimensioni della farm o del garden sono maggiore di un nodo non può garantire questo vincolo.

- Sessioni affidabili che usano canali HTTP duali (ad esempio, usando `WsDualHttpBinding`) può richiedere oltre il valore predefinito di due connessioni per ogni-client HTTP. Ciò significa che una sessione affidabile duplex può richiedere fino a due connessioni per ogni direzione, poiché i messaggi dell'applicazione e il protocollo simultanei possono essere in trasferimento ogni modo in qualsiasi momento. In determinate condizioni in base al modello di scambio di messaggi del servizio, ciò significa che è possibile creare un deadlock di un servizio ospitato sul web utilizzando HTTP duale e sessioni affidabili. Per aumentare il numero di connessioni HTTP consentite per client, aggiungere quanto segue al file di configurazione rilevanti (ad esempio, *Web. config* del servizio in questione):

  ```xml
  <configuration>
    <system.net>
      <connectionManagement>
        <add name="*" maxconnection="4" />
      </connectionManagement>
    </system.net>
  </configuration>
  ```

  Il valore di `maxconnection` attributo è il numero di connessioni necessarie. Il valore minimo in questo caso deve essere di quattro connessioni.

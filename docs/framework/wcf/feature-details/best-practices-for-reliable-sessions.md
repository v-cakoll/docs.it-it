---
title: Procedure consigliate per le sessioni affidabili
ms.date: 03/30/2017
ms.assetid: b94f6e01-8070-40b6-aac7-a2cb7b4cb4f2
ms.openlocfilehash: 1d9671e7e3124d535b66de8cd8468f76dcb32b10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857987"
---
# <a name="best-practices-for-reliable-sessions"></a>Procedure consigliate per le sessioni affidabili

In questo argomento illustra le procedure consigliate per le sessioni affidabili.

## <a name="setting-maxtransferwindowsize"></a>Impostazione di MaxTransferWindowSize

Le sessioni affidabili in Windows Communication Foundation (WCF) usano una finestra di trasferimento per contenere i messaggi sul client e servizio. La proprietà configurabile <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> indica quanti messaggi può contenere la finestra di trasferimento.

Nel mittente, questo indica quanti messaggi può contenere la finestra di trasferimento mentre attende gli acknowledgement; sul ricevitore, indica quanti messaggi memorizzare nel buffer per il servizio.

Scelta della dimensione giusta influisce sulla capacità ottimale del servizio e l'efficienza della rete. Le sezioni seguenti illustrato in dettaglio cosa considerare quando si sceglie un valore per questa proprietà e l'impatto del valore.

La dimensione predefinita della finestra di trasferimento è otto messaggi.

### <a name="efficient-use-of-the-network"></a>Uso efficiente della rete

In questo contesto il termine *rete* corrisponde a tutti gli elementi usati come base per la comunicazione tra un client (mittente) e un servizio (destinatario). Sono inclusi le connessioni di trasporto e qualsiasi intermediario o bridge tra, compresi i router SOAP o i proxy/firewall HTTP.

L'uso efficiente della rete assicura che la capacità della rete sia pienamente usata. Sia la quantità di dati che possono essere trasferiti al secondo in rete (*velocità dei dati*) e il tempo necessario per trasferire i dati dal mittente al destinatario (*latenza*) impatto sull'efficienza della rete viene usato.

Sul lato mittente, la proprietà <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> indica quanti messaggi può contenere la finestra di trasferimento durante l'attesa di acknowledgement. Se la latenza di rete è elevata e per assicurare un mittente reattive e un efficace uso della rete, è necessario aumentare le dimensioni di finestra di trasferimento.

Ad esempio anche se il server sender stare al passo con la velocità dati, la latenza potrebbe essere elevata se sono presenti diversi intermediari tra il mittente e ricevitore o i dati devono passare attraverso un intermediario con perdita di dati o una rete. Di conseguenza, il mittente deve attendere acknowledgement dei messaggi nella finestra di trasferimento prima di accettare nuovi messaggi da inviare in rete. Minore è il buffer con latenza elevata, i meno efficace l'utilizzo della rete. D'altra parte, troppo elevata una dimensioni di finestra di trasferimento possono incidere il servizio perché il servizio potrebbe essere necessario possono essere aggiornati alla frequenza elevata di dati inviati dal client.

### <a name="running-the-service-to-capacity"></a>Esecuzione del servizio alla capacità

Come la rete viene usata in modo efficiente, in teoria è il servizio venga eseguito in base alla capacità ottimale. La proprietà della dimensione della finestra di trasferimento indica quanti messaggi il destinatario può memorizzare nel buffer. La memorizzazione dei messaggi nel buffer non solo agevola il controllo del flusso di rete ma consente anche l'esecuzione del servizio alla capacità completa. Ad esempio se il buffer è un messaggio e i messaggi arrivano più velocemente di quanto il servizio possa elaborarli, quindi la rete può rilasciare messaggi e della capacità potrebbe essere sprecata o sottoutilizzata.

Usando un buffer aumenta la disponibilità del servizio come contemporaneamente riceve e memorizza nel buffer di un messaggio durante l'elaborazione di messaggi ricevuti in precedenza.

È consigliabile usare lo stesso `MaxTransferWindowSize` sul mittente e ricevitore.

### <a name="enabling-flow-control"></a>Abilitazione del controllo di flusso

*Controllo di flusso* è un meccanismo che assicura che il mittente e ricevitore tenere il passo con loro, vale a dire, i messaggi vengono utilizzati e intervenire più rapidamente ha generati. La dimensione della finestra di trasferimento sul client e sul servizio assicura che tra il mittente e il destinatario ci sia un intervallo di sincronizzazione accettabile.

È consigliabile impostare la proprietà <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled%2A> a `true` quando si usa una sessione affidabile tra un client WCF e un servizio WCF.

## <a name="setting-maxpendingchannels"></a>Impostazione di MaxPendingChannels

Quando si scrive un servizio che consente la comunicazione tramite sessione affidabile da client diversi, è possibile che molti client stabiliscano una sessione affidabile per il servizio nello stesso momento. La risposta del servizio in queste situazioni dipende dalla proprietà `MaxPendingChannels`.

Quando il mittente crea un canale di sessione affidabile per un destinatario, un handshake tra di loro stabilisce una sessione affidabile. Dopo la creazione della sessione affidabile, il canale viene inserito in una coda di canali in sospeso per l'accettazione da parte del servizio. La proprietà `MaxPendingChannels` indica quanti canali possono trovarsi in questo stato.

È possibile che il servizio sia in uno stato in cui in grado di accettare altri canali. Se la coda è piena, un tentativo di stabilire una sessione affidabile viene rifiutato e il client deve ripetere.

È anche possibile che i canali in sospeso nella coda di rimangano nella coda per un periodo più lungo. Nel frattempo, potrebbe verificarsi un timeout di inattività della sessione affidabile, causando il canale per la transizione a uno stato di errore.

Durante la scrittura di un servizio che fornisce servizi simultaneamente più client, è necessario impostare un valore che è adatto alle proprie esigenze. L'impostazione di un valore troppo alto per il `MaxPendingChannels` proprietà influisce sul working set.

Il valore predefinito per <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxPendingChannels%2A> canali quattro.

## <a name="reliable-sessions-and-hosting"></a>Le sessioni affidabili e hosting

Quando web che ospita un servizio che usa le sessioni affidabili, è necessario tenere presente le importanti considerazioni seguenti:

- Le sessioni affidabili hanno uno stato, che viene conservato nel dominio dell'applicazione. Questo significa che tutti i messaggi di una sessione affidabile devono essere elaborati nello stesso dominio dell'applicazione. Web farm e i web garden in cui la dimensione della farm o del garden è maggiore di un nodo non può garantire questo vincolo.

- Sessioni affidabili che usano canali HTTP duali (ad esempio, usando `WsDualHttpBinding`) può richiedere oltre il valore predefinito di due connessioni HTTP al client. Ciò significa che una sessione affidabile duplex può richiedere fino a due connessioni per ogni direzione perché vengano trasferiti messaggi dell'applicazione e il protocollo simultanei ciascuno dei quali prevede un determinato momento. In determinate condizioni a seconda del modello di scambio di messaggi del servizio, ciò significa che è possibile creare un deadlock di un servizio ospitato sul web utilizzando HTTP duale e sessioni affidabili. Per aumentare il numero di connessioni HTTP consentite per ogni client, aggiungere quanto segue al file di configurazione pertinente (ad esempio, *Web. config* del servizio in questione):

  ```xml
  <configuration>
    <system.net>
      <connectionManagement>
        <add name="*" maxconnection="4" />
      </connectionManagement>
    </system.net>
  </configuration>
  ```

  Il valore della `maxconnection` attributo è il numero di connessioni necessarie. Il valore minimo in questo caso deve essere quattro connessioni.

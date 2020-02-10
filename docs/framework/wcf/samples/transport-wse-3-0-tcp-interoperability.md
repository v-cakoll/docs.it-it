---
title: 'Trasporto: Interoperabilità WSE 3.0 TCP'
ms.date: 03/30/2017
ms.assetid: 5f7c3708-acad-4eb3-acb9-d232c77d1486
ms.openlocfilehash: 8e95d7e75ac49aea4b823ee3434f53ed5df11fb0
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094852"
---
# <a name="transport-wse-30-tcp-interoperability"></a>Trasporto: Interoperabilità WSE 3.0 TCP
Nell'esempio di trasporto di interoperabilità TCP WSE 3,0 viene illustrato come implementare una sessione duplex TCP come trasporto WCF (Custom Windows Communication Foundation). Illustra anche come utilizzare l'estendibilità del livello del canale per connettersi via cavo con sistemi distribuiti esistenti. Nei passaggi seguenti viene illustrato come compilare il trasporto WCF personalizzato:  
  
1. A partire da un socket TCP, creare client e implementazioni server di <xref:System.ServiceModel.Channels.IDuplexSessionChannel> che utilizzano framing DIME per delineare i limiti del messaggio.  
  
2. Creare una channel factory che si connette a un servizio TCP WSE e invia messaggi con limiti nelle classi <xref:System.ServiceModel.Channels.IDuplexSessionChannel> del client.  
  
3. Creare un listener del canale per accettare connessioni TCP in ingresso e produrre canali corrispondenti.  
  
4. Assicurarsi che eventuali eccezioni specifiche della rete vengano normalizzate nella classe derivata appropriata di <xref:System.ServiceModel.CommunicationException>.  
  
5. Inserire un elemento di associazione che aggiunge il trasporto personalizzato a uno stack di canali. Per ulteriori informazioni, vedere [aggiunta di un elemento di associazione].  
  
## <a name="creating-iduplexsessionchannel"></a>Creazione di IDuplexSessionChannel  
 Il primo passaggio per scrivere il trasporto interoperabilità WSE 3.0 TCP consiste nel creare un'implementazione di <xref:System.ServiceModel.Channels.IDuplexSessionChannel> su <xref:System.Net.Sockets.Socket>. `WseTcpDuplexSessionChannel` deriva da <xref:System.ServiceModel.Channels.ChannelBase>. La logica dell'invio di un messaggio è costituita da due parti principali: (1) codifica del messaggio in byte e (2) framing dei byte e invio via cavo.  
  
 `ArraySegment<byte> encodedBytes = EncodeMessage(message);`  
  
 `WriteData(encodedBytes);`  
  
 Inoltre, viene utilizzato un blocco in modo che le chiamate Send() mantengano la garanzia di ordine di IDuplexSessionChannel e per fare sì che le chiamate al socket sottostante siano sincronizzate correttamente.  
  
 `WseTcpDuplexSessionChannel` utilizza una classe <xref:System.ServiceModel.Channels.MessageEncoder> per tradurre classi <xref:System.ServiceModel.Channels.Message> da e verso byte[]. Poiché si tratta di un trasporto, `WseTcpDuplexSessionChannel` è inoltre responsabile dell'applicazione dell'indirizzo remoto con cui il canale è stato configurato. `EncodeMessage` contiene la logica per la conversione.  
  
 `this.RemoteAddress.ApplyTo(message);`  
  
 `return encoder.WriteMessage(message, maxBufferSize, bufferManager);`  
  
 Dopo essere stata codificata in byte, la classe <xref:System.ServiceModel.Channels.Message> deve essere trasmessa via cavo. Ciò richiede un sistema per la definizione dei limiti del messaggio. WSE 3,0 utilizza una versione di [dime](https://docs.microsoft.com/archive/msdn-magazine/2002/december/sending-files-attachments-and-soap-messages-via-dime) come protocollo di framing. `WriteData` contiene la logica di framing per eseguire il wrapping di un byte[] in un set di record DIME.  
  
 La logica alla base della ricezione dei messaggi è molto simile. Il problema più complesso sta nel gestite il fatto che la lettura di un socket può restituire meno byte di quanto richiesto. Per ricevere un messaggio, `WseTcpDuplexSessionChannel` legge i byte via cavo, decodifica il framing DIME e utilizza <xref:System.ServiceModel.Channels.MessageEncoder> per tradurre i byte [] in una classe <xref:System.ServiceModel.Channels.Message>.  
  
 `WseTcpDuplexSessionChannel` di base presuppone di ricevere un socket collegato. La classe di base gestisce l'arresto del socket. Ci sono tre posizioni che interfacciano con la chiusura del socket:  
  
- OnAbort -- chiude il socket in modo forzato (chiusura forzata).  
  
- On[Begin]Close -- chiude il socket normalmente (chiusura normale).  
  
- session.CloseOutputSession -- arresta il flusso di dati in uscita (chiusura parziale).  
  
## <a name="channel-factory"></a>Channel Factory  
 Il passaggio successivo per scrivere un trasporto TCP consiste nel creare un'implementazione di <xref:System.ServiceModel.Channels.IChannelFactory> per i canali client.  
  
- `WseTcpChannelFactory` deriva da <xref:System.ServiceModel.Channels.ChannelFactoryBase>\<IDuplexSessionChannel >. È una factory che esegue l'override di `OnCreateChannel` per produrre canali client.  
  
 `protected override IDuplexSessionChannel OnCreateChannel(EndpointAddress remoteAddress, Uri via)`  
  
 `{`  
  
 `return new ClientWseTcpDuplexSessionChannel(encoderFactory, bufferManager, remoteAddress, via, this);`  
  
 `}`  
  
- `ClientWseTcpDuplexSessionChannel` aggiunge la logica alla `WseTcpDuplexSessionChannel` di base per connettersi a un server TCP in fase di `channel.Open`. Il nome host viene innanzitutto risolto in un indirizzo IP, come illustrato nel codice seguente.  
  
 `hostEntry = Dns.GetHostEntry(Via.Host);`  
  
- Il nome host viene quindi connesso al primo indirizzo IP disponibile in un ciclo, come illustrato nel codice seguente.  
  
 `IPAddress address = hostEntry.AddressList[i];`  
  
 `socket = new Socket(address.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `socket.Connect(new IPEndPoint(address, port));`  
  
- Come parte del contratto del canale, viene eseguito l'incapsulamento delle eccezioni specifiche del dominio, ad esempio `SocketException` in <xref:System.ServiceModel.CommunicationException>.  
  
## <a name="channel-listener"></a>Channel Listener  
 Il passaggio successivo per scrivere un trasporto TCP consiste nel creare un'implementazione di <xref:System.ServiceModel.Channels.IChannelListener> per accettare canali server.  
  
- `WseTcpChannelListener` deriva da <xref:System.ServiceModel.Channels.ChannelListenerBase>\<IDuplexSessionChannel > e dalle sostituzioni in [begin] Open e on [begin] Close per controllare la durata del socket di ascolto. In OnOpen, un socket viene creato per ascoltare su IP_ANY. Implementazioni più avanzate possono creare un secondo socket per ascoltare anche su IPv6. Possono consentire anche che l'indirizzo IP sia specificato nel nome host.  
  
 `IPEndPoint localEndpoint = new IPEndPoint(IPAddress.Any, uri.Port);`  
  
 `this.listenSocket = new Socket(localEndpoint.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `this.listenSocket.Bind(localEndpoint);`  
  
 `this.listenSocket.Listen(10);`  
  
 Quando un nuovo socket viene accettato, viene inizializzato un canale server con esso. Tutti gli input e output sono già implementati nella classe di base, pertanto questo canale è responsabile dell'inizializzazione del socket.  
  
## <a name="adding-a-binding-element"></a>Aggiunta di un elemento di associazione.  
 Ora che le factory e i canali sono compilati, devono essere esposti al runtime di ServiceModel tramite un'associazione. Un'associazione è una raccolta di elementi di associazione che rappresentano lo stack di comunicazione associato a un indirizzo del servizio. Ogni elemento dello stack è rappresentato da un elemento di associazione.  
  
 Nell'esempio, l'elemento di associazione è `WseTcpTransportBindingElement`, che deriva dalla classe <xref:System.ServiceModel.Channels.TransportBindingElement>. Esso supporta la classe <xref:System.ServiceModel.Channels.IDuplexSessionChannel> ed esegue l'override dei metodi seguenti per compilare le factory associate all'associazione.  
  
 `public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelFactory<TChannel>)(object)new WseTcpChannelFactory(this, context);`  
  
 `}`  
  
 `public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelListener<TChannel>)(object)new WseTcpChannelListener(this, context);`  
  
 `}`  
  
 Contiene inoltre membri per duplicare `BindingElement` e restituire lo schema (wse.tcp).  
  
## <a name="the-wse-tcp-test-console"></a>Console per eseguire il test di TCP WSE  
 Codice per testare l'utilizzo di questo esempio di trasporto è disponibile in TestCode.cs. Nelle istruzioni seguenti viene illustrato come configurare l'esempio `TcpSyncStockService` WSE.  
  
 Il codice di prova crea un'associazione personalizzata che utilizza MTOM come codifica e `WseTcpTransport` come trasporto. Configura inoltre la versione di indirizzamento in modo che sia conforme a WSE 3.0, come illustrato nel codice seguente.  
  
 `CustomBinding binding = new CustomBinding();`  
  
 `MtomMessageEncodingBindingElement mtomBindingElement = new MtomMessageEncodingBindingElement();`  
  
 `mtomBindingElement.MessageVersion = MessageVersion.Soap11WSAddressingAugust2004;`  
  
 `binding.Elements.Add(mtomBindingElement);`  
  
 `binding.Elements.Add(new WseTcpTransportBindingElement());`  
  
 È costituito da due test. Il primo imposta un client tipizzato utilizzando codice generato da WSE 3.0 WSDL. Il secondo test USA WCF come client e server inviando messaggi direttamente sulle API del canale.  
  
 Quando si esegue l'esempio, viene visualizzato l'output seguente:  
  
 Client:  
  
```console  
Calling soap://stockservice.contoso.com/wse/samples/2003/06/TcpSyncStockService  
  
Symbol: FABRIKAM  
        Name: Fabrikam, Inc.  
        Last Price: 120  
  
Symbol: CONTOSO  
        Name: Contoso Corp.  
        Last Price: 50.07  
Press enter.  
  
Received Action: http://SayHello  
Received Body: to you.  
Hello to you.  
Press enter.  
  
Received Action: http://NotHello  
Received Body: to me.  
Press enter.  
```  
  
 Server:  
  
```console  
Listening for messages at soap://stockservice.contoso.com/wse/samples/2003/06/TcpSyncStockService  
  
Press any key to exit when done...  
  
Request received.  
Symbols:  
        FABRIKAM  
        CONTOSO  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Per eseguire l'esempio è necessario avere installato WSE 3.0 e l'esempio `TcpSyncStockService` WSE. È possibile scaricare [WSE 3,0 da MSDN](https://go.microsoft.com/fwlink/?LinkId=95000).  
  
> [!NOTE]
> Poiché WSE 3,0 non è supportato in Windows Server 2008, non è possibile installare o eseguire l'esempio `TcpSyncStockService` in tale sistema operativo.  
  
1. Dopo aver installato l'esempio `TcpSyncStockService`, eseguire le operazioni seguenti:  
  
    1. Aprire `TcpSyncStockService` in Visual Studio (si noti che l'esempio TcpSyncStockService viene installato con WSE 3.0 e non fa parte del codice di questo esempio).  
  
    2. Impostare StockService come progetto di avvio.  
  
    3. Aprire StockService.cs nel progetto StockService e impostare come commento l'attributo [Policy] sulla classe `StockService`. Ciò disabilita la sicurezza dell'esempio. Mentre WCF è in grado di interagire con gli endpoint sicuri di WSE 3,0, la sicurezza è disabilitata per evitare che questo esempio si concentri sul trasporto TCP personalizzato.  
  
    4. Premere F5 per avviare `TcpSyncStockService`. Il servizio si avvia in una nuova finestra della console.  
  
    5. Aprire questo esempio di trasporto TCP in Visual Studio.  
  
    6. Aggiornare la variabile "nome host" in TestCode.cs e farla corrispondere al nome del computer che esegue `TcpSyncStockService`.  
  
    7. Premere F5 per avviare l'esempio Trasporto TCP.  
  
    8. Il client di prova del trasporto TCP viene inizializzato in una nuova console. Il client richiede quotazioni al servizio e quindi visualizza i risultati nella finestra della console.  

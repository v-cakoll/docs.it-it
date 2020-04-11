---
title: 'Trasporto: Interoperabilità WSE 3.0 TCP'
ms.date: 03/30/2017
ms.assetid: 5f7c3708-acad-4eb3-acb9-d232c77d1486
ms.openlocfilehash: 55c59fe3a677d3aea8de62ae714e1007cfcbb86a
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121289"
---
# <a name="transport-wse-30-tcp-interoperability"></a><span data-ttu-id="1c5bf-102">Trasporto: Interoperabilità WSE 3.0 TCP</span><span class="sxs-lookup"><span data-stu-id="1c5bf-102">Transport: WSE 3.0 TCP Interoperability</span></span>
<span data-ttu-id="1c5bf-103">Nell'esempio di interoperabilità TCP di WSE 3.0 viene illustrato come implementare una sessione duplex TCP come trasporto Windows Communication Foundation (WCF) personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-103">The WSE 3.0 TCP Interoperability Transport sample demonstrates how to implement a TCP duplex session as a custom Windows Communication Foundation (WCF) transport.</span></span> <span data-ttu-id="1c5bf-104">Illustra anche come utilizzare l'estendibilità del livello del canale per connettersi via cavo con sistemi distribuiti esistenti.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-104">It also demonstrates how you can use the extensibility of the channel layer to interface over the wire with existing deployed systems.</span></span> <span data-ttu-id="1c5bf-105">I passaggi seguenti illustrano come compilare questo trasporto WCF personalizzato:The following steps show how to build this custom WCF transport:</span><span class="sxs-lookup"><span data-stu-id="1c5bf-105">The following steps show how to build this custom WCF transport:</span></span>  
  
1. <span data-ttu-id="1c5bf-106">A partire da un socket TCP, creare client e implementazioni server di <xref:System.ServiceModel.Channels.IDuplexSessionChannel> che utilizzano framing DIME per delineare i limiti del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-106">Starting with a TCP socket, create client and server implementations of <xref:System.ServiceModel.Channels.IDuplexSessionChannel> that use DIME Framing to delineate message boundaries.</span></span>  
  
2. <span data-ttu-id="1c5bf-107">Creare una channel factory che si connette a un servizio TCP WSE e invia messaggi con limiti nelle classi <xref:System.ServiceModel.Channels.IDuplexSessionChannel> del client.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-107">Create a channel factory that connects to a WSE TCP service and sends framed messages over the client <xref:System.ServiceModel.Channels.IDuplexSessionChannel>s.</span></span>  
  
3. <span data-ttu-id="1c5bf-108">Creare un listener del canale per accettare connessioni TCP in ingresso e produrre canali corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-108">Create a channel listener to accept incoming TCP connections and produce corresponding channels.</span></span>  
  
4. <span data-ttu-id="1c5bf-109">Assicurarsi che eventuali eccezioni specifiche della rete vengano normalizzate nella classe derivata appropriata di <xref:System.ServiceModel.CommunicationException>.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-109">Ensure that any network-specific exceptions are normalized to the appropriate derived class of <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
5. <span data-ttu-id="1c5bf-110">Inserire un elemento di associazione che aggiunge il trasporto personalizzato a uno stack di canali.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-110">Add a binding element that adds the custom transport to a channel stack.</span></span> <span data-ttu-id="1c5bf-111">Per altre informazioni, vedere [Aggiunta di un elemento di associazione].</span><span class="sxs-lookup"><span data-stu-id="1c5bf-111">For more information, see [Adding a Binding Element].</span></span>  
  
## <a name="creating-iduplexsessionchannel"></a><span data-ttu-id="1c5bf-112">Creazione di IDuplexSessionChannel</span><span class="sxs-lookup"><span data-stu-id="1c5bf-112">Creating IDuplexSessionChannel</span></span>  
 <span data-ttu-id="1c5bf-113">Il primo passaggio per scrivere il trasporto interoperabilità WSE 3.0 TCP consiste nel creare un'implementazione di <xref:System.ServiceModel.Channels.IDuplexSessionChannel> su <xref:System.Net.Sockets.Socket>.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-113">The first step in writing the WSE 3.0 TCP Interoperability Transport is to create an implementation of <xref:System.ServiceModel.Channels.IDuplexSessionChannel> on top of a <xref:System.Net.Sockets.Socket>.</span></span> <span data-ttu-id="1c5bf-114">`WseTcpDuplexSessionChannel` deriva da <xref:System.ServiceModel.Channels.ChannelBase>.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-114">`WseTcpDuplexSessionChannel` derives from <xref:System.ServiceModel.Channels.ChannelBase>.</span></span> <span data-ttu-id="1c5bf-115">La logica dell'invio di un messaggio è costituita da due parti principali: (1) codifica del messaggio in byte e (2) framing dei byte e invio via cavo.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-115">The logic of sending a message consists of two main pieces: (1) Encoding the message into bytes, and (2) framing those bytes and sending them on the wire.</span></span>  
  
 `ArraySegment<byte> encodedBytes = EncodeMessage(message);`  
  
 `WriteData(encodedBytes);`  
  
 <span data-ttu-id="1c5bf-116">Inoltre, viene utilizzato un blocco in modo che le chiamate Send() mantengano la garanzia di ordine di IDuplexSessionChannel e per fare sì che le chiamate al socket sottostante siano sincronizzate correttamente.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-116">In addition, a lock is taken so that the Send() calls preserve the IDuplexSessionChannel in-order guarantee, and so that calls to the underlying socket are synchronized correctly.</span></span>  
  
 <span data-ttu-id="1c5bf-117">`WseTcpDuplexSessionChannel` utilizza una classe <xref:System.ServiceModel.Channels.MessageEncoder> per tradurre classi <xref:System.ServiceModel.Channels.Message> da e verso byte[].</span><span class="sxs-lookup"><span data-stu-id="1c5bf-117">`WseTcpDuplexSessionChannel` uses a <xref:System.ServiceModel.Channels.MessageEncoder> for translating a <xref:System.ServiceModel.Channels.Message> to and from byte[].</span></span> <span data-ttu-id="1c5bf-118">Poiché si tratta di un trasporto, `WseTcpDuplexSessionChannel` è inoltre responsabile dell'applicazione dell'indirizzo remoto con cui il canale è stato configurato.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-118">Because it is a transport, `WseTcpDuplexSessionChannel` is also responsible for applying the remote address that the channel was configured with.</span></span> <span data-ttu-id="1c5bf-119">`EncodeMessage` contiene la logica per la conversione.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-119">`EncodeMessage` encapsulates the logic for this conversion.</span></span>  
  
 `this.RemoteAddress.ApplyTo(message);`  
  
 `return encoder.WriteMessage(message, maxBufferSize, bufferManager);`  
  
 <span data-ttu-id="1c5bf-120">Dopo essere stata codificata in byte, la classe <xref:System.ServiceModel.Channels.Message> deve essere trasmessa via cavo.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-120">Once the <xref:System.ServiceModel.Channels.Message> is encoded into bytes, it must be transmitted on the wire.</span></span> <span data-ttu-id="1c5bf-121">Ciò richiede un sistema per la definizione dei limiti del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-121">This requires a system for defining message boundaries.</span></span> <span data-ttu-id="1c5bf-122">WSE 3.0 utilizza una versione di [DIME](https://docs.microsoft.com/archive/msdn-magazine/2002/december/sending-files-attachments-and-soap-messages-via-dime) come protocollo di inquadratura.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-122">WSE 3.0 uses a version of [DIME](https://docs.microsoft.com/archive/msdn-magazine/2002/december/sending-files-attachments-and-soap-messages-via-dime) as its framing protocol.</span></span> <span data-ttu-id="1c5bf-123">`WriteData` contiene la logica di framing per eseguire il wrapping di un byte[] in un set di record DIME.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-123">`WriteData` encapsulates the framing logic to wrap a byte[] into a set of DIME records.</span></span>  
  
 <span data-ttu-id="1c5bf-124">La logica alla base della ricezione dei messaggi è molto simile.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-124">The logic for receiving messages is very similar.</span></span> <span data-ttu-id="1c5bf-125">Il problema più complesso sta nel gestite il fatto che la lettura di un socket può restituire meno byte di quanto richiesto.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-125">The main complexity is handling the fact that a socket read can return less bytes than were requested.</span></span> <span data-ttu-id="1c5bf-126">Per ricevere un messaggio, `WseTcpDuplexSessionChannel` legge i byte via cavo, decodifica il framing DIME e utilizza <xref:System.ServiceModel.Channels.MessageEncoder> per tradurre i byte [] in una classe <xref:System.ServiceModel.Channels.Message>.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-126">To receive a message, `WseTcpDuplexSessionChannel` reads bytes off the wire, decodes the DIME framing, and then uses the <xref:System.ServiceModel.Channels.MessageEncoder> for turning the byte[] into a <xref:System.ServiceModel.Channels.Message>.</span></span>  
  
 <span data-ttu-id="1c5bf-127">`WseTcpDuplexSessionChannel` di base presuppone di ricevere un socket collegato.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-127">The base `WseTcpDuplexSessionChannel` assumes that it receives a connected socket.</span></span> <span data-ttu-id="1c5bf-128">La classe di base gestisce l'arresto del socket.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-128">The base class handles socket shutdown.</span></span> <span data-ttu-id="1c5bf-129">Ci sono tre posizioni che interfacciano con la chiusura del socket:</span><span class="sxs-lookup"><span data-stu-id="1c5bf-129">There are three places that interface with socket closure:</span></span>  
  
- <span data-ttu-id="1c5bf-130">OnAbort -- chiude il socket in modo forzato (chiusura forzata).</span><span class="sxs-lookup"><span data-stu-id="1c5bf-130">OnAbort -- close the socket ungracefully (hard close).</span></span>  
  
- <span data-ttu-id="1c5bf-131">On[Begin]Close -- chiude il socket normalmente (chiusura normale).</span><span class="sxs-lookup"><span data-stu-id="1c5bf-131">On[Begin]Close -- close the socket gracefully (soft close).</span></span>  
  
- <span data-ttu-id="1c5bf-132">session.CloseOutputSession -- arresta il flusso di dati in uscita (chiusura parziale).</span><span class="sxs-lookup"><span data-stu-id="1c5bf-132">session.CloseOutputSession -- shutdown the outbound data stream (half close).</span></span>  
  
## <a name="channel-factory"></a><span data-ttu-id="1c5bf-133">Channel Factory</span><span class="sxs-lookup"><span data-stu-id="1c5bf-133">Channel Factory</span></span>  
 <span data-ttu-id="1c5bf-134">Il passaggio successivo per scrivere un trasporto TCP consiste nel creare un'implementazione di <xref:System.ServiceModel.Channels.IChannelFactory> per i canali client.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-134">The next step in writing the TCP transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels.</span></span>  
  
- <span data-ttu-id="1c5bf-135">`WseTcpChannelFactory`deriva dall'> <xref:System.ServiceModel.Channels.ChannelFactoryBase> \<IDuplexSessionChannel.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-135">`WseTcpChannelFactory` derives from <xref:System.ServiceModel.Channels.ChannelFactoryBase>\<IDuplexSessionChannel>.</span></span> <span data-ttu-id="1c5bf-136">È una factory che esegue l'override di `OnCreateChannel` per produrre canali client.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-136">It is a factory that overrides `OnCreateChannel` to produce client channels.</span></span>  
  
 `protected override IDuplexSessionChannel OnCreateChannel(EndpointAddress remoteAddress, Uri via)`  
  
 `{`  
  
 `return new ClientWseTcpDuplexSessionChannel(encoderFactory, bufferManager, remoteAddress, via, this);`  
  
 `}`  
  
- <span data-ttu-id="1c5bf-137">`ClientWseTcpDuplexSessionChannel`aggiunge la logica `WseTcpDuplexSessionChannel` alla base per `channel.Open` connettersi a un server TCP in tempo.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-137">`ClientWseTcpDuplexSessionChannel` adds logic to the base `WseTcpDuplexSessionChannel` to connect to a TCP server at `channel.Open` time.</span></span> <span data-ttu-id="1c5bf-138">Il nome host viene innanzitutto risolto in un indirizzo IP, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-138">First the hostname is resolved to an IP address, as shown in the following code.</span></span>  
  
 `hostEntry = Dns.GetHostEntry(Via.Host);`  
  
- <span data-ttu-id="1c5bf-139">Il nome host viene quindi connesso al primo indirizzo IP disponibile in un ciclo, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-139">Then the hostname is connected to the first available IP address in a loop, as shown in the following code.</span></span>  
  
 `IPAddress address = hostEntry.AddressList[i];`  
  
 `socket = new Socket(address.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `socket.Connect(new IPEndPoint(address, port));`  
  
- <span data-ttu-id="1c5bf-140">Come parte del contratto del canale, viene eseguito l'incapsulamento delle eccezioni specifiche del dominio, ad esempio `SocketException` in <xref:System.ServiceModel.CommunicationException>.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-140">As part of the channel contract, any domain-specific exceptions are wrapped, such as `SocketException` in <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
## <a name="channel-listener"></a><span data-ttu-id="1c5bf-141">Channel Listener</span><span class="sxs-lookup"><span data-stu-id="1c5bf-141">Channel Listener</span></span>  
 <span data-ttu-id="1c5bf-142">Il passaggio successivo per scrivere un trasporto TCP consiste nel creare un'implementazione di <xref:System.ServiceModel.Channels.IChannelListener> per accettare canali server.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-142">The next step in writing the TCP transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelListener> for accepting server channels.</span></span>  
  
- <span data-ttu-id="1c5bf-143">`WseTcpChannelListener`deriva da <xref:System.ServiceModel.Channels.ChannelListenerBase> \<IDuplexSessionChannel> e esegue l'override di On[Begin]Open e On[Begin]Close per controllare la durata del socket di ascolto.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-143">`WseTcpChannelListener` derives from <xref:System.ServiceModel.Channels.ChannelListenerBase>\<IDuplexSessionChannel> and overrides On[Begin]Open and On[Begin]Close to control the lifetime of its listen socket.</span></span> <span data-ttu-id="1c5bf-144">In OnOpen, un socket viene creato per ascoltare su IP_ANY.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-144">In OnOpen, a socket is created to listen on IP_ANY.</span></span> <span data-ttu-id="1c5bf-145">Implementazioni più avanzate possono creare un secondo socket per ascoltare anche su IPv6.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-145">More advanced implementations can create a second socket to listen on IPv6 as well.</span></span> <span data-ttu-id="1c5bf-146">Possono consentire anche che l'indirizzo IP sia specificato nel nome host.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-146">They can also allow the IP address to be specified in the hostname.</span></span>  
  
 `IPEndPoint localEndpoint = new IPEndPoint(IPAddress.Any, uri.Port);`  
  
 `this.listenSocket = new Socket(localEndpoint.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `this.listenSocket.Bind(localEndpoint);`  
  
 `this.listenSocket.Listen(10);`  
  
 <span data-ttu-id="1c5bf-147">Quando un nuovo socket viene accettato, viene inizializzato un canale server con esso.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-147">When a new socket is accepted, a server channel is initialized with this socket.</span></span> <span data-ttu-id="1c5bf-148">Tutti gli input e output sono già implementati nella classe di base, pertanto questo canale è responsabile dell'inizializzazione del socket.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-148">All the input and output is already implemented in the base class, so this channel is responsible for initializing the socket.</span></span>  
  
## <a name="adding-a-binding-element"></a><span data-ttu-id="1c5bf-149">Aggiunta di un elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-149">Adding a Binding Element</span></span>  
 <span data-ttu-id="1c5bf-150">Ora che le factory e i canali sono compilati, devono essere esposti al runtime di ServiceModel tramite un'associazione.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-150">Now that the factories and channels are built, they must be exposed to the ServiceModel runtime through a binding.</span></span> <span data-ttu-id="1c5bf-151">Un'associazione è una raccolta di elementi di associazione che rappresentano lo stack di comunicazione associato a un indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-151">A binding is a collection of binding elements that represents the communication stack associated with a service address.</span></span> <span data-ttu-id="1c5bf-152">Ogni elemento dello stack è rappresentato da un elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-152">Each element in the stack is represented by a binding element.</span></span>  
  
 <span data-ttu-id="1c5bf-153">Nell'esempio, l'elemento di associazione è `WseTcpTransportBindingElement`, che deriva dalla classe <xref:System.ServiceModel.Channels.TransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-153">In the sample, the binding element is `WseTcpTransportBindingElement`, which derives from <xref:System.ServiceModel.Channels.TransportBindingElement>.</span></span> <span data-ttu-id="1c5bf-154">Esso supporta la classe <xref:System.ServiceModel.Channels.IDuplexSessionChannel> ed esegue l'override dei metodi seguenti per compilare le factory associate all'associazione.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-154">It supports <xref:System.ServiceModel.Channels.IDuplexSessionChannel> and overrides the following methods to build the factories associated with our binding.</span></span>  
  
 `public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelFactory<TChannel>)(object)new WseTcpChannelFactory(this, context);`  
  
 `}`  
  
 `public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelListener<TChannel>)(object)new WseTcpChannelListener(this, context);`  
  
 `}`  
  
 <span data-ttu-id="1c5bf-155">Contiene inoltre membri per duplicare `BindingElement` e restituire lo schema (wse.tcp).</span><span class="sxs-lookup"><span data-stu-id="1c5bf-155">It also contains members for cloning the `BindingElement` and returning our scheme (wse.tcp).</span></span>  
  
## <a name="the-wse-tcp-test-console"></a><span data-ttu-id="1c5bf-156">Console per eseguire il test di TCP WSE</span><span class="sxs-lookup"><span data-stu-id="1c5bf-156">The WSE TCP Test Console</span></span>  
 <span data-ttu-id="1c5bf-157">Codice per testare l'utilizzo di questo esempio di trasporto è disponibile in TestCode.cs.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-157">Test code for using this sample transport is available in TestCode.cs.</span></span> <span data-ttu-id="1c5bf-158">Nelle istruzioni seguenti viene illustrato come configurare l'esempio `TcpSyncStockService` WSE.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-158">The following instructions show how to set up the WSE `TcpSyncStockService` sample.</span></span>  
  
 <span data-ttu-id="1c5bf-159">Il codice di prova crea un'associazione personalizzata che utilizza MTOM come codifica e `WseTcpTransport` come trasporto.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-159">The test code creates a custom binding that uses MTOM as the encoding and `WseTcpTransport` as the transport.</span></span> <span data-ttu-id="1c5bf-160">Configura inoltre la versione di indirizzamento in modo che sia conforme a WSE 3.0, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-160">It also sets up the AddressingVersion to be conformant with WSE 3.0, as shown in the following code.</span></span>  
  
 `CustomBinding binding = new CustomBinding();`  
  
 `MtomMessageEncodingBindingElement mtomBindingElement = new MtomMessageEncodingBindingElement();`  
  
 `mtomBindingElement.MessageVersion = MessageVersion.Soap11WSAddressingAugust2004;`  
  
 `binding.Elements.Add(mtomBindingElement);`  
  
 `binding.Elements.Add(new WseTcpTransportBindingElement());`  
  
 <span data-ttu-id="1c5bf-161">È costituito da due test. Il primo imposta un client tipizzato utilizzando codice generato da WSE 3.0 WSDL.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-161">It consists of two tests—one test sets up a typed client using code generated from the WSE 3.0 WSDL.</span></span> <span data-ttu-id="1c5bf-162">Il secondo test utilizza WCF sia come client che come server inviando messaggi direttamente sopra le API del canale.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-162">The second test uses WCF as both the client and the server by sending messages directly on top of the channel APIs.</span></span>  
  
 <span data-ttu-id="1c5bf-163">Quando si esegue l'esempio, viene visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="1c5bf-163">When running the sample, the following output is expected.</span></span>  
  
 <span data-ttu-id="1c5bf-164">Client:</span><span class="sxs-lookup"><span data-stu-id="1c5bf-164">Client:</span></span>  
  
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
  
 <span data-ttu-id="1c5bf-165">Server: </span><span class="sxs-lookup"><span data-stu-id="1c5bf-165">Server:</span></span>  
  
```console  
Listening for messages at soap://stockservice.contoso.com/wse/samples/2003/06/TcpSyncStockService  
  
Press any key to exit when done...  
  
Request received.  
Symbols:  
        FABRIKAM  
        CONTOSO  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1c5bf-166">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="1c5bf-166">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="1c5bf-167">Per eseguire questo esempio, è necessario disporre di [Web Services Enhancements (WSE) 3.0 per Microsoft .NET](https://www.microsoft.com/download/details.aspx?id=14089) e dell'esempio WSE `TcpSyncStockService` installati.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-167">To run this sample, you must have [Web Services Enhancements (WSE) 3.0 for Microsoft .NET](https://www.microsoft.com/download/details.aspx?id=14089) and the WSE `TcpSyncStockService` sample installed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1c5bf-168">Poiché WSE 3.0 non è supportato in Windows Server `TcpSyncStockService` 2008, non è possibile installare o eseguire l'esempio in tale sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-168">Because WSE 3.0 is not supported on Windows Server 2008, you cannot install or run the `TcpSyncStockService` sample on that operating system.</span></span>  
  
1. <span data-ttu-id="1c5bf-169">Dopo aver installato l'esempio `TcpSyncStockService`, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c5bf-169">Once you install the `TcpSyncStockService` sample, do the following:</span></span>  
  
    1. <span data-ttu-id="1c5bf-170">Aprire `TcpSyncStockService` in Visual Studio (si noti che l'esempio TcpSyncStockService viene installato con WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="1c5bf-170">Open the `TcpSyncStockService` in Visual Studio (Note that the TcpSyncStockService sample is installed with WSE 3.0.</span></span> <span data-ttu-id="1c5bf-171">e non fa parte del codice di questo esempio).</span><span class="sxs-lookup"><span data-stu-id="1c5bf-171">It is not part of this sample's code).</span></span>  
  
    2. <span data-ttu-id="1c5bf-172">Impostare StockService come progetto di avvio.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-172">Set the StockService project as the start up project.</span></span>  
  
    3. <span data-ttu-id="1c5bf-173">Aprire StockService.cs nel progetto StockService e impostare come commento l'attributo [Policy] sulla classe `StockService`.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-173">Open StockService.cs in the StockService project and comment out the [Policy] attribute on the `StockService` class.</span></span> <span data-ttu-id="1c5bf-174">Ciò disabilita la sicurezza dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-174">This disables security from the sample.</span></span> <span data-ttu-id="1c5bf-175">Mentre WCF può interagire con gli endpoint protetti di WSE 3.0, la sicurezza è disabilitata per mantenere questo esempio incentrato sul trasporto TCP personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-175">While WCF can interoperate with WSE 3.0 secure endpoints, security is disabled to keep this sample focused on the custom TCP transport.</span></span>  
  
    4. <span data-ttu-id="1c5bf-176">Premere F5 per avviare `TcpSyncStockService`.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-176">Press F5 to start the `TcpSyncStockService`.</span></span> <span data-ttu-id="1c5bf-177">Il servizio si avvia in una nuova finestra della console.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-177">The service starts in a new console window.</span></span>  
  
    5. <span data-ttu-id="1c5bf-178">Aprire questo esempio di trasporto TCP in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-178">Open this TCP transport sample in Visual Studio.</span></span>  
  
    6. <span data-ttu-id="1c5bf-179">Aggiornare la variabile "nome host" in TestCode.cs e farla corrispondere al nome del computer che esegue `TcpSyncStockService`.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-179">Update the "hostname" variable in TestCode.cs to match the machine name running the `TcpSyncStockService`.</span></span>  
  
    7. <span data-ttu-id="1c5bf-180">Premere F5 per avviare l'esempio Trasporto TCP.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-180">Press F5 to start the TCP transport sample.</span></span>  
  
    8. <span data-ttu-id="1c5bf-181">Il client di prova del trasporto TCP viene inizializzato in una nuova console.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-181">The TCP transport test client starts in a new console.</span></span> <span data-ttu-id="1c5bf-182">Il client richiede quotazioni al servizio e quindi visualizza i risultati nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-182">The client requests stock quotes from the service and then displays the results in its console window.</span></span>  

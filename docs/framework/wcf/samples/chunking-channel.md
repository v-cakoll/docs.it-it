---
title: Chunking del canale
ms.date: 03/30/2017
ms.assetid: e4d53379-b37c-4b19-8726-9cc914d5d39f
ms.openlocfilehash: 7b436e2ce708a122a7eae3b07ad01515fb2dce96
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463975"
---
# <a name="chunking-channel"></a><span data-ttu-id="17ddc-102">Chunking del canale</span><span class="sxs-lookup"><span data-stu-id="17ddc-102">Chunking Channel</span></span>

<span data-ttu-id="17ddc-103">Quando si inviano messaggi di grandi dimensioni utilizzando Windows Communication Foundation (WCF), è spesso opportuno limitare la quantità di memoria utilizzata per memorizzare nel buffer tali messaggi.</span><span class="sxs-lookup"><span data-stu-id="17ddc-103">When sending large messages using Windows Communication Foundation (WCF), it is often desirable to limit the amount of memory used to buffer those messages.</span></span> <span data-ttu-id="17ddc-104">Una possibile soluzione è di trasmettere il corpo del messaggio (presupponendo che il grosso dei dati è contenuto nel corpo).</span><span class="sxs-lookup"><span data-stu-id="17ddc-104">One possible solution is to stream the message body (assuming the bulk of the data is in the body).</span></span> <span data-ttu-id="17ddc-105">Tuttavia alcuni protocolli richiedono la memorizzazione nel buffer del messaggio intero.</span><span class="sxs-lookup"><span data-stu-id="17ddc-105">However some protocols require buffering of the entire message.</span></span> <span data-ttu-id="17ddc-106">Due esempi sono rappresentati dai protocolli di messaggistica affidabile e di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="17ddc-106">Reliable messaging and security are two such examples.</span></span> <span data-ttu-id="17ddc-107">Un'altra possibile soluzione è di suddividere il messaggio in messaggi più piccoli, chiamati blocchi, inviare quei blocchi uno alla volta e ricostruire il messaggio originale sul lato ricevente.</span><span class="sxs-lookup"><span data-stu-id="17ddc-107">Another possible solution is to divide up the large message into smaller messages called chunks, send those chunks one chunk at a time, and reconstitute the large message on the receiving side.</span></span> <span data-ttu-id="17ddc-108">L'applicazione stessa può eseguire questa suddivisione in blocchi e ricostruzione oppure può usare un canale personalizzato per eseguire queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="17ddc-108">The application itself could do this chunking and de-chunking or it could use a custom channel to do it.</span></span> <span data-ttu-id="17ddc-109">Nell'esempio relativo al canale per la suddivisione in blocchi viene illustrato come è possibile usare un protocollo personalizzato o un canale su più livelli per suddividere in blocchi e ricostruire i messaggi di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="17ddc-109">The chunking channel sample shows how a custom protocol or layered channel can be used to do chunking and de-chunking of arbitrarily large messages.</span></span>

<span data-ttu-id="17ddc-110">La suddivisione in blocchi deve essere eseguita solo dopo la costruzione dell'intero messaggio da inviare.</span><span class="sxs-lookup"><span data-stu-id="17ddc-110">Chunking should always be employed only after the entire message to be sent has been constructed.</span></span> <span data-ttu-id="17ddc-111">Un canale per la suddivisione in blocchi deve sempre distribuito su più livelli al di sotto di un canale di sicurezza e di un canale di sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="17ddc-111">A chunking channel should always be layered below a security channel and a reliable session channel.</span></span>

> [!NOTE]
> <span data-ttu-id="17ddc-112">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="17ddc-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17ddc-113">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="17ddc-113">The samples may already be installed on your machine.</span></span> <span data-ttu-id="17ddc-114">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="17ddc-114">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="17ddc-115">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="17ddc-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="17ddc-116">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="17ddc-116">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ChunkingChannel`

## <a name="chunking-channel-assumptions-and-limitations"></a><span data-ttu-id="17ddc-117">Presupposti e limitazioni del canale per la suddivisione in blocchi</span><span class="sxs-lookup"><span data-stu-id="17ddc-117">Chunking Channel Assumptions and Limitations</span></span>

### <a name="message-structure"></a><span data-ttu-id="17ddc-118">Struttura del messaggio</span><span class="sxs-lookup"><span data-stu-id="17ddc-118">Message Structure</span></span>

<span data-ttu-id="17ddc-119">Il canale per la suddivisione in blocchi presuppone che il messaggio sia strutturato nel modo seguente per eseguire la suddivisione in blocchi:</span><span class="sxs-lookup"><span data-stu-id="17ddc-119">The chunking channel assumes the following message structure for messages to be chunked:</span></span>

```xml
<soap:Envelope>
  <!-- headers -->
  <soap:Body>
    <operationElement>
      <paramElement>data to be chunked</paramElement>
    </operationElement>
  </soap:Body>
</soap:Envelope>
```

<span data-ttu-id="17ddc-120">Quando si usa ServiceModel, le operazioni del contratto che hanno 1 parametro di input si conformano con questa forma di messaggio per il messaggio di input.</span><span class="sxs-lookup"><span data-stu-id="17ddc-120">When using the ServiceModel, contract operations that have 1 input parameter comply with this shape of message for their input message.</span></span> <span data-ttu-id="17ddc-121">In modo simile, le operazioni del contratto che hanno 1 parametro di output o valore restituito si conformano con questa forma di messaggio per il messaggio di output.</span><span class="sxs-lookup"><span data-stu-id="17ddc-121">Similarly, contract operations that have 1 output parameter or return value comply with this shape of message for their output message.</span></span> <span data-ttu-id="17ddc-122">Di seguito sono elencati esempi di queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="17ddc-122">The following are examples of such operations:</span></span>

```csharp
[ServiceContract]
interface ITestService
{
    [OperationContract]
    Stream EchoStream(Stream stream);

    [OperationContract]
    Stream DownloadStream();

    [OperationContract(IsOneWay = true)]
    void UploadStream(Stream stream);
}
```

### <a name="sessions"></a><span data-ttu-id="17ddc-123">Sessioni</span><span class="sxs-lookup"><span data-stu-id="17ddc-123">Sessions</span></span>

<span data-ttu-id="17ddc-124">Il canale per la suddivisione in blocchi richiede che i messaggi vengano recapitati una volta sola, con recapito ordinato dei messaggi (blocchi).</span><span class="sxs-lookup"><span data-stu-id="17ddc-124">The chunking channel requires messages to be delivered exactly once, in ordered delivery of messages (chunks).</span></span> <span data-ttu-id="17ddc-125">Questo significa che lo stack di canali sottostante deve essere dotato di sessioni.</span><span class="sxs-lookup"><span data-stu-id="17ddc-125">This means the underlying channel stack must be sessionful.</span></span> <span data-ttu-id="17ddc-126">Le sessioni possono essere fornite dal trasporto (ad esempio, trasporto TCP) o da un canale del protocollo con sessione (ad esempio, il canale ReliableSession).</span><span class="sxs-lookup"><span data-stu-id="17ddc-126">Sessions can be provided by the transport (for example, TCP transport) or by a sessionful protocol channel (for example, ReliableSession channel).</span></span>

### <a name="asynchronous-send-and-receive"></a><span data-ttu-id="17ddc-127">Invio e ricezione asincroni</span><span class="sxs-lookup"><span data-stu-id="17ddc-127">Asynchronous Send and Receive</span></span>

<span data-ttu-id="17ddc-128">I metodi di invio e ricezione asincroni non vengono implementati in questa versione dell'esempio relativo al canale per la suddivisione in blocchi.</span><span class="sxs-lookup"><span data-stu-id="17ddc-128">Asynchronous send and receive methods are not implemented in this version of the chunking channel sample.</span></span>

## <a name="chunking-protocol"></a><span data-ttu-id="17ddc-129">Protocollo per la suddivisione in blocchi</span><span class="sxs-lookup"><span data-stu-id="17ddc-129">Chunking Protocol</span></span>

<span data-ttu-id="17ddc-130">Il canale per la suddivisione in blocchi definisce un protocollo che indica l'inizio e la fine di una serie di blocchi, oltre al numero di sequenza di ogni blocco.</span><span class="sxs-lookup"><span data-stu-id="17ddc-130">The chunking channel defines a protocol that indicates the start and end of a series of chunks as well as the sequence number of each chunk.</span></span> <span data-ttu-id="17ddc-131">Nei tre esempi di messaggio seguenti vengono descritti i messaggi iniziali, a blocchi e finali con i commenti che descrivono gli aspetti principali di ognuno.</span><span class="sxs-lookup"><span data-stu-id="17ddc-131">The following three example messages demonstrate the start, chunk and end messages with comments that describe the key aspects of each.</span></span>

### <a name="start-message"></a><span data-ttu-id="17ddc-132">Messaggio iniziale</span><span class="sxs-lookup"><span data-stu-id="17ddc-132">Start Message</span></span>

```xml
<s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing"
            xmlns:s="http://www.w3.org/2003/05/soap-envelope">
  <s:Header>
<!--Original message action is replaced with a chunking-specific action. -->
    <a:Action s:mustUnderstand="1">http://samples.microsoft.com/chunkingAction</a:Action>
<!--
Original message is assigned a unique id that is transmitted
in a MessageId header. Note that this is different from the WS-Addressing MessageId header.
-->
    <MessageId s:mustUnderstand="1" xmlns="http://samples.microsoft.com/chunking">
53f183ee-04aa-44a0-b8d3-e45224563109
</MessageId>
<!--
ChunkingStart header signals the start of a chunked message.
-->
    <ChunkingStart s:mustUnderstand="1" i:nil="true" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://samples.microsoft.com/chunking" />
<!--
Original message action is transmitted in OriginalAction.
This is required to re-create the original message on the other side.
-->
    <OriginalAction xmlns="http://samples.microsoft.com/chunking">
http://tempuri.org/ITestService/EchoStream
    </OriginalAction>
   <!--
    All original message headers are included here.
   -->
  </s:Header>
  <s:Body>
<!--
Chunking assumes this structure of Body content:
<element>
  <childelement>large data to be chunked<childelement>
</element>
The start message contains just <element> and <childelement> without
the data to be chunked.
-->
    <EchoStream xmlns="http://tempuri.org/">
      <stream />
    </EchoStream>
  </s:Body>
</s:Envelope>
```

### <a name="chunk-message"></a><span data-ttu-id="17ddc-133">Messaggio a blocchi</span><span class="sxs-lookup"><span data-stu-id="17ddc-133">Chunk Message</span></span>

```xml
<s:Envelope
  xmlns:a="http://www.w3.org/2005/08/addressing"
  xmlns:s="http://www.w3.org/2003/05/soap-envelope">
  <s:Header>
   <!--
    All chunking protocol messages have this action.
   -->
    <a:Action s:mustUnderstand="1">
      http://samples.microsoft.com/chunkingAction
    </a:Action>
<!--
Same as MessageId in the start message. The GUID indicates which original message this chunk belongs to.
-->
    <MessageId s:mustUnderstand="1"
               xmlns="http://samples.microsoft.com/chunking">
      53f183ee-04aa-44a0-b8d3-e45224563109
    </MessageId>
<!--
The sequence number of the chunk.
This number restarts at 1 with each new sequence of chunks.
-->
    <ChunkNumber s:mustUnderstand="1"
                 xmlns="http://samples.microsoft.com/chunking">
      1096
    </ChunkNumber>
  </s:Header>
  <s:Body>
<!--
The chunked data is wrapped in a chunk element.
The encoding of this data (and the entire message)
depends on the encoder used. The chunking channel does not mandate an encoding.
-->
    <chunk xmlns="http://samples.microsoft.com/chunking">
kfSr2QcBlkHTvQ==
    </chunk>
  </s:Body>
</s:Envelope>
```

### <a name="end-message"></a><span data-ttu-id="17ddc-134">Messaggio finale</span><span class="sxs-lookup"><span data-stu-id="17ddc-134">End Message</span></span>

```xml
<s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing"
            xmlns:s="http://www.w3.org/2003/05/soap-envelope">
  <s:Header>
    <a:Action s:mustUnderstand="1">
      http://samples.microsoft.com/chunkingAction
    </a:Action>
<!--
Same as MessageId in the start message. The GUID indicates which original message this chunk belongs to.
-->
    <MessageId s:mustUnderstand="1"
               xmlns="http://samples.microsoft.com/chunking">
      53f183ee-04aa-44a0-b8d3-e45224563109
    </MessageId>
<!--
ChunkingEnd header signals the end of a chunk sequence.
-->
    <ChunkingEnd s:mustUnderstand="1" i:nil="true"
                 xmlns:i="http://www.w3.org/2001/XMLSchema-instance"
                 xmlns="http://samples.microsoft.com/chunking" />
<!--
ChunkingEnd messages have a sequence number.
-->
    <ChunkNumber s:mustUnderstand="1"
                 xmlns="http://samples.microsoft.com/chunking">
      79
    </ChunkNumber>
  </s:Header>
  <s:Body>
<!--
The ChunkingEnd message has the same <element><childelement> structure
as the ChunkingStart message.
-->
    <EchoStream xmlns="http://tempuri.org/">
      <stream />
    </EchoStream>
  </s:Body>
</s:Envelope>
```

## <a name="chunking-channel-architecture"></a><span data-ttu-id="17ddc-135">Architettura del canale per la suddivisione in blocchi</span><span class="sxs-lookup"><span data-stu-id="17ddc-135">Chunking Channel Architecture</span></span>

<span data-ttu-id="17ddc-136">Il canale per la suddivisione in blocchi è un `IDuplexSessionChannel` che, a livello superiore, segue l'architettura del canale tipica.</span><span class="sxs-lookup"><span data-stu-id="17ddc-136">The chunking channel is an `IDuplexSessionChannel` that, at a high level, follows the typical channel architecture.</span></span> <span data-ttu-id="17ddc-137">C'è un `ChunkingBindingElement` che può compilare un `ChunkingChannelFactory` e un `ChunkingChannelListener`.</span><span class="sxs-lookup"><span data-stu-id="17ddc-137">There is a `ChunkingBindingElement` that can build a `ChunkingChannelFactory` and a `ChunkingChannelListener`.</span></span> <span data-ttu-id="17ddc-138">`ChunkingChannelFactory` crea istanze di `ChunkingChannel` quando gli viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="17ddc-138">The `ChunkingChannelFactory` creates instances of `ChunkingChannel` when it is asked to.</span></span> <span data-ttu-id="17ddc-139">`ChunkingChannelListener` crea istanze di `ChunkingChannel` quando viene accettato un nuovo canale interno.</span><span class="sxs-lookup"><span data-stu-id="17ddc-139">The `ChunkingChannelListener` creates instances of `ChunkingChannel` when a new inner channel is accepted.</span></span> <span data-ttu-id="17ddc-140">Il `ChunkingChannel` stesso è responsabile per l'invio e la ricezione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="17ddc-140">The `ChunkingChannel` itself is responsible for sending and receiving messages.</span></span>

<span data-ttu-id="17ddc-141">Al successivo livello inferiore, il `ChunkingChannel` si basa su molti componenti per implementare il protocollo per la suddivisione in blocchi.</span><span class="sxs-lookup"><span data-stu-id="17ddc-141">At the next level down, `ChunkingChannel` relies on several components to implement the chunking protocol.</span></span> <span data-ttu-id="17ddc-142">Per l'invio, il canale usa un oggetto <xref:System.Xml.XmlDictionaryWriter> personalizzato chiamato `ChunkingWriter` che esegue la vera e propria suddivisione in blocchi.</span><span class="sxs-lookup"><span data-stu-id="17ddc-142">On the send side, the channel uses a custom <xref:System.Xml.XmlDictionaryWriter> called `ChunkingWriter` that does the actual chunking.</span></span> <span data-ttu-id="17ddc-143">`ChunkingWriter` usa direttamente il canale interno per inviare i blocchi.</span><span class="sxs-lookup"><span data-stu-id="17ddc-143">`ChunkingWriter` uses the inner channel directly to send chunks.</span></span> <span data-ttu-id="17ddc-144">L'uso di un `XmlDictionaryWriter` personalizzato consente di inviare i blocchi mentre viene scritto il corpo del messaggio originale.</span><span class="sxs-lookup"><span data-stu-id="17ddc-144">Using a custom `XmlDictionaryWriter` allows us to send out chunks as the large body of the original message is being written.</span></span> <span data-ttu-id="17ddc-145">Questo significa che non viene memorizzato nel buffer l'intero messaggio originale.</span><span class="sxs-lookup"><span data-stu-id="17ddc-145">This means we do not buffer the entire original message.</span></span>

![Diagramma che mostra l'architettura di trasmissione del canale di suddivisione in blocchi.](./media/chunking-channel/chunking-channel-send.gif)

<span data-ttu-id="17ddc-147">Per la ricezione, `ChunkingChannel` esegue il pull dei messaggi dal canale interno e li consegna a un oggetto <xref:System.Xml.XmlDictionaryReader> personalizzato denominato `ChunkingReader`, che ricostruisce il messaggio originale dai blocchi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="17ddc-147">On the receive side, `ChunkingChannel` pulls messages from the inner channel and hands them to a custom <xref:System.Xml.XmlDictionaryReader> called `ChunkingReader`, which reconstitutes the original message from the incoming chunks.</span></span> <span data-ttu-id="17ddc-148">`ChunkingChannel` esegue il wrapping di questo `ChunkingReader` in un'implementazione `Message` personalizzata denominata `ChunkingMessage` e restituisce il messaggio al livello superiore.</span><span class="sxs-lookup"><span data-stu-id="17ddc-148">`ChunkingChannel` wraps this `ChunkingReader` in a custom `Message` implementation called `ChunkingMessage` and returns this message to the layer above.</span></span> <span data-ttu-id="17ddc-149">Questa combinazione di `ChunkingReader` e `ChunkingMessage` consente di ricostruire il corpo del messaggio originale mentre viene letto dal livello superiore, invece di dover memorizzare nel buffer l'intero corpo del messaggio originale.</span><span class="sxs-lookup"><span data-stu-id="17ddc-149">This combination of `ChunkingReader` and `ChunkingMessage` allows us to de-chunk the original message body as it is being read by the layer above instead of having to buffer the entire original message body.</span></span> <span data-ttu-id="17ddc-150">`ChunkingReader` è dotato di una coda in cui memorizza nel buffer i blocchi in arrivo, fino a un numero massimo configurabile di blocchi memorizzati.</span><span class="sxs-lookup"><span data-stu-id="17ddc-150">`ChunkingReader` has a queue where it buffers incoming chunks up to a maximum configurable number of buffered chunks.</span></span> <span data-ttu-id="17ddc-151">Quando questo limite massimo viene raggiunto, il lettore attende che i messaggi vengano svuotati dalla coda dal livello superiore (operazione eseguita semplicemente leggendo il corpo del messaggio originale) o fino a raggiungere il timeout di ricezione massimo.</span><span class="sxs-lookup"><span data-stu-id="17ddc-151">When this maximum limit is reached, the reader waits for messages to be drained from the queue by the layer above (that is, by just reading from the original message body) or until the maximum receive timeout is reached.</span></span>

![Diagramma che mostra l'architettura di ricezione del canale di suddivisione in blocchi.](./media/chunking-channel/chunking-channel-receive.gif)

## <a name="chunking-programming-model"></a><span data-ttu-id="17ddc-153">Modello di programmazione per la suddivisione in blocchi</span><span class="sxs-lookup"><span data-stu-id="17ddc-153">Chunking Programming Model</span></span>

<span data-ttu-id="17ddc-154">Gli sviluppatori del servizio possono specificare quali messaggi devono essere suddivisi in blocchi applicando l'attributo `ChunkingBehavior` alle operazioni all'interno del contratto.</span><span class="sxs-lookup"><span data-stu-id="17ddc-154">Service developers can specify which messages are to be chunked by applying the `ChunkingBehavior` attribute to operations within the contract.</span></span> <span data-ttu-id="17ddc-155">L'attributo espone una proprietà `AppliesTo` che consente allo sviluppatore di specificare se la suddivisione in blocchi si applica al messaggio di input, al messaggio di output o a entrambi.</span><span class="sxs-lookup"><span data-stu-id="17ddc-155">The attribute exposes an `AppliesTo` property that allows the developer to specify whether chunking applies to the input message, the output message or both.</span></span> <span data-ttu-id="17ddc-156">Nell'esempio seguente viene illustrato l'uso dell'attributo `ChunkingBehavior`:</span><span class="sxs-lookup"><span data-stu-id="17ddc-156">The following example shows the usage of `ChunkingBehavior` attribute:</span></span>

```csharp
[ServiceContract]
interface ITestService
{
    [OperationContract]
    [ChunkingBehavior(ChunkingAppliesTo.Both)]
    Stream EchoStream(Stream stream);

    [OperationContract]
    [ChunkingBehavior(ChunkingAppliesTo.OutMessage)]
    Stream DownloadStream();

    [OperationContract(IsOneWay=true)]
    [ChunkingBehavior(ChunkingAppliesTo.InMessage)]
    void UploadStream(Stream stream);

}
```

<span data-ttu-id="17ddc-157">Da questo modello di programmazione, il `ChunkingBindingElement` compila un elenco di URI dell'azione che identificano i messaggi da suddividere in blocchi.</span><span class="sxs-lookup"><span data-stu-id="17ddc-157">From this programming model, the `ChunkingBindingElement` compiles a list of action URIs that identify messages to be chunked.</span></span> <span data-ttu-id="17ddc-158">L'azione di ogni messaggio in uscita viene confrontata con questo elenco per determinare se il messaggio deve essere suddiviso in blocchi o inviato direttamente.</span><span class="sxs-lookup"><span data-stu-id="17ddc-158">The action of each outgoing message is compared against this list to determine if the message should be chunked or sent directly.</span></span>

## <a name="implementing-the-send-operation"></a><span data-ttu-id="17ddc-159">Implementazione dell'operazione Send</span><span class="sxs-lookup"><span data-stu-id="17ddc-159">Implementing the Send Operation</span></span>

<span data-ttu-id="17ddc-160">A livello superiore, l'operazione Send prima controlla se il messaggio in uscita deve essere suddiviso in blocchi e altrimenti invia direttamente il messaggio usando il canale interno.</span><span class="sxs-lookup"><span data-stu-id="17ddc-160">At a high level, the Send operation first checks whether the outgoing message must be chunked and, if not, sends the message directly using the inner channel.</span></span>

<span data-ttu-id="17ddc-161">Se il messaggio deve essere suddiviso in blocchi, l'operazione Send crea un nuovo `ChunkingWriter` e chiama `WriteBodyContents` sul messaggio in uscita passandogli il `ChunkingWriter`.</span><span class="sxs-lookup"><span data-stu-id="17ddc-161">If the message must be chunked, Send creates a new `ChunkingWriter` and calls `WriteBodyContents` on the outgoing message passing it this `ChunkingWriter`.</span></span> <span data-ttu-id="17ddc-162">Il `ChunkingWriter` esegue quindi la suddivisione in blocchi del messaggio (copiando le intestazioni del messaggio originale nel blocco di messaggio iniziale) e invia i blocchi usando il canale interno.</span><span class="sxs-lookup"><span data-stu-id="17ddc-162">The `ChunkingWriter` then does the message chunking (including copying original message headers to the start chunk message) and sends chunks using the inner channel.</span></span>

<span data-ttu-id="17ddc-163">Alcuni dettagli degni di nota:</span><span class="sxs-lookup"><span data-stu-id="17ddc-163">A few details worth noting:</span></span>

- <span data-ttu-id="17ddc-164">L'operazione Send prima chiama `ThrowIfDisposedOrNotOpened` per assicurarsi che `CommunicationState` sia aperto.</span><span class="sxs-lookup"><span data-stu-id="17ddc-164">Send first calls `ThrowIfDisposedOrNotOpened` to ensure the `CommunicationState` is opened.</span></span>

- <span data-ttu-id="17ddc-165">L'invio viene sincronizzato in modo che possa essere inviato solo uno messaggio alla volta per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="17ddc-165">Sending is synchronized so that only one message can be sent at a time for each session.</span></span> <span data-ttu-id="17ddc-166">C'è un `ManualResetEvent` denominato `sendingDone` che viene reimpostato quando viene inviato un messaggio suddiviso in blocchi.</span><span class="sxs-lookup"><span data-stu-id="17ddc-166">There is a `ManualResetEvent` named `sendingDone` that is reset when a chunked message is being sent.</span></span> <span data-ttu-id="17ddc-167">Una volta inviato il blocco di messaggio finale, l'evento viene impostato.</span><span class="sxs-lookup"><span data-stu-id="17ddc-167">Once the end chunk message is sent, this event is set.</span></span> <span data-ttu-id="17ddc-168">Il metodo Send attende che questo evento venga impostato prima che di tentare di inviare il messaggio in uscita.</span><span class="sxs-lookup"><span data-stu-id="17ddc-168">The Send method waits for this event to be set before it tries to send the outgoing message.</span></span>

- <span data-ttu-id="17ddc-169">L'operazione Send blocca `CommunicationObject.ThisLock` per evitare modifiche sincronizzate dello stato durante l'invio.</span><span class="sxs-lookup"><span data-stu-id="17ddc-169">Send locks the `CommunicationObject.ThisLock` to prevent synchronized state changes while sending.</span></span> <span data-ttu-id="17ddc-170">Vedere la documentazione relativa a <xref:System.ServiceModel.Channels.CommunicationObject> per altre informazioni sugli stati di <xref:System.ServiceModel.Channels.CommunicationObject> e sulla macchina a stati.</span><span class="sxs-lookup"><span data-stu-id="17ddc-170">See the <xref:System.ServiceModel.Channels.CommunicationObject> documentation for more information about <xref:System.ServiceModel.Channels.CommunicationObject> states and state machine.</span></span>

- <span data-ttu-id="17ddc-171">Il timeout passato a Send viene usato come timeout per l'intera operazione di invio, che comprende l'invio di tutti i blocchi.</span><span class="sxs-lookup"><span data-stu-id="17ddc-171">The timeout passed to Send is used as the timeout for the entire send operation which includes sending all of the chunks.</span></span>

- <span data-ttu-id="17ddc-172">La progettazione <xref:System.Xml.XmlDictionaryWriter> personalizzata viene scelta per evitare di memorizzare nel buffer l'intero corpo del messaggio originale.</span><span class="sxs-lookup"><span data-stu-id="17ddc-172">The custom <xref:System.Xml.XmlDictionaryWriter> design was chosen to avoid buffering the entire original message body.</span></span> <span data-ttu-id="17ddc-173">Se si dovesse usare un <xref:System.Xml.XmlDictionaryReader> sul corpo usando `message.GetReaderAtBodyContents`, l'intero corpo verrebbe memorizzato nel buffer.</span><span class="sxs-lookup"><span data-stu-id="17ddc-173">If we were to get an <xref:System.Xml.XmlDictionaryReader> on the body using `message.GetReaderAtBodyContents` the entire body would be buffered.</span></span> <span data-ttu-id="17ddc-174">Al contrario, <xref:System.Xml.XmlDictionaryWriter> abbiamo un `message.WriteBodyContents`abitudine che viene passato a .</span><span class="sxs-lookup"><span data-stu-id="17ddc-174">Instead, we have a custom  <xref:System.Xml.XmlDictionaryWriter> that is passed to `message.WriteBodyContents`.</span></span> <span data-ttu-id="17ddc-175">Quando il messaggio chiama WriteBase64 sul writer, il writer ricostruisce i blocchi in messaggi e li invia usando il canale interno.</span><span class="sxs-lookup"><span data-stu-id="17ddc-175">As the message calls WriteBase64 on the writer, the writer packages up chunks into messages and sends them using the inner channel.</span></span> <span data-ttu-id="17ddc-176">WriteBase64 si blocca fino a che non viene inviato il blocco.</span><span class="sxs-lookup"><span data-stu-id="17ddc-176">WriteBase64 blocks until the chunk is sent.</span></span>

## <a name="implementing-the-receive-operation"></a><span data-ttu-id="17ddc-177">Implementazione dell'operazione Receive</span><span class="sxs-lookup"><span data-stu-id="17ddc-177">Implementing the Receive Operation</span></span>

<span data-ttu-id="17ddc-178">A livello superiore, l'operazione Receive prima controlla che il messaggio in arrivo non sia `null` e che l'azione sia `ChunkingAction`.</span><span class="sxs-lookup"><span data-stu-id="17ddc-178">At a high level, the Receive operation first checks that the incoming message is not `null` and that its action is the `ChunkingAction`.</span></span> <span data-ttu-id="17ddc-179">Se non vengono soddisfatti entrambi i criteri, Receive restituisce il messaggio immutato.</span><span class="sxs-lookup"><span data-stu-id="17ddc-179">If it does not meet both criteria, the message is returned unchanged from Receive.</span></span> <span data-ttu-id="17ddc-180">In caso contrario, Receive crea un nuovo `ChunkingReader` su cui viene eseguito il wrapping di un nuovo `ChunkingMessage` (chiamando `GetNewChunkingMessage`).</span><span class="sxs-lookup"><span data-stu-id="17ddc-180">Otherwise, Receive creates a new `ChunkingReader` and a new `ChunkingMessage` wrapped around it (by calling `GetNewChunkingMessage`).</span></span> <span data-ttu-id="17ddc-181">Prima di restituire quel nuovo `ChunkingMessage`, Receive usa un che un thread del pool di thread per eseguire `ReceiveChunkLoop` che chiama `innerChannel.Receive` in un ciclo e consegna i blocchi al `ChunkingReader` fino a ricevere il blocco di messaggio finale o fino a raggiungere il timeout di ricezione.</span><span class="sxs-lookup"><span data-stu-id="17ddc-181">Before returning that new `ChunkingMessage`, Receive uses a threadpool thread to execute `ReceiveChunkLoop`, which calls `innerChannel.Receive` in a loop and hands off chunks to the `ChunkingReader` until the end chunk message is received or the receive timeout is hit.</span></span>

<span data-ttu-id="17ddc-182">Alcuni dettagli degni di nota:</span><span class="sxs-lookup"><span data-stu-id="17ddc-182">A few details worth noting:</span></span>

- <span data-ttu-id="17ddc-183">Come per l'operazione Send, Receive prima chiama `ThrowIfDisposedOrNotOepned` per assicurarsi che `CommunicationState` sia aperto.</span><span class="sxs-lookup"><span data-stu-id="17ddc-183">Like Send, Receive first calls `ThrowIfDisposedOrNotOepned` to ensure the `CommunicationState` is Opened.</span></span>

- <span data-ttu-id="17ddc-184">Anche l'operazione Receive viene sincronizzata in modo che si possa ricevere solo un messaggio alla volta dalla sessione.</span><span class="sxs-lookup"><span data-stu-id="17ddc-184">Receive is also synchronized so that only one message can be received at a time from the session.</span></span> <span data-ttu-id="17ddc-185">Questo è particolarmente importante perché una volta ricevuto un blocco di messaggio iniziale, si presuppone che tutti i messaggi seguenti ricevuti siano blocchi di questa nuova sequenza di blocchi, fino alla ricezione del blocco di messaggio finale.</span><span class="sxs-lookup"><span data-stu-id="17ddc-185">This is especially important because once a start chunk message is received, all subsequent received messages are expected to be chunks within this new chunk sequence until an end chunk message is received.</span></span> <span data-ttu-id="17ddc-186">L'operazione Receive non è in grado di eseguire il pull dei messaggi dal canale interno finché non vengono ricevuti tutti i blocchi che appartengono al messaggio in corso di ricostruzione.</span><span class="sxs-lookup"><span data-stu-id="17ddc-186">Receive cannot pull messages from the inner channel until all chunks that belong to the message currently being de-chunked are received.</span></span> <span data-ttu-id="17ddc-187">Per eseguire questa operazione, Receive usa un `ManualResetEvent` denominato `currentMessageCompleted`, impostato quando viene ricevuto il blocco di messaggio finale e reimpostato quando viene ricevuto un nuovo blocco di messaggio iniziale.</span><span class="sxs-lookup"><span data-stu-id="17ddc-187">To accomplish this, Receive uses a `ManualResetEvent` named `currentMessageCompleted`, which is set when the end chunk message is received and reset when a new start chunk message is received.</span></span>

- <span data-ttu-id="17ddc-188">A differenza dell'operazione Send, Receive non impedisce le transizioni sincronizzate dello stato durante la ricezione.</span><span class="sxs-lookup"><span data-stu-id="17ddc-188">Unlike Send, Receive does not prevent synchronized state transitions while receiving.</span></span> <span data-ttu-id="17ddc-189">Ad esempio, è possibile chiamare il metodo Close durante la ricezione. Il metodo attenderà che venga completata la ricezione del messaggio originale o che venga raggiunto il valore di timeout specificato.</span><span class="sxs-lookup"><span data-stu-id="17ddc-189">For example, Close can be called while receiving and waits until the pending receive of the original message is completed or the specified timeout value is reached.</span></span>

- <span data-ttu-id="17ddc-190">Il timeout passato a Receive viene usato come timeout per l'intera operazione di ricezione, che comprende la ricezione di tutti i blocchi.</span><span class="sxs-lookup"><span data-stu-id="17ddc-190">The timeout passed to Receive is used as the timeout for the entire receive operation, which includes receiving all of the chunks.</span></span>

- <span data-ttu-id="17ddc-191">Se il livello che usa il messaggio sta usando il corpo del messaggio a una velocità inferiore della velocità di arrivo dei blocchi dei messaggi, `ChunkingReader` memorizza nel buffer quei blocchi in arrivo fino al limite specificato da `ChunkingBindingElement.MaxBufferedChunks`.</span><span class="sxs-lookup"><span data-stu-id="17ddc-191">If the layer that consumes the message is consuming the message body at a rate lower than the rate of incoming chunk messages, the `ChunkingReader` buffers those incoming chunks up to the limit specified by `ChunkingBindingElement.MaxBufferedChunks`.</span></span> <span data-ttu-id="17ddc-192">Una volta raggiunto quel limite, non viene eseguito il pull di altri blocchi dal livello inferiore finché non viene usato un blocco memorizzato nel buffer o viene raggiunto il timeout di ricezione.</span><span class="sxs-lookup"><span data-stu-id="17ddc-192">Once that limit is reached, no more chunks are pulled from the lower layer until either a buffered chunk is consumed or the receive timeout is reached.</span></span>

## <a name="communicationobject-overrides"></a><span data-ttu-id="17ddc-193">Override di CommunicationObject</span><span class="sxs-lookup"><span data-stu-id="17ddc-193">CommunicationObject Overrides</span></span>

### <a name="onopen"></a><span data-ttu-id="17ddc-194">OnOpen</span><span class="sxs-lookup"><span data-stu-id="17ddc-194">OnOpen</span></span>

<span data-ttu-id="17ddc-195">`OnOpen` chiama `innerChannel.Open` per aprire il canale interno.</span><span class="sxs-lookup"><span data-stu-id="17ddc-195">`OnOpen` calls `innerChannel.Open` to open the inner channel.</span></span>

### <a name="onclose"></a><span data-ttu-id="17ddc-196">OnClose</span><span class="sxs-lookup"><span data-stu-id="17ddc-196">OnClose</span></span>

<span data-ttu-id="17ddc-197">`OnClose` prima imposta `stopReceive` su `true` per comunicare al `ReceiveChunkLoop` in sospeso di arrestarsi.</span><span class="sxs-lookup"><span data-stu-id="17ddc-197">`OnClose` first sets `stopReceive` to `true` to signal the pending `ReceiveChunkLoop` to stop.</span></span> <span data-ttu-id="17ddc-198">Quindi attende il `receiveStopped` <xref:System.Threading.ManualResetEvent>, che `ReceiveChunkLoop` viene impostato quando si ferma.</span><span class="sxs-lookup"><span data-stu-id="17ddc-198">It then waits for the `receiveStopped` <xref:System.Threading.ManualResetEvent>, which is set when `ReceiveChunkLoop` stops.</span></span> <span data-ttu-id="17ddc-199">Presupponendo che `ReceiveChunkLoop` si arresti entro il timeout specificato, `OnClose` chiama `innerChannel.Close` con il timeout rimanente.</span><span class="sxs-lookup"><span data-stu-id="17ddc-199">Assuming the `ReceiveChunkLoop` stops within the specified timeout, `OnClose` calls `innerChannel.Close` with the remaining timeout.</span></span>

### <a name="onabort"></a><span data-ttu-id="17ddc-200">OnAbort</span><span class="sxs-lookup"><span data-stu-id="17ddc-200">OnAbort</span></span>

<span data-ttu-id="17ddc-201">`OnAbort` chiama `innerChannel.Abort` per interrompere il canale interno.</span><span class="sxs-lookup"><span data-stu-id="17ddc-201">`OnAbort` calls `innerChannel.Abort` to abort the inner channel.</span></span> <span data-ttu-id="17ddc-202">Se c'è un `ReceiveChunkLoop` in sospeso, viene generata un'eccezione dalla chiamata `innerChannel.Receive` in sospeso.</span><span class="sxs-lookup"><span data-stu-id="17ddc-202">If there is a pending `ReceiveChunkLoop` it gets an exception from the pending `innerChannel.Receive` call.</span></span>

### <a name="onfaulted"></a><span data-ttu-id="17ddc-203">OnFaulted</span><span class="sxs-lookup"><span data-stu-id="17ddc-203">OnFaulted</span></span>

<span data-ttu-id="17ddc-204">Il `ChunkingChannel` non richiede un comportamento speciale quando il canale contiene errori, per cui non viene eseguito l'override di `OnFaulted`.</span><span class="sxs-lookup"><span data-stu-id="17ddc-204">The `ChunkingChannel` does not require special behavior when the channel is faulted so `OnFaulted` is not overridden.</span></span>

## <a name="implementing-channel-factory"></a><span data-ttu-id="17ddc-205">Implementazione di una channel factory</span><span class="sxs-lookup"><span data-stu-id="17ddc-205">Implementing Channel Factory</span></span>

<span data-ttu-id="17ddc-206">La `ChunkingChannelFactory` è responsabile per la creazione di istanze di `ChunkingDuplexSessionChannel` e per la sovrapposizione delle transizioni di stato nella channel factory interna.</span><span class="sxs-lookup"><span data-stu-id="17ddc-206">The `ChunkingChannelFactory` is responsible for creating instances of `ChunkingDuplexSessionChannel` and for cascading state transitions to the inner channel factory.</span></span>

<span data-ttu-id="17ddc-207">`OnCreateChannel` usa la channel factory interna per creare un canale interno `IDuplexSessionChannel`.</span><span class="sxs-lookup"><span data-stu-id="17ddc-207">`OnCreateChannel` uses the inner channel factory to create an `IDuplexSessionChannel` inner channel.</span></span> <span data-ttu-id="17ddc-208">Crea quindi un nuovo `ChunkingDuplexSessionChannel` passandogli questo canale interno, l'elenco di azioni del messaggio da suddividere in blocchi e il numero massimo di blocchi da memorizzare nel buffer al momento della ricezione.</span><span class="sxs-lookup"><span data-stu-id="17ddc-208">It then creates a new `ChunkingDuplexSessionChannel` passing it this inner channel along with the list of message actions to be chunked and the maximum number of chunks to buffer upon receive.</span></span> <span data-ttu-id="17ddc-209">L'elenco di azioni del messaggio da suddividere in blocchi e il numero massimo di blocchi da memorizzare nel buffer sono due parametri passati a `ChunkingChannelFactory` nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="17ddc-209">The list of message actions to be chunked and the maximum number of chunks to buffer are two parameters passed to `ChunkingChannelFactory` in its constructor.</span></span> <span data-ttu-id="17ddc-210">Nella sezione relativa all'elemento `ChunkingBindingElement` viene descritto da dove provengono questi valori.</span><span class="sxs-lookup"><span data-stu-id="17ddc-210">The section on `ChunkingBindingElement` describes where these values come from.</span></span>

<span data-ttu-id="17ddc-211">`OnOpen`, `OnClose`, `OnAbort` e gli equivalenti asincroni chiamano il metodo della transizione di stato corrispondente nella channel factory interna.</span><span class="sxs-lookup"><span data-stu-id="17ddc-211">The `OnOpen`, `OnClose`, `OnAbort` and their asynchronous equivalents call the corresponding state transition method on the inner channel factory.</span></span>

## <a name="implementing-channel-listener"></a><span data-ttu-id="17ddc-212">Implementazione di un listener del canale</span><span class="sxs-lookup"><span data-stu-id="17ddc-212">Implementing Channel Listener</span></span>

<span data-ttu-id="17ddc-213">Il `ChunkingChannelListener` è un wrapper del listener del canale interno.</span><span class="sxs-lookup"><span data-stu-id="17ddc-213">The `ChunkingChannelListener` is a wrapper around an inner channel listener.</span></span> <span data-ttu-id="17ddc-214">La sua funzione principale, oltre a delegare le chiamate al listener del canale interno, è di eseguire il wrapping dei nuovi `ChunkingDuplexSessionChannels` sui canali accettati dal listener del canale interno.</span><span class="sxs-lookup"><span data-stu-id="17ddc-214">Its main function, besides delegate calls to that inner channel listener, is to wrap new `ChunkingDuplexSessionChannels` around channels accepted from the inner channel listener.</span></span> <span data-ttu-id="17ddc-215">Questa operazione viene eseguita in `OnAcceptChannel` e `OnEndAcceptChannel`.</span><span class="sxs-lookup"><span data-stu-id="17ddc-215">This is done in `OnAcceptChannel` and `OnEndAcceptChannel`.</span></span> <span data-ttu-id="17ddc-216">Il nuovo `ChunkingDuplexSessionChannel` viene passato al canale interno insieme agli altri parametri precedentemente descritti.</span><span class="sxs-lookup"><span data-stu-id="17ddc-216">The newly created `ChunkingDuplexSessionChannel` is passed the inner channel along with the other parameters previously described.</span></span>

## <a name="implementing-binding-element-and-binding"></a><span data-ttu-id="17ddc-217">Implementazione degli elementi di associazione e delle associazioni</span><span class="sxs-lookup"><span data-stu-id="17ddc-217">Implementing Binding Element and Binding</span></span>

<span data-ttu-id="17ddc-218">`ChunkingBindingElement` è responsabile della creazione di `ChunkingChannelFactory` e di `ChunkingChannelListener`.</span><span class="sxs-lookup"><span data-stu-id="17ddc-218">`ChunkingBindingElement` is responsible for creating the `ChunkingChannelFactory` and `ChunkingChannelListener`.</span></span> <span data-ttu-id="17ddc-219">Il `ChunkingBindingElement` controlla se `CanBuildChannelFactory` \<T `CanBuildChannelListener` \<in T> `IDuplexSessionChannel` e T> è di tipo (l'unico canale supportato dal canale di suddivisione in blocchi) e che gli altri elementi di associazione nell'associazione supportano questo tipo di canale.</span><span class="sxs-lookup"><span data-stu-id="17ddc-219">The `ChunkingBindingElement` checks whether T in `CanBuildChannelFactory`\<T> and `CanBuildChannelListener`\<T> is of type `IDuplexSessionChannel` (the only channel supported by the chunking channel) and that the other binding elements in the binding support this channel type.</span></span>

<span data-ttu-id="17ddc-220">`BuildChannelFactory`\<T> controlla innanzitutto che il tipo di canale richiesto possa essere compilato e quindi ottiene un elenco di azioni messaggio da suddividere in blocchi.</span><span class="sxs-lookup"><span data-stu-id="17ddc-220">`BuildChannelFactory`\<T> first checks that the requested channel type can be built and then gets a list of message actions to be chunked.</span></span> <span data-ttu-id="17ddc-221">Per altre informazioni, vedere la sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="17ddc-221">For more information, see the following section.</span></span> <span data-ttu-id="17ddc-222">Crea quindi un nuovo `ChunkingChannelFactory` passandogli la channel factory interna (restituita da `context.BuildInnerChannelFactory<IDuplexSessionChannel>`), l'elenco di azioni del messaggio e il numero massimo di blocchi da memorizzare nel buffer.</span><span class="sxs-lookup"><span data-stu-id="17ddc-222">It then creates a new `ChunkingChannelFactory` passing it the inner channel factory (as returned from `context.BuildInnerChannelFactory<IDuplexSessionChannel>`), the list of message actions, and the maximum number of chunks to buffer.</span></span> <span data-ttu-id="17ddc-223">Il numero massimo di blocchi proviene da una proprietà chiamata `MaxBufferedChunks` esposta da `ChunkingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="17ddc-223">The maximum number of chunks comes from a property called `MaxBufferedChunks` exposed by the `ChunkingBindingElement`.</span></span>

<span data-ttu-id="17ddc-224">L'implementazione del metodo `BuildChannelListener<T>` per creare `ChunkingChannelListener` e passare il listener del canale interno è simile.</span><span class="sxs-lookup"><span data-stu-id="17ddc-224">`BuildChannelListener<T>` has a similar implementation for creating `ChunkingChannelListener` and passing it the inner channel listener.</span></span>

<span data-ttu-id="17ddc-225">In questo esempio viene incluso un esempio di associazione denominata `TcpChunkingBinding`.</span><span class="sxs-lookup"><span data-stu-id="17ddc-225">There is an example binding included in this sample named `TcpChunkingBinding`.</span></span> <span data-ttu-id="17ddc-226">Questa associazione è costituita da due elementi di associazione: `TcpTransportBindingElement` e `ChunkingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="17ddc-226">This binding consists of two binding elements: `TcpTransportBindingElement` and `ChunkingBindingElement`.</span></span> <span data-ttu-id="17ddc-227">Oltre a esporre la proprietà `MaxBufferedChunks`, l'associazione imposta anche alcune delle proprietà `TcpTransportBindingElement`, ad esempio `MaxReceivedMessageSize` (lo imposta su `ChunkingUtils.ChunkSize` + 100KB byte per le intestazioni).</span><span class="sxs-lookup"><span data-stu-id="17ddc-227">In addition to exposing the `MaxBufferedChunks` property, the binding also sets some of the `TcpTransportBindingElement` properties such as `MaxReceivedMessageSize` (sets it to `ChunkingUtils.ChunkSize` + 100KB bytes for headers).</span></span>

<span data-ttu-id="17ddc-228">`TcpChunkingBinding` implementa anche `IBindingRuntimePreferences` e restituisce true dal metodo `ReceiveSynchronously`, che indica che vengono implementate solo le chiamate Receive sincrone.</span><span class="sxs-lookup"><span data-stu-id="17ddc-228">`TcpChunkingBinding` also implements `IBindingRuntimePreferences` and returns true from the `ReceiveSynchronously` method indicating that only the synchronous Receive calls are implemented.</span></span>

### <a name="determining-which-messages-to-chunk"></a><span data-ttu-id="17ddc-229">Decidere quali messaggi vanno suddivisi in blocchi</span><span class="sxs-lookup"><span data-stu-id="17ddc-229">Determining Which Messages To Chunk</span></span>

<span data-ttu-id="17ddc-230">Il canale per la suddivisione in blocchi suddivide solo i messaggi identificati dall'attributo `ChunkingBehavior`.</span><span class="sxs-lookup"><span data-stu-id="17ddc-230">The chunking channel chunks only the messages identified through the `ChunkingBehavior` attribute.</span></span> <span data-ttu-id="17ddc-231">La classe `ChunkingBehavior` implementa `IOperationBehavior` e viene implementata chiamando il metodo `AddBindingParameter`.</span><span class="sxs-lookup"><span data-stu-id="17ddc-231">The `ChunkingBehavior` class implements `IOperationBehavior` and is implemented by calling the `AddBindingParameter` method.</span></span> <span data-ttu-id="17ddc-232">In questo metodo, `ChunkingBehavior` esamina il valore della proprietà `AppliesTo` (`InMessage`, `OutMessage` o entrambi) per determinare quali messaggi vanno suddivisi in blocchi.</span><span class="sxs-lookup"><span data-stu-id="17ddc-232">In this method, the `ChunkingBehavior` examines the value of its `AppliesTo` property (`InMessage`, `OutMessage` or both) to determine which messages should be chunked.</span></span> <span data-ttu-id="17ddc-233">Ottiene quindi l'azione di ognuno di quei messaggi (dalla raccolta dei messaggi in `OperationDescription`) e la aggiunge a una raccolta di stringhe contenuta all'interno di un'istanza di `ChunkingBindingParameter`.</span><span class="sxs-lookup"><span data-stu-id="17ddc-233">It then gets the action of each of those messages (from the Messages collection on `OperationDescription`) and adds it to a string collection contained within an instance of `ChunkingBindingParameter`.</span></span> <span data-ttu-id="17ddc-234">Aggiunge quindi questo `ChunkingBindingParameter` alla raccolta `BindingParameterCollection` fornito</span><span class="sxs-lookup"><span data-stu-id="17ddc-234">It then adds this `ChunkingBindingParameter` to the provided `BindingParameterCollection`.</span></span>

<span data-ttu-id="17ddc-235">`BindingParameterCollection` viene passato all'interno di `BindingContext` a ogni elemento di associazione nell'associazione quando l'elemento di associazione compila la channel factory o il listener del canale.</span><span class="sxs-lookup"><span data-stu-id="17ddc-235">This `BindingParameterCollection` is passed inside the `BindingContext` to each binding element in the binding when that binding element builds the channel factory or the channel listener.</span></span> <span data-ttu-id="17ddc-236">L'implementazione `ChunkingBindingElement` `BuildChannelFactory<T>` di `BuildChannelListener<T>` e `ChunkingBindingParameter` tirare `BindingContext’` `BindingParameterCollection`questo fuori dal s .</span><span class="sxs-lookup"><span data-stu-id="17ddc-236">The `ChunkingBindingElement`'s implementation of `BuildChannelFactory<T>` and `BuildChannelListener<T>` pull this `ChunkingBindingParameter` out of the `BindingContext’`s `BindingParameterCollection`.</span></span> <span data-ttu-id="17ddc-237">La raccolta di azioni contenuta all'interno di `ChunkingBindingParameter` viene quindi passata alla `ChunkingChannelFactory` o al `ChunkingChannelListener`, che a sua volta la passa al `ChunkingDuplexSessionChannel`.</span><span class="sxs-lookup"><span data-stu-id="17ddc-237">The collection of actions contained within the `ChunkingBindingParameter` is then passed to the `ChunkingChannelFactory` or `ChunkingChannelListener`, which in turn passes it to the `ChunkingDuplexSessionChannel`.</span></span>

## <a name="running-the-sample"></a><span data-ttu-id="17ddc-238">Esecuzione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="17ddc-238">Running the Sample</span></span>

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="17ddc-239">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="17ddc-239">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="17ddc-240">Installare ASP.NET 4.0 utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="17ddc-240">Install ASP.NET 4.0 using the following command.</span></span>

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. <span data-ttu-id="17ddc-241">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="17ddc-241">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

3. <span data-ttu-id="17ddc-242">Per compilare la soluzione, seguire le istruzioni in [Compilazione di Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="17ddc-242">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="17ddc-243">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="17ddc-243">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

5. <span data-ttu-id="17ddc-244">Eseguire prima Service.exe quindi Client.exe e controllare l'output di entrambe le finestre della console.</span><span class="sxs-lookup"><span data-stu-id="17ddc-244">Run Service.exe first, then run Client.exe and watch both console windows for output.</span></span>

<span data-ttu-id="17ddc-245">Quando si esegue l'esempio, viene visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="17ddc-245">When running the sample, the following output is expected.</span></span>

<span data-ttu-id="17ddc-246">Client:</span><span class="sxs-lookup"><span data-stu-id="17ddc-246">Client:</span></span>

```console
Press enter when service is available

 > Sent chunk 1 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 2 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 3 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 4 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 5 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 6 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 7 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 8 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 9 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 10 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 1 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 2 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 3 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 4 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 5 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 6 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 7 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 8 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 9 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 10 of message 5b226ad5-c088-4988-b737-6a565e0563dd
```

<span data-ttu-id="17ddc-247">Server: </span><span class="sxs-lookup"><span data-stu-id="17ddc-247">Server:</span></span>

```console
Service started, press enter to exit
 < Received chunk 1 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 2 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 3 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 4 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 5 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 6 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 7 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 8 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 9 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 10 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 1 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 2 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 3 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 4 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 5 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 6 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 7 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 8 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 9 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 10 of message 5b226ad5-c088-4988-b737-6a565e0563dd
```

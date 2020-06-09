---
title: STREAM
ms.date: 03/30/2017
ms.assetid: 58a3db81-20ab-4627-bf31-39d30b70b4fe
ms.openlocfilehash: a482c27dfd0970b319a605a480b5f54689e42d48
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589838"
---
# <a name="stream"></a><span data-ttu-id="b1316-102">STREAM</span><span class="sxs-lookup"><span data-stu-id="b1316-102">Stream</span></span>
<span data-ttu-id="b1316-103">L'esempio flusso illustra l'utilizzo della modalità di trasferimento con flusso.</span><span class="sxs-lookup"><span data-stu-id="b1316-103">The Stream sample demonstrates the use of streaming transfer mode communication.</span></span> <span data-ttu-id="b1316-104">Il servizio espone molte operazioni che inviano e ricevono flussi.</span><span class="sxs-lookup"><span data-stu-id="b1316-104">The service exposes several operations that send and receive streams.</span></span> <span data-ttu-id="b1316-105">Questo esempio è indipendente.</span><span class="sxs-lookup"><span data-stu-id="b1316-105">This sample is self-hosted.</span></span> <span data-ttu-id="b1316-106">Sia il client che il servizio sono programmi console.</span><span class="sxs-lookup"><span data-stu-id="b1316-106">Both the client and service are console programs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1316-107">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b1316-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="b1316-108">Windows Communication Foundation (WCF) è in grado di comunicare in due modalità di trasferimento, memorizzato nel buffer o in streaming.</span><span class="sxs-lookup"><span data-stu-id="b1316-108">Windows Communication Foundation (WCF) can communicate in two transfer modes—buffered or streaming.</span></span> <span data-ttu-id="b1316-109">Per impostazione predefinita, il messaggio viene memorizzato nel buffer e deve essere recapitato completamente prima che un destinatario sia in grado di leggerlo.</span><span class="sxs-lookup"><span data-stu-id="b1316-109">In the default buffered transfer mode, a message must be completely delivered before a receiver can read it.</span></span> <span data-ttu-id="b1316-110">Nella modalità di trasferimento con flusso, il destinatario può iniziare a elaborare il messaggio prima che esso venga recapitato completamente.</span><span class="sxs-lookup"><span data-stu-id="b1316-110">In the streaming transfer mode, the receiver can begin to process the message before it is completely delivered.</span></span> <span data-ttu-id="b1316-111">La modalità di trasmissione con flusso è utile quando le informazioni passate sono lunghe e possono essere elaborate in serie.</span><span class="sxs-lookup"><span data-stu-id="b1316-111">The streaming mode is useful when the information that is passed is lengthy and can be processed serially.</span></span> <span data-ttu-id="b1316-112">La modalità di trasmissione con flusso è utile anche quando il messaggio è troppo grande da memorizzare completamente nel buffer.</span><span class="sxs-lookup"><span data-stu-id="b1316-112">Streaming mode is also useful when the message is too large to be entirely buffered.</span></span>  
  
## <a name="streaming-and-service-contracts"></a><span data-ttu-id="b1316-113">Flusso e contratti di servizio</span><span class="sxs-lookup"><span data-stu-id="b1316-113">Streaming and Service Contracts</span></span>  
 <span data-ttu-id="b1316-114">Il flusso va preso in considerazione quando si progetta un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="b1316-114">Streaming is something to be considered when designing a service contract.</span></span> <span data-ttu-id="b1316-115">Se un'operazione riceve o restituisce grandi quantità di dati, è necessario trasmetterli per evitare un utilizzo eccessivo della memoria a causa della memorizzazione nel buffer di messaggi di input o output.</span><span class="sxs-lookup"><span data-stu-id="b1316-115">If an operation receives or returns large amounts of data, you should consider streaming this data to avoid high memory utilization due to buffering of input or output messages.</span></span> <span data-ttu-id="b1316-116">Per trasmettere dati, il parametro che contiene i dati deve essere il solo parametro del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b1316-116">To stream data, the parameter that holds that data must be the only parameter in the message.</span></span> <span data-ttu-id="b1316-117">Ad esempio, se il messaggio di input è quello da trasmettere, l'operazione deve avere esattamente un parametro di input.</span><span class="sxs-lookup"><span data-stu-id="b1316-117">For example, if the input message is the one to be streamed, the operation must have exactly one input parameter.</span></span> <span data-ttu-id="b1316-118">Allo stesso modo, se deve essere trasmesso il messaggio di output, l'operazione deve avere esattamente un solo parametro di output o un solo valore restituito.</span><span class="sxs-lookup"><span data-stu-id="b1316-118">Similarly, if the output message is to be streamed, the operation must have either exactly one output parameter or a return value.</span></span> <span data-ttu-id="b1316-119">In entrambi i casi, il parametro o il valore restituito devono essere `Stream`, `Message`, o `IXmlSerializable`.</span><span class="sxs-lookup"><span data-stu-id="b1316-119">In either case, the parameter or return value type must be either `Stream`, `Message`, or `IXmlSerializable`.</span></span> <span data-ttu-id="b1316-120">Segue il contratto di servizio utilizzato in questo esempio di flusso.</span><span class="sxs-lookup"><span data-stu-id="b1316-120">The following is the service contract used in this streaming sample.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IStreamingSample  
{  
    [OperationContract]  
    Stream GetStream(string data);  
    [OperationContract]  
    bool UploadStream(Stream stream);  
    [OperationContract]  
    Stream EchoStream(Stream stream);  
    [OperationContract]  
    Stream GetReversedStream();  
  
}  
```  
  
 <span data-ttu-id="b1316-121">L'operazione `GetStream` riceve alcuni dati di input come stringa, memorizzata nel buffer e restituisce un `Stream`, trasmesso.</span><span class="sxs-lookup"><span data-stu-id="b1316-121">The `GetStream` operation receives some input data as a string, which is buffered, and returns a `Stream`, which is streamed.</span></span> <span data-ttu-id="b1316-122">Viceversa, `UploadStream` accetta uno `Stream` (trasmesso) e restituisce un `bool` (memorizzato nel buffer).</span><span class="sxs-lookup"><span data-stu-id="b1316-122">Conversely, `UploadStream` takes in a `Stream` (streamed) and returns a `bool` (buffered).</span></span> <span data-ttu-id="b1316-123">`EchoStream` accetta e restituisce uno `Stream` ed è un esempio di un'operazione i cui messaggi di input e output vengono entrambi trasmessi.</span><span class="sxs-lookup"><span data-stu-id="b1316-123">`EchoStream` takes and returns `Stream` and is an example of an operation whose input and output messages are both streamed.</span></span> <span data-ttu-id="b1316-124">Infine, `GetReversedStream` non prende input e restituisce un `Stream` (trasmesso).</span><span class="sxs-lookup"><span data-stu-id="b1316-124">Finally, `GetReversedStream` takes no inputs and returns a `Stream` (streamed).</span></span>  
  
## <a name="enabling-streamed-transfers"></a><span data-ttu-id="b1316-125">Attivazione dei trasferimenti con flusso</span><span class="sxs-lookup"><span data-stu-id="b1316-125">Enabling Streamed Transfers</span></span>  
 <span data-ttu-id="b1316-126">La definizione di contratti dell'operazione, come descritto precedentemente, fornisce la trasmissione a livello del modello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="b1316-126">Defining operation contracts as previously described provides streaming at the programming model level.</span></span> <span data-ttu-id="b1316-127">Se ci si ferma a questo punto, il trasporto memorizza ancora nel buffer l'intero contenuto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b1316-127">If you stop there, the transport still buffers the entire message content.</span></span> <span data-ttu-id="b1316-128">Per abilitare il flusso di trasmissione, selezionare la modalità di trasferimento dall'elemento di associazione del trasporto.</span><span class="sxs-lookup"><span data-stu-id="b1316-128">To enable transport streaming, select a transfer mode on the binding element of the transport.</span></span> <span data-ttu-id="b1316-129">L'elemento di associazione presenta una proprietà `TransferMode` che può essere impostata su `Buffered`, `Streamed`, `StreamedRequest` o `StreamedResponse`.</span><span class="sxs-lookup"><span data-stu-id="b1316-129">The binding element has a `TransferMode` property that can be set to `Buffered`, `Streamed`, `StreamedRequest`, or `StreamedResponse`.</span></span> <span data-ttu-id="b1316-130">L'impostazione della modalità di trasferimento su `Streamed` consente di attivare la comunicazione con flusso bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="b1316-130">Setting the transfer mode to `Streamed` enables streaming communication in both directions.</span></span> <span data-ttu-id="b1316-131">L'impostazione della modalità di trasferimento su `StreamedRequest` o `StreamedResponse` consente di attivare la comunicazione con flusso soltanto come richiesta o come risposta.</span><span class="sxs-lookup"><span data-stu-id="b1316-131">Setting the transfer mode to `StreamedRequest` or `StreamedResponse` enables streaming communication in only the request or response, respectively.</span></span>  
  
 <span data-ttu-id="b1316-132">`basicHttpBinding` espone la proprietà `TransferMode` sull'associazione come fanno anche `NetTcpBinding` e `NetNamedPipeBinding`.</span><span class="sxs-lookup"><span data-stu-id="b1316-132">The `basicHttpBinding` exposes the `TransferMode` property on the binding as does `NetTcpBinding` and `NetNamedPipeBinding`.</span></span> <span data-ttu-id="b1316-133">Per impostare la modalità di trasferimento degli altri trasporti è necessario creare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b1316-133">For other transports, you must create a custom binding to set the transfer mode.</span></span>  
  
 <span data-ttu-id="b1316-134">Il codice di configurazione seguente, preso dall'esempio illustra l'impostazione della proprietà `TransferMode` su trasmissione su `basicHttpBinding` e un'associazione HTTP personalizzata:</span><span class="sxs-lookup"><span data-stu-id="b1316-134">The following configuration code from the sample shows setting the `TransferMode` property to streaming on the `basicHttpBinding` and a custom HTTP binding:</span></span>  
  
```xml  
<!-- An example basicHttpBinding using streaming. -->  
<basicHttpBinding>  
  <binding name="HttpStreaming" maxReceivedMessageSize="67108864"  
           transferMode="Streamed"/>  
</basicHttpBinding>  
<!-- An example customBinding using HTTP and streaming.-->  
<customBinding>  
  <binding name="Soap12">  
    <textMessageEncoding messageVersion="Soap12WSAddressing10" />  
    <httpTransport transferMode="Streamed"  
                   maxReceivedMessageSize="67108864"/>  
  </binding>  
</customBinding>  
```  
  
 <span data-ttu-id="b1316-135">Oltre a impostare `transferMode` su `Streamed`, il codice di configurazione precedente imposta `maxReceivedMessageSize` su 64 MB.</span><span class="sxs-lookup"><span data-stu-id="b1316-135">In addition to setting the `transferMode` to `Streamed`, the previous configuration code sets the `maxReceivedMessageSize` to 64MB.</span></span> <span data-ttu-id="b1316-136">Analogo a un meccanismo di difesa, `maxReceivedMessageSize` pone un limite alla dimensione massima consentita dei messaggi in ricezione.</span><span class="sxs-lookup"><span data-stu-id="b1316-136">As a defense mechanism, `maxReceivedMessageSize` places a cap on the maximum allowable size of messages on receive.</span></span> <span data-ttu-id="b1316-137">La misura predefinita è `maxReceivedMessageSize` 64 KB che è di solito troppo bassa per gli scenari di flusso.</span><span class="sxs-lookup"><span data-stu-id="b1316-137">The default `maxReceivedMessageSize` is 64 KB, which is usually too low for streaming scenarios.</span></span>  
  
## <a name="processing-data-as-it-is-streamed"></a><span data-ttu-id="b1316-138">Elaborazione dei dati durante la trasmissione</span><span class="sxs-lookup"><span data-stu-id="b1316-138">Processing Data As It Is Streamed</span></span>  
 <span data-ttu-id="b1316-139">Le operazioni `GetStream`, `UploadStream` e `EchoStream` riguardano entrambe l'invio diretto di dati da un file o il salvataggio diretto dei dati ricevuti in un file.</span><span class="sxs-lookup"><span data-stu-id="b1316-139">The operations `GetStream`, `UploadStream` and `EchoStream` all deal with sending data directly from a file or saving received data directly to a file.</span></span> <span data-ttu-id="b1316-140">C'è tuttavia, in alcuni casi, un requisito per inviare o ricevere grandi quantità di dati ed eseguire alcune elaborazioni su blocchi di dati appena essi vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="b1316-140">However in some cases, there is a requirement to send or receive large amounts of data and perform some processing on chunks of the data as it is being sent or received.</span></span> <span data-ttu-id="b1316-141">Una modalità per indirizzare tali scenari è scrivere un flusso personalizzato (una classe che deriva da <xref:System.IO.Stream>) che elabora i dati mentre vengono letti o scritti.</span><span class="sxs-lookup"><span data-stu-id="b1316-141">One way to address such scenarios is to write a custom stream (a class that derives from <xref:System.IO.Stream>) that processes data as it is read or written.</span></span> <span data-ttu-id="b1316-142">Ne sono un esempio l'operazione `GetReversedStream` e la classe `ReverseStream`.</span><span class="sxs-lookup"><span data-stu-id="b1316-142">The `GetReversedStream` operation and `ReverseStream` class are an example of this.</span></span>  
  
 <span data-ttu-id="b1316-143">`GetReversedStream` crea e restituisce una nuova istanza di `ReverseStream`.</span><span class="sxs-lookup"><span data-stu-id="b1316-143">`GetReversedStream` creates and returns a new instance of `ReverseStream`.</span></span> <span data-ttu-id="b1316-144">L'elaborazione effettiva si verifica quando il sistema legge da quell'oggetto `ReverseStream`.</span><span class="sxs-lookup"><span data-stu-id="b1316-144">The actual processing happens as the system reads from that `ReverseStream` object.</span></span> <span data-ttu-id="b1316-145">L'implementazione `ReverseStream.Read` legge un blocco di byte dal file sottostante, li inverte, quindi restituisce i byte invertiti.</span><span class="sxs-lookup"><span data-stu-id="b1316-145">The `ReverseStream.Read` implementation reads a chunk of bytes from the underlying file, reverses them, then returns the reversed bytes.</span></span> <span data-ttu-id="b1316-146">Non inverte il contenuto del file intero; inverte uno blocco di byte alla volta.</span><span class="sxs-lookup"><span data-stu-id="b1316-146">This does not reverse the entire file content; it reverses one chunk of bytes at a time.</span></span> <span data-ttu-id="b1316-147">Questo è un esempio per mostrare come è possibile eseguire elaborazione del flusso mentre il contenuto viene letto o scritto da e verso il flusso.</span><span class="sxs-lookup"><span data-stu-id="b1316-147">This is an example to show how you can perform stream processing as the content is being read or written from and to the stream.</span></span>  
  
```csharp
class ReverseStream : Stream  
{  
  
    FileStream inStream;  
    internal ReverseStream(string filePath)  
    {  
        //Opens the file and places a StreamReader around it.  
        inStream = File.OpenRead(filePath);  
    }  
  
    // Other methods removed for brevity.  
  
    public override int Read(byte[] buffer, int offset, int count)  
    {  
        int countRead=inStream.Read(buffer, offset,count);  
        ReverseBuffer(buffer, offset, countRead);  
        return countRead;  
    }  
  
    public override void Close()  
    {  
        inStream.Close();  
        base.Close();  
    }  
    protected override void Dispose(bool disposing)  
    {  
        inStream.Dispose();  
        base.Dispose(disposing);  
    }  
    void ReverseBuffer(byte[] buffer, int offset, int count)  
    {  
        int i, j;  
        for (i = offset, j = offset + count - 1; i < j; i++, j--)  
        {  
            byte currenti = buffer[i];  
            buffer[i] = buffer[j];  
            buffer[j] = currenti;  
        }  
  
    }  
}  
```  
  
## <a name="running-the-sample"></a><span data-ttu-id="b1316-148">Esecuzione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="b1316-148">Running the Sample</span></span>  
 <span data-ttu-id="b1316-149">Per eseguire l'esempio, prima compilare il servizio e il client seguendo le istruzioni alla fine di questo documento.</span><span class="sxs-lookup"><span data-stu-id="b1316-149">To run the sample, first build both the service and the client by following the directions at the end of this document.</span></span> <span data-ttu-id="b1316-150">Quindi avviare il servizio e il client in due finestre della console diverse.</span><span class="sxs-lookup"><span data-stu-id="b1316-150">Then start the service and the client in two different console windows.</span></span> <span data-ttu-id="b1316-151">Quando il client si avvia, aspetta la pressione del tasto INVIO quando il servizio è pronto.</span><span class="sxs-lookup"><span data-stu-id="b1316-151">When the client starts, it waits for you to press ENTER when the service is ready.</span></span> <span data-ttu-id="b1316-152">Il client chiama quindi prima i metodi `GetStream()`, `UploadStream()` e `GetReversedStream()` su HTTP e quindi su TCP.</span><span class="sxs-lookup"><span data-stu-id="b1316-152">The client then calls the methods `GetStream()`, `UploadStream()` and `GetReversedStream()` first over HTTP and then over TCP.</span></span> <span data-ttu-id="b1316-153">Ecco un esempio di output restituito dal servizio seguito da un esempio di output del client:</span><span class="sxs-lookup"><span data-stu-id="b1316-153">Here is an example output from the service followed by example output from the client:</span></span>  
  
 <span data-ttu-id="b1316-154">Output del servizio:</span><span class="sxs-lookup"><span data-stu-id="b1316-154">Service Output:</span></span>  
  
```console  
The streaming service is ready.  
Press <ENTER> to terminate service.  
  
Saving to file D:\...\uploadedfile  
......................  
File D:\...\uploadedfile saved  
Saving to file D:\...\uploadedfile  
...............  
File D:\...\uploadedfile saved  
```  
  
 <span data-ttu-id="b1316-155">Output del client:</span><span class="sxs-lookup"><span data-stu-id="b1316-155">Client Output:</span></span>  
  
```console  
Press <ENTER> when service is ready  
------ Using HTTP ------
Calling GetStream()  
Saving to file D:\...\clientfile  
......................  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
Calling UploadStream()  
Calling GetReversedStream()  
Saving to file D:\...\clientfile  
......................  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
------ Using Custom HTTP ------  
Calling GetStream()  
Saving to file D:\...\clientfile  
...............  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
Calling UploadStream()  
Calling GetReversedStream()  
Saving to file D:\...\clientfile  
...............  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b1316-156">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b1316-156">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b1316-157">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b1316-157">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="b1316-158">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b1316-158">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="b1316-159">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b1316-159">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1316-160">Se si usa Svcutil.exe per rigenerare la configurazione di questo esempio, assicurarsi di modificare il nome dell'endpoint nella configurazione client in modo che corrisponda al codice client.</span><span class="sxs-lookup"><span data-stu-id="b1316-160">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b1316-161">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="b1316-161">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b1316-162">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="b1316-162">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="b1316-163">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="b1316-163">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b1316-164">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="b1316-164">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Stream`  

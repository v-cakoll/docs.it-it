---
title: 'Codificatore di messaggi personalizzati: Codificatore di compressione'
ms.date: 03/30/2017
ms.assetid: 57450b6c-89fe-4b8a-8376-3d794857bfd7
ms.openlocfilehash: db20ec20579d6fcb0ec202920db0d7781b0676df
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600620"
---
# <a name="custom-message-encoder-compression-encoder"></a><span data-ttu-id="79d05-102">Codificatore di messaggi personalizzati: Codificatore di compressione</span><span class="sxs-lookup"><span data-stu-id="79d05-102">Custom Message Encoder: Compression Encoder</span></span>

<span data-ttu-id="79d05-103">In questo esempio viene illustrato come implementare un codificatore personalizzato utilizzando la piattaforma Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="79d05-103">This sample demonstrates how to implement a custom encoder using the Windows Communication Foundation (WCF) platform.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79d05-104">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="79d05-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="79d05-105">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="79d05-105">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="79d05-106">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="79d05-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="79d05-107">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="79d05-107">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Compression`

## <a name="sample-details"></a><span data-ttu-id="79d05-108">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="79d05-108">Sample Details</span></span>

<span data-ttu-id="79d05-109">Questo esempio è costituito da un programma di console client (con estensione exe), da un programma di console del servizio ospitato (exe) e da una libreria di codificatori di messaggi di compressione (dll).</span><span class="sxs-lookup"><span data-stu-id="79d05-109">This sample consists of a client console program (.exe), a self-hosted service console program (.exe) and a compression message encoder library (.dll).</span></span> <span data-ttu-id="79d05-110">Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="79d05-110">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="79d05-111">Il contratto viene definito dall'interfaccia `ISampleServer` che espone operazioni di ripetizione di stringhe di base (`Echo` e `BigEcho`).</span><span class="sxs-lookup"><span data-stu-id="79d05-111">The contract is defined by the `ISampleServer` interface, which exposes basic string echoing operations (`Echo` and `BigEcho`).</span></span> <span data-ttu-id="79d05-112">Il client esegue richieste sincrone a un'operazione specificata e il servizio risponde ripetendo il messaggio al client.</span><span class="sxs-lookup"><span data-stu-id="79d05-112">The client makes synchronous requests to a given operation and the service replies by repeating the message back to the client.</span></span> <span data-ttu-id="79d05-113">L'attività del client e del servizio è visibile nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="79d05-113">Client and service activity is visible in the console windows.</span></span> <span data-ttu-id="79d05-114">Lo scopo di questo esempio è illustrare come scrivere un codificatore personalizzato e dimostrare l'impatto della compressione di un messaggio sulla rete.</span><span class="sxs-lookup"><span data-stu-id="79d05-114">The intent of this sample is to show how to write a custom encoder and demonstrate the impact of compression of a message on the wire.</span></span> <span data-ttu-id="79d05-115">È possibile aggiungere strumenti al codificatore di messaggi di compressione per calcolare la dimensione del messaggio, il tempo di elaborazione o entrambi.</span><span class="sxs-lookup"><span data-stu-id="79d05-115">You can add instrumentation to the compression message encoder to calculate message size, processing time, or both.</span></span>

> [!NOTE]
> <span data-ttu-id="79d05-116">In .NET Framework 4, la decompressione automatica è stata abilitata su un client WCF se il server invia una risposta compressa (creata con un algoritmo quale GZip o Deflate).</span><span class="sxs-lookup"><span data-stu-id="79d05-116">In the .NET Framework 4, automatic decompression has been enabled on a WCF client if the server is sending a compressed response (created with an algorithm such as GZip or Deflate).</span></span> <span data-ttu-id="79d05-117">Se il servizio è ospitato su Web in Internet Information Server (IIS), IIS è in grado di essere configurato per il servizio per inviare una risposta compressa.</span><span class="sxs-lookup"><span data-stu-id="79d05-117">If the service is Web-hosted in Internet Information Server (IIS), then IIS can be configured for the service to send a compressed response.</span></span> <span data-ttu-id="79d05-118">Questo esempio può essere utilizzato se il requisito è effettuare compressione e decompressione sia nel client che nel servizio o se il servizio è indipendente.</span><span class="sxs-lookup"><span data-stu-id="79d05-118">This sample can be used if the requirement is to do compression and decompression on both the client and the service or if the service is self-hosted.</span></span>

<span data-ttu-id="79d05-119">Nell'esempio viene illustrato come compilare e integrare un codificatore di messaggi personalizzato in un'applicazione WCF.</span><span class="sxs-lookup"><span data-stu-id="79d05-119">The sample demonstrates how to build and integrate a custom message encoder into a WCF application.</span></span> <span data-ttu-id="79d05-120">La libreria GZipEncoder.dll viene distribuita con il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="79d05-120">The library GZipEncoder.dll is deployed with both the client and the service.</span></span> <span data-ttu-id="79d05-121">In questo esempio viene inoltre illustrato l'impatto della compressione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="79d05-121">This sample also demonstrates the impact of compressing messages.</span></span> <span data-ttu-id="79d05-122">Il codice in GZipEncoder.dll dimostra le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="79d05-122">The code in GZipEncoder.dll demonstrates the following:</span></span>

- <span data-ttu-id="79d05-123">Compilazione di un codificatore personalizzato e di una factory del codificatore.</span><span class="sxs-lookup"><span data-stu-id="79d05-123">Building a custom encoder and encoder factory.</span></span>

- <span data-ttu-id="79d05-124">Sviluppo di un elemento di associazione per un codificatore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="79d05-124">Developing a binding element for a custom encoder.</span></span>

- <span data-ttu-id="79d05-125">Utilizzo della configurazione dell'associazione personalizzata per l'integrazione di elementi di associazione personalizzati.</span><span class="sxs-lookup"><span data-stu-id="79d05-125">Using the custom binding configuration for integrating custom binding elements.</span></span>

- <span data-ttu-id="79d05-126">Sviluppo di un gestore di configurazione personalizzato per consentire la configurazione del file di un elemento di associazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="79d05-126">Developing a custom configuration handler to allow file configuration of a custom binding element.</span></span>

<span data-ttu-id="79d05-127">Come indicato in precedenza, in un codificatore personalizzato vengono implementati molti livelli.</span><span class="sxs-lookup"><span data-stu-id="79d05-127">As indicated previously, there are several layers that are implemented in a custom encoder.</span></span> <span data-ttu-id="79d05-128">Per illustrare meglio la relazione tra i singoli livelli, nell'elenco seguente è fornito un ordine semplificato di eventi per l'avvio del servizio:</span><span class="sxs-lookup"><span data-stu-id="79d05-128">To better illustrate the relationship between each of these layers, a simplified order of events for service start-up is in the following list:</span></span>

1. <span data-ttu-id="79d05-129">Il server viene avviato.</span><span class="sxs-lookup"><span data-stu-id="79d05-129">The server starts.</span></span>

2. <span data-ttu-id="79d05-130">Le informazioni di configurazione vengono lette.</span><span class="sxs-lookup"><span data-stu-id="79d05-130">The configuration information is read.</span></span>

    1. <span data-ttu-id="79d05-131">La configurazione del servizio registra il gestore di configurazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="79d05-131">The service configuration registers the custom configuration handler.</span></span>

    2. <span data-ttu-id="79d05-132">L'host del servizio viene creato e aperto.</span><span class="sxs-lookup"><span data-stu-id="79d05-132">The service host is created and opened.</span></span>

    3. <span data-ttu-id="79d05-133">L'elemento di configurazione personalizzato crea e restituisce l'elemento di associazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="79d05-133">The custom configuration element creates and returns the custom binding element.</span></span>

    4. <span data-ttu-id="79d05-134">L'elemento di associazione personalizzato crea e restituisce una factory del codificatore di messaggi.</span><span class="sxs-lookup"><span data-stu-id="79d05-134">The custom binding element creates and returns a message encoder factory.</span></span>

3. <span data-ttu-id="79d05-135">Un messaggio viene ricevuto.</span><span class="sxs-lookup"><span data-stu-id="79d05-135">A message is received.</span></span>

4. <span data-ttu-id="79d05-136">La factory del codificatore di messaggi restituisce un codificatore di messaggi per la lettura del messaggio e la scrittura della risposta.</span><span class="sxs-lookup"><span data-stu-id="79d05-136">The message encoder factory returns a message encoder for reading in the message and writing out the response.</span></span>

5. <span data-ttu-id="79d05-137">Il livello del codificatore viene implementato come una class factory.</span><span class="sxs-lookup"><span data-stu-id="79d05-137">The encoder layer is implemented as a class factory.</span></span> <span data-ttu-id="79d05-138">Solo la class factory del codificatore deve essere esposta pubblicamente per il codificatore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="79d05-138">Only the encoder class factory must be publicly exposed for the custom encoder.</span></span> <span data-ttu-id="79d05-139">L'oggetto della factory viene restituito dall'elemento di associazione quando viene creato l'oggetto <xref:System.ServiceModel.ServiceHost> o <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="79d05-139">The factory object is returned by the binding element when the <xref:System.ServiceModel.ServiceHost> or <xref:System.ServiceModel.ChannelFactory%601> object is created.</span></span> <span data-ttu-id="79d05-140">I codificatori di messaggi possono operare in modalità di memorizzazione nel buffer o di trasmissione.</span><span class="sxs-lookup"><span data-stu-id="79d05-140">Message encoders can operate in a buffered or streaming mode.</span></span> <span data-ttu-id="79d05-141">In questo esempio vengono illustrate entrambe le modalità.</span><span class="sxs-lookup"><span data-stu-id="79d05-141">This sample demonstrates both buffered mode and streaming mode.</span></span>

<span data-ttu-id="79d05-142">A ogni modalità è associato un metodo `ReadMessage` e un metodo `WriteMessage` sulla classe `MessageEncoder` astratta.</span><span class="sxs-lookup"><span data-stu-id="79d05-142">For each mode there is an accompanying `ReadMessage` and `WriteMessage` method on the abstract `MessageEncoder` class.</span></span> <span data-ttu-id="79d05-143">La maggior parte del lavoro di codifica si verifica in questi metodi.</span><span class="sxs-lookup"><span data-stu-id="79d05-143">A majority of the encoding work takes place in these methods.</span></span> <span data-ttu-id="79d05-144">Nell'esempio viene eseguito il wrapping dei codificatori di testo e di messaggi binari esistenti.</span><span class="sxs-lookup"><span data-stu-id="79d05-144">The sample wraps the existing text and binary message encoders.</span></span> <span data-ttu-id="79d05-145">In questo modo l'esempio può delegare la lettura e la scrittura della rappresentazione in rete dei messaggi al codificatore interno e il codificatore di compressione può comprimere o decomprimere i risultati.</span><span class="sxs-lookup"><span data-stu-id="79d05-145">This allows the sample to delegate the reading and writing of the wire representation of messages to the inner encoder and allows the compression encoder to compress or decompress the results.</span></span> <span data-ttu-id="79d05-146">Poiché non esiste alcuna pipeline per la codifica dei messaggi, questo è l'unico modello per l'utilizzo di più codificatori in WCF.</span><span class="sxs-lookup"><span data-stu-id="79d05-146">Because there is no pipeline for message encoding, this is the only model for using multiple encoders in WCF.</span></span> <span data-ttu-id="79d05-147">Quando il messaggio è stato decompresso, il messaggio risultante viene passato sullo stack affinché venga gestito dallo stack di canali.</span><span class="sxs-lookup"><span data-stu-id="79d05-147">Once the message has been decompressed, the resulting message is passed up the stack for the channel stack to handle.</span></span> <span data-ttu-id="79d05-148">Durante la compressione, il messaggio compresso risultante viene scritto direttamente nel flusso fornito.</span><span class="sxs-lookup"><span data-stu-id="79d05-148">During compression, the resulting compressed message is written directly to the stream provided.</span></span>

<span data-ttu-id="79d05-149">In questo esempio vengono utilizzati metodi helper (`CompressBuffer` e `DecompressBuffer`) per eseguire la conversione da buffer a flussi allo scopo di utilizzare la classe `GZipStream`.</span><span class="sxs-lookup"><span data-stu-id="79d05-149">This sample uses helper methods (`CompressBuffer` and `DecompressBuffer`) to perform conversion from buffers to streams to use the `GZipStream` class.</span></span>

<span data-ttu-id="79d05-150">Le classi `ReadMessage` e `WriteMessage` memorizzate nel buffer utilizzano la classe `BufferManager`.</span><span class="sxs-lookup"><span data-stu-id="79d05-150">The buffered `ReadMessage` and `WriteMessage` classes make use of the `BufferManager` class.</span></span> <span data-ttu-id="79d05-151">Il codificatore è accessibile solo tramite la factory del codificatore.</span><span class="sxs-lookup"><span data-stu-id="79d05-151">The encoder is accessible only through the encoder factory.</span></span> <span data-ttu-id="79d05-152">La classe `MessageEncoderFactory` astratta fornisce una proprietà denominata `Encoder` per l'accesso al codificatore corrente e un metodo denominato `CreateSessionEncoder` per la creazione di un codificatore che supporta le sessioni.</span><span class="sxs-lookup"><span data-stu-id="79d05-152">The abstract `MessageEncoderFactory` class provides a property named `Encoder` for accessing the current encoder and a method named `CreateSessionEncoder` for creating an encoder that supports sessions.</span></span> <span data-ttu-id="79d05-153">Tale codificatore può essere utilizzato nello scenario in cui il canale supporta le sessioni, è ordinato e affidabile.</span><span class="sxs-lookup"><span data-stu-id="79d05-153">Such an encoder can be used in the scenario where the channel supports sessions, is ordered and is reliable.</span></span> <span data-ttu-id="79d05-154">Questo scenario consente l'ottimizzazione in ogni sessione dei dati scritti in rete.</span><span class="sxs-lookup"><span data-stu-id="79d05-154">This scenario allows for optimization in each session of the data written to the wire.</span></span> <span data-ttu-id="79d05-155">Se non si desidera questo aspetto, non deve essere eseguito l'overload del metodo di base.</span><span class="sxs-lookup"><span data-stu-id="79d05-155">If this is not desired, the base method should not be overloaded.</span></span> <span data-ttu-id="79d05-156">La proprietà `Encoder` fornisce un meccanismo di accesso al codificatore senza sessione e l'implementazione predefinita del metodo `CreateSessionEncoder` restituisce il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="79d05-156">The `Encoder` property provides a mechanism for accessing the session-less encoder and the default implementation of the `CreateSessionEncoder` method returns the value of the property.</span></span> <span data-ttu-id="79d05-157">Poiché nell'esempio viene eseguito il wrapping di un codificatore esistente per fornire la compressione, l'implementazione `MessageEncoderFactory` accetta un elemento `MessageEncoderFactory` che rappresenta la factory del codificatore interna.</span><span class="sxs-lookup"><span data-stu-id="79d05-157">Because the sample wraps an existing encoder to provide compression, the `MessageEncoderFactory` implementation accepts a `MessageEncoderFactory` that represents the inner encoder factory.</span></span>

<span data-ttu-id="79d05-158">Ora che il codificatore e la factory del codificatore sono definiti, possono essere usati con un client e un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="79d05-158">Now that the encoder and encoder factory are defined, they can be used with a WCF client and service.</span></span> <span data-ttu-id="79d05-159">Tuttavia, questi codificatori devono essere aggiunti allo stack di canali.</span><span class="sxs-lookup"><span data-stu-id="79d05-159">However, these encoders must be added to the channel stack.</span></span> <span data-ttu-id="79d05-160">È possibile dedurre le classi dalle classi <xref:System.ServiceModel.ServiceHost> e <xref:System.ServiceModel.ChannelFactory%601> ed eseguire l'override dei metodi `OnInitialize` per aggiungere manualmente questa factory del codificatore.</span><span class="sxs-lookup"><span data-stu-id="79d05-160">You can derive classes from the <xref:System.ServiceModel.ServiceHost> and <xref:System.ServiceModel.ChannelFactory%601> classes and override the `OnInitialize` methods to add this encoder factory manually.</span></span> <span data-ttu-id="79d05-161">È inoltre possibile esporre la factory del codificatore tramite un elemento di associazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="79d05-161">You can also expose the encoder factory through a custom binding element.</span></span>

<span data-ttu-id="79d05-162">Per creare un nuovo elemento di associazione personalizzato, derivare una classe dalla classe <xref:System.ServiceModel.Channels.BindingElement>.</span><span class="sxs-lookup"><span data-stu-id="79d05-162">To create a new custom binding element, derive a class from the <xref:System.ServiceModel.Channels.BindingElement> class.</span></span> <span data-ttu-id="79d05-163">Sono tuttavia disponibili molti tipi di elementi di associazione.</span><span class="sxs-lookup"><span data-stu-id="79d05-163">There are, however, several types of binding elements.</span></span> <span data-ttu-id="79d05-164">Per assicurare che l'elemento di associazione personalizzato venga riconosciuto come un elemento di associazione di codifica dei messaggi, è necessario implementare anche <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="79d05-164">To ensure that the custom binding element is recognized as a message encoding binding element, you also must implement the <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.</span></span> <span data-ttu-id="79d05-165"><xref:System.ServiceModel.Channels.MessageEncodingBindingElement> espone un metodo per la creazione di una nuova factory del codificatore di messaggi (`CreateMessageEncoderFactory`), che viene implementato per restituire un'istanza della factory del codificatore di messaggi corrispondente.</span><span class="sxs-lookup"><span data-stu-id="79d05-165">The <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> exposes a method for creating a new message encoder factory (`CreateMessageEncoderFactory`), which is implemented to return an instance of the matching message encoder factory.</span></span> <span data-ttu-id="79d05-166">Inoltre, <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> dispone di una proprietà per indicare la versione Addressing.</span><span class="sxs-lookup"><span data-stu-id="79d05-166">Additionally, the <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> has a property to indicate the addressing version.</span></span> <span data-ttu-id="79d05-167">Poiché in questo esempio viene eseguito il wrapping dei codificatori esistenti, l'implementazione di esempio esegue il wrapping anche degli elementi di associazione del codificatore esistente e accetta un elemento di associazione del codificatore interno come parametro del costruttore e lo espone tramite una proprietà.</span><span class="sxs-lookup"><span data-stu-id="79d05-167">Because this sample wraps the existing encoders, the sample implementation also wraps the existing encoder binding elements and takes an inner encoder binding element as a parameter to the constructor and exposes it through a property.</span></span> <span data-ttu-id="79d05-168">Nell'esempio di codice seguente viene illustrata l'implementazione della classe `GZipMessageEncodingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="79d05-168">The following sample code shows the implementation of the `GZipMessageEncodingBindingElement` class.</span></span>

```csharp
public sealed class GZipMessageEncodingBindingElement
                        : MessageEncodingBindingElement //BindingElement
                        , IPolicyExportExtension
{

    //We use an inner binding element to store information
    //required for the inner encoder.
    MessageEncodingBindingElement innerBindingElement;

        //By default, use the default text encoder as the inner encoder.
        public GZipMessageEncodingBindingElement()
            : this(new TextMessageEncodingBindingElement()) { }

    public GZipMessageEncodingBindingElement(MessageEncodingBindingElement messageEncoderBindingElement)
    {
        this.innerBindingElement = messageEncoderBindingElement;
    }

    public MessageEncodingBindingElement InnerMessageEncodingBindingElement
    {
        get { return innerBindingElement; }
        set { innerBindingElement = value; }
    }

    //Main entry point into the encoder binding element.
    // Called by WCF to get the factory that creates the
    //message encoder.
    public override MessageEncoderFactory CreateMessageEncoderFactory()
    {
        return new
GZipMessageEncoderFactory(innerBindingElement.CreateMessageEncoderFactory());
    }

    public override MessageVersion MessageVersion
    {
        get { return innerBindingElement.MessageVersion; }
        set { innerBindingElement.MessageVersion = value; }
    }

    public override BindingElement Clone()
    {
        return new
        GZipMessageEncodingBindingElement(this.innerBindingElement);
    }

    public override T GetProperty<T>(BindingContext context)
    {
        if (typeof(T) == typeof(XmlDictionaryReaderQuotas))
        {
            return innerBindingElement.GetProperty<T>(context);
        }
        else
        {
            return base.GetProperty<T>(context);
        }
    }

    public override IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)
    {
        if (context == null)
            throw new ArgumentNullException("context");

        context.BindingParameters.Add(this);
        return context.BuildInnerChannelFactory<TChannel>();
    }

    public override IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)
    {
        if (context == null)
            throw new ArgumentNullException("context");

        context.BindingParameters.Add(this);
        return context.BuildInnerChannelListener<TChannel>();
    }

    public override bool CanBuildChannelListener<TChannel>(BindingContext context)
    {
        if (context == null)
            throw new ArgumentNullException("context");

        context.BindingParameters.Add(this);
        return context.CanBuildInnerChannelListener<TChannel>();
    }

    void IPolicyExportExtension.ExportPolicy(MetadataExporter exporter, PolicyConversionContext policyContext)
    {
        if (policyContext == null)
        {
            throw new ArgumentNullException("policyContext");
        }
       XmlDocument document = new XmlDocument();
       policyContext.GetBindingAssertions().Add(document.CreateElement(
            GZipMessageEncodingPolicyConstants.GZipEncodingPrefix,
            GZipMessageEncodingPolicyConstants.GZipEncodingName,
            GZipMessageEncodingPolicyConstants.GZipEncodingNamespace));
    }
}
```

<span data-ttu-id="79d05-169">Si noti che la classe `GZipMessageEncodingBindingElement` implementa l'interfaccia `IPolicyExportExtension`, in modo che questo elemento di associazione può essere esportato come un criterio nei metadati, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="79d05-169">Note that `GZipMessageEncodingBindingElement` class implements the `IPolicyExportExtension` interface, so that this binding element can be exported as a policy in metadata, as shown in the following example.</span></span>

```xml
<wsp:Policy wsu:Id="BufferedHttpSampleServer_ISampleServer_policy">
    <wsp:ExactlyOne>
      <wsp:All>
        <gzip:text xmlns:gzip=
        "http://schemas.microsoft.com/ws/06/2004/mspolicy/netgzip1" />
       <wsaw:UsingAddressing />
     </wsp:All>
   </wsp:ExactlyOne>
</wsp:Policy>
```

<span data-ttu-id="79d05-170">La classe `GZipMessageEncodingBindingElementImporter` implementa l'interfaccia `IPolicyImportExtension` e importa i criteri per `GZipMessageEncodingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="79d05-170">The `GZipMessageEncodingBindingElementImporter` class implements the `IPolicyImportExtension` interface, this class imports policy for `GZipMessageEncodingBindingElement`.</span></span> <span data-ttu-id="79d05-171">Lo strumento Svcutil.exe può essere utilizzato per importare criteri nel file di configurazione e, per gestire `GZipMessageEncodingBindingElement`, è necessario aggiungere quanto segue al file Svcutil.exe.config.</span><span class="sxs-lookup"><span data-stu-id="79d05-171">Svcutil.exe tool can be used to import policies to the configuration file, to handle `GZipMessageEncodingBindingElement`, the following should be added to Svcutil.exe.config.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <extensions>
      <bindingElementExtensions>
        <add name="gzipMessageEncoding"
          type=
            "Microsoft.ServiceModel.Samples.GZipMessageEncodingElement, GZipEncoder, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
      </bindingElementExtensions>
    </extensions>
    <client>
      <metadata>
        <policyImporters>
          <remove type=
"System.ServiceModel.Channels.MessageEncodingBindingElementImporter, System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
          <extension type=
"Microsoft.ServiceModel.Samples.GZipMessageEncodingBindingElementImporter, GZipEncoder, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
        </policyImporters>
      </metadata>
    </client>
  </system.serviceModel>
</configuration>
```

<span data-ttu-id="79d05-172">A questo punto, poiché è disponibile un elemento di associazione corrispondente per il codificatore di compressione, è possibile associarlo a livello di programmazione nel servizio o client costruendo un nuovo oggetto di associazione personalizzato e aggiungendo ad esso l'elemento di associazione personalizzato, come mostrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="79d05-172">Now that there is a matching binding element for the compression encoder, it can be programmatically hooked into the service or client by constructing a new custom binding object and adding the custom binding element to it, as shown in the following sample code.</span></span>

```csharp
ICollection<BindingElement> bindingElements = new List<BindingElement>();
HttpTransportBindingElement httpBindingElement = new HttpTransportBindingElement();
GZipMessageEncodingBindingElement compBindingElement = new GZipMessageEncodingBindingElement ();
bindingElements.Add(compBindingElement);
bindingElements.Add(httpBindingElement);
CustomBinding binding = new CustomBinding(bindingElements);
binding.Name = "SampleBinding";
binding.Namespace = "http://tempuri.org/bindings";
```

<span data-ttu-id="79d05-173">Sebbene questo possa essere sufficiente per la maggioranza degli scenari utente, se un servizio deve essere ospitato sul Web è essenziale che supporti un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="79d05-173">While this may be sufficient for the majority of user scenarios, supporting a file configuration is critical if a service is to be Web-hosted.</span></span> <span data-ttu-id="79d05-174">Per supportare lo scenario ospitato sul Web, è necessario sviluppare un gestore di configurazione personalizzato per consentire a un elemento di associazione personalizzato di essere configurabile in un file.</span><span class="sxs-lookup"><span data-stu-id="79d05-174">To support the Web-hosted scenario, you must develop a custom configuration handler to allow a custom binding element to be configurable in a file.</span></span>

<span data-ttu-id="79d05-175">È possibile compilare un gestore di configurazione per l'elemento di associazione nella parte superiore del sistema di configurazione.</span><span class="sxs-lookup"><span data-stu-id="79d05-175">You can build a configuration handler for the binding element on top of the configuration system.</span></span> <span data-ttu-id="79d05-176">Il gestore di configurazione per l'elemento di associazione deve derivare dalla classe <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>.</span><span class="sxs-lookup"><span data-stu-id="79d05-176">The configuration handler for the binding element must derive from the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> class.</span></span> <span data-ttu-id="79d05-177"><xref:System.ServiceModel.Configuration.BindingElementExtensionElement.BindingElementType?displayProperty=nameWithType>Informa il sistema di configurazione del tipo di elemento di associazione da creare per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="79d05-177">The <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.BindingElementType?displayProperty=nameWithType> informs the configuration system of the type of binding element to create for this section.</span></span> <span data-ttu-id="79d05-178">Tutti gli aspetti di `BindingElement` che possono essere impostati devono essere esposti come proprietà nella classe derivata <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>.</span><span class="sxs-lookup"><span data-stu-id="79d05-178">All aspects of the `BindingElement` that can be set should be exposed as properties in the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> derived class.</span></span> <span data-ttu-id="79d05-179"><xref:System.Configuration.ConfigurationPropertyAttribute>Supporta il mapping degli attributi degli elementi di configurazione alle proprietà e l'impostazione dei valori predefiniti se gli attributi non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="79d05-179">The <xref:System.Configuration.ConfigurationPropertyAttribute> assists in mapping the configuration element attributes to the properties and setting default values if attributes are missing.</span></span> <span data-ttu-id="79d05-180">Dopo aver caricato i valori della configurazione e averli applicati alle proprietà, viene chiamato il metodo <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A?displayProperty=nameWithType> che converte le proprietà in un'istanza concreta di un elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="79d05-180">After the values from configuration are loaded and applied to the properties, the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A?displayProperty=nameWithType> method is called, which converts the properties into a concrete instance of a binding element.</span></span> <span data-ttu-id="79d05-181">Il <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.ApplyConfiguration%2A?displayProperty=nameWithType> metodo viene utilizzato per convertire le proprietà della <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> classe derivata nei valori da impostare sull'elemento di associazione appena creato.</span><span class="sxs-lookup"><span data-stu-id="79d05-181">The <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.ApplyConfiguration%2A?displayProperty=nameWithType> method is used to convert the properties on the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> derived class into the values to be set on the newly created binding element.</span></span>

<span data-ttu-id="79d05-182">Nel codice di esempio seguente viene mostrata l'implementazione di `GZipMessageEncodingElement`.</span><span class="sxs-lookup"><span data-stu-id="79d05-182">The following sample code shows the implementation of the `GZipMessageEncodingElement`.</span></span>

```csharp
public class GZipMessageEncodingElement : BindingElementExtensionElement
{
    public GZipMessageEncodingElement()
    {
    }

//Called by the WCF to discover the type of binding element this
//config section enables
    public override Type BindingElementType
    {
        get { return typeof(GZipMessageEncodingBindingElement); }
    }

    //The only property we need to configure for our binding element is
    //the type of inner encoder to use. Here, we support text and
    //binary.
    [ConfigurationProperty("innerMessageEncoding",
                         DefaultValue = "textMessageEncoding")]
    public string InnerMessageEncoding
    {
        get { return (string)base["innerMessageEncoding"]; }
        set { base["innerMessageEncoding"] = value; }
    }

    //Called by the WCF to apply the configuration settings (the
    //property above) to the binding element
    public override void ApplyConfiguration(BindingElement bindingElement)
    {
        GZipMessageEncodingBindingElement binding =
                (GZipMessageEncodingBindingElement)bindingElement;
        PropertyInformationCollection propertyInfo =
                    this.ElementInformation.Properties;
        if (propertyInfo["innerMessageEncoding"].ValueOrigin !=
                                     PropertyValueOrigin.Default)
        {
            switch (this.InnerMessageEncoding)
            {
                case "textMessageEncoding":
                    binding.InnerMessageEncodingBindingElement =
                      new TextMessageEncodingBindingElement();
                    break;
                case "binaryMessageEncoding":
                    binding.InnerMessageEncodingBindingElement =
                         new BinaryMessageEncodingBindingElement();
                    break;
            }
        }
    }

    //Called by the WCF to create the binding element
    protected override BindingElement CreateBindingElement()
    {
        GZipMessageEncodingBindingElement bindingElement =
                new GZipMessageEncodingBindingElement();
        this.ApplyConfiguration(bindingElement);
        return bindingElement;
    }
}
```

<span data-ttu-id="79d05-183">Questo gestore di configurazione esegue il mapping alla rappresentazione seguente in App.config o Web.config per il servizio o il client.</span><span class="sxs-lookup"><span data-stu-id="79d05-183">This configuration handler maps to the following representation in the App.config or Web.config for the service or client.</span></span>

```xml
<gzipMessageEncoding innerMessageEncoding="textMessageEncoding" />
```

<span data-ttu-id="79d05-184">Per utilizzare questo gestore di configurazione, è necessario registrarlo all'interno dell' [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elemento, come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="79d05-184">To use this configuration handler, it must be registered within the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, as shown in the following sample configuration.</span></span>

```xml
<extensions>
    <bindingElementExtensions>
       <add
           name="gzipMessageEncoding"
           type=
           "Microsoft.ServiceModel.Samples.GZipMessageEncodingElement,
           GZipEncoder, Version=1.0.0.0, Culture=neutral,
           PublicKeyToken=null" />
      </bindingElementExtensions>
</extensions>
```

<span data-ttu-id="79d05-185">Quando si esegue il server, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="79d05-185">When you run the server, the operation requests and responses are displayed in the console window.</span></span> <span data-ttu-id="79d05-186">Premere INVIO nella finestra per arrestare il server.</span><span class="sxs-lookup"><span data-stu-id="79d05-186">Press ENTER in the window to shut down the server.</span></span>

```console
Press Enter key to Exit.

        Server Echo(string input) called:
        Client message: Simple hello

        Server BigEcho(string[] input) called:
        64 client messages
```

<span data-ttu-id="79d05-187">Quando si esegue il client, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="79d05-187">When you run the client, the operation requests and responses are displayed in the console window.</span></span> <span data-ttu-id="79d05-188">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="79d05-188">Press ENTER in the client window to shut down the client.</span></span>

```console
Calling Echo(string):
Server responds: Simple hello Simple hello

Calling BigEcho(string[]):
Server responds: Hello 0

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="79d05-189">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="79d05-189">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="79d05-190">Installare ASP.NET 4,0 usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="79d05-190">Install ASP.NET 4.0 using the following command:</span></span>

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. <span data-ttu-id="79d05-191">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="79d05-191">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

3. <span data-ttu-id="79d05-192">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="79d05-192">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="79d05-193">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="79d05-193">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79d05-194">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="79d05-194">The samples may already be installed on your machine.</span></span> <span data-ttu-id="79d05-195">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="79d05-195">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="79d05-196">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="79d05-196">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="79d05-197">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="79d05-197">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Compression`

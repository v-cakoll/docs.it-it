---
title: HttpCookieSession
ms.date: 03/30/2017
ms.assetid: 101cb624-8303-448a-a3af-933247c1e109
ms.openlocfilehash: 8dba147ace7ada221b5d274cd233e4b9618835d9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585130"
---
# <a name="httpcookiesession"></a><span data-ttu-id="2a838-102">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="2a838-102">HttpCookieSession</span></span>
<span data-ttu-id="2a838-103">In questo esempio viene illustrato come compilare un canale di protocollo personalizzato per utilizzare cookie HTTP per la gestione della sessione.</span><span class="sxs-lookup"><span data-stu-id="2a838-103">This sample demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span> <span data-ttu-id="2a838-104">Questo canale consente la comunicazione tra i servizi Windows Communication Foundation (WCF) e i client ASMX o tra i client WCF e i servizi ASMX.</span><span class="sxs-lookup"><span data-stu-id="2a838-104">This channel enables communication between Windows Communication Foundation (WCF) services and ASMX clients or between WCF clients and ASMX services.</span></span>  
  
 <span data-ttu-id="2a838-105">Quando un client chiama un metodo Web in un servizio Web ASMX basato sulla sessione, il motore ASP.NET esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a838-105">When a client calls a Web method in an ASMX Web service that is session-based, the ASP.NET engine does the following:</span></span>  
  
- <span data-ttu-id="2a838-106">Genera un ID univoco (ID sessione).</span><span class="sxs-lookup"><span data-stu-id="2a838-106">Generates a unique ID (session ID).</span></span>  
  
- <span data-ttu-id="2a838-107">Genera l'oggetto sessione e lo associa all'ID univoco.</span><span class="sxs-lookup"><span data-stu-id="2a838-107">Generates the session object and associates it with the unique ID.</span></span>  
  
- <span data-ttu-id="2a838-108">Aggiunge l'ID univoco a un'intestazione della risposta HTTP Set-Cookie e la invia al client.</span><span class="sxs-lookup"><span data-stu-id="2a838-108">Adds the unique ID to a Set-Cookie HTTP response header and sends it to the client.</span></span>  
  
- <span data-ttu-id="2a838-109">Identifica il client su chiamate successive in base all'ID di sessione inviato.</span><span class="sxs-lookup"><span data-stu-id="2a838-109">Identifies the client on subsequent calls based on the session ID it sends to it.</span></span>  
  
 <span data-ttu-id="2a838-110">Il client include questo ID di sessione nelle richieste successive al server.</span><span class="sxs-lookup"><span data-stu-id="2a838-110">The client includes this session ID in its subsequent requests to the server.</span></span> <span data-ttu-id="2a838-111">Il server utilizza l'ID di sessione dal client per caricare l'oggetto sessione appropriato per il contesto HTTP corrente.</span><span class="sxs-lookup"><span data-stu-id="2a838-111">The server uses the session ID from the client to load the appropriate session object for the current HTTP context.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2a838-112">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2a838-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2a838-113">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="2a838-113">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="2a838-114">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="2a838-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2a838-115">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="2a838-115">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpCookieSession`  
  
## <a name="httpcookiesession-channel-message-exchange-pattern"></a><span data-ttu-id="2a838-116">Modello di scambio messaggi sul canale HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="2a838-116">HttpCookieSession Channel Message Exchange Pattern</span></span>  
 <span data-ttu-id="2a838-117">In questo esempio vengono abilitate sessioni per gli scenari simili ad ASMX.</span><span class="sxs-lookup"><span data-stu-id="2a838-117">This sample enables sessions for ASMX-like scenarios.</span></span> <span data-ttu-id="2a838-118">Nella parte inferiore dello stack dei canali, è presente il trasporto HTTP che supporta <xref:System.ServiceModel.Channels.IRequestChannel> e <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="2a838-118">At the bottom of our channel stack, we have the HTTP transport that supports <xref:System.ServiceModel.Channels.IRequestChannel> and <xref:System.ServiceModel.Channels.IReplyChannel>.</span></span> <span data-ttu-id="2a838-119">È il processo del canale a fornire le sessioni ai livelli più elevati dello stack dei canali.</span><span class="sxs-lookup"><span data-stu-id="2a838-119">It is the job of the channel to provide sessions to the higher levels of the channel stack.</span></span> <span data-ttu-id="2a838-120">L'esempio implementa due canali (<xref:System.ServiceModel.Channels.IRequestSessionChannel> e <xref:System.ServiceModel.Channels.IReplySessionChannel>) che supportano le sessioni.</span><span class="sxs-lookup"><span data-stu-id="2a838-120">The sample implements two channels, (<xref:System.ServiceModel.Channels.IRequestSessionChannel> and <xref:System.ServiceModel.Channels.IReplySessionChannel>) that support sessions.</span></span>  
  
## <a name="service-channel"></a><span data-ttu-id="2a838-121">Canale del servizio</span><span class="sxs-lookup"><span data-stu-id="2a838-121">Service Channel</span></span>  
 <span data-ttu-id="2a838-122">Nell'esempio viene fornito un canale del servizio nella classe `HttpCookieReplySessionChannelListener`.</span><span class="sxs-lookup"><span data-stu-id="2a838-122">The sample provides a service channel in the `HttpCookieReplySessionChannelListener` class.</span></span> <span data-ttu-id="2a838-123">Questa classe implementa l'interfaccia <xref:System.ServiceModel.Channels.IChannelListener> e converte il canale <xref:System.ServiceModel.Channels.IReplyChannel> da una posizione inferiore nello stack dei canali a un'interfaccia <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span><span class="sxs-lookup"><span data-stu-id="2a838-123">This class implements the <xref:System.ServiceModel.Channels.IChannelListener> interface and converts the <xref:System.ServiceModel.Channels.IReplyChannel> channel from lower in the channel stack to a <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span></span> <span data-ttu-id="2a838-124">Questo processo può essere suddiviso nelle parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a838-124">This process can be divided into the following parts:</span></span>  
  
- <span data-ttu-id="2a838-125">Quando il listener del canale è aperto, accetta un canale interno dal listener interno.</span><span class="sxs-lookup"><span data-stu-id="2a838-125">When the channel listener is opened, it accepts an inner channel from its inner listener.</span></span> <span data-ttu-id="2a838-126">Poiché il listener interno è un listener del datagramma e la durata di un canale accettato è separata dalla durata del listener, è possibile chiudere il listener interno e utilizzare solo il canale interno</span><span class="sxs-lookup"><span data-stu-id="2a838-126">Because the inner listener is a datagram listener and the lifetime of an accepted channel is decoupled from the lifetime of the listener, we can close the inner listener and only hold on to the inner channel</span></span>  
  
    ```csharp  
                this.innerChannelListener.Open(timeoutHelper.RemainingTime());  
    this.innerChannel = this.innerChannelListener.AcceptChannel(timeoutHelper.RemainingTime());  
    this.innerChannel.Open(timeoutHelper.RemainingTime());  
    this.innerChannelListener.Close(timeoutHelper.RemainingTime());  
    ```  
  
- <span data-ttu-id="2a838-127">Quando il processo aperto viene completato, si imposta un ciclo di messaggi per ricevere messaggi dal canale interno.</span><span class="sxs-lookup"><span data-stu-id="2a838-127">When the open process completes, we set up a message loop to receive messages from the inner channel.</span></span>  
  
    ```csharp  
    IAsyncResult result = BeginInnerReceiveRequest();  
    if (result != null && result.CompletedSynchronously)  
    {  
       // do not block the user thread  
       this.completeReceiveCallback ??= new WaitCallback(CompleteReceiveCallback);
       ThreadPool.QueueUserWorkItem(this.completeReceiveCallback, result);  
    }  
    ```  
  
- <span data-ttu-id="2a838-128">Quando arriva un messaggio, il canale del servizio esamina l'identificatore di sessione ed esegue il demultiplexing al canale della sessione appropriato.</span><span class="sxs-lookup"><span data-stu-id="2a838-128">When a message arrives, the service channel examines the session identifier and de-multiplexes to the appropriate session channel.</span></span> <span data-ttu-id="2a838-129">Il listener del canale gestisce un dizionario che esegue il mapping degli identificatori di sessione alle istanze del canale della sessione.</span><span class="sxs-lookup"><span data-stu-id="2a838-129">The channel listener maintains a dictionary that maps the session identifiers to the session channel instances.</span></span>  
  
    ```csharp  
    Dictionary<string, IReplySessionChannel> channelMapping;  
    ```  
  
 <span data-ttu-id="2a838-130">La `HttpCookieReplySessionChannel` classe implementa <xref:System.ServiceModel.Channels.IReplySessionChannel> .</span><span class="sxs-lookup"><span data-stu-id="2a838-130">The `HttpCookieReplySessionChannel` class implements <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span></span> <span data-ttu-id="2a838-131">I livelli più elevati dello stack dei canali chiamano il metodo <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> per leggere le richieste per la sessione.</span><span class="sxs-lookup"><span data-stu-id="2a838-131">Higher levels of the channel stack call the <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> method to read requests for this session.</span></span> <span data-ttu-id="2a838-132">Ogni canale della sessione ha una coda di messaggi privata in cui vengono inseriti messaggi dal canale del servizio.</span><span class="sxs-lookup"><span data-stu-id="2a838-132">Each session channel has a private message queue that is populated by the service channel.</span></span>  
  
```csharp  
InputQueue<RequestContext> requestQueue;  
```  
  
 <span data-ttu-id="2a838-133">Se qualcuno chiama il metodo <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> e non sono presenti messaggi nella coda di messaggi, il canale attende per un determinato periodo di tempo prima di spegnersi.</span><span class="sxs-lookup"><span data-stu-id="2a838-133">In the case when someone calls the <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> method and there are no messages in the message queue, the channel waits for a specified amount of time before shutting itself down.</span></span> <span data-ttu-id="2a838-134">Questa operazione consente di pulire i canali della sessione creati per i client non WCF.</span><span class="sxs-lookup"><span data-stu-id="2a838-134">This cleans up the session channels created for non-WCF clients.</span></span>  
  
 <span data-ttu-id="2a838-135">Si utilizza `channelMapping` per tenere traccia di `ReplySessionChannels` e non si chiude il `innerChannel` sottostante fino a quando tutti i canali accettati non sono stati chiusi.</span><span class="sxs-lookup"><span data-stu-id="2a838-135">We use the `channelMapping` to track the `ReplySessionChannels`, and we do not close our underlying `innerChannel` until all the accepted channels have been closed.</span></span> <span data-ttu-id="2a838-136">In questo modo `HttpCookieReplySessionChannel` può essere attivo oltre la durata di `HttpCookieReplySessionChannelListener`.</span><span class="sxs-lookup"><span data-stu-id="2a838-136">This way `HttpCookieReplySessionChannel` can exist beyond the lifetime of `HttpCookieReplySessionChannelListener`.</span></span> <span data-ttu-id="2a838-137">Non è inoltre necessario preoccuparsi che il listener venga sottoposto a procedure di garbage collection perché i canali accettati conservano un riferimento al listener tramite il callback di `OnClosed`.</span><span class="sxs-lookup"><span data-stu-id="2a838-137">We also do not have to worry about the listener getting garbage collected underneath us because the accepted channels keep a reference to their listener through the `OnClosed` callback.</span></span>  
  
## <a name="client-channel"></a><span data-ttu-id="2a838-138">Canale del client</span><span class="sxs-lookup"><span data-stu-id="2a838-138">Client channel</span></span>  
 <span data-ttu-id="2a838-139">Il canale del client corrispondente è incluso nella classe `HttpCookieSessionChannelFactory`.</span><span class="sxs-lookup"><span data-stu-id="2a838-139">The corresponding client channel is in the `HttpCookieSessionChannelFactory` class.</span></span> <span data-ttu-id="2a838-140">Durante la creazione del canale, la channel factory esegue il wrapping del canale della richiesta interno con una classe `HttpCookieRequestSessionChannel`.</span><span class="sxs-lookup"><span data-stu-id="2a838-140">During channel creation, the channel factory wraps the inner request channel with an `HttpCookieRequestSessionChannel`.</span></span> <span data-ttu-id="2a838-141">La classe `HttpCookieRequestSessionChannel` inoltra le chiamate al canale della richiesta sottostante.</span><span class="sxs-lookup"><span data-stu-id="2a838-141">The `HttpCookieRequestSessionChannel` class forwards the calls to the underlying request channel.</span></span> <span data-ttu-id="2a838-142">Quando il client chiude il proxy, `HttpCookieRequestSessionChannel` invia un messaggio al servizio nel quale viene indicato che il canale sta per essere chiuso.</span><span class="sxs-lookup"><span data-stu-id="2a838-142">When the client closes the proxy, `HttpCookieRequestSessionChannel` sends a message to the service that indicates that the channel is being closed.</span></span> <span data-ttu-id="2a838-143">In questo modo, lo stack dei canali del servizio può arrestare normalmente il canale della sessione in uso.</span><span class="sxs-lookup"><span data-stu-id="2a838-143">Thus, the service channel stack can gracefully shutdown the session channel that is in use.</span></span>  
  
## <a name="binding-and-binding-element"></a><span data-ttu-id="2a838-144">Associazioni ed elementi di associazione</span><span class="sxs-lookup"><span data-stu-id="2a838-144">Binding and Binding Element</span></span>  
 <span data-ttu-id="2a838-145">Dopo aver creato i canali del servizio e del client, il passaggio successivo consiste nell'integrarli nel runtime WCF.</span><span class="sxs-lookup"><span data-stu-id="2a838-145">After creating the service and client channels, the next step is to integrate them into the WCF runtime.</span></span> <span data-ttu-id="2a838-146">I canali vengono esposti a WCF tramite associazioni ed elementi di associazione.</span><span class="sxs-lookup"><span data-stu-id="2a838-146">Channels are exposed to WCF through bindings and binding elements.</span></span> <span data-ttu-id="2a838-147">Un'associazione è costituita da uno o più elementi di associazione.</span><span class="sxs-lookup"><span data-stu-id="2a838-147">A binding consists of one or many binding elements.</span></span> <span data-ttu-id="2a838-148">WCF offre diverse associazioni definite dal sistema. ad esempio, BasicHttpBinding o WSHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="2a838-148">WCF offers several system-defined bindings; for example, BasicHttpBinding or WSHttpBinding.</span></span> <span data-ttu-id="2a838-149">La classe `HttpCookieSessionBindingElement` contiene l'implementazione per l'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="2a838-149">The `HttpCookieSessionBindingElement` class contains the implementation for the binding element.</span></span> <span data-ttu-id="2a838-150">Esegue l'override del listener del canale e dei metodi di creazione della channel factory per creare le istanze del listener del canale o della channel factory necessarie.</span><span class="sxs-lookup"><span data-stu-id="2a838-150">It overrides the channel listener and channel factory creation methods to do the necessary channel listener or channel factory instantiations.</span></span>  
  
 <span data-ttu-id="2a838-151">Nell'esempio vengono utilizzate asserzioni di criteri per la descrizione del servizio.</span><span class="sxs-lookup"><span data-stu-id="2a838-151">The sample uses policy assertions for the service description.</span></span> <span data-ttu-id="2a838-152">In questo modo, nell'esempio i requisiti del canale possono essere pubblicati negli altri client che possono utilizzare il servizio.</span><span class="sxs-lookup"><span data-stu-id="2a838-152">This allows the sample to publish its channel requirements to other clients that can consume the service.</span></span> <span data-ttu-id="2a838-153">Ad esempio, questo elemento di associazione pubblica le asserzioni di criteri per segnalare ai client potenziali che supporta le sessioni.</span><span class="sxs-lookup"><span data-stu-id="2a838-153">For example, this binding element publishes policy assertions to let potential clients know that it supports sessions.</span></span> <span data-ttu-id="2a838-154">Poiché nell'esempio viene abilitata la proprietà `ExchangeTerminateMessage` nella configurazione dell'elemento di associazione, vengono aggiunte le asserzioni necessarie per mostrare che il servizio supporta un'azione di scambio messaggi aggiuntiva per terminare la conversazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="2a838-154">Because the sample enables the `ExchangeTerminateMessage` property in the binding element configuration, it adds the necessary assertions to show that the service supports an extra message exchange action to terminate the session conversation.</span></span> <span data-ttu-id="2a838-155">I client possono quindi utilizzare questa azione.</span><span class="sxs-lookup"><span data-stu-id="2a838-155">Clients can then use this action.</span></span> <span data-ttu-id="2a838-156">Nel codice WSDL seguente vengono mostrate le asserzioni di criteri create da `HttpCookieSessionBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="2a838-156">The following WSDL code shows the policy assertions created from the `HttpCookieSessionBindingElement`.</span></span>  
  
```xml  
<wsp:Policy wsu:Id="HttpCookieSessionBinding_IWcfCookieSessionService_policy" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
<wsp:ExactlyOne>  
<wsp:All>  
<wspe:Utf816FFFECharacterEncoding xmlns:wspe="http://schemas.xmlsoap.org/ws/2004/09/policy/encoding"/>  
<mhsc:httpSessionCookie xmlns:mhsc="http://samples.microsoft.com/wcf/mhsc/policy"/>  
</wsp:All>  
</wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="2a838-157">La classe `HttpCookieSessionBinding` è un'associazione fornita dal sistema che utilizza l'elemento di associazione descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2a838-157">The `HttpCookieSessionBinding` class is a system-provided binding that uses the binding element described previously.</span></span>  
  
## <a name="adding-the-channel-to-the-configuration-system"></a><span data-ttu-id="2a838-158">Aggiunta del canale al sistema di configurazione</span><span class="sxs-lookup"><span data-stu-id="2a838-158">Adding the Channel to the Configuration System</span></span>  
 <span data-ttu-id="2a838-159">Nell'esempio vengono fornite due classi che espongono il canale di esempio tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="2a838-159">The sample provides two classes that expose the sample channel through configuration.</span></span> <span data-ttu-id="2a838-160">La prima è una classe <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> per `HttpCookieSessionBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="2a838-160">The first is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> for the `HttpCookieSessionBindingElement`.</span></span> <span data-ttu-id="2a838-161">La maggior parte dell'implementazione viene delegata a `HttpCookieSessionBindingConfigurationElement` che deriva da <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="2a838-161">The bulk of the implementation is delegated to the `HttpCookieSessionBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="2a838-162">La classe `HttpCookieSessionBindingConfigurationElement` dispone di proprietà che corrispondono alle proprietà di `HttpCookieSessionBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="2a838-162">The `HttpCookieSessionBindingConfigurationElement` has properties that correspond to the properties on `HttpCookieSessionBindingElement`.</span></span>  
  
### <a name="binding-element-extension-section"></a><span data-ttu-id="2a838-163">Sezione di estensione dell'elemento di associazione</span><span class="sxs-lookup"><span data-stu-id="2a838-163">Binding Element Extension Section</span></span>  
 <span data-ttu-id="2a838-164">La sezione `HttpCookieSessionBindingElementSection` è una classe <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> che espone `HttpCookieSessionBindingElement` al sistema di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2a838-164">The section `HttpCookieSessionBindingElementSection` is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> that exposes `HttpCookieSessionBindingElement` to the configuration system.</span></span> <span data-ttu-id="2a838-165">Con alcuni override, vengono definiti il nome della sezione di configurazione, il tipo dell'elemento di associazione e come creare l'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="2a838-165">With a few overrides the configuration section name, the type of the binding element and how to create the binding element are defined.</span></span> <span data-ttu-id="2a838-166">È quindi possibile registrare la sezione di estensione in un file di configurazione come segue:</span><span class="sxs-lookup"><span data-stu-id="2a838-166">We can then register the extension section in a configuration file as follows:</span></span>  
  
```xml  
<configuration>
    <system.serviceModel>
      <extensions>
        <bindingElementExtensions>
          <add name="httpCookieSession"
               type=  
"Microsoft.ServiceModel.Samples.HttpCookieSessionBindingElementElement,
                    HttpCookieSessionExtension, Version=1.0.0.0,
                    Culture=neutral, PublicKeyToken=null"/>  
        </bindingElementExtensions >  
      </extensions>  
  
      <bindings>  
      <customBinding>  
        <binding name="allowCookiesBinding">  
          <textMessageEncoding messageVersion="Soap11WSAddressing10" />  
          <httpCookieSession sessionTimeout="10" exchangeTerminateMessage="true" />  
          <httpTransport allowCookies="true" />  
        </binding>  
      </customBinding>  
      </bindings>
    </system.serviceModel>
</configuration>  
```  
  
## <a name="test-code"></a><span data-ttu-id="2a838-167">Codice di test</span><span class="sxs-lookup"><span data-stu-id="2a838-167">Test Code</span></span>  
 <span data-ttu-id="2a838-168">Il codice di test per l'utilizzo di questo trasporto di esempio è disponibile nelle directory Client e Service.</span><span class="sxs-lookup"><span data-stu-id="2a838-168">Test code for using this sample transport is available in the Client and Service directories.</span></span> <span data-ttu-id="2a838-169">È costituito da due test: un test usa un'associazione con `allowCookies` impostato `true` su nel client.</span><span class="sxs-lookup"><span data-stu-id="2a838-169">It consists of two tests—one test uses a binding with `allowCookies` set to `true` on the client.</span></span> <span data-ttu-id="2a838-170">mentre il secondo test abilita l'arresto esplicito (mediante l'arresto dello scambio di messaggi) sull'associazione.</span><span class="sxs-lookup"><span data-stu-id="2a838-170">The second test enables explicit shutdown (using the terminate message exchange) on the binding.</span></span>  
  
 <span data-ttu-id="2a838-171">Quando si esegue l'esempio, verrà visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="2a838-171">When you run the sample, you should see the following output:</span></span>  
  
```console  
Simple binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
Smart binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2a838-172">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="2a838-172">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="2a838-173">Installare ASP.NET 4,0 usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="2a838-173">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="2a838-174">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2a838-174">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="2a838-175">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2a838-175">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="2a838-176">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2a838-176">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  

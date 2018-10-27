---
title: Interoperabilità con applicazioni POX
ms.date: 03/30/2017
ms.assetid: 449276b8-4633-46f0-85c9-81f01d127636
ms.openlocfilehash: b7fdb4e16bce52025515ced065d0f48cffb7fa3f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192642"
---
# <a name="interoperability-with-pox-applications"></a><span data-ttu-id="8e514-102">Interoperabilità con applicazioni POX</span><span class="sxs-lookup"><span data-stu-id="8e514-102">Interoperability with POX applications</span></span>

<span data-ttu-id="8e514-103">"Plain Old XML" applicazioni (POX) comunicano scambiando messaggi HTTP non elaborati che contengono solo dati di applicazioni XML non inclusi all'interno di una SOAP envelope.</span><span class="sxs-lookup"><span data-stu-id="8e514-103">"Plain Old XML" (POX) applications communicate by exchanging raw HTTP messages that contain only XML application data that is not enclosed within a SOAP envelope.</span></span> <span data-ttu-id="8e514-104">Windows Communication Foundation (WCF) può fornire servizi e client che utilizzano messaggi POX.</span><span class="sxs-lookup"><span data-stu-id="8e514-104">Windows Communication Foundation (WCF) can provide both services and clients that use POX messages.</span></span> <span data-ttu-id="8e514-105">Nel servizio, WCF è utilizzabile per implementare servizi che espongono endpoint a client, ad esempio i browser Web e linguaggi di scripting che inviano e ricevono messaggi POX.</span><span class="sxs-lookup"><span data-stu-id="8e514-105">On the service, WCF can be used to implement services that expose endpoints to clients such as Web browsers and scripting languages that send and receive POX messages.</span></span> <span data-ttu-id="8e514-106">Sul client, il modello di programmazione WCF è utilizzabile per implementare i client che comunicano con servizi basati su POX.</span><span class="sxs-lookup"><span data-stu-id="8e514-106">On the client, the WCF programming model can be used to implement clients that communicate with POX-based services.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e514-107">Questo documento è stato scritto originariamente per [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0.</span><span class="sxs-lookup"><span data-stu-id="8e514-107">This document was originally written for the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0.</span></span>  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] <span data-ttu-id="8e514-108">3.5 dispone di supporto incorporato per l'utilizzo di applicazioni POX.</span><span class="sxs-lookup"><span data-stu-id="8e514-108">3.5 has built-in support for working with POX applications.</span></span> <span data-ttu-id="8e514-109">Per altre informazioni, vedere [modello di programmazione HTTP Web WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).</span><span class="sxs-lookup"><span data-stu-id="8e514-109">For more information about see [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).</span></span>
  
## <a name="pox-programming-with-wcf"></a><span data-ttu-id="8e514-110">Programmazione POX con WCF</span><span class="sxs-lookup"><span data-stu-id="8e514-110">POX programming with WCF</span></span>

<span data-ttu-id="8e514-111">I servizi WCF che comunicano su HTTP tramite messaggi POX utilizzano un' [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="8e514-111">WCF services that communicate over HTTP using POX messages use a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>

```xml
<customBinding>
   <binding name="poxServerBinding">
       <textMessageEncoding messageVersion="None" />
       <httpTransport />
   </binding>
</customBinding>
```

<span data-ttu-id="8e514-112">Questa associazione personalizzata contiene due elementi:</span><span class="sxs-lookup"><span data-stu-id="8e514-112">This custom binding contains two elements:</span></span>

- [<span data-ttu-id="8e514-113">\<httpTransport ></span><span class="sxs-lookup"><span data-stu-id="8e514-113">\<httpTransport></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)

- [<span data-ttu-id="8e514-114">\<textMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="8e514-114">\<textMessageEncoding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)

<span data-ttu-id="8e514-115">Lo standard di codificatore di messaggi di testo di WCF è configurato per l'utilizzo di <xref:System.ServiceModel.Channels.MessageVersion.None%2A> valore, che consente di elaborare payload di messaggi XML che non arrivano incapsulati in una SOAP envelope.</span><span class="sxs-lookup"><span data-stu-id="8e514-115">The standard WCF Text Message Encoder is specially configured to use the <xref:System.ServiceModel.Channels.MessageVersion.None%2A> value, which allows it to process XML message payloads that do not arrive wrapped in a SOAP envelope.</span></span>

<span data-ttu-id="8e514-116">I client WCF che comunicano su HTTP tramite messaggi POX utilizzano un'associazione simile (illustrata nel codice imperativo seguente).</span><span class="sxs-lookup"><span data-stu-id="8e514-116">WCF clients that communicate over HTTP using POX messages use a similar binding (shown in the following imperative code).</span></span>

```csharp
private static Binding CreatePoxBinding()
{
    TextMessageEncodingBindingElement encoder =
        new TextMessageEncodingBindingElement( MessageVersion.None, Encoding.UTF8 );
    HttpTransportBindingElement transport = new HttpTransportBindingElement();
    transport.ManualAddressing = true;
    return new CustomBinding( new BindingElement[] { encoder, transport } );
}
```

<span data-ttu-id="8e514-117">Poiché i client POX devono specificare in modo esplicito gli URI ai quali inviano messaggi, devono in genere configurare <xref:System.ServiceModel.Channels.HttpTransportBindingElement> come modalità di indirizzamento manuale impostando la proprietà <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> su `true` nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="8e514-117">Because POX clients must explicitly specify the URIs to which they send messages, they usually must configure the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> to a manual addressing mode by setting the <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> property to `true` on the element.</span></span> <span data-ttu-id="8e514-118">Ciò consente ai messaggi di essere indirizzati in modo esplicito dal codice dell'applicazione e non sarà quindi necessario creare un nuovo <xref:System.ServiceModel.ChannelFactory> ogni volta che un'applicazione invia un messaggio a un URI HTTP diverso.</span><span class="sxs-lookup"><span data-stu-id="8e514-118">This allows messages to be addressed explicitly by application code and it is not necessary to create a new <xref:System.ServiceModel.ChannelFactory> every time an application sends a message to a different HTTP URI.</span></span>

<span data-ttu-id="8e514-119">Poiché i messaggi POX non utilizzano intestazioni SOAP per trasmettere informazioni importanti sul protocollo, i client e i servizi POX spesso devono modificare parti della richiesta HTTP sottostante utilizzata per inviare o ricevere un messaggio.</span><span class="sxs-lookup"><span data-stu-id="8e514-119">Because POX messages do not use SOAP headers to convey important protocol information, POX clients and services often must manipulate pieces of the underlying HTTP request used to send or receive a message.</span></span> <span data-ttu-id="8e514-120">Informazioni sul protocollo HTTP-specifiche, ad esempio le intestazioni HTTP e i codici di stato vengono rilevate nel modello di programmazione WCF di due classi:</span><span class="sxs-lookup"><span data-stu-id="8e514-120">HTTP-specific protocol information such as the HTTP headers and status codes are surfaced in the WCF programming model through two classes:</span></span>

- <span data-ttu-id="8e514-121"><xref:System.ServiceModel.Channels.HttpRequestMessageProperty> che contiene informazioni sulla richiesta HTTP, ad esempio le intestazioni di metodo e di richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="8e514-121"><xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, which contains information about the HTTP request, such as the HTTP method and request headers.</span></span>

- <span data-ttu-id="8e514-122"><xref:System.ServiceModel.Channels.HttpResponseMessageProperty> che contiene informazioni sulla risposta HTTP, ad esempio il codice di stato e la descrizione dello stato HTTP, come pure qualsiasi intestazione di risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="8e514-122"><xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, which contains information about the HTTP response, such as the HTTP status code and status description, as well as any HTTP response headers.</span></span>
  
<span data-ttu-id="8e514-123">Esempio di codice seguente viene illustrato come creare un messaggio di richiesta HTTP GET indirizzato a `http://localhost:8100/customers`.</span><span class="sxs-lookup"><span data-stu-id="8e514-123">The following code example shows how to create an HTTP GET request message that is addressed to `http://localhost:8100/customers`.</span></span>

```csharp
Message request = Message.CreateMessage( MessageVersion.None, String.Empty );
request.Headers.To = "http://localhost:8100/customers";

HttpRequestMessageProperty property = new HttpRequestMessageProperty();
property.Method = "GET";
property.SuppressEntityBody = true;
request.Properties.Add( HttpRequestMessageProperty.Name, property );
```

<span data-ttu-id="8e514-124">In primo luogo viene creata una richiesta vuota <xref:System.ServiceModel.Channels.Message> chiamando <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="8e514-124">First, an empty request <xref:System.ServiceModel.Channels.Message> is created by calling <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>.</span></span> <span data-ttu-id="8e514-125">Il parametro <xref:System.ServiceModel.Channels.MessageVersion.None%2A> viene utilizzato per indicare che non è necessaria una SOAP envelope e il parametro <xref:System.String.Empty> viene passato come Action.</span><span class="sxs-lookup"><span data-stu-id="8e514-125">The <xref:System.ServiceModel.Channels.MessageVersion.None%2A> parameter is used to indicate that a SOAP envelope is not required and <xref:System.String.Empty> parameter is passed as the Action.</span></span> <span data-ttu-id="8e514-126">Il messaggio di richiesta viene quindi indirizzato impostando l'intestazione <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> sull'URI desiderato.</span><span class="sxs-lookup"><span data-stu-id="8e514-126">The request message is then addressed by setting <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> header to the desired URI.</span></span> <span data-ttu-id="8e514-127">Viene quindi creato <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> e <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> viene impostato sul metodo del verbo HTTP GET e <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> viene impostato su `true` per indicare che nessun dato deve essere inviato nel corpo del messaggio di richiesta HTTP in uscita.</span><span class="sxs-lookup"><span data-stu-id="8e514-127">Next, an <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> is created and the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> is set to the HTTP verb GET method and the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> is set to `true` to indicate that no data should be sent in the body of the outgoing HTTP request message.</span></span> <span data-ttu-id="8e514-128">Infine la proprietà della richiesta viene aggiunta alla raccolta <xref:System.ServiceModel.Channels.Message.Properties%2A> del messaggio di richiesta in modo da influire sull'invio della richiesta da parte del trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="8e514-128">Finally, the request property is added to the <xref:System.ServiceModel.Channels.Message.Properties%2A> collection of the request message so it can influence how the HTTP Transport sends the request.</span></span> <span data-ttu-id="8e514-129">Il messaggio è quindi pronto per essere inviato su un'istanza appropriata di <xref:System.ServiceModel.Channels.IRequestChannel>.</span><span class="sxs-lookup"><span data-stu-id="8e514-129">The message is then ready to be sent over an appropriate instance of the <xref:System.ServiceModel.Channels.IRequestChannel>.</span></span>

<span data-ttu-id="8e514-130">È possibile utilizzare tecniche simili nel servizio per estrarre <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> da un messaggio in ingresso e creare una risposta.</span><span class="sxs-lookup"><span data-stu-id="8e514-130">Similar techniques can be used on the service to extract the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> from an incoming message and construct a response.</span></span>

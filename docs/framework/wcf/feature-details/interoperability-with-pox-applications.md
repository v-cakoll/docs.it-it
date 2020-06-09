---
title: Interoperabilità con applicazioni POX
ms.date: 03/30/2017
ms.assetid: 449276b8-4633-46f0-85c9-81f01d127636
ms.openlocfilehash: 64a6d850a32b14bc60cd43466e04b53a7a39be81
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579267"
---
# <a name="interoperability-with-pox-applications"></a><span data-ttu-id="ff0c8-102">Interoperabilità con applicazioni POX</span><span class="sxs-lookup"><span data-stu-id="ff0c8-102">Interoperability with POX applications</span></span>

<span data-ttu-id="ff0c8-103">Le applicazioni POX (Plain Old XML) comunicano scambiando messaggi HTTP non elaborati che contengono solo dati di applicazioni XML non inclusi in una busta SOAP.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-103">"Plain Old XML" (POX) applications communicate by exchanging raw HTTP messages that contain only XML application data that is not enclosed within a SOAP envelope.</span></span> <span data-ttu-id="ff0c8-104">Windows Communication Foundation (WCF) può fornire sia i servizi che i client che utilizzano messaggi POX.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-104">Windows Communication Foundation (WCF) can provide both services and clients that use POX messages.</span></span> <span data-ttu-id="ff0c8-105">Nel servizio WCF può essere utilizzato per implementare servizi che espongono endpoint a client quali Web browser e linguaggi di scripting che inviano e ricevono messaggi POX.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-105">On the service, WCF can be used to implement services that expose endpoints to clients such as Web browsers and scripting languages that send and receive POX messages.</span></span> <span data-ttu-id="ff0c8-106">Sul client, il modello di programmazione WCF può essere utilizzato per implementare client che comunicano con servizi basati su POX.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-106">On the client, the WCF programming model can be used to implement clients that communicate with POX-based services.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ff0c8-107">Questo documento è stato scritto in origine per il .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-107">This document was originally written for the .NET Framework 3.0.</span></span>  <span data-ttu-id="ff0c8-108">.NET Framework 3,5 dispone di supporto incorporato per l'utilizzo di applicazioni POX.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-108">.NET Framework 3.5 has built-in support for working with POX applications.</span></span> <span data-ttu-id="ff0c8-109">Per ulteriori informazioni su, vedere [modello di programmazione HTTP Web WCF](wcf-web-http-programming-model.md).</span><span class="sxs-lookup"><span data-stu-id="ff0c8-109">For more information about see [WCF Web HTTP Programming Model](wcf-web-http-programming-model.md).</span></span>
  
## <a name="pox-programming-with-wcf"></a><span data-ttu-id="ff0c8-110">Programmazione POX con WCF</span><span class="sxs-lookup"><span data-stu-id="ff0c8-110">POX programming with WCF</span></span>

<span data-ttu-id="ff0c8-111">I servizi WCF che comunicano tramite HTTP tramite messaggi POX utilizzano un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="ff0c8-111">WCF services that communicate over HTTP using POX messages use a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).</span></span>

```xml
<customBinding>
   <binding name="poxServerBinding">
       <textMessageEncoding messageVersion="None" />
       <httpTransport />
   </binding>
</customBinding>
```

<span data-ttu-id="ff0c8-112">Questa associazione personalizzata contiene due elementi:</span><span class="sxs-lookup"><span data-stu-id="ff0c8-112">This custom binding contains two elements:</span></span>

- [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md)

- [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md)

<span data-ttu-id="ff0c8-113">Il codificatore di messaggi di testo WCF standard è stato configurato in modo specifico per l'utilizzo del <xref:System.ServiceModel.Channels.MessageVersion.None%2A> valore, che consente di elaborare payload di messaggi XML che non arrivano incapsulati in una busta SOAP.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-113">The standard WCF Text Message Encoder is specially configured to use the <xref:System.ServiceModel.Channels.MessageVersion.None%2A> value, which allows it to process XML message payloads that do not arrive wrapped in a SOAP envelope.</span></span>

<span data-ttu-id="ff0c8-114">I client WCF che comunicano tramite HTTP tramite messaggi POX utilizzano un'associazione simile (illustrata nel codice imperativo seguente).</span><span class="sxs-lookup"><span data-stu-id="ff0c8-114">WCF clients that communicate over HTTP using POX messages use a similar binding (shown in the following imperative code).</span></span>

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

<span data-ttu-id="ff0c8-115">Poiché i client POX devono specificare in modo esplicito gli URI ai quali inviano messaggi, devono in genere configurare <xref:System.ServiceModel.Channels.HttpTransportBindingElement> come modalità di indirizzamento manuale impostando la proprietà <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> su `true` nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-115">Because POX clients must explicitly specify the URIs to which they send messages, they usually must configure the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> to a manual addressing mode by setting the <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> property to `true` on the element.</span></span> <span data-ttu-id="ff0c8-116">Ciò consente ai messaggi di essere indirizzati in modo esplicito dal codice dell'applicazione e non sarà quindi necessario creare un nuovo <xref:System.ServiceModel.ChannelFactory> ogni volta che un'applicazione invia un messaggio a un URI HTTP diverso.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-116">This allows messages to be addressed explicitly by application code and it is not necessary to create a new <xref:System.ServiceModel.ChannelFactory> every time an application sends a message to a different HTTP URI.</span></span>

<span data-ttu-id="ff0c8-117">Poiché i messaggi POX non utilizzano intestazioni SOAP per trasmettere informazioni importanti sul protocollo, i client e i servizi POX spesso devono modificare parti della richiesta HTTP sottostante utilizzata per inviare o ricevere un messaggio.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-117">Because POX messages do not use SOAP headers to convey important protocol information, POX clients and services often must manipulate pieces of the underlying HTTP request used to send or receive a message.</span></span> <span data-ttu-id="ff0c8-118">Le informazioni sul protocollo specifiche di HTTP come le intestazioni HTTP e i codici di stato sono riportate nel modello di programmazione WCF tramite due classi:</span><span class="sxs-lookup"><span data-stu-id="ff0c8-118">HTTP-specific protocol information such as the HTTP headers and status codes are surfaced in the WCF programming model through two classes:</span></span>

- <span data-ttu-id="ff0c8-119"><xref:System.ServiceModel.Channels.HttpRequestMessageProperty> che contiene informazioni sulla richiesta HTTP, ad esempio le intestazioni di metodo e di richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-119"><xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, which contains information about the HTTP request, such as the HTTP method and request headers.</span></span>

- <span data-ttu-id="ff0c8-120"><xref:System.ServiceModel.Channels.HttpResponseMessageProperty> che contiene informazioni sulla risposta HTTP, ad esempio il codice di stato e la descrizione dello stato HTTP, come pure qualsiasi intestazione di risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-120"><xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, which contains information about the HTTP response, such as the HTTP status code and status description, as well as any HTTP response headers.</span></span>
  
<span data-ttu-id="ff0c8-121">Nell'esempio di codice seguente viene illustrato come creare un messaggio di richiesta HTTP GET a cui è destinato `http://localhost:8100/customers` .</span><span class="sxs-lookup"><span data-stu-id="ff0c8-121">The following code example shows how to create an HTTP GET request message that is addressed to `http://localhost:8100/customers`.</span></span>

```csharp
Message request = Message.CreateMessage( MessageVersion.None, String.Empty );
request.Headers.To = "http://localhost:8100/customers";

HttpRequestMessageProperty property = new HttpRequestMessageProperty();
property.Method = "GET";
property.SuppressEntityBody = true;
request.Properties.Add( HttpRequestMessageProperty.Name, property );
```

<span data-ttu-id="ff0c8-122">In primo luogo viene creata una richiesta vuota <xref:System.ServiceModel.Channels.Message> chiamando <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-122">First, an empty request <xref:System.ServiceModel.Channels.Message> is created by calling <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>.</span></span> <span data-ttu-id="ff0c8-123">Il parametro <xref:System.ServiceModel.Channels.MessageVersion.None%2A> viene utilizzato per indicare che non è necessaria una SOAP envelope e il parametro <xref:System.String.Empty> viene passato come Action.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-123">The <xref:System.ServiceModel.Channels.MessageVersion.None%2A> parameter is used to indicate that a SOAP envelope is not required and <xref:System.String.Empty> parameter is passed as the Action.</span></span> <span data-ttu-id="ff0c8-124">Il messaggio di richiesta viene quindi indirizzato impostando l'intestazione <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> sull'URI desiderato.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-124">The request message is then addressed by setting <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> header to the desired URI.</span></span> <span data-ttu-id="ff0c8-125">Viene quindi creato <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> e <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> viene impostato sul metodo del verbo HTTP GET e <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> viene impostato su `true` per indicare che nessun dato deve essere inviato nel corpo del messaggio di richiesta HTTP in uscita.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-125">Next, an <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> is created and the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> is set to the HTTP verb GET method and the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> is set to `true` to indicate that no data should be sent in the body of the outgoing HTTP request message.</span></span> <span data-ttu-id="ff0c8-126">Infine la proprietà della richiesta viene aggiunta alla raccolta <xref:System.ServiceModel.Channels.Message.Properties%2A> del messaggio di richiesta in modo da influire sull'invio della richiesta da parte del trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-126">Finally, the request property is added to the <xref:System.ServiceModel.Channels.Message.Properties%2A> collection of the request message so it can influence how the HTTP Transport sends the request.</span></span> <span data-ttu-id="ff0c8-127">Il messaggio è quindi pronto per essere inviato su un'istanza appropriata di <xref:System.ServiceModel.Channels.IRequestChannel>.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-127">The message is then ready to be sent over an appropriate instance of the <xref:System.ServiceModel.Channels.IRequestChannel>.</span></span>

<span data-ttu-id="ff0c8-128">È possibile utilizzare tecniche simili nel servizio per estrarre <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> da un messaggio in ingresso e creare una risposta.</span><span class="sxs-lookup"><span data-stu-id="ff0c8-128">Similar techniques can be used on the service to extract the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> from an incoming message and construct a response.</span></span>

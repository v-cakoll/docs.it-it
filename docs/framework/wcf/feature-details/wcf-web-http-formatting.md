---
title: Formattazione HTTP Web WCFWCF Web HTTP formatting
ms.date: 03/30/2017
ms.assetid: e2414896-5463-41cd-b0a6-026a713eac2c
ms.openlocfilehash: b6c9728fe40e26977366b73337e72b1514a12a19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184202"
---
# <a name="wcf-web-http-formatting"></a><span data-ttu-id="5c6c0-102">Formattazione HTTP Web WCFWCF Web HTTP formatting</span><span class="sxs-lookup"><span data-stu-id="5c6c0-102">WCF Web HTTP formatting</span></span>
<span data-ttu-id="5c6c0-103">Il modello di programmazione HTTP Web WCF consente di determinare in modo dinamico il formato migliore in cui un'operazione di servizio debba restituire la risposta.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-103">The WCF Web HTTP programming model allows you to dynamically determine the best format for a service operation to return its response in.</span></span> <span data-ttu-id="5c6c0-104">Vengono supportati due metodi per determinare un formato appropriato: automatico ed esplicito.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-104">Two methods for determining an appropriate format are supported: automatic and explicit.</span></span>  
  
## <a name="automatic-formatting"></a><span data-ttu-id="5c6c0-105">Formattazione automatica</span><span class="sxs-lookup"><span data-stu-id="5c6c0-105">Automatic formatting</span></span>  
 <span data-ttu-id="5c6c0-106">Se abilitata, la formattazione automatica sceglie il formato migliore nel quale verrà restituita la risposta,</span><span class="sxs-lookup"><span data-stu-id="5c6c0-106">When enabled, automatic formatting chooses the best format in which to return the response.</span></span> <span data-ttu-id="5c6c0-107">controllando gli elementi seguenti, in ordine:</span><span class="sxs-lookup"><span data-stu-id="5c6c0-107">It determines the best format by checking the following, in order:</span></span>  
  
1. <span data-ttu-id="5c6c0-108">i tipi di supporto nell'intestazione Accept del messaggio di richiesta;</span><span class="sxs-lookup"><span data-stu-id="5c6c0-108">The media types in the request message’s Accept header.</span></span>  
  
2. <span data-ttu-id="5c6c0-109">il valore content-type del messaggio di richiesta;</span><span class="sxs-lookup"><span data-stu-id="5c6c0-109">The content-type of the request message.</span></span>  
  
3. <span data-ttu-id="5c6c0-110">l'impostazione del formato predefinita nell'operazione;</span><span class="sxs-lookup"><span data-stu-id="5c6c0-110">The default format setting in the operation.</span></span>  
  
4. <span data-ttu-id="5c6c0-111">l'impostazione del formato predefinita in WebHttpBehavior.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-111">The default format setting in the WebHttpBehavior.</span></span>  
  
 <span data-ttu-id="5c6c0-112">Se il messaggio di richiesta contiene un'intestazione Accept, l'infrastruttura Windows Communication Foundation (WCF) cerca un tipo supportato.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-112">If the request message contains an Accept header the Windows Communication Foundation (WCF) infrastructure searches for a type that it supports.</span></span> <span data-ttu-id="5c6c0-113">Se l'intestazione `Accept` specifica le priorità per i propri tipi di supporto, queste vengono rispettate.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-113">If the `Accept` header specifies priorities for its media types, they are honored.</span></span> <span data-ttu-id="5c6c0-114">Se non viene individuato alcun formato adatto nell'intestazione `Accept`, viene usato il valore content-type del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-114">If no suitable format is found in the `Accept` header, the content-type of the request message is used.</span></span> <span data-ttu-id="5c6c0-115">Se non viene specificato alcun valore content-type adatto, viene usata l'impostazione del formato predefinita per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-115">If no suitable content-type is specified, the default format setting for the operation is used.</span></span> <span data-ttu-id="5c6c0-116">Il formato predefinito viene impostato con il parametro `ResponseFormat` degli attributi <xref:System.ServiceModel.Web.WebGetAttribute> e <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-116">The default format is set with the `ResponseFormat` parameter of the <xref:System.ServiceModel.Web.WebGetAttribute> and <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes.</span></span> <span data-ttu-id="5c6c0-117">Se non viene specificato alcun formato predefinito nell'operazione, viene usato il valore della proprietà <xref:System.ServiceModel.Description.WebHttpBehavior.DefaultOutgoingResponseFormat%2A>.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-117">If no default format is specified on the operation, the value of the <xref:System.ServiceModel.Description.WebHttpBehavior.DefaultOutgoingResponseFormat%2A> property is used.</span></span> <span data-ttu-id="5c6c0-118">La formattazione automatica si basa sulla proprietà <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-118">Automatic formatting relies on the <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A> property.</span></span> <span data-ttu-id="5c6c0-119">Quando questa proprietà è impostata su `true`, l'infrastruttura di WCF determina il formato migliore da usare.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-119">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="5c6c0-120">La selezione automatica del formato è disabilitata per impostazione predefinita per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-120">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="5c6c0-121">La selezione automatica del formato automatica può essere abilitata a livello di codice o tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-121">Automatic format selection can be enabled programmatically or through configuration.</span></span> <span data-ttu-id="5c6c0-122">Nell'esempio seguente viene mostrato come abilitare la selezione automatica del formato nel codice.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-122">The following example shows how to enable automatic format selection in code.</span></span>  
  
```csharp
// This code assumes the service name is MyService and the service contract is IMyContract
Uri baseAddress = new Uri("http://localhost:8000");  
  
WebServiceHost host = new WebServiceHost(typeof(MyService), baseAddress)  
try  
{  
   ServiceEndpoint sep = host.AddServiceEndpoint(typeof(IMyContract), new WebHttpBinding(), "");  
   // Check it see if the WebHttpBehavior already exists  
   WebHttpBehavior whb = sep.Behaviors.Find<WebHttpBehavior>();  
  
   if (whb != null)  
   {  
      whb.AutomaticFormatSelectionEnabled = true;  
   }  
   else  
   {  
      WebHttpBehavior webBehavior = new WebHttpBehavior();  
      webBehavior.AutomaticFormatSelectionEnabled = true;  
      sep.Behaviors.Add(webBehavior);  
   }  
         // Open host to start listening for messages  
   host.Open();
  
  // ...  
}  
  catch(CommunicationException ex)  
  {  
     Console.WriteLine("An exception occurred: " + ex.Message());  
  }  
```  
  
 <span data-ttu-id="5c6c0-123">La formattazione automatica può inoltre essere abilitata tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-123">Automatic formatting can also be enabled through configuration.</span></span> <span data-ttu-id="5c6c0-124">È possibile impostare la proprietà <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A> direttamente nell'elemento <xref:System.ServiceModel.Description.WebHttpBehavior> o mediante l'elemento <xref:System.ServiceModel.Description.WebHttpEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-124">You can set the <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A> property directly on the <xref:System.ServiceModel.Description.WebHttpBehavior> or using the <xref:System.ServiceModel.Description.WebHttpEndpoint>.</span></span> <span data-ttu-id="5c6c0-125">Nell'esempio seguente viene indicato come abilitare la selezione automatica del formato nell'elemento <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-125">The following example shows how to enable the automatic format selection on the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
```xml  
<system.serviceModel>  
  <behaviors>  
    <endpointBehaviors>  
      <behavior>  
        <webHttp automaticFormatSelectionEnabled="true" />  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <!-- the "" standard endpoint is used by WebServiceHost for auto creating a web endpoint. -->  
      <standardEndpoint name="" helpEnabled="true" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="5c6c0-126">Nell'esempio seguente viene mostrato come abilitare la selezione automatica del formato mediante <xref:System.ServiceModel.Description.WebHttpEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-126">The following example shows how to enable automatic format selection using <xref:System.ServiceModel.Description.WebHttpEndpoint>.</span></span>  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>  
      <webHttpEndpoint>  
        <!-- the "" standard endpoint is used by WebServiceHost for auto creating a web endpoint. -->  
        <standardEndpoint name="" helpEnabled="true" automaticFormatSelectionEnabled="true"  />  
      </webHttpEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
```  
  
## <a name="explicit-formatting"></a><span data-ttu-id="5c6c0-127">Formattazione esplicita</span><span class="sxs-lookup"><span data-stu-id="5c6c0-127">Explicit formatting</span></span>  
 <span data-ttu-id="5c6c0-128">Come indicato nel nome, nella formattazione esplicita lo sviluppatore determina il formato migliore da usare all'interno del codice operativo.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-128">As the name implies, in explicit formatting the developer determines the best format to use within the operation code.</span></span> <span data-ttu-id="5c6c0-129">Se il formato migliore è XML o JSON, lo sviluppatore imposta <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> su <xref:System.ServiceModel.Web.WebMessageFormat.Xml> o <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-129">If the best format is XML or JSON the developer sets <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> to either <xref:System.ServiceModel.Web.WebMessageFormat.Xml> or <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span> <span data-ttu-id="5c6c0-130">Se la proprietà <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> non è impostata in modo esplicito, viene usato il formato predefinito dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-130">If the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> property is not explicitly set, then the operation’s default format is used.</span></span>  
  
 <span data-ttu-id="5c6c0-131">Nell'esempio seguente viene verificato il parametro della stringa di query di formato per un formato da usare.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-131">The following example checks the format query string parameter for a format to use.</span></span> <span data-ttu-id="5c6c0-132">Se è stato specificato, viene impostato il formato dell'operazione mediante <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-132">If it has been specified, it sets the operation’s format using <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>.</span></span>  
  
```csharp
public class Service : IService  
{  
    [WebGet]  
     public string EchoWithGet(string s)  
    {  
        // if a format query string parameter has been specified, set the response format to that. If no such
        // query string parameter exists the Accept header will be used
        string formatQueryStringValue = WebOperationContext.Current.IncomingRequest.UriTemplateMatch.QueryParameters["format"];  
        if (!string.IsNullOrEmpty(formatQueryStringValue))  
        {  
            if (formatQueryStringValue.Equals("xml", System.StringComparison.OrdinalIgnoreCase))  
            {
                WebOperationContext.Current.OutgoingResponse.Format = WebMessageFormat.Xml;
            }
            else if (formatQueryStringValue.Equals("json", System.StringComparison.OrdinalIgnoreCase))  
            {  
                WebOperationContext.Current.OutgoingResponse.Format = WebMessageFormat.Json;  
            }  
            else  
            {  
                throw new WebFaultException<string>($"Unsupported format '{formatQueryStringValue}'",   HttpStatusCode.BadRequest);
            }  
        }  
        return "You said " + s;  
    }  
```  
  
 <span data-ttu-id="5c6c0-133">Se è necessario supportare formati diversi da XML o JSON, definire l'operazione per ottenere un tipo restituito di <xref:System.ServiceModel.Channels.Message>.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-133">If you need to support formats other than XML or JSON, define your operation to have a return type of <xref:System.ServiceModel.Channels.Message>.</span></span> <span data-ttu-id="5c6c0-134">All'interno del codice operativo, determinare il formato appropriato da usare e creare quindi un oggetto <xref:System.ServiceModel.Channels.Message> usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c6c0-134">Within the operation code, determine the appropriate format to use and then create a <xref:System.ServiceModel.Channels.Message> object using one of the following methods:</span></span>  
  
- `WebOperationContext.CreateAtom10Response`  
  
- `WebOperationContext.CreateJsonResponse`  
  
- `WebOperationContext.CreateStreamResponse`  
  
- `WebOperationContext.CreateTextResponse`  
  
- `WebOperationContext.CreateXmlResponse`  
  
 <span data-ttu-id="5c6c0-135">Ognuno di questi metodi usa il contenuto e crea un messaggio con il formato appropriato.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-135">Each of these methods takes content and creates a message with the appropriate format.</span></span> <span data-ttu-id="5c6c0-136">Il metodo `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` può essere usato per ottenere un elenco di formati preferiti dal client in ordine di preferenza decrescente.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-136">The `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` method can be used to get a list of formats preferred by the client in order of decreasing preference.</span></span> <span data-ttu-id="5c6c0-137">Nell'esempio seguente viene indicato come usare `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` per determinare il formato da usare e viene quindi impiegato il metodo di risposta di creazione appropriato per creare il messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="5c6c0-137">The following example shows how to use `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` to determine the format to use and then uses the appropriate create response method to create the response message.</span></span>  
  
```csharp
public class Service : IService  
{  
    public Message EchoListWithGet(string list)  
    {  
        List<string> returnList = new List<string>(list.Split(new char[] { ',' }, StringSplitOptions.RemoveEmptyEntries));  
        IList<ContentType> acceptHeaderElements = WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements();  
        for (int x = 0; x < acceptHeaderElements.Count; x++)  
        {  
            string normalizedMediaType = acceptHeaderElements[x].MediaType.ToLowerInvariant();  
            switch (normalizedMediaType)  
            {  
                case "image/jpeg": return CreateJpegResponse(returnList);  
                case "application/xhtml+xml": return CreateXhtmlResponse(returnList);  
                case "application/atom+xml": return CreateAtom10Response(returnList);  
                case "application/xml": return CreateXmlResponse(returnList);  
                case "application/json": return CreateJsonResponse(returnList);  
          }  
    }  
  
    // Default response format is XML  
    return CreateXmlResponse(returnList);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c6c0-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c6c0-138">See also</span></span>

- <xref:System.UriTemplate>
- <xref:System.UriTemplateMatch>
- [<span data-ttu-id="5c6c0-139">Modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="5c6c0-139">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [<span data-ttu-id="5c6c0-140">UriTemplate e UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="5c6c0-140">UriTemplate and UriTemplateTable</span></span>](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md)
- [<span data-ttu-id="5c6c0-141">Panoramica sul modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="5c6c0-141">WCF Web HTTP Programming Model Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)
- [<span data-ttu-id="5c6c0-142">Modello a oggetti per la programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="5c6c0-142">WCF Web HTTP Programming Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)

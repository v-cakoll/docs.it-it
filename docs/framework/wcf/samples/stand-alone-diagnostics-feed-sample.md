---
title: Esempio di feed di diagnostica autonomo
ms.date: 03/30/2017
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
ms.openlocfilehash: 730cf011208ea1b57929fff4a1953fd3a935335c
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="stand-alone-diagnostics-feed-sample"></a><span data-ttu-id="73cb3-102">Esempio di feed di diagnostica autonomo</span><span class="sxs-lookup"><span data-stu-id="73cb3-102">Stand-Alone Diagnostics Feed Sample</span></span>
<span data-ttu-id="73cb3-103">In questo esempio viene illustrato come creare un feed di diffusione con Windows Communication Foundation (WCF) RSS/Atom.</span><span class="sxs-lookup"><span data-stu-id="73cb3-103">This sample demonstrates how to create an RSS/Atom feed for syndication with Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="73cb3-104">È un programma "Hello World" di base che illustra le nozioni di base del modello a oggetti e configurarlo in un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="73cb3-104">It is a basic "Hello World" program that shows the basics of the object model and how to set it up on a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="73cb3-105">WCF modella i feed di diffusione come operazioni del servizio che restituiscono un tipo di dati speciali <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span><span class="sxs-lookup"><span data-stu-id="73cb3-105">WCF models syndication feeds as service operations that return a special data type, <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span></span> <span data-ttu-id="73cb3-106">Le istanze dell’elemento <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> possono serializzare un feed in entrambi i formati RSS 2.0 e ATOM, 1.0.</span><span class="sxs-lookup"><span data-stu-id="73cb3-106">Instances of <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> can serialize a feed into both the RSS 2.0 and Atom 1.0 formats.</span></span> <span data-ttu-id="73cb3-107">Nell'esempio di codice seguente viene illustrato il contratto usato.</span><span class="sxs-lookup"><span data-stu-id="73cb3-107">The following sample code shows the contract used.</span></span>  
  
```  
[ServiceContract(Namespace = "")]  
    interface IDiagnosticsService  
    {  
        [OperationContract]  
        //The [WebGet] attribute controls how WCF dispatches  
        //HTTP requests to service operations based on a URI suffix  
        //(the part of the request URI after the endpoint address)  
        //using the HTTP GET method. The UriTemplate specifies a relative  
        //path of 'feed', and specifies that the format is  
        //supplied using a query string.   
        [WebGet(UriTemplate="feed?format={format}")]  
        [ServiceKnownType(typeof(Atom10FeedFormatter))]  
        [ServiceKnownType(typeof(Rss20FeedFormatter))]  
        SyndicationFeedFormatter GetProcesses(string format);  
    }  
```  
  
 <span data-ttu-id="73cb3-108">Il `GetProcesses` operazione è annotata con la <xref:System.ServiceModel.Web.WebGetAttribute> richieste di attributo che consente di controllare la modalità WCF invia HTTP GET da operazioni del servizio e specificare il formato dei messaggi inviati.</span><span class="sxs-lookup"><span data-stu-id="73cb3-108">The `GetProcesses` operation is annotated with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute that enables you to control how WCF dispatches HTTP GET requests to service operations and specify the format of the messages sent.</span></span>  
  
 <span data-ttu-id="73cb3-109">Come qualsiasi servizio WCF, feed di diffusione possono essere indipendenti o ospitati in qualsiasi applicazione gestita.</span><span class="sxs-lookup"><span data-stu-id="73cb3-109">Like any WCF service, syndication feeds can be self hosted in any managed application.</span></span> <span data-ttu-id="73cb3-110">Per funzionare correttamente, i servizi di diffusione richiedono un'associazione specifica (<xref:System.ServiceModel.WebHttpBinding>) e un comportamento dell'endpoint specifico (<xref:System.ServiceModel.Description.WebHttpBehavior>).</span><span class="sxs-lookup"><span data-stu-id="73cb3-110">Syndication services require a specific binding (the <xref:System.ServiceModel.WebHttpBinding>) and a specific endpoint behavior (the <xref:System.ServiceModel.Description.WebHttpBehavior>) to function correctly.</span></span> <span data-ttu-id="73cb3-111">La nuova classe <xref:System.ServiceModel.Web.WebServiceHost> fornisce una API appropriata per la creazione degli endpoint senza configurazione specifica.</span><span class="sxs-lookup"><span data-stu-id="73cb3-111">The new <xref:System.ServiceModel.Web.WebServiceHost> class provides a convenient API for creating such endpoints without specific configuration.</span></span>  
  
```  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 <span data-ttu-id="73cb3-112">In alternativa, è possibile usare <xref:System.ServiceModel.Activation.WebServiceHostFactory> dall'interno di un file con estensione svc ospitato in IIS per fornire una funzionalità equivalente (questa tecnica non viene dimostrata in questo codice di esempio).</span><span class="sxs-lookup"><span data-stu-id="73cb3-112">Alternatively, you can use <xref:System.ServiceModel.Activation.WebServiceHostFactory> from within an IIS-hosted .svc file to provide equivalent functionality (this technique is not demonstrated in this sample code).</span></span>  
  
```  
<%@ ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>  
```  
  
 <span data-ttu-id="73cb3-113">Dato che il servizio riceve richieste usando l’ HTTP GET standard, per accedere al servizio è possibile usare qualsiasi client che supporta il formato RSS o ATOM.</span><span class="sxs-lookup"><span data-stu-id="73cb3-113">Because this service receives requests using the standard HTTP GET, you can use any RSS or ATOM-aware client to access the service.</span></span> <span data-ttu-id="73cb3-114">Ad esempio, è possibile visualizzare l'output di questo servizio, passare a http://localhost:8000/diagnostics/feed/?format=atom o http://localhost:8000/diagnostics/feed/?format=rss in un browser che supporta RSS, ad esempio Internet Explorer 7.</span><span class="sxs-lookup"><span data-stu-id="73cb3-114">For example, you can view the output of this service by navigating to http://localhost:8000/diagnostics/feed/?format=atom or http://localhost:8000/diagnostics/feed/?format=rss in an RSS-aware browser such as Internet Explorer 7.</span></span>  
  
 <span data-ttu-id="73cb3-115">È inoltre possibile utilizzare il [come il WCF diffusione oggetto modello esegue il mapping a Atom e RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) per leggere dati diffusi ed elaborazione mediante codice imperativo.</span><span class="sxs-lookup"><span data-stu-id="73cb3-115">You can also use the [How the WCF Syndication Object Model Maps to Atom and RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) to read syndicated data and process it using imperative code.</span></span>  
  
```  
XmlReader reader = XmlReader.Create( "http://localhost:8000/diagnostics/feed/?format=rss",  
new XmlReaderSettings()  
{  
//MaxCharactersInDocument can be used to control the maximum amount of data   
//read from the reader and helps prevent OutOfMemoryException  
MaxCharactersInDocument = 1024 * 64  
} );  
  
SyndicationFeed feed = SyndicationFeed.Load( reader );  
  
foreach (SyndicationItem i in feed.Items)  
{  
        XmlSyndicationContent content = i.Content as XmlSyndicationContent;  
        ProcessData pd = content.ReadContent<ProcessData>();  
  
        Console.WriteLine(i.Title.Text);  
        Console.WriteLine(pd.ToString());  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="73cb3-116">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="73cb3-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="73cb3-117">Assicurarsi di disporre dell'autorizzazione di registrazione indirizzo destra per HTTP e HTTPS nel computer come descritto nel set di istruzioni in [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="73cb3-117">Ensure that you have the right address registration permission for HTTP and HTTPS on the computer as explained in the set up instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="73cb3-118">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="73cb3-118">Build the solution.</span></span>  
  
3.  <span data-ttu-id="73cb3-119">Eseguire l'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="73cb3-119">Run the console application.</span></span>  
  
4.  <span data-ttu-id="73cb3-120">Mentre l'applicazione console è in esecuzione, passare a http://localhost:8000/diagnostics/feed/?format=atom o http://localhost:8000/diagnostics/feed/?format=rss utilizzando un browser che supporta RSS.</span><span class="sxs-lookup"><span data-stu-id="73cb3-120">While the console application is running, navigate to http://localhost:8000/diagnostics/feed/?format=atom or http://localhost:8000/diagnostics/feed/?format=rss using an RSS-aware browser.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="73cb3-121">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="73cb3-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="73cb3-122">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="73cb3-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="73cb3-123">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="73cb3-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="73cb3-124">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="73cb3-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`  
  
## <a name="see-also"></a><span data-ttu-id="73cb3-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73cb3-125">See Also</span></span>  
 [<span data-ttu-id="73cb3-126">Modello di programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="73cb3-126">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="73cb3-127">Diffusione WCF</span><span class="sxs-lookup"><span data-stu-id="73cb3-127">WCF Syndication</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)

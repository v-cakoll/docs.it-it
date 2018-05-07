---
title: Esempio di feed di diagnostica autonomo
ms.date: 03/30/2017
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
ms.openlocfilehash: 1edd1c2184dde368fbd16299a836f1811dd24ba6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="stand-alone-diagnostics-feed-sample"></a>Esempio di feed di diagnostica autonomo
In questo esempio viene illustrato come creare un feed di diffusione con Windows Communication Foundation (WCF) RSS/Atom. È un programma "Hello World" di base che illustra le nozioni di base del modello a oggetti e configurarlo in un servizio Windows Communication Foundation (WCF).  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] modella i feed di diffusione in forma di operazioni di servizio che restituiscono un tipo di dati speciale, <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>. Le istanze dell’elemento <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> possono serializzare un feed in entrambi i formati RSS 2.0 e ATOM, 1.0. Nell'esempio di codice seguente viene illustrato il contratto usato.  
  
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
  
 L'operazione `GetProcesses` è annotata con l'attributo <xref:System.ServiceModel.Web.WebGetAttribute> che consente di controllare come [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invia richieste HTTP GET alle operazioni di servizio e di specificare il formato dei messaggi inviati.  
  
 Come tutti i servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], i feed di diffusione possono essere indipendenti o ospitati in qualsiasi applicazione gestita. Per funzionare correttamente, i servizi di diffusione richiedono un'associazione specifica (<xref:System.ServiceModel.WebHttpBinding>) e un comportamento dell'endpoint specifico (<xref:System.ServiceModel.Description.WebHttpBehavior>). La nuova classe <xref:System.ServiceModel.Web.WebServiceHost> fornisce una API appropriata per la creazione degli endpoint senza configurazione specifica.  
  
```  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 In alternativa, è possibile usare <xref:System.ServiceModel.Activation.WebServiceHostFactory> dall'interno di un file con estensione svc ospitato in IIS per fornire una funzionalità equivalente (questa tecnica non viene dimostrata in questo codice di esempio).  
  
```  
<%@ ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>  
```  
  
 Dato che il servizio riceve richieste usando l’ HTTP GET standard, per accedere al servizio è possibile usare qualsiasi client che supporta il formato RSS o ATOM. Ad esempio, è possibile visualizzare l'output di questo servizio, passare a http://localhost:8000/diagnostics/feed/?format=atom o http://localhost:8000/diagnostics/feed/?format=rss in un browser che supporta RSS, ad esempio Internet Explorer 7.  
  
 È inoltre possibile utilizzare il [come il WCF diffusione oggetto modello esegue il mapping a Atom e RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) per leggere dati diffusi ed elaborazione mediante codice imperativo.  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di disporre dell'autorizzazione di registrazione indirizzo destra per HTTP e HTTPS nel computer come descritto nel set di istruzioni in [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Compilare la soluzione.  
  
3.  Eseguire l'applicazione console.  
  
4.  Mentre l'applicazione console è in esecuzione, passare a http://localhost:8000/diagnostics/feed/?format=atom o http://localhost:8000/diagnostics/feed/?format=rss utilizzando un browser che supporta RSS.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`  
  
## <a name="see-also"></a>Vedere anche  
 [Modello di programmazione HTTP Web di WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [Diffusione WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)

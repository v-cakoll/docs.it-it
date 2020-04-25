---
title: Esempio di feed di diagnostica autonomo
ms.date: 03/30/2017
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
ms.openlocfilehash: e8edb6c603e21a517244901993226fce3f055bbe
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141104"
---
# <a name="stand-alone-diagnostics-feed-sample"></a>Esempio di feed di diagnostica autonomo
In questo esempio viene illustrato come creare un feed RSS/Atom per la diffusione con Windows Communication Foundation (WCF). Si tratta di un programma "Hello World" di base che illustra le nozioni di base del modello a oggetti e come configurarlo in un servizio di Windows Communication Foundation (WCF).  
  
 Modelli WCF i feed di diffusione come operazioni del servizio che restituiscono un <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>tipo di dati speciale,. Le istanze dell’elemento <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> possono serializzare un feed in entrambi i formati RSS 2.0 e ATOM, 1.0. Nell'esempio di codice seguente viene illustrato il contratto usato.  
  
```csharp  
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
  
 L' `GetProcesses` operazione viene annotata con <xref:System.ServiceModel.Web.WebGetAttribute> l'attributo che consente di controllare il modo in cui WCF invia le richieste HTTP Get alle operazioni del servizio e specifica il formato dei messaggi inviati.  
  
 Analogamente a qualsiasi servizio WCF, i feed di diffusione possono essere ospitati in qualsiasi applicazione gestita. Per funzionare correttamente, i servizi di diffusione richiedono un'associazione specifica (<xref:System.ServiceModel.WebHttpBinding>) e un comportamento dell'endpoint specifico (<xref:System.ServiceModel.Description.WebHttpBehavior>). La nuova classe <xref:System.ServiceModel.Web.WebServiceHost> fornisce una API appropriata per la creazione degli endpoint senza configurazione specifica.  
  
```csharp  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 In alternativa, è possibile usare <xref:System.ServiceModel.Activation.WebServiceHostFactory> dall'interno di un file con estensione svc ospitato in IIS per fornire una funzionalità equivalente (questa tecnica non viene dimostrata in questo codice di esempio).  
  
```xml
<% @ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>
```
  
 Dato che il servizio riceve richieste usando l’ HTTP GET standard, per accedere al servizio è possibile usare qualsiasi client che supporta il formato RSS o ATOM. Ad esempio, è possibile visualizzare l'output di questo servizio passando a `http://localhost:8000/diagnostics/feed/?format=atom` o `http://localhost:8000/diagnostics/feed/?format=rss` in un browser compatibile con RSS.
  
 È inoltre possibile utilizzare il [modo in cui il modello a oggetti di diffusione WCF viene mappato ad Atom e RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) per leggere i dati diffusi e elaborarli utilizzando codice imperativo.  
  
```csharp
XmlReader reader = XmlReader.Create( "http://localhost:8000/diagnostics/feed/?format=rss",
    new XmlReaderSettings()
    {
        //MaxCharactersInDocument can be used to control the maximum amount of data
        //read from the reader and helps prevent OutOfMemoryException
        MaxCharactersInDocument = 1024 * 64
    } );

SyndicationFeed feed = SyndicationFeed.Load(reader);

foreach (SyndicationItem i in feed.Items)
{
    XmlSyndicationContent content = i.Content as XmlSyndicationContent;
    ProcessData pd = content.ReadContent<ProcessData>();

    Console.WriteLine(i.Title.Text);
    Console.WriteLine(pd.ToString());
}
```
  
## <a name="set-up-build-and-run-the-sample"></a>Configurare, compilare ed eseguire l'esempio
  
1. Assicurarsi di disporre dell'autorizzazione di registrazione dell'indirizzo corretta per HTTP e HTTPS nel computer, come illustrato nella procedura di installazione di istruzioni in [una sola volta per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Compilare la soluzione.

3. Eseguire l'applicazione console.

4. Durante l'esecuzione dell'applicazione console, passare a `http://localhost:8000/diagnostics/feed/?format=atom` o `http://localhost:8000/diagnostics/feed/?format=rss` usare un browser compatibile con RSS.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`

## <a name="see-also"></a>Vedi anche

- [Modello di programmazione HTTP Web WCF](../feature-details/wcf-web-http-programming-model.md)
- [Diffusione WCF](../feature-details/wcf-syndication.md)

---
title: Utilizzo di azioni per implementare il comportamento lato server
ms.date: 03/30/2017
ms.assetid: 11a372db-7168-498b-80d2-9419ff557ba5
ms.openlocfilehash: 515553540053ed0c16085fde06e2cc2d2dedda1e
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46697776"
---
# <a name="using-actions-to-implement-server-side-behavior"></a>Utilizzo di azioni per implementare il comportamento lato server

Le azioni OData consentono di implementare un comportamento che agisce su una risorsa recuperata da un servizio OData. Ad esempio, se si considera come risorsa un filmato digitale, sono diverse le operazioni che è possibile eseguire, ad esempio l'estrazione, la valutazione, l'aggiunta di commenti o l'archiviazione. Sono tutti esempi di azioni che possono essere implementate da un servizio di WCF Data Services che gestisce i filmati digitali. Le azioni vengono descritte in una risposta OData che contiene una risorsa in cui l'azione può essere richiamata. Quando un utente richiede una risorsa che rappresenta un filmato digitale, la risposta restituita da un servizio di WCF Data Services contiene le informazioni sulle azioni disponibili per tale risorsa. La disponibilità di un'azione può dipendere dallo stato del servizio dati o della risorsa. Ad esempio, una volta estratto, un filmato digitale non può essere estratto da un altro utente. I client possono richiamare un'azione semplicemente specificando un URL. Ad esempio, `http://MyServer/MovieService.svc/Movies(6)` identifica un filmato digitale specifico e `http://MyServer/MovieService.svc/Movies(6)/Checkout` richiama l'azione sul filmato specifico. Le azioni consentono di esporre il modello di servizio senza esporre il modello di dati. Continuando con l'esempio del servizio del filmato, è possibile che si desideri consentire a un utente di valutare un filmato ma non di esporre direttamente i dati della valutazione come risorsa. È possibile implementare un'azione Rate per consentire all'utente di valutare un filmato ma non di accedere direttamente ai dati della valutazione come risorsa.
  
## <a name="implementing-an-action"></a>Implementazione di un'azione  
 Per implementare un'azione di servizio è necessario implementare il <xref:System.IServiceProvider>, [IDataServiceActionProvider](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider(v=vs.113).aspx), e [IDataServiceInvokable](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceinvokable(v=vs.113).aspx) interfacce. <xref:System.IServiceProvider> consente a WCF Data Services ottenere l'implementazione di [IDataServiceActionProvider](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider(v=vs.113).aspx). [IDataServiceActionProvider](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider(v=vs.113).aspx) consente a WCF Data Services creare, trovare, descrivere e richiamare le azioni di servizio. [IDataServiceInvokable](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceinvokable(v=vs.113).aspx) consente di richiamare il codice che implementa il comportamento di azioni di servizio e ottenere i risultati, se presente. Tenere presente che WCF Data Services contiene servizi WCF "per chiamata", ovvero ogni volta che viene chiamato il servizio, verrà creata una nuova istanza del servizio.  Assicurarsi che non vengano eseguite operazioni non necessarie quando viene creato il servizio.  
  
### <a name="iserviceprovider"></a>IServiceProvider  
 <xref:System.IServiceProvider> contiene un metodo denominato <xref:System.IServiceProvider.GetService%2A>. Questo metodo viene chiamato da WCF Data Services per recuperare diversi provider di servizi, tra cui provider di servizi di metadati e provider di azioni di servizio dati. Quando viene richiesto un provider di azioni di servizio dati, restituire le [IDataServiceActionProvider](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider(v=vs.113).aspx) implementazione.  
  
### <a name="idataserviceactionprovider"></a>IDataServiceActionProvider  
 [IDataServiceActionProvider](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider(v=vs.113).aspx) contiene metodi che consentono di recuperare le informazioni sulle azioni disponibili. Quando si implementa [IDataServiceActionProvider](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider(v=vs.113).aspx) si sono aumentando i metadati per il servizio definito dall'implementazione del servizio [IDataServiceActionProvider](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider(v=vs.113).aspx) con azioni e Gestione distribuzione a tali azioni come appropriato.  
  
#### <a name="advertiseserviceaction"></a>AdvertiseServiceAction  
 [IDataServiceActionProvider](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider.advertiseserviceaction(v=vs.113).aspx) viene chiamato per determinare quali azioni sono disponibili per la risorsa specificata. Questo metodo viene chiamato solo per le azioni che non sono sempre disponibili. Viene usato per verificare se l'azione deve essere inclusa nella risposta OData in base allo stato della risorsa richiesta o allo stato del servizio. La modalità con cui viene eseguita tale verifica viene scelta dall'utente. Se calcolare la disponibilità richiede tempo e la risorsa corrente è presente in un feed, è possibile ignorare la verifica e annunciare l'azione. Il parametro `inFeed` viene impostato su `true` se la risorsa corrente da restituire fa parte di un feed.  
  
#### <a name="createinvokable"></a>CreateInvokable  
 [CreateInvokable](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider.createinvokable(v=vs.113).aspx) viene chiamato per creare un [IDataServiceInvokable](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceinvokable(v=vs.113).aspx) che contiene un delegato che incapsula il codice che implementa il comportamento dell'azione. Verrà creato il [IDataServiceInvokable](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceinvokable(v=vs.113).aspx) istanza ma non richiama l'azione. Le azioni di WCF Data Services hanno effetti collaterali e devono essere usate insieme al provider di aggiornamento per salvare le modifiche su disco. Il [IDataServiceInvokable.Invoke](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceinvokable.invoke(v=vs.113).aspx) da SaveChanges () del Provider di aggiornamento viene chiamato il metodo viene chiamato.  
  
#### <a name="getserviceactions"></a>GetServiceActions  
 Questo metodo restituisce una raccolta di [ServiceAction](https://msdn.microsoft.com/library/system.data.services.providers.serviceaction(v=vs.113).aspx) istanze che rappresentano tutte le azioni espone un servizio dati WCF. [Oggetto ServiceAction](https://msdn.microsoft.com/library/system.data.services.providers.serviceaction(v=vs.113).aspx) è la rappresentazione dei metadati di un'azione, che include informazioni quali il nome dell'azione, i relativi parametri e il relativo tipo restituito.  
  
#### <a name="getserviceactionsbybindingparametertype"></a>GetServiceActionsByBindingParameterType  
 Questo metodo restituisce una raccolta di tutti i [ServiceAction](https://msdn.microsoft.com/library/system.data.services.providers.serviceaction(v=vs.113).aspx) istanze che possono essere associate al tipo di parametro di binding specificati. In altre parole, tutto [ServiceAction](https://msdn.microsoft.com/library/system.data.services.providers.serviceaction(v=vs.113).aspx)che possono agire sul tipo di risorsa specificata (detto anche tipo di parametro di associazione). Viene utilizzato quando il servizio restituisce una risorsa per includere le informazioni sulle azioni che possono essere richiamate sulla risorsa. Questo metodo deve restituire solo le azioni che è possibile associare al tipo di parametro di associazione esatto (nessun tipo derivato). Il metodo viene chiamato una volta per ogni richiesta per tipo rilevato e il risultato viene memorizzato nella cache da WCF Data Services.  
  
#### <a name="tryresolveserviceaction"></a>TryResolveServiceAction  
 Questo metodo cerca un oggetto specificato [ServiceAction](https://msdn.microsoft.com/library/system.data.services.providers.serviceaction(v=vs.113).aspx) e restituisce `true` se il [ServiceAction](https://msdn.microsoft.com/library/system.data.services.providers.serviceaction(v=vs.113).aspx) viene trovato. Se viene trovato, il [ServiceAction](https://msdn.microsoft.com/library/system.data.services.providers.serviceaction(v=vs.113).aspx) viene restituito nel `serviceAction` `out` parametro.  
  
### <a name="idataserviceinvokable"></a>IDataServiceInvokable  
 Questa interfaccia consente di eseguire un'azione di WCF Data Services. Quando si implementa IDataServiceInvokable, si è responsabili di tre operazioni:  
  
1.  Acquisizione e marshalling potenziale dei parametri  
  
2.  Distribuzione dei parametri nel codice che implementa effettivamente l'azione quando viene chiamato Invoke()  
  
3.  Archiviazione dei risultati restituiti da Invoke() in modo da poter essere recuperati mediante GetResult()  
  
 I parametri possono essere passati come token poiché è possibile scrivere un provider di servizi dati da usare con i token che rappresentano le risorse. In tal caso, potrebbe essere necessario convertire (effettuare il marshalling) i token in risorse effettive prima della distribuzione all'azione effettiva. Dopo il marshalling del parametro, è necessario che venga impostato uno stato modificabile in modo tale che tutte le modifiche alla risorsa, che si verificano quando l'azione viene richiamata, vengano salvate e scritte su disco.  
  
 Questa interfaccia richiede due metodi: Invoke e GetResult. Invoke richiama il delegato che implementa il comportamento dell'azione e GetResult restituisce il risultato dell'azione.  
  
## <a name="invoking-a-wcf-data-service-action"></a>Richiamo di un'azione di WCF Data Services  
 Le azioni vengono richiamate mediante una richiesta HTTP POST. L'URL specifica la risorsa seguita dal nome dell'azione. I parametri vengono passati nel corpo della richiesta. Se ad esempio è presente un servizio denominato MovieService che espone un'azione denominata Rate, è possibile usare l'URL seguente per richiamare l'azione Rate in un filmato specifico:  
  
 `http://MovieServer/MovieService.svc/Movies(1)/Rate`
  
 Movies(1) specifica il filmato che si desidera valutare e Rate specifica l'azione di valutazione. Il valore effettivo della valutazione sarà presente nel corpo della richiesta HTTP come mostrato nell'esempio seguente:  
  
```  
POST http://MovieServer/MoviesService.svc/Movies(1)/Rate HTTP/1.1   
Content-Type: application/json   
Content-Length: 20   
Host: localhost:15238  
{   
   "rating": 4   
}  
```  
  
> [!WARNING]
> Il codice di esempio precedente funzionerà solo con WCF Data Services 5.2 e versioni successive che supportano la versione light di JSON. Se si usa una versione precedente di WCF Data Services, è necessario specificare il tipo di contenuto json verbose come segue: `application/json;odata=verbose`.  
  
 In alternativa, è possibile richiamare un'azione mediante il client di WCF Data Services come mostrato nel frammento di codice seguente.  
  
```csharp
MoviesModel context = new MoviesModel (new Uri("http://MyServer/MoviesService.svc/"));  
//...  
context.Execute(new Uri("http://MyServer/MoviesService.svc/Movies(1)/Rate"), "POST", new BodyOperationParameter("rating",4) );
```
  
 Nel frammento di codice precedente la classe `MoviesModel` è stata generata mediante la procedura per aggiungere il riferimento a un servizio WCF Data Services in Visual Studio.  
  
## <a name="see-also"></a>Vedere anche  
 [WCF Data Services 4.5](../../../../docs/framework/data/wcf/index.md)  
 [Definizione di WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [Sviluppo e distribuzione di WCF Data Services](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md)  
 [Provider di servizi dati personalizzati](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md)

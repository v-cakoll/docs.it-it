---
title: Utilizzo di azioni per implementare il comportamento lato server
ms.date: 03/30/2017
ms.assetid: 11a372db-7168-498b-80d2-9419ff557ba5
ms.openlocfilehash: bdfa8e37904395b402874b743ca4069cae75c504
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70779698"
---
# <a name="using-actions-to-implement-server-side-behavior"></a>Utilizzo di azioni per implementare il comportamento lato server

Le azioni OData consentono di implementare un comportamento che agisce su una risorsa recuperata da un servizio OData. Ad esempio, se si considera come risorsa un filmato digitale, sono diverse le operazioni che è possibile eseguire, ad esempio l'estrazione, la valutazione, l'aggiunta di commenti o l'archiviazione. Sono tutti esempi di azioni che possono essere implementate da un servizio di WCF Data Services che gestisce i filmati digitali. Le azioni vengono descritte in una risposta OData che contiene una risorsa in cui l'azione può essere richiamata. Quando un utente richiede una risorsa che rappresenta un filmato digitale, la risposta restituita da un servizio di WCF Data Services contiene le informazioni sulle azioni disponibili per tale risorsa. La disponibilità di un'azione può dipendere dallo stato del servizio dati o della risorsa. Ad esempio, una volta estratto, un filmato digitale non può essere estratto da un altro utente. I client possono richiamare un'azione semplicemente specificando un URL. Ad esempio, `http://MyServer/MovieService.svc/Movies(6)` identifica un film digitale specifico e `http://MyServer/MovieService.svc/Movies(6)/Checkout` richiama l'azione sul film specifico. Le azioni consentono di esporre il modello di servizio senza esporre il modello di dati. Continuando con l'esempio del servizio del filmato, è possibile che si desideri consentire a un utente di valutare un filmato ma non di esporre direttamente i dati della valutazione come risorsa. È possibile implementare un'azione Rate per consentire all'utente di valutare un filmato ma non di accedere direttamente ai dati della valutazione come risorsa.
  
## <a name="implementing-an-action"></a>Implementazione di un'azione  
 Per implementare un'azione del servizio, è necessario <xref:System.IServiceProvider>implementare le interfacce, [IDataServiceActionProvider](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103))e [IDataServiceInvokable](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859893(v=vs.103)) . <xref:System.IServiceProvider>consente WCF Data Services di ottenere l'implementazione di [IDataServiceActionProvider](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)). [IDataServiceActionProvider](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)) consente WCF Data Services di creare, trovare, descrivere e richiamare le azioni del servizio. [IDataServiceInvokable](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859893(v=vs.103)) consente di richiamare il codice che implementa il comportamento delle azioni di servizio e di ottenere i risultati, se presenti. Tenere presente che WCF Data Services contiene servizi WCF "per chiamata", ovvero ogni volta che viene chiamato il servizio, verrà creata una nuova istanza del servizio.  Assicurarsi che non vengano eseguite operazioni non necessarie quando viene creato il servizio.  
  
### <a name="iserviceprovider"></a>IServiceProvider  
 <xref:System.IServiceProvider> contiene un metodo denominato <xref:System.IServiceProvider.GetService%2A>. Questo metodo viene chiamato da WCF Data Services per recuperare diversi provider di servizi, tra cui provider di servizi di metadati e provider di azioni di servizio dati. Quando viene richiesto un provider di azioni di servizio dati, restituire l'implementazione di [IDataServiceActionProvider](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)) .  
  
### <a name="idataserviceactionprovider"></a>IDataServiceActionProvider  
 [IDataServiceActionProvider](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)) contiene metodi che consentono di recuperare informazioni sulle azioni disponibili. Quando si implementa [IDataServiceActionProvider](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)) si stanno aumentando i metadati per il servizio definito dall'implementazione del servizio di [IDataServiceActionProvider](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)) con azioni e gestendo la distribuzione a tali azioni come appropriato.  
  
#### <a name="advertiseserviceaction"></a>AdvertiseServiceAction  
 Viene chiamato il [Metodo AdvertiseServiceAction](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859971(v=vs.103)) per determinare quali azioni sono disponibili per la risorsa specificata. Questo metodo viene chiamato solo per le azioni che non sono sempre disponibili. Viene usato per verificare se l'azione deve essere inclusa nella risposta OData in base allo stato della risorsa richiesta o allo stato del servizio. La modalità con cui viene eseguita tale verifica viene scelta dall'utente. Se calcolare la disponibilità richiede tempo e la risorsa corrente è presente in un feed, è possibile ignorare la verifica e annunciare l'azione. Il parametro `inFeed` viene impostato su `true` se la risorsa corrente da restituire fa parte di un feed.  
  
#### <a name="createinvokable"></a>CreateInvokable  
 [CreateInvokable](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859940(v=vs.103)) viene chiamato per creare un [IDataServiceInvokable](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859893(v=vs.103)) che contiene un delegato che incapsula il codice che implementa il comportamento dell'azione. In questo modo viene creata l'istanza di [IDataServiceInvokable](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859893(v=vs.103)) , ma non viene richiamata l'azione. Le azioni di WCF Data Services hanno effetti collaterali e devono essere usate insieme al provider di aggiornamento per salvare le modifiche su disco. Il metodo [IDataServiceInvokable. Invoke](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh859924(v=vs.103)) viene chiamato dal metodo SaveChanges () del provider di aggiornamenti.  
  
#### <a name="getserviceactions"></a>GetServiceActions  
 Questo metodo restituisce una raccolta di istanze di [oggetto ServiceAction](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) che rappresentano tutte le azioni esposte da un servizio dati WCF. [Oggetto ServiceAction](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) è la rappresentazione dei metadati di un'azione che include informazioni quali il nome dell'azione, i relativi parametri e il tipo restituito.  
  
#### <a name="getserviceactionsbybindingparametertype"></a>GetServiceActionsByBindingParameterType  
 Questo metodo restituisce una raccolta di tutte le istanze di [oggetto ServiceAction](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) che possono essere associate al tipo di parametro di associazione specificato. In altre parole, tutti i [oggetto ServiceAction](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103))che possono agire sul tipo di risorsa specificato (detto anche tipo di parametro di associazione). Viene usato quando il servizio restituisce una risorsa per includere informazioni sulle azioni che possono essere richiamate sulla risorsa. Questo metodo deve restituire solo le azioni che è possibile associare al tipo di parametro di associazione esatto (nessun tipo derivato). Il metodo viene chiamato una volta per ogni richiesta per tipo rilevato e il risultato viene memorizzato nella cache da WCF Data Services.  
  
#### <a name="tryresolveserviceaction"></a>TryResolveServiceAction  
 Questo metodo cerca un [oggetto ServiceAction](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) specificato e restituisce `true` se viene trovato [oggetto ServiceAction](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) . Se viene trovato, il [oggetto ServiceAction](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) viene restituito nel `serviceAction` `out` parametro.  
  
### <a name="idataserviceinvokable"></a>IDataServiceInvokable  
 Questa interfaccia consente di eseguire un'azione di WCF Data Services. Quando si implementa IDataServiceInvokable, si è responsabili di tre operazioni:  
  
1. Acquisizione e marshalling potenziale dei parametri  
  
2. Distribuzione dei parametri nel codice che implementa effettivamente l'azione quando viene chiamato Invoke()  
  
3. Archiviazione dei risultati restituiti da Invoke() in modo da poter essere recuperati mediante GetResult()  
  
 I parametri possono essere passati come token poiché è possibile scrivere un provider di servizi dati da usare con i token che rappresentano le risorse. In tal caso, potrebbe essere necessario convertire (effettuare il marshalling) i token in risorse effettive prima della distribuzione all'azione effettiva. Al termine del marshalling del parametro, lo stato deve essere modificabile, in modo che tutte le modifiche apportate alla risorsa che si verificano quando viene richiamata l'azione verranno salvate e scritte su disco.  
  
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

- [WCF Data Services 4.5](index.md)
- [Definizione di WCF Data Services](defining-wcf-data-services.md)
- [Sviluppo e distribuzione di WCF Data Services](developing-and-deploying-wcf-data-services.md)
- [Provider di servizi dati personalizzati](custom-data-service-providers-wcf-data-services.md)

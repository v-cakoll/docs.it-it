---
title: 'Procedura: scegliere tra richieste HTTP POST e HTTP GET per gli endpoint ASP.NET AJAX'
ms.date: 03/30/2017
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
ms.openlocfilehash: 0f7a221d1fd14b4a978683f008858e35cbd2df19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184760"
---
# <a name="how-to-choose-between-http-post-and-http-get-requests-for-aspnet-ajax-endpoints"></a>Procedura: scegliere tra richieste HTTP POST e HTTP GET per gli endpoint ASP.NET AJAX

Windows Communication Foundation (WCF) consente di creare un servizio che espone un ASP.NET endpoint con supporto AJAX che può essere chiamato da JavaScript in un sito Web client. Le procedure di base per la creazione di tali servizi sono illustrate in [Procedura: Utilizzare](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) la configurazione per aggiungere un endpoint AJAX ASP.NET e [procedura: aggiungere un ASP.NET endpoint AJAX senza utilizzare](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)la configurazione .  
  
 ASP.NET AJAX supporta operazioni che usano verbi HTTP POST e HTTP GET, con HTTP POST come impostazione predefinita. Quando si crea un'operazione che non ha effetti collaterali e restituisce dati che non vengono mai modificati o vengono modificati solo di rado, usare HTTP GET. I risultati delle operazioni GET possono essere memorizzati nella cache, il che significa che più chiamate alla stessa operazione possono produrre una sola richiesta al servizio. La memorizzazione nella cache non viene eseguita da WCF, ma può essere eseguita a qualsiasi livello (nel browser di un utente, in un server proxy e altri livelli). La memorizzazione nella cache è vantaggiosa se si desidera aumentare le prestazioni del servizio, ma potrebbe non essere accettabile se i dati vengono modificati di frequente o se l'operazione esegue un'azione.  
  
 Ad esempio, se si sta progettando un servizio per gestire il catalogo musicale di un utente, un'operazione che ricerca l'artista in base al titolo di un album trae vantaggio dall'utilizzo di GET, ma un'operazione che aggiunge un album alla raccolta personale dell'utente deve usare POST.  
  
 Per controllare la durata della cache, usare il tipo <xref:System.ServiceModel.Web.OutgoingWebResponseContext>. Ad esempio, quando si progetta un servizio che restituisce previsioni meteorologiche aggiornate ogni ora, si utilizzerà GET limitando però la durata della cache a massimo un'ora, per impedire agli utenti del servizio di accedere a dati non aggiornati.  
  
 Quando si usano servizi da una pagina ASP.NET AJAX che usano il controllo Script Manager, non c'è alcuna differenza se l'operazione usa GET o POST, il meccanismo di gestione degli script assicura che venga emesso il tipo di richiesta corretto.  
  
 Le operazioni HTTP GET usano qualsiasi parametro di input supportato dalle operazioni POST, inclusi i tipi di contratto dati complessi. Tuttavia, nella maggior parte dei casi è consigliabile evitare di usare troppi parametri o parametri troppo complessi nelle operazioni GET, per non ridurre l'efficienza della memorizzazione nella cache.  
  
 In questo argomento viene illustrato come scegliere tra GET e POST aggiungendo gli attributi <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> alle operazioni pertinenti nel contratto di servizio. Gli altri passaggi (per implementare, configurare e ospitare il servizio) necessari per ottenere il servizio in esecuzione sono simili a quelli utilizzati da qualsiasi ASP.NET servizio AJAX in WCF.  
  
 Un'operazione contrassegnata da <xref:System.ServiceModel.Web.WebGetAttribute> usa sempre una richiesta GET. Un'operazione contrassegnata da <xref:System.ServiceModel.Web.WebInvokeAttribute> o non contrassegnata da nessuno dei due attributi, usa una richiesta POST. <xref:System.ServiceModel.Web.WebInvokeAttribute> consente di usare altri verbi HTTP, diversi da GET e POST, quali PUT e DELETE, tramite la proprietà <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>. Tuttavia, questi verbi non sono supportati da ASP.NET AJAX. Se si intende usare il servizio da pagine ASP.NET che usano il controllo Script Manager, non usare la proprietà <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>.  
  
 Per un esempio funzionante di passaggio a GET, vedere l'esempio di [servizio AJAX di base.](../../../../docs/framework/wcf/samples/basic-ajax-service.md)  
  
 Per un esempio che usa POST, vedere il [servizio AJAX utilizzando HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) esempio.  
  
## <a name="to-create-a-wcf-service-that-responds-to-http-get-or-http-post-requests"></a>Per creare un servizio WCF che risponde a richieste HTTP GET o HTTP POST
  
1. Definire un contratto di servizio WCF <xref:System.ServiceModel.ServiceContractAttribute> di base con un'interfaccia contrassegnata con l'attributo . Contrassegnare ogni operazione con <xref:System.ServiceModel.OperationContractAttribute>. Aggiungere l'attributo <xref:System.ServiceModel.Web.WebGetAttribute> per stabilire che un'operazione deve rispondere a richieste HTTP GET. È inoltre possibile aggiungere l'attributo <xref:System.ServiceModel.Web.WebInvokeAttribute> per specificare esplicitamente HTTP POST o non specificare alcun attributo e scegliere quindi HTTP POST per impostazione predefinita.
  
    ```csharp
    [ServiceContract]  
    public interface IMusicService  
    {  
        //This operation uses a GET method.  
        [OperationContract]  
        [WebGet]  
        string LookUpArtist(string album);  
  
        //This operation will use a POST method.  
        [OperationContract]  
        [WebInvoke]  
        void AddAlbum(string user, string album);  
  
        //This operation will use POST method by default  
        //since nothing else is explicitly specified.  
        [OperationContract]  
        string[] GetAlbums(string user);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. Implementare il contratto di servizio `IMusicService` con `MusicService`.
  
    ```csharp
    public class MusicService : IMusicService  
    {  
        public void AddAlbum(string user, string album)  
        {  
            //Add implementation here.  
        }  
  
         //Other operations omitted…  
    }  
    ```  
  
3. Creare un nuovo file denominato "file del servizio" con estensione svc nell'applicazione. Modificare questo file aggiungendo [ \@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) le informazioni appropriate della direttiva ServiceHost per il servizio. Specificare <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> che l'oggetto deve essere utilizzato nella direttiva [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) per configurare automaticamente un endpoint AJAX ASP.NET.  
  
    ```
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
## <a name="to-call-the-service"></a>Per chiamare il servizio  
  
1. È possibile testare le operazioni GET del servizio senza alcun codice client, usando il browser. Ad esempio, se il servizio `http://example.com/service.svc` è configurato `http://example.com/service.svc/LookUpArtist?album=SomeAlbum` all'indirizzo, digitando nella barra degli indirizzi del browser viene richiamato il servizio e la risposta viene scaricata o visualizzata.
  
2. È possibile usare servizi con operazioni GET esattamente come qualsiasi altro servizio ASP.NET AJAX, immettendo l'URL del servizio nella raccolta degli script del controllo Script Manager ASP.NET AJAX. Per un esempio, vedere il [servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md).
  
## <a name="see-also"></a>Vedere anche

- [Creazione di servizi WCF per ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [Procedura: eseguire la migrazione di servizi Web ASP.NET compatibili AJAX a WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)

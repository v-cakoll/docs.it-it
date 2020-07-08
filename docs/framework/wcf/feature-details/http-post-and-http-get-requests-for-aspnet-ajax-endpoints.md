---
title: 'Procedura: scegliere tra richieste HTTP POST e HTTP GET per gli endpoint ASP.NET AJAX'
ms.date: 03/30/2017
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
ms.openlocfilehash: c74b1acdf3802ab680123cd9d676919fe47236e8
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051584"
---
# <a name="how-to-choose-between-http-post-and-http-get-requests-for-aspnet-ajax-endpoints"></a>Procedura: scegliere tra richieste HTTP POST e HTTP GET per gli endpoint ASP.NET AJAX

Windows Communication Foundation (WCF) consente di creare un servizio che espone un endpoint abilitato per AJAX ASP.NET che può essere chiamato da JavaScript su un sito Web client. Le procedure di base per la compilazione di tali servizi sono illustrate in [procedura: usare la configurazione per aggiungere un endpoint ASP.NET AJAX](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) e [procedura: aggiungere un endpoint ASP.NET AJAX senza usare la configurazione](how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
 ASP.NET AJAX supporta operazioni che usano verbi HTTP POST e HTTP GET, con HTTP POST come impostazione predefinita. Quando si crea un'operazione che non ha effetti collaterali e restituisce dati che non vengono mai modificati o vengono modificati solo di rado, usare HTTP GET. I risultati delle operazioni GET possono essere memorizzati nella cache, il che significa che più chiamate alla stessa operazione possono produrre una sola richiesta al servizio. La memorizzazione nella cache non viene eseguita da WCF, ma può essere eseguita a qualsiasi livello (nel browser di un utente, in un server proxy e in altri livelli). La memorizzazione nella cache è vantaggiosa se si desidera aumentare le prestazioni del servizio, ma potrebbe non essere accettabile se i dati vengono modificati di frequente o se l'operazione esegue un'azione.  
  
 Ad esempio, se si sta progettando un servizio per gestire il catalogo musicale di un utente, un'operazione che ricerca l'artista in base al titolo di un album trae vantaggio dall'utilizzo di GET, ma un'operazione che aggiunge un album alla raccolta personale dell'utente deve usare POST.  
  
 Per controllare la durata della cache, usare il tipo <xref:System.ServiceModel.Web.OutgoingWebResponseContext>. Ad esempio, quando si progetta un servizio che restituisce previsioni meteorologiche aggiornate ogni ora, si utilizzerà GET limitando però la durata della cache a massimo un'ora, per impedire agli utenti del servizio di accedere a dati non aggiornati.  
  
 Quando si usano servizi da una pagina ASP.NET AJAX che usano il controllo Script Manager, non c'è alcuna differenza se l'operazione usa GET o POST, il meccanismo di gestione degli script assicura che venga emesso il tipo di richiesta corretto.  
  
 Le operazioni HTTP GET usano qualsiasi parametro di input supportato dalle operazioni POST, inclusi i tipi di contratto dati complessi. Tuttavia, nella maggior parte dei casi è consigliabile evitare di usare troppi parametri o parametri troppo complessi nelle operazioni GET, per non ridurre l'efficienza della memorizzazione nella cache.  
  
 In questo argomento viene illustrato come scegliere tra GET e POST aggiungendo gli attributi <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> alle operazioni pertinenti nel contratto di servizio. Gli altri passaggi (per implementare, configurare e ospitare il servizio) necessari per eseguire il servizio sono simili a quelli usati da qualsiasi servizio ASP.NET AJAX in WCF.  
  
 Un'operazione contrassegnata da <xref:System.ServiceModel.Web.WebGetAttribute> usa sempre una richiesta GET. Un'operazione contrassegnata da <xref:System.ServiceModel.Web.WebInvokeAttribute> o non contrassegnata da nessuno dei due attributi, usa una richiesta POST. <xref:System.ServiceModel.Web.WebInvokeAttribute> consente di usare altri verbi HTTP, diversi da GET e POST, quali PUT e DELETE, tramite la proprietà <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>. Tuttavia, questi verbi non sono supportati da ASP.NET AJAX. Se si intende usare il servizio da pagine ASP.NET che usano il controllo Script Manager, non usare la proprietà <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>.  
  
 Per un esempio funzionante di cambio da ottenere, vedere l'esempio di [servizio AJAX di base](../samples/basic-ajax-service.md) .  
  
 Per un esempio che usa POST, vedere l'esempio di [servizio AJAX con http post](../samples/ajax-service-using-http-post.md) .  
  
## <a name="to-create-a-wcf-service-that-responds-to-http-get-or-http-post-requests"></a>Per creare un servizio WCF che risponde a richieste HTTP GET o HTTP POST
  
1. Definire un contratto di servizio WCF di base con un'interfaccia contrassegnata con l' <xref:System.ServiceModel.ServiceContractAttribute> attributo. Contrassegnare ogni operazione con <xref:System.ServiceModel.OperationContractAttribute>. Aggiungere l'attributo <xref:System.ServiceModel.Web.WebGetAttribute> per stabilire che un'operazione deve rispondere a richieste HTTP GET. È inoltre possibile aggiungere l'attributo <xref:System.ServiceModel.Web.WebInvokeAttribute> per specificare esplicitamente HTTP POST o non specificare alcun attributo e scegliere quindi HTTP POST per impostazione predefinita.
  
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
  
3. Creare un nuovo file denominato "file del servizio" con estensione svc nell'applicazione. Modificare questo file aggiungendo le informazioni della direttiva [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) appropriate per il servizio. Consente di specificare che deve <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> essere utilizzato nella direttiva [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) per configurare automaticamente un endpoint ASP.NET AJAX.  
  
    ```aspx-csharp
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
## <a name="to-call-the-service"></a>Per chiamare il servizio  
  
1. È possibile testare le operazioni GET del servizio senza alcun codice client, usando il browser. Se, ad esempio, il servizio è configurato in corrispondenza dell' `http://example.com/service.svc` Indirizzo, digitando `http://example.com/service.svc/LookUpArtist?album=SomeAlbum` nella barra degli indirizzi del browser viene richiamato il servizio e la risposta viene scaricata o visualizzata.
  
2. È possibile usare servizi con operazioni GET esattamente come qualsiasi altro servizio ASP.NET AJAX, immettendo l'URL del servizio nella raccolta degli script del controllo Script Manager ASP.NET AJAX. Per un esempio, vedere [servizio AJAX di base](../samples/basic-ajax-service.md).
  
## <a name="see-also"></a>Vedere anche

- [Creazione di servizi WCF per ASP.NET AJAX](creating-wcf-services-for-aspnet-ajax.md)
- [Procedura: eseguire la migrazione di servizi Web ASP.NET compatibili AJAX a WCF](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)

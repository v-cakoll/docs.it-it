---
title: Creazione di servizi WCF per ASP.NET AJAX
ms.date: 03/30/2017
ms.assetid: 04c0402c-e617-4ba5-aedf-d17692234776
ms.openlocfilehash: 4d3953046a796686a465cd8096b8f2ba930aa9fd
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43463260"
---
# <a name="creating-wcf-services-for-aspnet-ajax"></a>Creazione di servizi WCF per ASP.NET AJAX
Microsoft ASP.NET AJAX consente di creare rapidamente pagine Web caratterizzate da un'esperienza utente più soddisfacente con i classici elementi dell'interfaccia utente di elevata reattività. ASP.NET AJAX fornisce librerie di script client in cui sono incorporate tecnologie multibrowser ECMAScript (JavaScript) e DHTML (HTML dinamico), nonché l'integrazione con la piattaforma di sviluppo basata su server ASP.NET 2.0. Con ASP.NET AJAX è possibile migliorare l'esperienza utente e l'efficienza delle applicazioni Web.  
  
 ASP.NET AJAX è costituito da librerie di script client e da componenti server integrati per fornire un framework di sviluppo affidabile. Per accedere a un servizio da una pagina ASP.NET: dopo l'aggiunta dell'URL del servizio al controllo Script Manager di ASP.NET nella pagina, è possibile richiamare le operazioni del servizio utilizzando codice JavaScript che assomiglia esattamente a una normale chiamata alla funzione JavaScript. Visualizzare [Learn ASP.NET AJAX](https://go.microsoft.com/fwlink/?LinkId=186475) sull'utilizzo dei servizi Web all'interno del framework AJAX.  
  
 La maggior parte dei servizi Windows Communication Foundation (WCF) possono essere esposta come servizio compatibile con ASP.NET AJAX aggiungendo un endpoint ASP.NET AJAX appropriato.  
  
 Se si usa Visual Studio, è possibile utilizzare un modello predefinito per i servizi WCF compatibile con AJAX, disponibile nel **Aggiungi nuovo elemento** finestra di dialogo quando si lavora con siti Web ASP.NET o applicazioni Web.  
  
 Se non si stanno utilizzando i modelli di Visual Studio, esistono due modalità per creare un endpoint ASP.NET AJAX:  
  
-   Creare l'endpoint utilizzando l'attivazione dinamica dell'host senza utilizzare alcuna configurazione. Questo è l'approccio più elementare se non si conosce il sistema di configurazione WCF. Per altre informazioni, vedere [procedura: aggiungere un ASP.NET AJAX senza mediante configurazione dell'Endpoint](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
-   Aggiungere un endpoint compatibile AJAX a un servizio WCF utilizzando la configurazione. Per altre informazioni, vedere [procedura: utilizzare la configurazione per aggiungere un Endpoint ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).  
  
 Il modello di programmazione Web descritto nel [HTTP Web WCF Programming Model Overview](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md) possono essere utilizzati con i servizi ASP.NET AJAX. In particolare:  
  
-   È possibile utilizzare gli attributi <xref:System.ServiceModel.Web.WebGetAttribute> e <xref:System.ServiceModel.Web.WebInvokeAttribute> per selezionare tra i verbi HTTP GET e HTTP POST. Se utilizzati correttamente, possono migliorare notevolmente le prestazioni dell'applicazione. Per altre informazioni, vedere [procedura: scegliere tra HTTP POST e HTTP GET richieste per gli endpoint ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md).  
  
-   È possibile utilizzare le proprietà <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> e <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> affinché il servizio restituisca dati XML anziché la notazione JSON (JavaScript Object Notation) predefinita. L'utilizzo di questo approccio con il framework ASP.NET AJAX fa sì che il client JavaScript riceva un oggetto XML DOM.  
  
    > [!WARNING]
    >  Per funzionare, l'operazione deve impostare il tipo di contenuto su Text/XML. In caso contrario, il client JavaScript riceverà una stringa che contiene XML anziché un oggetto XML DOM.  
  
     Di seguito viene riportato l'esempio di un'operazione che restituisce dati XML con il tipo di contenuto impostato in modo appropriato:  
  
    ```  
    [OperationContract, WebGet(ResponseFormat=WebMessageFormat.Xml)]  
    public XElement GetData()  
    {  
    XElement x;  
    //Get some data here...  
  
    WebOperationContext.Current.OutgoingResponse.ContentType = "text/xml";      
    return x;  
    }  
    ```  
  
-   Se è richiesta la compatibilità con ASP.NET AJAX, non è possibile modificare nessun'altra proprietà negli attributi <xref:System.ServiceModel.Web.WebGetAttribute> e <xref:System.ServiceModel.Web.WebInvokeAttribute>. Gli altri aspetti del modello di programmazione Web possono essere utilizzati a condizione che non vengano violate le convenzioni di chiamata ASP.NET AJAX.  
  
 Gli scenari più avanzati richiedono alcuni dettagli aggiuntivi di supporto AJAX in WCF comprensibile:  
  
-   Per comprendere il modo in cui i dati vengono trasferiti tra un client della pagina AJAX e un servizio WCF tramite JavaScript e per informazioni dettagliate su come eseguire il mapping tipi di .NET Framework a tipi JavaScript, vedere [supporto per JSON e altri formati trasferimento di dati](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md).  
  
-   Per sfruttare le funzionalità di ASP.NET, ad esempio, l'autenticazione basata su URL e l'accesso alle informazioni della sessione ASP.NET, è consigliabile abilitare la modalità di compatibilità ASP.NET tramite la configurazione.  
  
 Gli endpoint AJAX in WCF possono essere utilizzati anche senza il framework ASP.NET AJAX. Questa operazione richiede la comprensione dell'architettura di supporto di AJAX in WCF. Per una descrizione di questa architettura, vedere [WCF modello oggetto di programmazione HTTP di Web](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md). Per un esempio di codice che illustra questo approccio, vedere la [servizio AJAX con JSON e XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Modello di programmazione HTTP Web di WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [Procedura: Aggiungere un endpoint ASP.NET AJAX senza usare la configurazione](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)  
 [Procedura: Usare la configurazione per aggiungere un endpoint ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)  
 [Procedura: Scegliere tra richieste HTTP POST e HTTP GET per endpoint ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md)

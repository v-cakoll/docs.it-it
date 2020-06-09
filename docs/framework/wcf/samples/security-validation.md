---
title: Convalida della sicurezza
ms.date: 03/30/2017
ms.assetid: 48dcd496-0c4f-48ce-8b9b-0e25b77ffa58
ms.openlocfilehash: 70408976469b1cbcf9c4679bd91d81872ec74ae1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599971"
---
# <a name="security-validation"></a>Convalida della sicurezza
In questo esempio viene illustrato come utilizzare un comportamento personalizzato per convalidare i servizi in un computer per garantire che soddisfino criteri specifici. Nell'esempio i servizi vengono convalidati dal comportamento personalizzato mediante l'analisi di ogni endpoint nel servizio e verificando se contengono elementi di associazione protetti. Questo esempio è basato sul [Introduzione](getting-started-sample.md).  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
## <a name="endpoint-validation-custom-behavior"></a>Comportamento personalizzato di convalida dell'endpoint  
 Aggiungendo il codice utente al metodo `Validate` contenuto nell'interfaccia <xref:System.ServiceModel.Description.IServiceBehavior>, il comportamento personalizzato può essere assegnato a un servizio o a un endpoint per eseguire azioni definite dall'utente. Il codice seguente viene utilizzato per eseguire un ciclo in ogni endpoint contenuto in un servizio allo scopo di esaminare le raccolte di associazioni per individuare le associazioni protette.  
  
```csharp
public void Validate(ServiceDescription serviceDescription,
                                       ServiceHostBase serviceHostBase)  
{  
    // Loop through each endpoint individually, gathering their
    // binding elements.  
    foreach (ServiceEndpoint endpoint in serviceDescription.Endpoints)  
    {  
        secureElementFound = false;  
  
        // Retrieve the endpoint's binding element collection.  
        BindingElementCollection bindingElements =
            endpoint.Binding.CreateBindingElements();  
  
        // Look to see if the binding elements collection contains any
        // secure binding elements. Transport, Asymmetric, and Symmetric
        // binding elements are all derived from SecurityBindingElement.  
        if ((bindingElements.Find<SecurityBindingElement>() != null) || (bindingElements.Find<HttpsTransportBindingElement>() != null) || (bindingElements.Find<WindowsStreamSecurityBindingElement>() != null) || (bindingElements.Find<SslStreamSecurityBindingElement>() != null))  
        {  
            secureElementFound = true;  
        }  
  
    // Send a message to the system event viewer when an endpoint is deemed insecure.  
    if (!secureElementFound)  
        throw new Exception(System.DateTime.Now.ToString() + ": The endpoint \"" + endpoint.Name + "\" has no secure bindings.");  
    }  
}  
```  
  
 L'aggiunta del codice seguente a file Web.config aggiunge l'estensione del comportamento `serviceValidate` affinché venga riconosciuta dal servizio.  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="endpointValidate" type="Microsoft.ServiceModel.Samples.EndpointValidateElement, endpointValidate, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </behaviorExtensions>  
    </extensions>
    ...
</system.serviceModel>
```  
  
 Quando l'estensione del comportamento è stata aggiunta al servizio, è possibile aggiungere il comportamento `endpointValidate` all'elenco dei comportamenti nel file Web.config e, di conseguenza, al servizio.  
  
```xml  
<behaviors>  
    <serviceBehaviors>  
        <behavior name="CalcServiceSEB1">  
            <serviceMetadata httpGetEnabled="true" />  
            <endpointValidate />  
        </behavior>  
    </serviceBehaviors>  
</behaviors>  
```  
  
 I comportamenti e le estensioni aggiunti al file Web.config applicano il comportamento ai singoli servizi, mentre se sono aggiunti al file Machine.config applicano il comportamento a ogni servizio attivo nel computer.  
  
> [!NOTE]
> Quando si aggiunge il comportamento a tutti i servizi, è consigliabile eseguire il backup del file Machine.config prima di apportare qualsiasi modifica.  
  
 Eseguire quindi il client fornito nella directory client\bin di questo esempio. Viene generata un'eccezione con il messaggio seguente: "Impossibile attivare il servizio richiesto ' http://localhost/servicemodelsamples/service.svc '. Si tratta di un problema previsto poiché un endpoint viene considerato non protetto dall'endpoint che convalida il comportamento e impedisce l'avvio del servizio. Il comportamento genera anche un'eccezione interna che descrive quale endpoint non è protetto e scrive un messaggio nel visualizzatore eventi di sistema nell'origine "System.ServiceModel 4.0.0.0", categoria "WebHost". È anche possibile attivare la traccia nel servizio in questo esempio. Questa operazione consente all'utente di visualizzare le eccezioni generate dall'endpoint che convalida il comportamento aprendo le tracce del servizio risultanti mediante Service Trace Viewer.  
  
### <a name="view-failed-endpoint-validation-exception-messages-in-the-event-viewer"></a>Visualizza i messaggi di eccezione di convalida endpoint non riusciti nel Visualizzatore eventi  
  
1. Fare clic sul menu **Start** e selezionare **Esegui...**.  
  
2. Digitare `eventvwr` e fare clic su **OK**.  
  
3. Nella finestra di Visualizzatore eventi fare clic su **applicazione**.  
  
4. Fare doppio clic sull'evento "System. ServiceModel 4.0.0.0" aggiunto di recente nella categoria "provider" nella finestra **dell'applicazione** per visualizzare i messaggi dell'endpoint non protetto.  
  
## <a name="set-up-build-and-run-the-sample"></a>Configurare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ServiceValidation`  
  
## <a name="see-also"></a>Vedere anche

- [Monitoraggio](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))

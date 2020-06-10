---
title: Servizio AJAX con esempi JSON e XML
ms.date: 03/30/2017
ms.assetid: 8ea5860d-0c42-4ae9-941a-e07efdd8e29c
ms.openlocfilehash: 8f70b6aa2e61d01a075a6edb3fe490ef593e73b0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575953"
---
# <a name="ajax-service-with-json-and-xml-sample"></a>Servizio AJAX con esempi JSON e XML

In questo esempio viene illustrato come utilizzare Windows Communication Foundation (WCF) per creare un servizio AJAX (Asynchronous JavaScript and XML) che restituisce i dati JavaScript Object Notation (JSON) o XML. È possibile accedere a un servizio AJAX utilizzando codice JavaScript a partire da un client del browser Web. Questo esempio si basa sull'esempio di [servizio AJAX di base](basic-ajax-service.md) .

A differenza degli altri esempi AJAX, questo esempio non utilizza ASP.NET AJAX e il controllo <xref:System.Web.UI.ScriptManager>. Con alcune configurazioni aggiuntive, è possibile accedere ai servizi WCF AJAX da qualsiasi pagina HTML tramite JavaScript e questo scenario è illustrato di seguito. Per un esempio dell'uso di WCF con ASP.NET AJAX, vedere [esempi di AJAX](ajax.md).

Questo esempio mostra come cambiare il tipo di risposta di un'operazione da JSON a XML. Questa funzionalità è disponibile indipendentemente dal fatto che il servizio sia configurato per l'accesso da ASP.NET AJAX o da una pagina client HTML/JavaScript semplice.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

Per abilitare l'utilizzo di client AJAX non ASP.NET, utilizzare <xref:System.ServiceModel.Activation.WebServiceHostFactory> (non <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) nel file con estensione svc. <xref:System.ServiceModel.Activation.WebServiceHostFactory> aggiunge un endpoint <xref:System.ServiceModel.Description.WebHttpEndpoint> standard al servizio. L'endpoint è configurato in un indirizzo vuoto relativo al file con estensione svc; Ciò significa che l'indirizzo del servizio è `http://localhost/ServiceModelSamples/service.svc` , senza suffissi aggiuntivi oltre al nome dell'operazione.

`<%@ServiceHost language="c#" Debug="true" Service="Microsoft.Samples.XmlAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebServiceHostFactory" %>`

La sezione seguente in Web.config può essere usata per effettuare modifiche di configurazione aggiuntive all'endpoint Può essere rimossa se non sono necessarie modifiche aggiuntive.

```xml
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <!-- Use this element to configure the endpoint -->
      <standardEndpoint name="" />
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

Il formato di dati predefinito per <xref:System.ServiceModel.Description.WebHttpEndpoint> è XML, mentre il formato di dati predefinito per <xref:System.ServiceModel.Description.WebScriptEndpoint> è JSON. Per ulteriori informazioni, vedere [creazione di servizi WCF AJAX senza ASP.NET](../feature-details/creating-wcf-ajax-services-without-aspnet.md).

Il servizio nell'esempio seguente è un servizio WCF standard con due operazioni. Entrambe le operazioni richiedono lo stile del corpo <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> sugli attributi <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> che è specifico del comportamento `webHttp` e non è rilevante per il cambiamento di formato JSON/XML.

```csharp
[OperationContract]
[WebInvoke(ResponseFormat = WebMessageFormat.Xml, BodyStyle = WebMessageBodyStyle.Wrapped)]
MathResult DoMathXml(double n1, double n2);
```

Il formato della risposta per l'operazione viene specificato come XML, che è l'impostazione predefinita per il [\<webHttp>](../../configure-apps/file-schema/wcf/webhttp.md) comportamento. Tuttavia, si consiglia di specificare esplicitamente il formato della risposta.

L'altra operazione utilizza l'attributo `WebInvokeAttribute` e specifica in modo esplicito JSON anziché XML per la risposta.

```csharp
[OperationContract]
[WebInvoke(ResponseFormat = WebMessageFormat.Json, BodyStyle = WebMessageBodyStyle.Wrapped)]
MathResult DoMathJson(double n1, double n2);
```

Si noti che in entrambi i casi le operazioni restituiscono un tipo complesso, `MathResult` , che è un tipo di contratto dati WCF standard.

La pagina Web client XmlAjaxClientPage. htm contiene codice JavaScript che richiama una delle due operazioni precedenti quando l'utente fa clic sui pulsanti **Esegui calcolo (Restituisci JSON)** o **Esegui calcolo (Restituisci XML)** nella pagina. Il codice per richiamare il servizio costruisce un corpo JSON e lo invia utilizzando HTTP POST. La richiesta viene creata manualmente in JavaScript, a differenza dell'esempio di [servizio AJAX di base](basic-ajax-service.md) e degli altri esempi che usano ASP.NET AJAX.

```csharp
// Create HTTP request
var xmlHttp;
// Request instantiation code omitted…
// Result handler code omitted…

// Build the operation URL
var url = "service.svc/ajaxEndpoint/";
url = url + operation;

// Build the body of the JSON message
var body = '{"n1":';
body = body + document.getElementById("num1").value + ',"n2":';
body = body + document.getElementById("num2").value + '}';

// Send the HTTP request
xmlHttp.open("POST", url, true);
xmlHttp.setRequestHeader("Content-type", "application/json");
xmlHttp.send(body);
```

Quando il servizio risponde, la risposta viene visualizzata senza nessuna ulteriore elaborazione in una casella di testo nella pagina. Viene implementata a mero scopo esemplificativo per consentire di osservare direttamente i formati dati XML e JSON utilizzati.

```javascript
// Create result handler
xmlHttp.onreadystatechange=function(){
     if(xmlHttp.readyState == 4){
          document.getElementById("result").value = xmlHttp.responseText;
     }
}
```

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\XmlAjaxService`

#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Compilare la soluzione XmlAjaxService. sln come descritto in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).

3. Passare a `http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm` (non aprire XmlAjaxClientPage. htm nel browser dalla directory del progetto).

## <a name="see-also"></a>Vedere anche

- [Servizio AJAX con il protocollo HTTP POST](ajax-service-using-http-post.md)

---
title: Servizio AJAX con esempi JSON e XML
ms.date: 03/30/2017
ms.assetid: 8ea5860d-0c42-4ae9-941a-e07efdd8e29c
ms.openlocfilehash: a93e7bdf8cda88a1e86b59e5c3d37f049bdfcf28
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59304792"
---
# <a name="ajax-service-with-json-and-xml-sample"></a>Servizio AJAX con esempi JSON e XML
Questo esempio viene illustrato come utilizzare Windows Communication Foundation (WCF) per creare un servizio Asynchronous JavaScript and XML (AJAX) che restituisce dati JavaScript Object Notation (JSON) o XML. È possibile accedere a un servizio AJAX utilizzando codice JavaScript a partire da un client del browser Web. In questo esempio si basa sul [servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md) esempio.  
  
 A differenza degli altri esempi AJAX, questo esempio non utilizza ASP.NET AJAX e il controllo <xref:System.Web.UI.ScriptManager>. Con alcune configurazioni aggiuntive, servizi WCF AJAX è possibile accedere da qualsiasi pagina HTML tramite JavaScript e questo scenario è illustrato di seguito. Per un esempio dell'utilizzo di WCF con ASP.NET AJAX, vedere [esempi AJAX](ajax.md).
  
 Questo esempio mostra come cambiare il tipo di risposta di un'operazione da JSON a XML. Questa funzionalità è disponibile indipendentemente dal fatto che il servizio sia configurato per l'accesso da ASP.NET AJAX o da una pagina client HTML/JavaScript semplice.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.
  
Per abilitare l'utilizzo di client AJAX non ASP.NET, utilizzare <xref:System.ServiceModel.Activation.WebServiceHostFactory> (non <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) nel file con estensione svc. <xref:System.ServiceModel.Activation.WebServiceHostFactory> Aggiunge un <xref:System.ServiceModel.Description.WebHttpEndpoint> endpoint standard al servizio. L'endpoint viene configurato in un indirizzo vuoto relativo al file con estensione svc; Ciò significa che l'indirizzo del servizio è `http://localhost/ServiceModelSamples/service.svc`, senza suffissi aggiuntivi tranne il nome dell'operazione.  
  
```svc
<%@ServiceHost language="c#" Debug="true" Service="Microsoft.Samples.XmlAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebServiceHostFactory" %>  
```  
  
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
  
 Formattare i dati predefiniti per <xref:System.ServiceModel.Description.WebHttpEndpoint> è XML, mentre il formato dati predefinito per <xref:System.ServiceModel.Description.WebScriptEndpoint> è JSON. Per altre informazioni, vedere [creazione di servizi WCF AJAX senza ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md).  
  
 Il servizio nell'esempio seguente è un servizio WCF standard con due operazioni. Entrambe le operazioni richiedono lo stile del corpo <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> sugli attributi <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> che è specifico del comportamento `webHttp` e non è rilevante per il cambiamento di formato JSON/XML.  

```csharp
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Xml, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathXml(double n1, double n2);  
```

 Il formato della risposta per l'operazione viene specificato come XML, ovvero l'impostazione predefinita l'impostazione per il [ \<webHttp >](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) comportamento. Tuttavia, si consiglia di specificare esplicitamente il formato della risposta.  
  
 L'altra operazione utilizza l'attributo `WebInvokeAttribute` e specifica in modo esplicito JSON anziché XML per la risposta.  

```csharp
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Json, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathJson(double n1, double n2);  
```

 Si noti che in entrambi i casi le operazioni restituiscono un tipo complesso, `MathResult`, ovvero un tipo di contratto dati WCF standard.  
  
 Il client xmlajaxclientpage. htm pagina Web contiene codice JavaScript che richiama una delle due precedenti operazioni quando l'utente fa clic il **eseguire il calcolo (restituire JSON)** o **eseguire il calcolo (restituire XML)**  pulsanti nella pagina. Il codice per richiamare il servizio costruisce un corpo JSON e lo invia utilizzando HTTP POST. La richiesta viene creata manualmente in JavaScript, a differenza di [servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md) campione e altri esempi di utilizzo di ASP.NET AJAX.  

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
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\XmlAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Compilare la soluzione Xmlajaxservice come descritto in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Passare a `http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm` (non aprire xmlajaxclientpage. htm nel browser dalla directory del progetto).  
  
## <a name="see-also"></a>Vedere anche

- [Servizio AJAX con il protocollo HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)

---
title: Servizio AJAX di base
ms.date: 03/30/2017
ms.assetid: d66d0c91-0109-45a0-a901-f3e4667c2465
ms.openlocfilehash: 8bcfb9a751670d3d1c32de6d8e6f7dc1b84ea30d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62002703"
---
# <a name="basic-ajax-service"></a>Servizio AJAX di base
Questo esempio viene illustrato come utilizzare Windows Communication Foundation (WCF) per creare un servizio base di ASP.NET Asynchronous JavaScript and XML (AJAX) (un servizio che è possibile accedere mediante codice JavaScript da un client browser Web). Il servizio usa l'attributo <xref:System.ServiceModel.Web.WebGetAttribute> per garantire che il servizio risponda alle richieste HTTP GET ed è configurato per usare il formato dati JSON (JavaScript Object Notation) per le risposte.  
  
 Supporto AJAX in WCF è ottimizzato per l'utilizzo con ASP.NET AJAX tramite il `ScriptManager` controllo. Per un esempio dell'utilizzo di WCF con ASP.NET AJAX, vedere la [esempi AJAX](ajax.md).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Nel seguente codice, l'attributo <xref:System.ServiceModel.Web.WebGetAttribute> viene applicato all'operazione `Add` per assicurare che il servizio risponda alle richieste HTTP GET. Il codice usa GET per semplicità (è possibile costruire una richiesta HTTP GET da qualsiasi browser Web). È inoltre possibile usare GET per abilitare la memorizzazione nella cache. HTTP POST è l'impostazione predefinita nel caso in cui l'attributo `WebGetAttribute` non sia presente.  

```csharp
[ServiceContract(Namespace = "SimpleAjaxService")]
public interface ICalculator
{
    [WebGet]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

 Nel file di esempio con estensione svc viene usato <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, che aggiunge un endpoint standard <xref:System.ServiceModel.Description.WebScriptEndpoint> al servizio. Tale endpoint viene configurato in un indirizzo vuoto relativo al file con estensione svc. Ciò significa che l'indirizzo del servizio è `http://localhost/ServiceModelSamples/service.svc`, senza suffissi aggiuntivi tranne il nome dell'operazione.  

```svc
<%@ServiceHost language="C#" Debug="true" Service="Microsoft.Samples.SimpleAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory" %>
```

 L'oggetto <xref:System.ServiceModel.Description.WebScriptEndpoint> è pre-configurato in modo che una pagina client AJAX ASP.NET sia in grado di accedere al servizio. La sezione seguente in Web.config può essere usata per effettuare modifiche di configurazione aggiuntive all'endpoint e può essere rimossa se tali modifiche non sono necessarie.  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webScriptEndpoint>  
      <!-- Use this element to configure the endpoint -->  
      <standardEndpoint name=""  />  
    </webScriptEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 L'oggetto <xref:System.ServiceModel.Description.WebScriptEndpoint> imposta il formato dei dati predefinito per il servizio su JSON anziché su XML. Per richiamare il servizio, passare a `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` dopo il completamento di set di backup di passaggi e di compilazione illustrati più avanti in questo argomento. Questa semplice funzionalità di test viene abilitata dall'uso di una richiesta HTTP GET.  
  
 La pagina Web SimpleAjaxClientPage.aspx del client contiene il codice ASP.NET per richiamare il servizio quando l'utente fa clic su uno dei pulsanti di operazione nella pagina. Il controllo `ScriptManager` viene usato per rendere accessibile un proxy al servizio tramite JavaScript.  

```aspx-csharp
<asp:ScriptManager ID="ScriptManager" runat="server">  
    <Services>  
        <asp:ServiceReference Path="service.svc" />  
    </Services>  
</asp:ScriptManager>  
```

 Viene creata un'istanza del proxy locale e le operazioni vengono richiamate usando il codice JavaScript seguente.  

```javascript
// Code for extracting arguments n1 and n2 omitted…  
// Instantiate a service proxy  
var proxy = new SimpleAjaxService.ICalculator();  
// Code for selecting operation omitted…  
proxy.Add(parseFloat(n1), parseFloat(n2), onSuccess, onFail, null);  
```

 Se la chiamata al servizio riesce, il codice richiama il gestore `onSuccess` e il risultato dell'operazione viene visualizzato in una casella di testo.  

```javascript
function onSuccess(mathResult){  
     document.getElementById("result").value = mathResult;  
}
```

> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\SimpleAjaxService`  

---
title: Servizio AJAX di base
ms.date: 03/30/2017
ms.assetid: d66d0c91-0109-45a0-a901-f3e4667c2465
ms.openlocfilehash: 8bcfb9a751670d3d1c32de6d8e6f7dc1b84ea30d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146997"
---
# <a name="basic-ajax-service"></a><span data-ttu-id="8cc53-102">Servizio AJAX di base</span><span class="sxs-lookup"><span data-stu-id="8cc53-102">Basic AJAX Service</span></span>
<span data-ttu-id="8cc53-103">Questo esempio viene illustrato come utilizzare Windows Communication Foundation (WCF) per creare un servizio base di ASP.NET Asynchronous JavaScript and XML (AJAX) (un servizio che è possibile accedere mediante codice JavaScript da un client browser Web).</span><span class="sxs-lookup"><span data-stu-id="8cc53-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access using JavaScript code from a Web browser client).</span></span> <span data-ttu-id="8cc53-104">Il servizio usa l'attributo <xref:System.ServiceModel.Web.WebGetAttribute> per garantire che il servizio risponda alle richieste HTTP GET ed è configurato per usare il formato dati JSON (JavaScript Object Notation) per le risposte.</span><span class="sxs-lookup"><span data-stu-id="8cc53-104">The service uses the <xref:System.ServiceModel.Web.WebGetAttribute> attribute to ensure that the service responds to HTTP GET requests and is configured to use the JavaScript Object Notation (JSON) data format for responses.</span></span>  
  
 <span data-ttu-id="8cc53-105">Supporto AJAX in WCF è ottimizzato per l'utilizzo con ASP.NET AJAX tramite il `ScriptManager` controllo.</span><span class="sxs-lookup"><span data-stu-id="8cc53-105">AJAX support in WCF is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="8cc53-106">Per un esempio dell'utilizzo di WCF con ASP.NET AJAX, vedere la [esempi AJAX](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="8cc53-106">For an example of using WCF with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8cc53-107">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8cc53-107">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="8cc53-108">Nel seguente codice, l'attributo <xref:System.ServiceModel.Web.WebGetAttribute> viene applicato all'operazione `Add` per assicurare che il servizio risponda alle richieste HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="8cc53-108">In the following code, the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is applied to the `Add` operation to ensure that the service responds to HTTP GET requests.</span></span> <span data-ttu-id="8cc53-109">Il codice usa GET per semplicità (è possibile costruire una richiesta HTTP GET da qualsiasi browser Web).</span><span class="sxs-lookup"><span data-stu-id="8cc53-109">The code uses GET for simplicity (you can construct an HTTP GET request from any Web browser).</span></span> <span data-ttu-id="8cc53-110">È inoltre possibile usare GET per abilitare la memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="8cc53-110">You can also use GET to enable caching.</span></span> <span data-ttu-id="8cc53-111">HTTP POST è l'impostazione predefinita nel caso in cui l'attributo `WebGetAttribute` non sia presente.</span><span class="sxs-lookup"><span data-stu-id="8cc53-111">HTTP POST is the default in the absence of the `WebGetAttribute` attribute.</span></span>  

```csharp
[ServiceContract(Namespace = "SimpleAjaxService")]
public interface ICalculator
{
    [WebGet]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

 <span data-ttu-id="8cc53-112">Nel file di esempio con estensione svc viene usato <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, che aggiunge un endpoint standard <xref:System.ServiceModel.Description.WebScriptEndpoint> al servizio.</span><span class="sxs-lookup"><span data-stu-id="8cc53-112">The sample .svc file uses <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, which adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> standard endpoint to the service.</span></span> <span data-ttu-id="8cc53-113">Tale endpoint viene configurato in un indirizzo vuoto relativo al file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="8cc53-113">The endpoint is configured at an empty address relative to the .svc file.</span></span> <span data-ttu-id="8cc53-114">Ciò significa che l'indirizzo del servizio è `http://localhost/ServiceModelSamples/service.svc`, senza suffissi aggiuntivi tranne il nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="8cc53-114">This means that the address of the service is `http://localhost/ServiceModelSamples/service.svc`, with no additional suffixes other than the operation name.</span></span>  

```svc
<%@ServiceHost language="C#" Debug="true" Service="Microsoft.Samples.SimpleAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory" %>
```

 <span data-ttu-id="8cc53-115">L'oggetto <xref:System.ServiceModel.Description.WebScriptEndpoint> è pre-configurato in modo che una pagina client AJAX ASP.NET sia in grado di accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="8cc53-115">The <xref:System.ServiceModel.Description.WebScriptEndpoint> is pre-configured to make the service accessible from an ASP.NET AJAX client page.</span></span> <span data-ttu-id="8cc53-116">La sezione seguente in Web.config può essere usata per effettuare modifiche di configurazione aggiuntive all'endpoint</span><span class="sxs-lookup"><span data-stu-id="8cc53-116">The following section in Web.config can be used to make additional configuration changes to the endpoint.</span></span> <span data-ttu-id="8cc53-117">e può essere rimossa se tali modifiche non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="8cc53-117">It can be removed if no extra changes are required.</span></span>  
  
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
  
 <span data-ttu-id="8cc53-118">L'oggetto <xref:System.ServiceModel.Description.WebScriptEndpoint> imposta il formato dei dati predefinito per il servizio su JSON anziché su XML.</span><span class="sxs-lookup"><span data-stu-id="8cc53-118">The <xref:System.ServiceModel.Description.WebScriptEndpoint> sets the default data format for the service to JSON instead of XML.</span></span> <span data-ttu-id="8cc53-119">Per richiamare il servizio, passare a `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` dopo il completamento di set di backup di passaggi e di compilazione illustrati più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8cc53-119">To invoke the service, navigate to `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` after completing the set up and build steps shown later in this topic.</span></span> <span data-ttu-id="8cc53-120">Questa semplice funzionalità di test viene abilitata dall'uso di una richiesta HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="8cc53-120">This testing functionality is enabled by the use of a HTTP GET request.</span></span>  
  
 <span data-ttu-id="8cc53-121">La pagina Web SimpleAjaxClientPage.aspx del client contiene il codice ASP.NET per richiamare il servizio quando l'utente fa clic su uno dei pulsanti di operazione nella pagina.</span><span class="sxs-lookup"><span data-stu-id="8cc53-121">The client Web page SimpleAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="8cc53-122">Il controllo `ScriptManager` viene usato per rendere accessibile un proxy al servizio tramite JavaScript.</span><span class="sxs-lookup"><span data-stu-id="8cc53-122">The `ScriptManager` control is used to make a proxy to the service accessible through JavaScript.</span></span>  

```aspx-csharp
<asp:ScriptManager ID="ScriptManager" runat="server">  
    <Services>  
        <asp:ServiceReference Path="service.svc" />  
    </Services>  
</asp:ScriptManager>  
```

 <span data-ttu-id="8cc53-123">Viene creata un'istanza del proxy locale e le operazioni vengono richiamate usando il codice JavaScript seguente.</span><span class="sxs-lookup"><span data-stu-id="8cc53-123">The local proxy is instantiated and operations are invoked using the following JavaScript code.</span></span>  

```javascript
// Code for extracting arguments n1 and n2 omitted…  
// Instantiate a service proxy  
var proxy = new SimpleAjaxService.ICalculator();  
// Code for selecting operation omitted…  
proxy.Add(parseFloat(n1), parseFloat(n2), onSuccess, onFail, null);  
```

 <span data-ttu-id="8cc53-124">Se la chiamata al servizio riesce, il codice richiama il gestore `onSuccess` e il risultato dell'operazione viene visualizzato in una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="8cc53-124">If the service call succeeds, the code invokes the `onSuccess` handler and the result of the operation is displayed in a text box.</span></span>  

```javascript
function onSuccess(mathResult){  
     document.getElementById("result").value = mathResult;  
}
```

> [!IMPORTANT]
>  <span data-ttu-id="8cc53-125">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="8cc53-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8cc53-126">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="8cc53-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8cc53-127">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="8cc53-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8cc53-128">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="8cc53-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\SimpleAjaxService`  

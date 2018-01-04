---
title: JSONP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c13b4d7b-dac7-4ffd-9f84-765c903511e1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02332e04f729abd125f43acdbe0883851004537e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="jsonp"></a><span data-ttu-id="14eb2-102">JSONP</span><span class="sxs-lookup"><span data-stu-id="14eb2-102">JSONP</span></span>
<span data-ttu-id="14eb2-103">In questo esempio viene illustrato come supportare JSONP (JSON with Padding) nei servizi WCF REST.</span><span class="sxs-lookup"><span data-stu-id="14eb2-103">This sample demonstrates how to support JSON with Padding (JSONP) in WCF REST services.</span></span> <span data-ttu-id="14eb2-104">JSONP è una convenzione usata per richiamare script tra domini mediante la generazione di tag script nel documento corrente.</span><span class="sxs-lookup"><span data-stu-id="14eb2-104">JSONP is a convention used to invoke cross-domain scripts by generating script tags in the current document.</span></span> <span data-ttu-id="14eb2-105">Il risultato viene restituito in una funzione di callback specificata.</span><span class="sxs-lookup"><span data-stu-id="14eb2-105">The result is returned in a specified callback function.</span></span> <span data-ttu-id="14eb2-106">JSONP si basa sul concetto che tag quali \<script src = "http:/ /..." > grado di valutare script da ogni dominio e lo script recuperato da tali tag venga valutato all'interno di un ambito in cui potrebbero già essere definite altre funzioni.</span><span class="sxs-lookup"><span data-stu-id="14eb2-106">JSONP is based on the idea that tags such as \<script src="http://..." > can evaluate scripts from any domain and the script retrieved by those tags is evaluated within a scope in which other functions may already be defined.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="14eb2-107">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="14eb2-107">Demonstrates</span></span>  
 <span data-ttu-id="14eb2-108">Generazione di script tra domini con JSONP.</span><span class="sxs-lookup"><span data-stu-id="14eb2-108">Cross-domain scripting with JSONP.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="14eb2-109">Discussione</span><span class="sxs-lookup"><span data-stu-id="14eb2-109">Discussion</span></span>  
 <span data-ttu-id="14eb2-110">Nell'esempio è inclusa una pagina Web che aggiunge dinamicamente un blocco di script dopo il rendering della pagina nel browser.</span><span class="sxs-lookup"><span data-stu-id="14eb2-110">The sample includes a Web page that dynamically adds a script block after the page has been rendered in the browser.</span></span> <span data-ttu-id="14eb2-111">Questo blocco di script chiama un servizio WCF REST che dispone di una sola operazione, ovvero `GetCustomer`.</span><span class="sxs-lookup"><span data-stu-id="14eb2-111">This script block calls a WCF REST service that has a single operation, `GetCustomer`.</span></span> <span data-ttu-id="14eb2-112">Il servizio WCF REST restituisce il nome e l'indirizzo di un cliente incapsulati in un nome di funzione di callback.</span><span class="sxs-lookup"><span data-stu-id="14eb2-112">The WCF REST service returns a customer’s name and address wrapped in a callback function name.</span></span> <span data-ttu-id="14eb2-113">Quando il servizio WCF REST risponde, la funzione di callback nella pagina Web viene richiamata con i dati del cliente e la funzione di callback visualizza i dati nella pagina Web.</span><span class="sxs-lookup"><span data-stu-id="14eb2-113">When the WCF REST service responds, the callback function on the Web page is invoked with the customer data and the callback function displays the data on the Web page.</span></span> <span data-ttu-id="14eb2-114">L'inserimento del tag script e l'esecuzione della funzione di callback vengono gestite automaticamente dal controllo ScriptManager di AJAX ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="14eb2-114">The injection of the script tag and the execution of the callback function is automatically handled by the ASP.NET AJAX ScriptManager control.</span></span> <span data-ttu-id="14eb2-115">Il modello di utilizzo è lo stesso di tutti i proxy AJAX ASP.NET, con l'aggiunta di una riga per l'abilitazione di JSONP, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="14eb2-115">The usage pattern is the same as with all ASP.NET AJAX proxies, with the addition of one line to enable JSONP, as shown in the following code:</span></span>  
  
```csharp  
var proxy = new JsonpAjaxService.CustomerService();  
proxy.set_enableJsonp(true);  
proxy.GetCustomer(onSuccess, onFail, null);  
```  
  
 <span data-ttu-id="14eb2-116">La pagina Web può chiamare il servizio WCF REST perché il servizio sta usando <xref:System.ServiceModel.Description.WebScriptEndpoint> con `crossDomainScriptAccessEnabled` impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="14eb2-116">The Web page can call the WCF REST service because the service is using the <xref:System.ServiceModel.Description.WebScriptEndpoint> with `crossDomainScriptAccessEnabled` set to `true`.</span></span> <span data-ttu-id="14eb2-117">Entrambe queste configurazioni vengono eseguite nel file Web. config sotto il \<System. ServiceModel > elemento.</span><span class="sxs-lookup"><span data-stu-id="14eb2-117">Both of these configurations are done in the Web.config file under the \<system.serviceModel> element.</span></span>  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
  <standardEndpoints>  
    <webScriptEndpoint>  
      <standardEndpoint name="" crossDomainScriptAccessEnabled="true"/>  
    </webScriptEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="14eb2-118">ScriptManager gestisce l'interazione con il servizio non rivelando la complessità dell'implementazione manuale dell'accesso JSONP.</span><span class="sxs-lookup"><span data-stu-id="14eb2-118">ScriptManager manages the interaction with the service and hides away the complexity of manually implementing JSONP access.</span></span> <span data-ttu-id="14eb2-119">Quando `crossDomainScriptAccessEnabled` è impostato su `true` e il formato di risposta per un'operazione è JSON, l'infrastruttura di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verifica la presenza di un parametro della stringa di query di callback nell'URI della richiesta ed esegue il wrapping della risposta JSON con il valore del parametro della stringa di query di callback.</span><span class="sxs-lookup"><span data-stu-id="14eb2-119">When `crossDomainScriptAccessEnabled` is set to `true` and the response format for an operation is JSON, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure inspects the URI of the request for a callback query string parameter and wraps the JSON response with the value of the callback query string parameter.</span></span> <span data-ttu-id="14eb2-120">Nell'esempio la pagina Web chiama il servizio WCF REST con l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="14eb2-120">In the sample, the Web page calls the WCF REST service with the following URI.</span></span>  
  
```  
http://localhost:33695/CustomerService/GetCustomer?callback=Sys._json0  
```  
  
 <span data-ttu-id="14eb2-121">Poiché il parametro della stringa di query di callback dispone di un valore `JsonPCallback`, il servizio WCF restituisce la risposta JSONP illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="14eb2-121">Because the callback query string parameter has a value of `JsonPCallback`, the WCF service returns a JSONP response shown in the following example.</span></span>  
  
```  
Sys._json0({"__type":"Customer:#Microsoft.Samples.Jsonp","Address":"1 Example Way","Name":"Bob"});  
```  
  
 <span data-ttu-id="14eb2-122">Questa risposta JSONP include i dati del cliente formattati come JSON, di cui è stato eseguito il wrapping con il nome della funzione di callback richiesta dalla pagina Web.</span><span class="sxs-lookup"><span data-stu-id="14eb2-122">This JSONP response includes the customer data formatted as JSON, wrapped with the callback function name that the Web page requested.</span></span> <span data-ttu-id="14eb2-123">ScriptManager eseguirà questo callback usando un tag script per portare a termine la richiesta tra domini, quindi passerà il risultato al gestore onSuccess passato all'operazione GetCustomer del proxy AJAX ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="14eb2-123">ScriptManager will execute this callback using a script tag to accomplish the cross-domain request, and then pass the result to the onSuccess handler that was passed to the GetCustomer operation of the ASP.NET AJAX proxy.</span></span>  
  
 <span data-ttu-id="14eb2-124">L'esempio è costituito da due applicazioni Web ASP.NET: una contiene solo un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e un'altra contiene la pagina Web .aspx che chiama il servizio.</span><span class="sxs-lookup"><span data-stu-id="14eb2-124">The sample consists of two ASP.NET web applications: one contains just a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, and another one contains the .aspx webpage, which calls the service.</span></span> <span data-ttu-id="14eb2-125">Quando la soluzione viene eseguita, in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] verranno ospitati i due siti web su porte diverse, creando un ambiente in cui il servizio e il client sono presenti in domini diversi.</span><span class="sxs-lookup"><span data-stu-id="14eb2-125">When running the solution, [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] will host the two websites on different ports, which creates an environment where the service and client live on different domains.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="14eb2-126">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="14eb2-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="14eb2-127">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="14eb2-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="14eb2-128">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14eb2-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="14eb2-129">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="14eb2-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\JSONP`  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="14eb2-130">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="14eb2-130">To run the sample</span></span>  
  
1.  <span data-ttu-id="14eb2-131">Aprire la soluzione per l'esempio relativo a JSONP.</span><span class="sxs-lookup"><span data-stu-id="14eb2-131">Open the solution for the JSONP Sample.</span></span>  
  
2.  <span data-ttu-id="14eb2-132">Premere F5 per avviare un collegamento ipertestuale "http://localhost:26648/JSONPClientPage.aspx" http://localhost:26648/JSONPClientPage.aspx nel browser.</span><span class="sxs-lookup"><span data-stu-id="14eb2-132">Press F5 to launch  HYPERLINK "http://localhost:26648/JSONPClientPage.aspx" http://localhost:26648/JSONPClientPage.aspx in the browser.</span></span>  
  
3.  <span data-ttu-id="14eb2-133">Si noti che dopo il caricamento della pagina, gli input di testo per "Name" e "Address" vengono popolati dai valori.</span><span class="sxs-lookup"><span data-stu-id="14eb2-133">Notice that after the page loads, the text inputs for "Name" and "Address" are populated by values.</span></span>  <span data-ttu-id="14eb2-134">Questi valori vengono forniti da una chiamata al servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] al termine del rendering della pagina da parte del browser.</span><span class="sxs-lookup"><span data-stu-id="14eb2-134">These values were supplied from a call to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service after the browser finished rendering the page.</span></span>

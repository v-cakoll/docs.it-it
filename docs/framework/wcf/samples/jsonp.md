---
title: JSONP
ms.date: 03/30/2017
ms.assetid: c13b4d7b-dac7-4ffd-9f84-765c903511e1
ms.openlocfilehash: 6b5b42285539c2334bccaa04e1ba179d2cf0046c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183577"
---
# <a name="jsonp"></a><span data-ttu-id="5c0ce-102">JSONP</span><span class="sxs-lookup"><span data-stu-id="5c0ce-102">JSONP</span></span>
<span data-ttu-id="5c0ce-103">In questo esempio viene illustrato come supportare JSONP (JSON with Padding) nei servizi WCF REST.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-103">This sample demonstrates how to support JSON with Padding (JSONP) in WCF REST services.</span></span> <span data-ttu-id="5c0ce-104">JSONP è una convenzione usata per richiamare script tra domini mediante la generazione di tag script nel documento corrente.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-104">JSONP is a convention used to invoke cross-domain scripts by generating script tags in the current document.</span></span> <span data-ttu-id="5c0ce-105">Il risultato viene restituito in una funzione di callback specificata.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-105">The result is returned in a specified callback function.</span></span> <span data-ttu-id="5c0ce-106">JSONP si basa sull'idea `<script src="http://..." >` che i tag come possono valutare gli script da qualsiasi dominio e lo script recuperato da tali tag viene valutato all'interno di un ambito in cui altre funzioni possono già essere definite.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-106">JSONP is based on the idea that tags such as `<script src="http://..." >` can evaluate scripts from any domain and the script retrieved by those tags is evaluated within a scope in which other functions may already be defined.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="5c0ce-107">Dimostra</span><span class="sxs-lookup"><span data-stu-id="5c0ce-107">Demonstrates</span></span>
 <span data-ttu-id="5c0ce-108">Generazione di script tra domini con JSONP.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-108">Cross-domain scripting with JSONP.</span></span>

## <a name="discussion"></a><span data-ttu-id="5c0ce-109">Discussione</span><span class="sxs-lookup"><span data-stu-id="5c0ce-109">Discussion</span></span>
 <span data-ttu-id="5c0ce-110">Nell'esempio è inclusa una pagina Web che aggiunge dinamicamente un blocco di script dopo il rendering della pagina nel browser.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-110">The sample includes a Web page that dynamically adds a script block after the page has been rendered in the browser.</span></span> <span data-ttu-id="5c0ce-111">Questo blocco di script chiama un servizio WCF REST che dispone di una sola operazione, ovvero `GetCustomer`.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-111">This script block calls a WCF REST service that has a single operation, `GetCustomer`.</span></span> <span data-ttu-id="5c0ce-112">Il servizio WCF REST restituisce il nome e l'indirizzo di un cliente incapsulati in un nome di funzione di callback.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-112">The WCF REST service returns a customer’s name and address wrapped in a callback function name.</span></span> <span data-ttu-id="5c0ce-113">Quando il servizio WCF REST risponde, la funzione di callback nella pagina Web viene richiamata con i dati del cliente e la funzione di callback visualizza i dati nella pagina Web.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-113">When the WCF REST service responds, the callback function on the Web page is invoked with the customer data and the callback function displays the data on the Web page.</span></span> <span data-ttu-id="5c0ce-114">L'inserimento del tag script e l'esecuzione della funzione di callback vengono gestite automaticamente dal controllo ScriptManager di AJAX ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-114">The injection of the script tag and the execution of the callback function is automatically handled by the ASP.NET AJAX ScriptManager control.</span></span> <span data-ttu-id="5c0ce-115">Il modello di utilizzo è lo stesso di tutti i proxy AJAX ASP.NET, con l'aggiunta di una riga per l'abilitazione di JSONP, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="5c0ce-115">The usage pattern is the same as with all ASP.NET AJAX proxies, with the addition of one line to enable JSONP, as shown in the following code:</span></span>

```csharp
var proxy = new JsonpAjaxService.CustomerService();
proxy.set_enableJsonp(true);
proxy.GetCustomer(onSuccess, onFail, null);
```

 <span data-ttu-id="5c0ce-116">La pagina Web può chiamare il servizio WCF REST perché il servizio sta usando <xref:System.ServiceModel.Description.WebScriptEndpoint> con `crossDomainScriptAccessEnabled` impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-116">The Web page can call the WCF REST service because the service is using the <xref:System.ServiceModel.Description.WebScriptEndpoint> with `crossDomainScriptAccessEnabled` set to `true`.</span></span> <span data-ttu-id="5c0ce-117">Entrambe queste configurazioni vengono eseguite nel \<file Web.config nell'elemento system.serviceModel>.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-117">Both of these configurations are done in the Web.config file under the \<system.serviceModel> element.</span></span>

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

 <span data-ttu-id="5c0ce-118">ScriptManager gestisce l'interazione con il servizio non rivelando la complessità dell'implementazione manuale dell'accesso JSONP.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-118">ScriptManager manages the interaction with the service and hides away the complexity of manually implementing JSONP access.</span></span> <span data-ttu-id="5c0ce-119">Quando `crossDomainScriptAccessEnabled` è `true` impostato su e il formato della risposta per un'operazione è JSON, l'infrastruttura WCF controlla l'URI della richiesta per un parametro di stringa di query di callback ed esegue il wrapping della risposta JSON con il valore del parametro della stringa di query di callback.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-119">When `crossDomainScriptAccessEnabled` is set to `true` and the response format for an operation is JSON, the WCF infrastructure inspects the URI of the request for a callback query string parameter and wraps the JSON response with the value of the callback query string parameter.</span></span> <span data-ttu-id="5c0ce-120">Nell'esempio la pagina Web chiama il servizio WCF REST con l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="5c0ce-120">In the sample, the Web page calls the WCF REST service with the following URI.</span></span>

```http
http://localhost:33695/CustomerService/GetCustomer?callback=Sys._json0
```

 <span data-ttu-id="5c0ce-121">Poiché il parametro della stringa di query di callback dispone di un valore `JsonPCallback`, il servizio WCF restituisce la risposta JSONP illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-121">Because the callback query string parameter has a value of `JsonPCallback`, the WCF service returns a JSONP response shown in the following example.</span></span>

```json
Sys._json0({"__type":"Customer:#Microsoft.Samples.Jsonp","Address":"1 Example Way","Name":"Bob"});
```

 <span data-ttu-id="5c0ce-122">Questa risposta JSONP include i dati del cliente formattati come JSON, di cui è stato eseguito il wrapping con il nome della funzione di callback richiesta dalla pagina Web.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-122">This JSONP response includes the customer data formatted as JSON, wrapped with the callback function name that the Web page requested.</span></span> <span data-ttu-id="5c0ce-123">ScriptManager eseguirà questo callback usando un tag script per portare a termine la richiesta tra domini, quindi passerà il risultato al gestore onSuccess passato all'operazione GetCustomer del proxy AJAX ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-123">ScriptManager will execute this callback using a script tag to accomplish the cross-domain request, and then pass the result to the onSuccess handler that was passed to the GetCustomer operation of the ASP.NET AJAX proxy.</span></span>

 <span data-ttu-id="5c0ce-124">L'esempio è costituito da due ASP.NET applicazioni Web: uno contiene solo un servizio WCF e un altro contiene la pagina Web aspx, che chiama il servizio.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-124">The sample consists of two ASP.NET web applications: one contains just a WCF service, and another one contains the .aspx webpage, which calls the service.</span></span> <span data-ttu-id="5c0ce-125">Quando si esegue la soluzione, Visual Studio 2012 ospiterà i due siti Web su porte diverse, che crea un ambiente in cui il servizio e il client risiedono in domini diversi.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-125">When running the solution, Visual Studio 2012 will host the two websites on different ports, which creates an environment where the service and client live on different domains.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c0ce-126">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5c0ce-127">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-127">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="5c0ce-128">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5c0ce-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5c0ce-129">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-129">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\JSONP`  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="5c0ce-130">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="5c0ce-130">To run the sample</span></span>  
  
1. <span data-ttu-id="5c0ce-131">Aprire la soluzione per l'esempio relativo a JSONP.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-131">Open the solution for the JSONP Sample.</span></span>  
  
2. <span data-ttu-id="5c0ce-132">Premere F5 `http://localhost:26648/JSONPClientPage.aspx` per avviare il browser.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-132">Press F5 to launch `http://localhost:26648/JSONPClientPage.aspx` in the browser.</span></span>  
  
3. <span data-ttu-id="5c0ce-133">Si noti che dopo il caricamento della pagina, gli input di testo per "Name" e "Address" vengono popolati da valori.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-133">Notice that after the page loads, the text inputs for "Name" and "Address" are populated by values.</span></span>  <span data-ttu-id="5c0ce-134">Questi valori sono stati forniti da una chiamata al servizio WCF dopo il browser completato il rendering della pagina.</span><span class="sxs-lookup"><span data-stu-id="5c0ce-134">These values were supplied from a call to the WCF service after the browser finished rendering the page.</span></span>

---
title: Endpoint SOAP e HTTP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3c8be75-9dda-4afa-89b6-a82cb3b73cf8
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9404d304302360b2be590c814d1f94cb46bd5f84
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="soap-and-http-endpoints"></a><span data-ttu-id="f7aa9-102">Endpoint SOAP e HTTP</span><span class="sxs-lookup"><span data-stu-id="f7aa9-102">SOAP and HTTP Endpoints</span></span>
<span data-ttu-id="f7aa9-103">In questo esempio viene illustrato come implementare un servizio basato su RPC e come esporlo nel formato SOAP e il "Plain Old XML" (POX) formato utilizzando il [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] modello di programmazione Web.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-103">This sample demonstrates how to implement an RPC-based service and expose it in the SOAP format and the "Plain Old XML" (POX) format using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web Programming model.</span></span> <span data-ttu-id="f7aa9-104">Vedere il [servizio HTTP di base](../../../../docs/framework/wcf/samples/basic-http-service.md) per ulteriori dettagli sul binding HTTP per il servizio.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-104">See the [Basic HTTP Service](../../../../docs/framework/wcf/samples/basic-http-service.md) sample for more details about the HTTP binding for the service.</span></span> <span data-ttu-id="f7aa9-105">Questo esempio si concentra sui dettagli che riguardano l'esposizione dello stesso servizio su SOAP e HTTP tramite associazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-105">This sample focuses on the details that pertain to exposing the same service over SOAP and HTTP using different bindings.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="f7aa9-106">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="f7aa9-106">Demonstrates</span></span>  
 <span data-ttu-id="f7aa9-107">Esposizione di un servizio RPC su SOAP e HTTP con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7aa9-107">Exposing an RPC service over SOAP and HTTP using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="f7aa9-108">Discussione</span><span class="sxs-lookup"><span data-stu-id="f7aa9-108">Discussion</span></span>  
 <span data-ttu-id="f7aa9-109">Questo esempio è costituito da due componenti: un progetto di applicazione Web (Service) contenente un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e un'applicazione console (Client) che richiama le operazioni del servizio usando associazioni SOAP e HTTP.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-109">This sample consists of two components: a Web Application project (Service) that contains a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service and a console application (Client) that invokes service operations using SOAP and HTTP bindings.</span></span>  
  
 <span data-ttu-id="f7aa9-110">Il servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] espone 2 operazioni, ovvero `GetData` e `PutData`, che eseguono l'eco della stringa passata come input.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-110">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service exposes 2 operations –`GetData` and `PutData` – that echo the string that was passed as input.</span></span> <span data-ttu-id="f7aa9-111">Le operazioni del servizio vengono annotate con <xref:System.ServiceModel.Web.WebGetAttribute> e <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-111">The service operations are annotated with <xref:System.ServiceModel.Web.WebGetAttribute> and <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span></span> <span data-ttu-id="f7aa9-112">Questi attributi controllano la proiezione HTTP di queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-112">These attributes control the HTTP projection of these operations.</span></span> <span data-ttu-id="f7aa9-113">Vengono inoltre annotate con <xref:System.ServiceModel.OperationContractAttribute>, consentendone l'esposizione su associazioni SOAP.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-113">In addition, they are annotated with <xref:System.ServiceModel.OperationContractAttribute>, which enables them to be exposed over SOAP bindings.</span></span> <span data-ttu-id="f7aa9-114">Il metodo `PutData` del servizio genera un oggetto <xref:System.ServiceModel.Web.WebFaultException> che viene inviato di nuovo su HTTP usando il codice di stato HTTP e su SOAP come errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-114">The service’s `PutData` method throws a <xref:System.ServiceModel.Web.WebFaultException>, which gets sent back over HTTP using the HTTP status code and gets sent back over SOAP as a SOAP fault.</span></span>  
  
 <span data-ttu-id="f7aa9-115">Il file Web.config configura il servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con 3 endpoint:</span><span class="sxs-lookup"><span data-stu-id="f7aa9-115">The Web.config file configures the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with 3 endpoints:</span></span>  
  
-   <span data-ttu-id="f7aa9-116">L'endpoint ~/service.svc/mex che espone i metadati del servizio per l'accesso da client basati su SOAP.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-116">The ~/service.svc/mex endpoint that exposes the service metadata for access by SOAP-based clients.</span></span>  
  
-   <span data-ttu-id="f7aa9-117">L'endpoint ~/service.svc/http che consente ai client di accedere al servizio usando l'associazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-117">The ~/service.svc/http endpoint that enables clients to access the service using the HTTP binding.</span></span>  
  
-   <span data-ttu-id="f7aa9-118">L'endpoint ~/service.svc/soap che consente ai client di accedere al servizio usando SOAP sull'associazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-118">The ~/service.svc/soap endpoint that allows the clients to access the service using the SOAP over HTTP binding.</span></span>  
  
 <span data-ttu-id="f7aa9-119">L'endpoint HTTP viene configurato con un endpoint standard<`webHttp`> con `helpEnabled` impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-119">The HTTP endpoint is configured with a <`webHttp`> standard endpoint which has `helpEnabled` set to `true`.</span></span> <span data-ttu-id="f7aa9-120">Di conseguenza, il servizio espone una pagina della Guida basata su XHTML in corrispondenza di ~/service.svc/http/help che i client basati su HTTP possono usare per accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-120">As a result, the service exposes an XHTML based help page at ~/service.svc/http/help that HTTP-based clients can use to access the service.</span></span>  
  
 <span data-ttu-id="f7aa9-121">Il progetto client viene illustrato l'accesso al servizio tramite un proxy SOAP (generato tramite **Aggiungi riferimento al servizio**) e l'accesso del servizio utilizzando <xref:System.Net.WebClient>.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-121">The client project demonstrates accessing the service using a SOAP proxy (generated through **Add Service Reference**) and accessing the service using <xref:System.Net.WebClient>.</span></span>  
  
 <span data-ttu-id="f7aa9-122">L'esempio è costituito da un servizio ospitato sul Web e da un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-122">The sample consists of a Web-hosted service and a console application.</span></span> <span data-ttu-id="f7aa9-123">Quando l'applicazione console è in esecuzione, il client invia richieste al servizio e scrive nella finestra della console le informazioni pertinenti incluse nelle risposte.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-123">As the console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="f7aa9-124">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="f7aa9-124">To run the sample</span></span>  
  
1.  <span data-ttu-id="f7aa9-125">Aprire la soluzione per l'esempio relativo agli endpoint SOAP e HTTP.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-125">Open the solution for the SOAP and HTTP Endpoints Sample.</span></span>  
  
2.  <span data-ttu-id="f7aa9-126">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-126">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="f7aa9-127">Se non è già aperto, premere CTRL + W, S per aprire la **Esplora** finestra.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-127">If it is not already open, press CTRL+W, S to open the **Solution Explorer** window.</span></span>  
  
4.  <span data-ttu-id="f7aa9-128">Dal **Esplora soluzioni** finestra, fare doppio clic sul **servizio** del progetto e posizionare il cursore sul **Debug** opzione del menu di scelta in modo che il **Avvia nuovo Istanza** menu di scelta rapida visualizzato.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-128">From the **Solution Explorer** window, right-click the **Service** project and place the cursor over the **Debug** context menu option so that the **Start New Instance** context menu appears.</span></span> <span data-ttu-id="f7aa9-129">Fare clic su **Avvia nuova istanza**.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-129">Click **Start New Instance**.</span></span> <span data-ttu-id="f7aa9-130">Verrà avviato il server di sviluppo ASP.NET che ospita il servizio.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-130">This launches the ASP.NET development server, which hosts the service.</span></span>  
  
5.  <span data-ttu-id="f7aa9-131">Da Esplora soluzioni, fare clic sul progetto Client e posizionare il cursore di **Debug** opzione del menu di scelta in modo che il **Avvia nuova istanza** menu di scelta rapida viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-131">From the Solution Explorer windows, right-click the Client project and place the cursor over the **Debug** context menu option so that the **Start New Instance** context menu appears.</span></span> <span data-ttu-id="f7aa9-132">Fare clic su **Avvia nuova istanza**.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-132">Click **Start New Instance**.</span></span>  
  
6.  <span data-ttu-id="f7aa9-133">Verrà visualizzata la finestra della console client in cui sono inclusi l'URI del servizio in esecuzione e l'URI della pagina della Guida HTML per il servizio in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-133">The client console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span> <span data-ttu-id="f7aa9-134">In qualsiasi momento è possibile visualizzare la pagina della Guida HTML digitando l'URI della pagina della Guida in un browser.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-134">At any point in time you can view the HTML help page by typing the URI of the help page in a browser.</span></span>  
  
7.  <span data-ttu-id="f7aa9-135">Durante l'esecuzione dell'esempio, il client scrive lo stato dell'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-135">As the sample runs, the client writes the status of the current activity.</span></span>  
  
8.  <span data-ttu-id="f7aa9-136">Premere un tasto qualsiasi per chiudere l'applicazione console client.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-136">Press any key to terminate the client console application.</span></span>  
  
9. <span data-ttu-id="f7aa9-137">Premere MAIUSC+F5 per interrompere il debug del servizio.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-137">Press SHIFT+F5 to stop debugging the service.</span></span>  
  
10. <span data-ttu-id="f7aa9-138">Nell'Area di notifica Windows, fare doppio clic sull'icona del server di sviluppo ASP.NET e selezionare **arrestare** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-138">In the Windows Notification Area, right-click the ASP.NET development server icon and select **Stop** from the context menu.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7aa9-139">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f7aa9-140">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-140">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f7aa9-141">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f7aa9-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f7aa9-142">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="f7aa9-142">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\SoapAndHttpEndpoints`

---
title: Associazione dei dati in un client ASP.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
caps.latest.revision: "23"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7ceb63315d94c0deed161bb294e8f61bf523bb63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="data-binding-in-an-aspnet-client"></a><span data-ttu-id="5c61b-102">Associazione dei dati in un client ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5c61b-102">Data Binding in an ASP.NET Client</span></span>
<span data-ttu-id="5c61b-103">In questo esempio viene descritto come associare i dati restituiti da un servizio tipico [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in un'applicazione Web Form.</span><span class="sxs-lookup"><span data-stu-id="5c61b-103">This sample demonstrates how to bind data returned by a typical [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service in a Web Forms application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c61b-104">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="5c61b-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="5c61b-105">In questo esempio viene illustrato un servizio che implementa un contratto in cui viene definito un modello di comunicazione request/reply.</span><span class="sxs-lookup"><span data-stu-id="5c61b-105">This sample demonstrates a service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="5c61b-106">L'esempio è costituito da un'applicazione Web Form client accessibile da un browser e un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ospitato su Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="5c61b-106">The sample consists of a client Web Forms application accessible from a browser and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service hosted by Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="5c61b-107">Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="5c61b-107">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="5c61b-108">Il contratto viene definito mediante l'interfaccia `IWeatherService`, che espone un'operazione denominata `GetWeatherData`.</span><span class="sxs-lookup"><span data-stu-id="5c61b-108">The contract is defined by the `IWeatherService` interface, which exposes an operation named `GetWeatherData`.</span></span> <span data-ttu-id="5c61b-109">Questa operazione accetta una matrice di città e restituisce una matrice di oggetti `WeatherData` che rappresentano la temperatura massima e minima prevista per una città.</span><span class="sxs-lookup"><span data-stu-id="5c61b-109">This operation accepts an array of cities and returns an array of `WeatherData` objects that represent the high and low forecasted temperature for a city.</span></span>  
  
 <span data-ttu-id="5c61b-110">Sulla pagina aspx del client [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], viene definito un controllo Web DataGrid che contiene la rappresentazione grafica dei dati restituiti dal servizio.</span><span class="sxs-lookup"><span data-stu-id="5c61b-110">On the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] client .aspx page, a DataGrid Web control is defined, which contains the graphical representation of the data returned by the service.</span></span> <span data-ttu-id="5c61b-111">Il codice presente sulla pagina aspx chiama il servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per ottenere i dati meteorologici e li restituisce a una matrice di oggetti `WeatherData`.</span><span class="sxs-lookup"><span data-stu-id="5c61b-111">Code on the .aspx page calls the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service for weather data and returns the data to an array of `WeatherData` objects.</span></span> <span data-ttu-id="5c61b-112">Il DataGrid specifica dove ottenere i dati impostando la proprietà `DataSource` su quella matrice.</span><span class="sxs-lookup"><span data-stu-id="5c61b-112">The DataGrid specifies where to get its data from by setting its `DataSource` property to that array.</span></span> <span data-ttu-id="5c61b-113">Si verifica l'associazione dati con una chiamata al metodo `DataBind` del DataGrid.</span><span class="sxs-lookup"><span data-stu-id="5c61b-113">The data binding occurs with a call to the DataGrid's `DataBind` method.</span></span> <span data-ttu-id="5c61b-114">Tutto il codice è contenuto all'interno di.`aspx`</span><span class="sxs-lookup"><span data-stu-id="5c61b-114">All of this code is contained inside the .`aspx`</span></span> <span data-ttu-id="5c61b-115">della pagina `Page_Load` metodo, pertanto ogni volta che l'utente aggiorna la pagina del browser, i dati viene aggiornato in DataGrid.</span><span class="sxs-lookup"><span data-stu-id="5c61b-115">page's `Page_Load` method, so every time the user refreshes the browser page, the data is updated in the DataGrid.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5c61b-116">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="5c61b-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="5c61b-117">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5c61b-117">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="5c61b-118">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5c61b-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="5c61b-119">Il client di questo esempio è un sito Web che è in esecuzione sotto un server Web di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="5c61b-119">This sample's client is a Web site that runs under a development Web server.</span></span> <span data-ttu-id="5c61b-120">Per avviare il server di sviluppo Web, digitare quanto segue al prompt dei comandi: "`%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`.</span><span class="sxs-lookup"><span data-stu-id="5c61b-120">To launch the development Web server, type the following at the command prompt: "`%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`.</span></span> <span data-ttu-id="5c61b-121">Quindi selezionare http://localhost:8000/client.</span><span class="sxs-lookup"><span data-stu-id="5c61b-121">Then browse to http://localhost:8000/client.</span></span> <span data-ttu-id="5c61b-122">Per eseguire questo esempio tra più computer, sostituire tutti i riferimenti a `localhost` nel file Web.config del client con il nome del computer che ospita il server.</span><span class="sxs-lookup"><span data-stu-id="5c61b-122">To run this sample across computers, replace all references to `localhost` in the client's Web.config file with the computer name of the server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5c61b-123">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="5c61b-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5c61b-124">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="5c61b-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5c61b-125">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5c61b-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5c61b-126">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="5c61b-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`  
  
## <a name="see-also"></a><span data-ttu-id="5c61b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c61b-127">See Also</span></span>

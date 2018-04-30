---
title: Accesso al servizio da un Web browser (Guida rapida di WCF Data Services)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5550e97d97adf28a84566c5d7936369656c65e43
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a><span data-ttu-id="47c96-102">Accesso al servizio da un Web browser (Guida rapida di WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="47c96-102">Accessing the Service from a Web Browser (WCF Data Services Quickstart)</span></span>
<span data-ttu-id="47c96-103">In questa attività si avvierà [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] da Visual Studio e si disabiliterà facoltativamente la lettura di feed nel browser.</span><span class="sxs-lookup"><span data-stu-id="47c96-103">In this task, you will start the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] from Visual Studio and optionally disable feed reading in the Web browser.</span></span> <span data-ttu-id="47c96-104">Si verrà quindi recuperare il documento di definizione del servizio, nonché accedere alle risorse del servizio dati inviando richieste GET HTTP attraverso un browser Web alle risorse esposte.</span><span class="sxs-lookup"><span data-stu-id="47c96-104">You will then retrieve the service definition document as well as access data service resources by submitting HTTP GET requests through a Web browser to the exposed resources.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47c96-105">Per impostazione predefinita, Visual Studio assegna automaticamente un numero di porta all'URI `localhost` del computer in uso.</span><span class="sxs-lookup"><span data-stu-id="47c96-105">By default, Visual Studio auto-assigns a port number to the `localhost` URI on your computer.</span></span> <span data-ttu-id="47c96-106">In questa attività viene usato il numero di porta `12345` negli URI di esempio.</span><span class="sxs-lookup"><span data-stu-id="47c96-106">This task uses the port number `12345` in the URI examples.</span></span> <span data-ttu-id="47c96-107">Per ulteriori informazioni su come impostare un numero di porta specifico nel progetto di Visual Studio, vedere [creazione del servizio dati](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="47c96-107">For more information about how to set a specific port number in your Visual Studio project see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
### <a name="to-request-the-default-service-document-by-using-internet-explorer"></a><span data-ttu-id="47c96-108">Per richiedere il documento di servizio predefinito usando Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="47c96-108">To request the default service document by using Internet Explorer</span></span>  
  
1.  <span data-ttu-id="47c96-109">In Internet Explorer dal **strumenti** dal menu **Opzioni Internet**, fare clic su di **contenuto** scheda, fare clic su **impostazioni**e deselezionare  **Attivare la visualizzazione di lettura feed**.</span><span class="sxs-lookup"><span data-stu-id="47c96-109">In Internet Explorer, from the **Tools** menu, select **Internet Options**, click the **Content** tab, click **Settings**, and clear **Turn on feed viewing**.</span></span>  
  
     <span data-ttu-id="47c96-110">In questo modo viene disabilitata la lettura dei feed.</span><span class="sxs-lookup"><span data-stu-id="47c96-110">This makes sure that feed reading is disabled.</span></span> <span data-ttu-id="47c96-111">Se non si disabilita questa funzionalità, anziché visualizzare i dati XML non elaborati, il browser considererà il documento con codifica AtomPub restituito come un feed XML.</span><span class="sxs-lookup"><span data-stu-id="47c96-111">If you do not disable this functionality, then the Web browser will treat the returned AtomPub encoded document as an XML feed instead of displaying the raw XML data.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="47c96-112">Se nel browser non è possibile visualizzare il feed come dati XML non elaborati, dovrebbe ancora essere possibile visualizzarlo come codice sorgente per la pagina.</span><span class="sxs-lookup"><span data-stu-id="47c96-112">If your browser cannot display the feed as raw XML data, you should still be able to view the feed as the source code for the page.</span></span>  
  
2.  <span data-ttu-id="47c96-113">In Visual Studio premere F5 per avviare il debug dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="47c96-113">In Visual Studio, press the F5 key to start debugging the application.</span></span>  
  
3.  <span data-ttu-id="47c96-114">Aprire un browser sul computer locale.</span><span class="sxs-lookup"><span data-stu-id="47c96-114">Open a Web browser on the local computer.</span></span> <span data-ttu-id="47c96-115">Nella barra degli indirizzi digitare l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="47c96-115">In the address bar, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc  
    ```  
  
     <span data-ttu-id="47c96-116">Verrà restituito il documento di servizio predefinito che contiene un elenco di set di entità esposti dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="47c96-116">This returns the default service document, which contains a list of entity sets that are exposed by this data service.</span></span>  
  
### <a name="to-access-entity-set-resources-from-a-web-browser"></a><span data-ttu-id="47c96-117">Per accedere alle risorse del set di entità da un browser</span><span class="sxs-lookup"><span data-stu-id="47c96-117">To access entity set resources from a Web browser</span></span>  
  
1.  <span data-ttu-id="47c96-118">Nella barra dell'indirizzo del browser immettere l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="47c96-118">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers  
    ```  
  
     <span data-ttu-id="47c96-119">Verrà restituito un set di tutti i clienti inclusi nel database Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="47c96-119">This returns a set of all customers in the Northwind sample database.</span></span>  
  
2.  <span data-ttu-id="47c96-120">Nella barra dell'indirizzo del browser immettere l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="47c96-120">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')  
    ```  
  
     <span data-ttu-id="47c96-121">Verrà restituita un'istanza di entità per il cliente specifico, `ALFKI`.</span><span class="sxs-lookup"><span data-stu-id="47c96-121">This returns an entity instance for the specific customer, `ALFKI`.</span></span>  
  
3.  <span data-ttu-id="47c96-122">Nella barra dell'indirizzo del browser immettere l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="47c96-122">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders  
    ```  
  
     <span data-ttu-id="47c96-123">Verrà attraversata la relazione tra clienti e ordini per restituire un set di tutti gli ordini per il cliente specifico `ALFKI`.</span><span class="sxs-lookup"><span data-stu-id="47c96-123">This traverses the relationship between customers and orders to return a set of all orders for the specific customer `ALFKI`.</span></span>  
  
4.  <span data-ttu-id="47c96-124">Nella barra dell'indirizzo del browser immettere l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="47c96-124">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643  
    ```  
  
     <span data-ttu-id="47c96-125">Verranno filtrati gli ordini che appartengono al cliente specifico `ALFKI`, in modo che venga restituito solo un ordine specifico in base al valore `OrderID` fornito.</span><span class="sxs-lookup"><span data-stu-id="47c96-125">This filters orders that belong to the specific customer `ALFKI` so that only a specific order is returned based on the supplied `OrderID` value.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="47c96-126">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="47c96-126">Next Steps</span></span>  
 <span data-ttu-id="47c96-127">L'accesso a [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] da un browser è stato eseguito correttamente, con il browser che invia richieste GET HTTP alle risorse specificate.</span><span class="sxs-lookup"><span data-stu-id="47c96-127">You have successfully accessed the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] from a Web browser, with the browser issuing HTTP GET requests to specified resources.</span></span> <span data-ttu-id="47c96-128">L'utilizzo di un browser consente di sperimentare il funzionamento della sintassi di indirizzamento delle richieste e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="47c96-128">A Web browser provides an easy way to experiment with the addressing syntax of requests and view the results.</span></span> <span data-ttu-id="47c96-129">L'accesso a un servizio dati di produzione non viene in genere eseguito mediante questo metodo.</span><span class="sxs-lookup"><span data-stu-id="47c96-129">However, a production data service is not generally accessed by this method.</span></span> <span data-ttu-id="47c96-130">Di norma, le applicazioni interagiscono con il servizio dati tramite linguaggi di codice delle applicazioni o di script.</span><span class="sxs-lookup"><span data-stu-id="47c96-130">Typically, applications interact with the data service through application code or scripting languages.</span></span> <span data-ttu-id="47c96-131">Si creerà quindi un'applicazione client che utilizza librerie client per accedere alle risorse del servizio dati come se fossero oggetti CLR (Common Language Runtime):</span><span class="sxs-lookup"><span data-stu-id="47c96-131">Next, you will create a client application that uses client libraries to access data service resources as if they were common language runtime (CLR) objects:</span></span>  
  
 [<span data-ttu-id="47c96-132">Creazione dell'applicazione client .NET Framework</span><span class="sxs-lookup"><span data-stu-id="47c96-132">Creating the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a><span data-ttu-id="47c96-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47c96-133">See Also</span></span>  
 [<span data-ttu-id="47c96-134">Accesso alle risorse di un servizio dati</span><span class="sxs-lookup"><span data-stu-id="47c96-134">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)

---
title: Accesso al servizio da un Web browser (Guida rapida di WCF Data Services)
ms.date: 03/30/2017
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
ms.openlocfilehash: 01184969b7bfcc0f68351db7c8daeebe79be583c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392323"
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a><span data-ttu-id="a82ba-102">Accesso al servizio da un Web browser (Guida rapida di WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="a82ba-102">Accessing the Service from a Web Browser (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="a82ba-103">Questa è la seconda attività di avvio rapido di WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="a82ba-103">This is the second task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="a82ba-104">In questa attività si avvia WCF Data Services da Visual Studio e, facoltativamente, disabilita la lettura di feed nel Web browser.</span><span class="sxs-lookup"><span data-stu-id="a82ba-104">In this task, you start the WCF Data Services from Visual Studio and optionally disable feed reading in the Web browser.</span></span> <span data-ttu-id="a82ba-105">È quindi recuperare il documento di definizione del servizio, nonché accedere alle risorse del servizio dati inviando richieste GET HTTP attraverso un browser alle risorse esposte.</span><span class="sxs-lookup"><span data-stu-id="a82ba-105">You then retrieve the service definition document as well as access data service resources by submitting HTTP GET requests through a Web browser to the exposed resources.</span></span>

> [!NOTE]
> <span data-ttu-id="a82ba-106">Per impostazione predefinita, Visual Studio assegna automaticamente un numero di porta all'URI `localhost` del computer in uso.</span><span class="sxs-lookup"><span data-stu-id="a82ba-106">By default, Visual Studio auto-assigns a port number to the `localhost` URI on your computer.</span></span> <span data-ttu-id="a82ba-107">In questa attività viene usato il numero di porta `12345` negli URI di esempio.</span><span class="sxs-lookup"><span data-stu-id="a82ba-107">This task uses the port number `12345` in the URI examples.</span></span> <span data-ttu-id="a82ba-108">Per altre informazioni su come impostare un numero di porta specifico nel progetto di Visual Studio, vedere [creazione del servizio dati](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="a82ba-108">For more information about how to set a specific port number in your Visual Studio project see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>

## <a name="to-request-the-default-service-document-by-using-internet-explorer"></a><span data-ttu-id="a82ba-109">Per richiedere il documento di servizio predefinito usando Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="a82ba-109">To request the default service document by using Internet Explorer</span></span>

1.  <span data-ttu-id="a82ba-110">In Internet Explorer dal **degli strumenti** dal menu **Opzioni Internet**, fare clic sul **contenuto** scheda, fare clic su **impostazioni**e deselezionare  **Attivare la visualizzazione di lettura feed**.</span><span class="sxs-lookup"><span data-stu-id="a82ba-110">In Internet Explorer, from the **Tools** menu, select **Internet Options**, click the **Content** tab, click **Settings**, and clear **Turn on feed viewing**.</span></span>

     <span data-ttu-id="a82ba-111">In questo modo viene disabilitata la lettura dei feed.</span><span class="sxs-lookup"><span data-stu-id="a82ba-111">This makes sure that feed reading is disabled.</span></span> <span data-ttu-id="a82ba-112">Se non si disabilita questa funzionalità, anziché visualizzare i dati XML non elaborati, il browser considererà il documento con codifica AtomPub restituito come un feed XML.</span><span class="sxs-lookup"><span data-stu-id="a82ba-112">If you do not disable this functionality, then the Web browser will treat the returned AtomPub encoded document as an XML feed instead of displaying the raw XML data.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a82ba-113">Se nel browser non è possibile visualizzare il feed come dati XML non elaborati, dovrebbe ancora essere possibile visualizzarlo come codice sorgente per la pagina.</span><span class="sxs-lookup"><span data-stu-id="a82ba-113">If your browser cannot display the feed as raw XML data, you should still be able to view the feed as the source code for the page.</span></span>

2.  <span data-ttu-id="a82ba-114">In Visual Studio, premere il **F5** tasto per avviare il debug dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a82ba-114">In Visual Studio, press the **F5** key to start debugging the application.</span></span>

3.  <span data-ttu-id="a82ba-115">Aprire un browser sul computer locale.</span><span class="sxs-lookup"><span data-stu-id="a82ba-115">Open a Web browser on the local computer.</span></span> <span data-ttu-id="a82ba-116">Nella barra degli indirizzi digitare l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="a82ba-116">In the address bar, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc
    ```

     <span data-ttu-id="a82ba-117">Verrà restituito il documento di servizio predefinito che contiene un elenco di set di entità esposti dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="a82ba-117">This returns the default service document, which contains a list of entity sets that are exposed by this data service.</span></span>

## <a name="to-access-entity-set-resources-from-a-web-browser"></a><span data-ttu-id="a82ba-118">Per accedere alle risorse del set di entità da un browser</span><span class="sxs-lookup"><span data-stu-id="a82ba-118">To access entity set resources from a Web browser</span></span>

1.  <span data-ttu-id="a82ba-119">Nella barra dell'indirizzo del browser immettere l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="a82ba-119">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers
    ```

     <span data-ttu-id="a82ba-120">Verrà restituito un set di tutti i clienti inclusi nel database Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="a82ba-120">This returns a set of all customers in the Northwind sample database.</span></span>

2.  <span data-ttu-id="a82ba-121">Nella barra dell'indirizzo del browser immettere l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="a82ba-121">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')
    ```

     <span data-ttu-id="a82ba-122">Verrà restituita un'istanza di entità per il cliente specifico, `ALFKI`.</span><span class="sxs-lookup"><span data-stu-id="a82ba-122">This returns an entity instance for the specific customer, `ALFKI`.</span></span>

3.  <span data-ttu-id="a82ba-123">Nella barra dell'indirizzo del browser immettere l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="a82ba-123">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders
    ```

     <span data-ttu-id="a82ba-124">Verrà attraversata la relazione tra clienti e ordini per restituire un set di tutti gli ordini per il cliente specifico `ALFKI`.</span><span class="sxs-lookup"><span data-stu-id="a82ba-124">This traverses the relationship between customers and orders to return a set of all orders for the specific customer `ALFKI`.</span></span>

4.  <span data-ttu-id="a82ba-125">Nella barra dell'indirizzo del browser immettere l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="a82ba-125">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643
    ```

     <span data-ttu-id="a82ba-126">Verranno filtrati gli ordini che appartengono al cliente specifico `ALFKI`, in modo che venga restituito solo un ordine specifico in base al valore `OrderID` fornito.</span><span class="sxs-lookup"><span data-stu-id="a82ba-126">This filters orders that belong to the specific customer `ALFKI` so that only a specific order is returned based on the supplied `OrderID` value.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a82ba-127">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a82ba-127">Next Steps</span></span>

<span data-ttu-id="a82ba-128">L'accesso di WCF Data Services da un Web browser, con il browser invia HTTP GET richieste alle risorse specificate è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="a82ba-128">You have successfully accessed the WCF Data Services from a Web browser, with the browser issuing HTTP GET requests to specified resources.</span></span> <span data-ttu-id="a82ba-129">L'utilizzo di un browser consente di sperimentare il funzionamento della sintassi di indirizzamento delle richieste e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="a82ba-129">A Web browser provides an easy way to experiment with the addressing syntax of requests and view the results.</span></span> <span data-ttu-id="a82ba-130">L'accesso a un servizio dati di produzione non viene in genere eseguito mediante questo metodo.</span><span class="sxs-lookup"><span data-stu-id="a82ba-130">However, a production data service is not generally accessed by this method.</span></span> <span data-ttu-id="a82ba-131">Di norma, le applicazioni interagiscono con il servizio dati tramite linguaggi di codice delle applicazioni o di script.</span><span class="sxs-lookup"><span data-stu-id="a82ba-131">Typically, applications interact with the data service through application code or scripting languages.</span></span> <span data-ttu-id="a82ba-132">Si creerà quindi un'applicazione client che utilizza librerie client per accedere alle risorse del servizio dati come se fossero oggetti CLR (Common Language Runtime):</span><span class="sxs-lookup"><span data-stu-id="a82ba-132">Next, you will create a client application that uses client libraries to access data service resources as if they were common language runtime (CLR) objects:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a82ba-133">Creazione dell'applicazione client .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a82ba-133">Creating the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="a82ba-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a82ba-134">See Also</span></span>

- [<span data-ttu-id="a82ba-135">Accesso alle risorse di un servizio dati</span><span class="sxs-lookup"><span data-stu-id="a82ba-135">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)

---
title: Accesso al servizio da un Web browser (Guida rapida di WCF Data Services)
description: Informazioni su come avviare WCF Data Services in Visual Studio e disabilitare la lettura del feed in un browser. Ottenere il documento di definizione del servizio e accedere alle risorse del servizio dati.
ms.date: 03/30/2017
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
ms.openlocfilehash: 713436c31bc3f622c4f44a83e33fff3fcbba1c1c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247778"
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a><span data-ttu-id="932c0-104">Accesso al servizio da un Web browser (Guida rapida di WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="932c0-104">Accessing the Service from a Web Browser (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="932c0-105">Questa è la seconda attività del WCF Data Services avvio rapido.</span><span class="sxs-lookup"><span data-stu-id="932c0-105">This is the second task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="932c0-106">In questa attività si avvia il WCF Data Services da Visual Studio e, facoltativamente, si disabilita la lettura del feed nel Web browser.</span><span class="sxs-lookup"><span data-stu-id="932c0-106">In this task, you start the WCF Data Services from Visual Studio and optionally disable feed reading in the Web browser.</span></span> <span data-ttu-id="932c0-107">È quindi possibile recuperare il documento di definizione del servizio e accedere alle risorse del servizio dati inviando richieste HTTP GET tramite un Web browser alle risorse esposte.</span><span class="sxs-lookup"><span data-stu-id="932c0-107">You then retrieve the service definition document as well as access data service resources by submitting HTTP GET requests through a Web browser to the exposed resources.</span></span>

> [!NOTE]
> <span data-ttu-id="932c0-108">Per impostazione predefinita, Visual Studio assegna automaticamente un numero di porta all'URI `localhost` del computer in uso.</span><span class="sxs-lookup"><span data-stu-id="932c0-108">By default, Visual Studio auto-assigns a port number to the `localhost` URI on your computer.</span></span> <span data-ttu-id="932c0-109">In questa attività viene usato il numero di porta `12345` negli URI di esempio.</span><span class="sxs-lookup"><span data-stu-id="932c0-109">This task uses the port number `12345` in the URI examples.</span></span> <span data-ttu-id="932c0-110">Per ulteriori informazioni su come impostare un numero di porta specifico nel progetto di Visual Studio, vedere [creazione del servizio dati](creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="932c0-110">For more information about how to set a specific port number in your Visual Studio project see [Creating the Data Service](creating-the-data-service.md).</span></span>

## <a name="to-request-the-default-service-document-by-using-internet-explorer"></a><span data-ttu-id="932c0-111">Per richiedere il documento di servizio predefinito usando Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="932c0-111">To request the default service document by using Internet Explorer</span></span>

1. <span data-ttu-id="932c0-112">In Internet Explorer scegliere **Opzioni Internet**dal menu **strumenti** , fare clic sulla scheda **contenuto** , fare clic su **Impostazioni**e deselezionare **Attiva visualizzazione feed**.</span><span class="sxs-lookup"><span data-stu-id="932c0-112">In Internet Explorer, from the **Tools** menu, select **Internet Options**, click the **Content** tab, click **Settings**, and clear **Turn on feed viewing**.</span></span>

     <span data-ttu-id="932c0-113">In questo modo viene disabilitata la lettura dei feed.</span><span class="sxs-lookup"><span data-stu-id="932c0-113">This makes sure that feed reading is disabled.</span></span> <span data-ttu-id="932c0-114">Se non si disabilita questa funzionalità, anziché visualizzare i dati XML non elaborati, il browser considererà il documento con codifica AtomPub restituito come un feed XML.</span><span class="sxs-lookup"><span data-stu-id="932c0-114">If you do not disable this functionality, then the Web browser will treat the returned AtomPub encoded document as an XML feed instead of displaying the raw XML data.</span></span>

    > [!NOTE]
    > <span data-ttu-id="932c0-115">Se nel browser non è possibile visualizzare il feed come dati XML non elaborati, dovrebbe ancora essere possibile visualizzarlo come codice sorgente per la pagina.</span><span class="sxs-lookup"><span data-stu-id="932c0-115">If your browser cannot display the feed as raw XML data, you should still be able to view the feed as the source code for the page.</span></span>

2. <span data-ttu-id="932c0-116">In Visual Studio premere il tasto **F5** per avviare il debug dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="932c0-116">In Visual Studio, press the **F5** key to start debugging the application.</span></span>

3. <span data-ttu-id="932c0-117">Aprire un browser sul computer locale.</span><span class="sxs-lookup"><span data-stu-id="932c0-117">Open a Web browser on the local computer.</span></span> <span data-ttu-id="932c0-118">Nella barra degli indirizzi digitare l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="932c0-118">In the address bar, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc
    ```

     <span data-ttu-id="932c0-119">Verrà restituito il documento di servizio predefinito che contiene un elenco di set di entità esposti dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="932c0-119">This returns the default service document, which contains a list of entity sets that are exposed by this data service.</span></span>

## <a name="to-access-entity-set-resources-from-a-web-browser"></a><span data-ttu-id="932c0-120">Per accedere alle risorse del set di entità da un browser</span><span class="sxs-lookup"><span data-stu-id="932c0-120">To access entity set resources from a Web browser</span></span>

1. <span data-ttu-id="932c0-121">Nella barra dell'indirizzo del browser immettere l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="932c0-121">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers
    ```

     <span data-ttu-id="932c0-122">Verrà restituito un set di tutti i clienti inclusi nel database Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="932c0-122">This returns a set of all customers in the Northwind sample database.</span></span>

2. <span data-ttu-id="932c0-123">Nella barra dell'indirizzo del browser immettere l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="932c0-123">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')
    ```

     <span data-ttu-id="932c0-124">Verrà restituita un'istanza di entità per il cliente specifico, `ALFKI`.</span><span class="sxs-lookup"><span data-stu-id="932c0-124">This returns an entity instance for the specific customer, `ALFKI`.</span></span>

3. <span data-ttu-id="932c0-125">Nella barra dell'indirizzo del browser immettere l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="932c0-125">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders
    ```

     <span data-ttu-id="932c0-126">Verrà attraversata la relazione tra clienti e ordini per restituire un set di tutti gli ordini per il cliente specifico `ALFKI`.</span><span class="sxs-lookup"><span data-stu-id="932c0-126">This traverses the relationship between customers and orders to return a set of all orders for the specific customer `ALFKI`.</span></span>

4. <span data-ttu-id="932c0-127">Nella barra dell'indirizzo del browser immettere l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="932c0-127">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643
    ```

     <span data-ttu-id="932c0-128">Verranno filtrati gli ordini che appartengono al cliente specifico `ALFKI`, in modo che venga restituito solo un ordine specifico in base al valore `OrderID` fornito.</span><span class="sxs-lookup"><span data-stu-id="932c0-128">This filters orders that belong to the specific customer `ALFKI` so that only a specific order is returned based on the supplied `OrderID` value.</span></span>

## <a name="next-steps"></a><span data-ttu-id="932c0-129">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="932c0-129">Next Steps</span></span>

<span data-ttu-id="932c0-130">È stato eseguito l'accesso al WCF Data Services da un Web browser, con il browser che invia richieste HTTP GET alle risorse specificate.</span><span class="sxs-lookup"><span data-stu-id="932c0-130">You have successfully accessed the WCF Data Services from a Web browser, with the browser issuing HTTP GET requests to specified resources.</span></span> <span data-ttu-id="932c0-131">L'utilizzo di un browser consente di sperimentare il funzionamento della sintassi di indirizzamento delle richieste e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="932c0-131">A Web browser provides an easy way to experiment with the addressing syntax of requests and view the results.</span></span> <span data-ttu-id="932c0-132">L'accesso a un servizio dati di produzione non viene in genere eseguito mediante questo metodo.</span><span class="sxs-lookup"><span data-stu-id="932c0-132">However, a production data service is not generally accessed by this method.</span></span> <span data-ttu-id="932c0-133">Di norma, le applicazioni interagiscono con il servizio dati tramite linguaggi di codice delle applicazioni o di script.</span><span class="sxs-lookup"><span data-stu-id="932c0-133">Typically, applications interact with the data service through application code or scripting languages.</span></span> <span data-ttu-id="932c0-134">Si creerà quindi un'applicazione client che utilizza librerie client per accedere alle risorse del servizio dati come se fossero oggetti CLR (Common Language Runtime):</span><span class="sxs-lookup"><span data-stu-id="932c0-134">Next, you will create a client application that uses client libraries to access data service resources as if they were common language runtime (CLR) objects:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="932c0-135">Creazione dell'applicazione client .NET Framework</span><span class="sxs-lookup"><span data-stu-id="932c0-135">Creating the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="932c0-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="932c0-136">See also</span></span>

- [<span data-ttu-id="932c0-137">Accesso alle risorse di un servizio dati</span><span class="sxs-lookup"><span data-stu-id="932c0-137">Accessing Data Service Resources</span></span>](accessing-data-service-resources-wcf-data-services.md)

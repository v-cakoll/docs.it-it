---
title: Esempio di federazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e9da0ca-e925-4644-aa96-8bfaf649d4bb
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b66bf65ba6165902eb90191a262f2715424d8b7e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="federation-sample"></a><span data-ttu-id="99152-102">Esempio di federazione</span><span class="sxs-lookup"><span data-stu-id="99152-102">Federation Sample</span></span>
<span data-ttu-id="99152-103">Nell'esempio viene illustrata la sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="99152-103">This sample demonstrates federated security.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="99152-104">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="99152-104">Sample Details</span></span>  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="99152-105"> fornisce supporto per la distribuzione di architetture di sicurezza federate tramite `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="99152-105"> provides support for deploying federated security architectures through the `wsFederationHttpBinding`.</span></span> <span data-ttu-id="99152-106">L'elemento `wsFederationHttpBinding` offre un'associazione sicura, affidabile e interoperativa che comporta l'utilizzo di HTTP come meccanismo di trasporto sottostante per la comunicazione request/reply e Text/XML come formato di trasmissione per la codifica.</span><span class="sxs-lookup"><span data-stu-id="99152-106">The `wsFederationHttpBinding` provides a secure, reliable, and interoperable binding that involves the use of HTTP as the underlying transport mechanism for request/reply communication, and Text/XML as the wire format for encoding.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="99152-107">Federazione in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vedere [federazione](../../../../docs/framework/wcf/feature-details/federation.md).</span><span class="sxs-lookup"><span data-stu-id="99152-107"> Federation in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], see [Federation](../../../../docs/framework/wcf/feature-details/federation.md).</span></span>  
  
 <span data-ttu-id="99152-108">Lo scenario è costituito da 4 elementi:</span><span class="sxs-lookup"><span data-stu-id="99152-108">The scenario is made up of 4 pieces:</span></span>  
  
-   <span data-ttu-id="99152-109">Servizio della libreria</span><span class="sxs-lookup"><span data-stu-id="99152-109">BookStore service</span></span>  
  
-   <span data-ttu-id="99152-110">Servizio token di protezione della libreria</span><span class="sxs-lookup"><span data-stu-id="99152-110">BookStore STS</span></span>  
  
-   <span data-ttu-id="99152-111">Servizio token di protezione HomeRealm</span><span class="sxs-lookup"><span data-stu-id="99152-111">HomeRealm STS</span></span>  
  
-   <span data-ttu-id="99152-112">Client della libreria</span><span class="sxs-lookup"><span data-stu-id="99152-112">BookStore Client</span></span>  
  
 <span data-ttu-id="99152-113">Il servizio della libreria supporta due operazioni, `BrowseBooks` e `BuyBook`.</span><span class="sxs-lookup"><span data-stu-id="99152-113">The BookStore service supports two operations, `BrowseBooks` and `BuyBook`.</span></span> <span data-ttu-id="99152-114">Consente accesso anonimo all'operazione `BrowseBooks`, ma richiede accesso autenticato per l'operazione `BuyBooks`.</span><span class="sxs-lookup"><span data-stu-id="99152-114">It allows anonymous access to the `BrowseBooks` operation, but requires authenticated access to access the `BuyBooks` operation.</span></span> <span data-ttu-id="99152-115">L'autenticazione prende il form di un token pubblicato dal Servizio token di sicurezza della libreria.</span><span class="sxs-lookup"><span data-stu-id="99152-115">The authentication takes the form of a token issued by the BookStore STS.</span></span> <span data-ttu-id="99152-116">Il file di configurazione per Servizio della Libreria punta i client al Servizio token di protezione della libreria utilizzando l'`wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="99152-116">The configuration file for the BookStore Service points clients to the BookStore STS using the `wsFederationHttpBinding`.</span></span>  
  
```xml  
<wsFederationHttpBinding>  
<!-- This is the Service binding for the BuyBooks endpoint. It redirects clients to the BookStore STS -->  
    <binding name='BuyBookBinding'>  
        <security mode="Message">  
            <message>  
                <issuerMetadata  
  address='http://localhost/FederationSample/BookStoreSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='BookStoreSTS.com'/>  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 <span data-ttu-id="99152-117">Il servizio token di protezione della libreria richiede quindi che i client si autentichino utilizzando un token pubblicato dal servizio token di protezione HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="99152-117">The BookStore STS then requires that clients authenticate using a token issued by the HomeRealm STS.</span></span> <span data-ttu-id="99152-118">Anche in questo caso, il file di configurazione per il servizio token di protezione della libreria punta i client al servizio token di protezione HomeRealm utilizzando `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="99152-118">Again, the configuration file for the BookStore STS points clients to the HomeRealm STS using the `wsFederationHttpBinding`.</span></span>  
  
```xml  
<wsFederationHttpBinding>  
 <!-- This is the binding for the clients requesting tokens from this STS. It redirects clients to the HomeRealm STS -->  
    <binding name='BookStoreSTSBinding'>  
        <security mode='Message'>  
            <message>  
                <issuerMetadata  
 address='http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='HomeRealmSTS.com' />  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 <span data-ttu-id="99152-119">La sequenza di eventi quando si accede all'operazione `BuyBook` è la seguente:</span><span class="sxs-lookup"><span data-stu-id="99152-119">The sequence of events when accessing the `BuyBook` operation is as follows:</span></span>  
  
1.  <span data-ttu-id="99152-120">Il client effettua l'accesso al servizio token di sicurezza HomeRealm utilizzando le credenziali di Windows.</span><span class="sxs-lookup"><span data-stu-id="99152-120">The client authenticates to the HomeRealm STS using Windows credentials.</span></span>  
  
2.  <span data-ttu-id="99152-121">Il servizio token di protezione HomeRealm pubblica un token che può essere utilizzato per accedere al servizio token di protezione della libreria.</span><span class="sxs-lookup"><span data-stu-id="99152-121">The HomeRealm STS issues a token that can be used to authenticate to the BookStore STS.</span></span>  
  
3.  <span data-ttu-id="99152-122">Il client accede al servizio token di protezione della libreria utilizzando il token pubblicato dal servizio token di protezione HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="99152-122">The client authenticates to the BookStore STS using the token issued by the HomeRealm STS.</span></span>  
  
4.  <span data-ttu-id="99152-123">Il servizio token di protezione della libreria pubblica un token che può essere utilizzato per accedere al servizio della libreria.</span><span class="sxs-lookup"><span data-stu-id="99152-123">The BookStore STS issues a token that can be used to authenticate to the BookStore Service.</span></span>  
  
5.  <span data-ttu-id="99152-124">Il client accede a al servizio della libreria utilizzando il token pubblicato dal servizio token di sicurezza della libreria.</span><span class="sxs-lookup"><span data-stu-id="99152-124">The client authenticates to the BookStore service using the token issued by the BookStore STS.</span></span>  
  
6.  <span data-ttu-id="99152-125">Il client accede all'operazione `BuyBook`.</span><span class="sxs-lookup"><span data-stu-id="99152-125">The client accesses the `BuyBook` operation.</span></span>  
  
 <span data-ttu-id="99152-126">Vedere le istruzioni seguenti su come impostare ed eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="99152-126">See the following instructions about how to set up and run this sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99152-127">È necessario disporre delle autorizzazioni di scrittura per il **wwwroot** directory per eseguire questo esempio.</span><span class="sxs-lookup"><span data-stu-id="99152-127">You must have Write permissions to the **wwwroot** directory to run this sample.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="99152-128">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="99152-128">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="99152-129">Aprire la finestra del prompt dei comandi SDK.</span><span class="sxs-lookup"><span data-stu-id="99152-129">Open the SDK command window.</span></span> <span data-ttu-id="99152-130">Nel percorso di esempio, eseguire Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="99152-130">In the sample path, run Setup.bat.</span></span> <span data-ttu-id="99152-131">Ciò crea le directory virtuali richieste per l'esempio e installa i certificati obbligatori con le autorizzazioni adeguate.</span><span class="sxs-lookup"><span data-stu-id="99152-131">This creates the virtual directories required for the sample and installs the required certificates with appropriate permissions.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="99152-132">Il file batch Setup.bat è progettato per essere eseguito da un prompt dei comandi di SDK di Windows.</span><span class="sxs-lookup"><span data-stu-id="99152-132">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="99152-133">e richiede che la variabile di ambiente MSSDK punti alla directory in cui è installato SDK.</span><span class="sxs-lookup"><span data-stu-id="99152-133">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="99152-134">Questa variabile di ambiente viene impostata automaticamente all'interno di un prompt dei comandi di SDK di Windows.</span><span class="sxs-lookup"><span data-stu-id="99152-134">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span> <span data-ttu-id="99152-135">In [!INCLUDE[wv](../../../../includes/wv-md.md)], è necessario assicurarsi che Compatibilità di gestione con IIS 6.0 sia installato perché la configurazione utilizza script amministrativi di IIS.</span><span class="sxs-lookup"><span data-stu-id="99152-135">On [!INCLUDE[wv](../../../../includes/wv-md.md)], you must ensure that IIS 6.0 Management Compatibility is installed because the set up uses IIS administrator scripts.</span></span> <span data-ttu-id="99152-136">L'esecuzione dello script di installazione in [!INCLUDE[wv](../../../../includes/wv-md.md)] richiede privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="99152-136">Running the set-up script on [!INCLUDE[wv](../../../../includes/wv-md.md)] requires administrator privileges.</span></span>  
  
2.  <span data-ttu-id="99152-137">Aprire FederationSample.sln in Visual Studio e selezionare **Compila soluzione** dal **compilare** menu.</span><span class="sxs-lookup"><span data-stu-id="99152-137">Open FederationSample.sln in Visual Studio and select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="99152-138">Compila i file di progetto comuni, il servizio della libreria, gli STS della libreria, gli STS di HomeRealm e li distribuisce in IIS.</span><span class="sxs-lookup"><span data-stu-id="99152-138">This builds the common project files, Bookstore service, Bookstore STS, HomeRealm STS, and deploys them in IIS.</span></span> <span data-ttu-id="99152-139">Compila anche l'applicazione client della libreria e posiziona il file eseguibile BookStoreClient.exe nella cartella FederationSample\BookStoreClient\bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="99152-139">This also builds the Bookstore client application and places the executable BookStoreClient.exe in the FederationSample\BookStoreClient\bin\Debug folder.</span></span>  
  
3.  <span data-ttu-id="99152-140">Fare doppio clic su BookStoreClient.exe.</span><span class="sxs-lookup"><span data-stu-id="99152-140">Double-click BookStoreClient.exe.</span></span> <span data-ttu-id="99152-141">Verrà visualizzata la finestra BookStoreClient.</span><span class="sxs-lookup"><span data-stu-id="99152-141">The BookStoreClient window is displayed.</span></span>  
  
4.  <span data-ttu-id="99152-142">È possibile esplorare i libri disponibili nella libreria facendo **Sfoglia libri**.</span><span class="sxs-lookup"><span data-stu-id="99152-142">You can browse the books available in the bookstore by clicking **Browse Books**.</span></span>  
  
5.  <span data-ttu-id="99152-143">Per acquistare un particolare libro, selezionarlo dall'elenco e fare clic su **acquista libro**.</span><span class="sxs-lookup"><span data-stu-id="99152-143">To purchase a particular book, select the book in the list and click **Buy Book**.</span></span> <span data-ttu-id="99152-144">L'applicazione si avvia e effettua l'autenticazione utilizzando l'autenticazione di Windows con il servizio token di protezione HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="99152-144">The application starts up and authenticates using Windows authentication with the HomeRealm Security Token Service.</span></span>  
  
     <span data-ttu-id="99152-145">L'esempio è configurato per consentire agli utenti di acquistare libri che costano 15$ o meno.</span><span class="sxs-lookup"><span data-stu-id="99152-145">The sample is configured to allow users to purchase books that cost $15 or less.</span></span> <span data-ttu-id="99152-146">Il tentativo di acquistare volumi che costano più di 15$ comporta il ricevimento da parte del client di un messaggio Accesso negato dal servizio della libreria.</span><span class="sxs-lookup"><span data-stu-id="99152-146">Attempting to buy books that cost more than $15 results in the client getting an Access Denied message from the Book Store Service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="99152-147">L'esempio non aggiorna il limite di credito dell'utente dopo un acquisto.</span><span class="sxs-lookup"><span data-stu-id="99152-147">The sample does not update the user’s credit limit after a purchase.</span></span> <span data-ttu-id="99152-148">È possibile acquistare ripetutamente libri entro i limiti di credito (fissi) dell'utente.</span><span class="sxs-lookup"><span data-stu-id="99152-148">You can repeatedly purchase books within the user’s (fixed) credit limit.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="99152-149">Per eseguire la pulizia</span><span class="sxs-lookup"><span data-stu-id="99152-149">To clean up</span></span>  
  
1.  <span data-ttu-id="99152-150">Eseguire Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="99152-150">Run Cleanup.bat.</span></span> <span data-ttu-id="99152-151">Ciò consente di eliminare le directory virtuali create durante l'installazione e di rimuovere inoltre i certificati installati durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="99152-151">This deletes the virtual directories that were created during set up and also removes the certificates installed during setup.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="99152-152">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="99152-152">The samples may already be installed on your machine.</span></span> <span data-ttu-id="99152-153">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="99152-153">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="99152-154">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99152-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="99152-155">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="99152-155">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Federation`  
  
## <a name="see-also"></a><span data-ttu-id="99152-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99152-156">See Also</span></span>

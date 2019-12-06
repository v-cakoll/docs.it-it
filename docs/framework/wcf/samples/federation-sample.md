---
title: Esempio di federazione
ms.date: 03/30/2017
ms.assetid: 7e9da0ca-e925-4644-aa96-8bfaf649d4bb
ms.openlocfilehash: c143ad9315df94a2d836a2c2c742ffa9a7728511
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837883"
---
# <a name="federation-sample"></a><span data-ttu-id="b753c-102">Esempio di federazione</span><span class="sxs-lookup"><span data-stu-id="b753c-102">Federation Sample</span></span>
<span data-ttu-id="b753c-103">Nell'esempio viene illustrata la sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="b753c-103">This sample demonstrates federated security.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="b753c-104">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="b753c-104">Sample Details</span></span>  
 <span data-ttu-id="b753c-105">Windows Communication Foundation (WCF) fornisce il supporto per la distribuzione di architetture di sicurezza federata tramite l'`wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="b753c-105">Windows Communication Foundation (WCF) provides support for deploying federated security architectures through the `wsFederationHttpBinding`.</span></span> <span data-ttu-id="b753c-106">L'elemento `wsFederationHttpBinding` offre un'associazione sicura, affidabile e interoperativa che comporta l'utilizzo di HTTP come meccanismo di trasporto sottostante per la comunicazione request/reply e Text/XML come formato di trasmissione per la codifica.</span><span class="sxs-lookup"><span data-stu-id="b753c-106">The `wsFederationHttpBinding` provides a secure, reliable, and interoperable binding that involves the use of HTTP as the underlying transport mechanism for request/reply communication, and Text/XML as the wire format for encoding.</span></span> <span data-ttu-id="b753c-107">Per ulteriori informazioni sulla Federazione in WCF, vedere [Federazione](../../../../docs/framework/wcf/feature-details/federation.md).</span><span class="sxs-lookup"><span data-stu-id="b753c-107">For more information about Federation in WCF, see [Federation](../../../../docs/framework/wcf/feature-details/federation.md).</span></span>  
  
 <span data-ttu-id="b753c-108">Lo scenario è costituito da 4 elementi:</span><span class="sxs-lookup"><span data-stu-id="b753c-108">The scenario is made up of 4 pieces:</span></span>  
  
- <span data-ttu-id="b753c-109">Servizio della libreria</span><span class="sxs-lookup"><span data-stu-id="b753c-109">BookStore service</span></span>  
  
- <span data-ttu-id="b753c-110">Servizio token di protezione della libreria</span><span class="sxs-lookup"><span data-stu-id="b753c-110">BookStore STS</span></span>  
  
- <span data-ttu-id="b753c-111">Servizio token di protezione HomeRealm</span><span class="sxs-lookup"><span data-stu-id="b753c-111">HomeRealm STS</span></span>  
  
- <span data-ttu-id="b753c-112">Client della libreria</span><span class="sxs-lookup"><span data-stu-id="b753c-112">BookStore Client</span></span>  
  
 <span data-ttu-id="b753c-113">Il servizio della libreria supporta due operazioni, `BrowseBooks` e `BuyBook`.</span><span class="sxs-lookup"><span data-stu-id="b753c-113">The BookStore service supports two operations, `BrowseBooks` and `BuyBook`.</span></span> <span data-ttu-id="b753c-114">Consente accesso anonimo all'operazione `BrowseBooks`, ma richiede accesso autenticato per l'operazione `BuyBooks`.</span><span class="sxs-lookup"><span data-stu-id="b753c-114">It allows anonymous access to the `BrowseBooks` operation, but requires authenticated access to access the `BuyBooks` operation.</span></span> <span data-ttu-id="b753c-115">L'autenticazione prende il form di un token pubblicato dal Servizio token di sicurezza della libreria.</span><span class="sxs-lookup"><span data-stu-id="b753c-115">The authentication takes the form of a token issued by the BookStore STS.</span></span> <span data-ttu-id="b753c-116">Il file di configurazione per Servizio della Libreria punta i client al Servizio token di protezione della libreria utilizzando l'`wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="b753c-116">The configuration file for the BookStore Service points clients to the BookStore STS using the `wsFederationHttpBinding`.</span></span>  
  
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
  
 <span data-ttu-id="b753c-117">Il servizio token di protezione della libreria richiede quindi che i client si autentichino utilizzando un token pubblicato dal servizio token di protezione HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="b753c-117">The BookStore STS then requires that clients authenticate using a token issued by the HomeRealm STS.</span></span> <span data-ttu-id="b753c-118">Anche in questo caso, il file di configurazione per il servizio token di protezione della libreria punta i client al servizio token di protezione HomeRealm utilizzando `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="b753c-118">Again, the configuration file for the BookStore STS points clients to the HomeRealm STS using the `wsFederationHttpBinding`.</span></span>  
  
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
  
 <span data-ttu-id="b753c-119">La sequenza di eventi quando si accede all'operazione `BuyBook` è la seguente:</span><span class="sxs-lookup"><span data-stu-id="b753c-119">The sequence of events when accessing the `BuyBook` operation is as follows:</span></span>  
  
1. <span data-ttu-id="b753c-120">Il client effettua l'accesso al servizio token di sicurezza HomeRealm utilizzando le credenziali di Windows.</span><span class="sxs-lookup"><span data-stu-id="b753c-120">The client authenticates to the HomeRealm STS using Windows credentials.</span></span>  
  
2. <span data-ttu-id="b753c-121">Il servizio token di protezione HomeRealm pubblica un token che può essere utilizzato per accedere al servizio token di protezione della libreria.</span><span class="sxs-lookup"><span data-stu-id="b753c-121">The HomeRealm STS issues a token that can be used to authenticate to the BookStore STS.</span></span>  
  
3. <span data-ttu-id="b753c-122">Il client accede al servizio token di protezione della libreria utilizzando il token pubblicato dal servizio token di protezione HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="b753c-122">The client authenticates to the BookStore STS using the token issued by the HomeRealm STS.</span></span>  
  
4. <span data-ttu-id="b753c-123">Il servizio token di protezione della libreria pubblica un token che può essere utilizzato per accedere al servizio della libreria.</span><span class="sxs-lookup"><span data-stu-id="b753c-123">The BookStore STS issues a token that can be used to authenticate to the BookStore Service.</span></span>  
  
5. <span data-ttu-id="b753c-124">Il client accede a al servizio della libreria utilizzando il token pubblicato dal servizio token di sicurezza della libreria.</span><span class="sxs-lookup"><span data-stu-id="b753c-124">The client authenticates to the BookStore service using the token issued by the BookStore STS.</span></span>  
  
6. <span data-ttu-id="b753c-125">Il client accede all'operazione `BuyBook`.</span><span class="sxs-lookup"><span data-stu-id="b753c-125">The client accesses the `BuyBook` operation.</span></span>  
  
 <span data-ttu-id="b753c-126">Vedere le istruzioni seguenti su come impostare ed eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="b753c-126">See the following instructions about how to set up and run this sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b753c-127">Per eseguire l'esempio, è necessario disporre delle autorizzazioni di scrittura per la directory **wwwroot** .</span><span class="sxs-lookup"><span data-stu-id="b753c-127">You must have Write permissions to the **wwwroot** directory to run this sample.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b753c-128">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b753c-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b753c-129">Aprire la finestra del prompt dei comandi SDK.</span><span class="sxs-lookup"><span data-stu-id="b753c-129">Open the SDK command window.</span></span> <span data-ttu-id="b753c-130">Nel percorso di esempio, eseguire Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="b753c-130">In the sample path, run Setup.bat.</span></span> <span data-ttu-id="b753c-131">Ciò crea le directory virtuali richieste per l'esempio e installa i certificati obbligatori con le autorizzazioni adeguate.</span><span class="sxs-lookup"><span data-stu-id="b753c-131">This creates the virtual directories required for the sample and installs the required certificates with appropriate permissions.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="b753c-132">Il file batch Setup.bat è progettato per essere eseguito da un prompt dei comandi di SDK di Windows.</span><span class="sxs-lookup"><span data-stu-id="b753c-132">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="b753c-133">e richiede che la variabile di ambiente MSSDK punti alla directory in cui è installato SDK.</span><span class="sxs-lookup"><span data-stu-id="b753c-133">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="b753c-134">Questa variabile di ambiente viene impostata automaticamente all'interno di un prompt dei comandi di SDK di Windows.</span><span class="sxs-lookup"><span data-stu-id="b753c-134">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span> <span data-ttu-id="b753c-135">In Windows Vista, è necessario assicurarsi che sia installata la compatibilità di gestione con IIS 6,0 perché la configurazione utilizza gli script di amministratore di IIS.</span><span class="sxs-lookup"><span data-stu-id="b753c-135">On Windows Vista, you must ensure that IIS 6.0 Management Compatibility is installed because the set up uses IIS administrator scripts.</span></span> <span data-ttu-id="b753c-136">Per eseguire lo script di configurazione in Windows Vista sono necessari i privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="b753c-136">Running the set-up script on Windows Vista requires administrator privileges.</span></span>  
  
2. <span data-ttu-id="b753c-137">Aprire FederationSample. sln in Visual Studio e scegliere **Compila soluzione** dal menu **Compila** .</span><span class="sxs-lookup"><span data-stu-id="b753c-137">Open FederationSample.sln in Visual Studio and select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="b753c-138">Compila i file di progetto comuni, il servizio della libreria, gli STS della libreria, gli STS di HomeRealm e li distribuisce in IIS.</span><span class="sxs-lookup"><span data-stu-id="b753c-138">This builds the common project files, Bookstore service, Bookstore STS, HomeRealm STS, and deploys them in IIS.</span></span> <span data-ttu-id="b753c-139">Compila anche l'applicazione client della libreria e posiziona il file eseguibile BookStoreClient.exe nella cartella FederationSample\BookStoreClient\bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="b753c-139">This also builds the Bookstore client application and places the executable BookStoreClient.exe in the FederationSample\BookStoreClient\bin\Debug folder.</span></span>  
  
3. <span data-ttu-id="b753c-140">Fare doppio clic su BookStoreClient.exe.</span><span class="sxs-lookup"><span data-stu-id="b753c-140">Double-click BookStoreClient.exe.</span></span> <span data-ttu-id="b753c-141">Verrà visualizzata la finestra BookStoreClient.</span><span class="sxs-lookup"><span data-stu-id="b753c-141">The BookStoreClient window is displayed.</span></span>  
  
4. <span data-ttu-id="b753c-142">È possibile esplorare i libri disponibili nella libreria facendo clic su **Sfoglia libri**.</span><span class="sxs-lookup"><span data-stu-id="b753c-142">You can browse the books available in the bookstore by clicking **Browse Books**.</span></span>  
  
5. <span data-ttu-id="b753c-143">Per acquistare un libro specifico, selezionare il libro nell'elenco e fare clic su **Acquista libro**.</span><span class="sxs-lookup"><span data-stu-id="b753c-143">To purchase a particular book, select the book in the list and click **Buy Book**.</span></span> <span data-ttu-id="b753c-144">L'applicazione si avvia e effettua l'autenticazione utilizzando l'autenticazione di Windows con il servizio token di protezione HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="b753c-144">The application starts up and authenticates using Windows authentication with the HomeRealm Security Token Service.</span></span>  
  
     <span data-ttu-id="b753c-145">L'esempio è configurato per consentire agli utenti di acquistare libri che costano 15$ o meno.</span><span class="sxs-lookup"><span data-stu-id="b753c-145">The sample is configured to allow users to purchase books that cost $15 or less.</span></span> <span data-ttu-id="b753c-146">Il tentativo di acquistare volumi che costano più di 15$ comporta il ricevimento da parte del client di un messaggio Accesso negato dal servizio della libreria.</span><span class="sxs-lookup"><span data-stu-id="b753c-146">Attempting to buy books that cost more than $15 results in the client getting an Access Denied message from the Book Store Service.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="b753c-147">L'esempio non aggiorna il limite di credito dell'utente dopo un acquisto.</span><span class="sxs-lookup"><span data-stu-id="b753c-147">The sample does not update the user’s credit limit after a purchase.</span></span> <span data-ttu-id="b753c-148">È possibile acquistare ripetutamente libri entro i limiti di credito (fissi) dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b753c-148">You can repeatedly purchase books within the user’s (fixed) credit limit.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="b753c-149">Per eseguire la pulizia</span><span class="sxs-lookup"><span data-stu-id="b753c-149">To clean up</span></span>  
  
1. <span data-ttu-id="b753c-150">Eseguire Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="b753c-150">Run Cleanup.bat.</span></span> <span data-ttu-id="b753c-151">Ciò consente di eliminare le directory virtuali create durante l'installazione e di rimuovere inoltre i certificati installati durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="b753c-151">This deletes the virtual directories that were created during set up and also removes the certificates installed during setup.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b753c-152">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="b753c-152">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b753c-153">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="b753c-153">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="b753c-154">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="b753c-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b753c-155">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="b753c-155">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Federation`  

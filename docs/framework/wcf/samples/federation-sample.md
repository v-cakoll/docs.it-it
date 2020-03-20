---
title: Esempio di federazione
ms.date: 03/30/2017
ms.assetid: 7e9da0ca-e925-4644-aa96-8bfaf649d4bb
ms.openlocfilehash: 9ec462f88c0e3a039b7f288554be3e28f13ece08
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144669"
---
# <a name="federation-sample"></a><span data-ttu-id="591f2-102">Esempio di federazione</span><span class="sxs-lookup"><span data-stu-id="591f2-102">Federation Sample</span></span>
<span data-ttu-id="591f2-103">Nell'esempio viene illustrata la sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="591f2-103">This sample demonstrates federated security.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="591f2-104">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="591f2-104">Sample Details</span></span>  
 <span data-ttu-id="591f2-105">Windows Communication Foundation (WCF) fornisce supporto per la `wsFederationHttpBinding`distribuzione di architetture di sicurezza federate tramite l'oggetto .</span><span class="sxs-lookup"><span data-stu-id="591f2-105">Windows Communication Foundation (WCF) provides support for deploying federated security architectures through the `wsFederationHttpBinding`.</span></span> <span data-ttu-id="591f2-106">L'elemento `wsFederationHttpBinding` offre un'associazione sicura, affidabile e interoperativa che comporta l'utilizzo di HTTP come meccanismo di trasporto sottostante per la comunicazione request/reply e Text/XML come formato di trasmissione per la codifica.</span><span class="sxs-lookup"><span data-stu-id="591f2-106">The `wsFederationHttpBinding` provides a secure, reliable, and interoperable binding that involves the use of HTTP as the underlying transport mechanism for request/reply communication, and Text/XML as the wire format for encoding.</span></span> <span data-ttu-id="591f2-107">Per ulteriori informazioni sulla federazione in WCF, vedere [federazione](../../../../docs/framework/wcf/feature-details/federation.md).</span><span class="sxs-lookup"><span data-stu-id="591f2-107">For more information about Federation in WCF, see [Federation](../../../../docs/framework/wcf/feature-details/federation.md).</span></span>  
  
 <span data-ttu-id="591f2-108">Lo scenario è costituito da 4 elementi:</span><span class="sxs-lookup"><span data-stu-id="591f2-108">The scenario is made up of 4 pieces:</span></span>  
  
- <span data-ttu-id="591f2-109">Servizio della libreria</span><span class="sxs-lookup"><span data-stu-id="591f2-109">BookStore service</span></span>  
  
- <span data-ttu-id="591f2-110">Servizio token di protezione della libreria</span><span class="sxs-lookup"><span data-stu-id="591f2-110">BookStore STS</span></span>  
  
- <span data-ttu-id="591f2-111">Servizio token di protezione HomeRealm</span><span class="sxs-lookup"><span data-stu-id="591f2-111">HomeRealm STS</span></span>  
  
- <span data-ttu-id="591f2-112">Client della libreria</span><span class="sxs-lookup"><span data-stu-id="591f2-112">BookStore Client</span></span>  
  
 <span data-ttu-id="591f2-113">Il servizio della libreria supporta due operazioni, `BrowseBooks` e `BuyBook`.</span><span class="sxs-lookup"><span data-stu-id="591f2-113">The BookStore service supports two operations, `BrowseBooks` and `BuyBook`.</span></span> <span data-ttu-id="591f2-114">Consente accesso anonimo all'operazione `BrowseBooks`, ma richiede accesso autenticato per l'operazione `BuyBooks`.</span><span class="sxs-lookup"><span data-stu-id="591f2-114">It allows anonymous access to the `BrowseBooks` operation, but requires authenticated access to access the `BuyBooks` operation.</span></span> <span data-ttu-id="591f2-115">L'autenticazione prende il form di un token pubblicato dal Servizio token di sicurezza della libreria.</span><span class="sxs-lookup"><span data-stu-id="591f2-115">The authentication takes the form of a token issued by the BookStore STS.</span></span> <span data-ttu-id="591f2-116">Il file di configurazione per Servizio della Libreria punta i client al Servizio token di protezione della libreria utilizzando l'`wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="591f2-116">The configuration file for the BookStore Service points clients to the BookStore STS using the `wsFederationHttpBinding`.</span></span>  
  
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
  
 <span data-ttu-id="591f2-117">Il servizio token di protezione della libreria richiede quindi che i client si autentichino utilizzando un token pubblicato dal servizio token di protezione HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="591f2-117">The BookStore STS then requires that clients authenticate using a token issued by the HomeRealm STS.</span></span> <span data-ttu-id="591f2-118">Anche in questo caso, il file di configurazione per il servizio token di protezione della libreria punta i client al servizio token di protezione HomeRealm utilizzando `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="591f2-118">Again, the configuration file for the BookStore STS points clients to the HomeRealm STS using the `wsFederationHttpBinding`.</span></span>  
  
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
  
 <span data-ttu-id="591f2-119">La sequenza di eventi quando si accede all'operazione `BuyBook` è la seguente:</span><span class="sxs-lookup"><span data-stu-id="591f2-119">The sequence of events when accessing the `BuyBook` operation is as follows:</span></span>  
  
1. <span data-ttu-id="591f2-120">Il client effettua l'accesso al servizio token di sicurezza HomeRealm utilizzando le credenziali di Windows.</span><span class="sxs-lookup"><span data-stu-id="591f2-120">The client authenticates to the HomeRealm STS using Windows credentials.</span></span>  
  
2. <span data-ttu-id="591f2-121">Il servizio token di protezione HomeRealm pubblica un token che può essere utilizzato per accedere al servizio token di protezione della libreria.</span><span class="sxs-lookup"><span data-stu-id="591f2-121">The HomeRealm STS issues a token that can be used to authenticate to the BookStore STS.</span></span>  
  
3. <span data-ttu-id="591f2-122">Il client accede al servizio token di protezione della libreria utilizzando il token pubblicato dal servizio token di protezione HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="591f2-122">The client authenticates to the BookStore STS using the token issued by the HomeRealm STS.</span></span>  
  
4. <span data-ttu-id="591f2-123">Il servizio token di protezione della libreria pubblica un token che può essere utilizzato per accedere al servizio della libreria.</span><span class="sxs-lookup"><span data-stu-id="591f2-123">The BookStore STS issues a token that can be used to authenticate to the BookStore Service.</span></span>  
  
5. <span data-ttu-id="591f2-124">Il client accede a al servizio della libreria utilizzando il token pubblicato dal servizio token di sicurezza della libreria.</span><span class="sxs-lookup"><span data-stu-id="591f2-124">The client authenticates to the BookStore service using the token issued by the BookStore STS.</span></span>  
  
6. <span data-ttu-id="591f2-125">Il client accede all'operazione `BuyBook`.</span><span class="sxs-lookup"><span data-stu-id="591f2-125">The client accesses the `BuyBook` operation.</span></span>  
  
 <span data-ttu-id="591f2-126">Vedere le istruzioni seguenti su come impostare ed eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="591f2-126">See the following instructions about how to set up and run this sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="591f2-127">Per eseguire questo esempio, è necessario disporre delle autorizzazioni di scrittura per la directory **wwwroot.**</span><span class="sxs-lookup"><span data-stu-id="591f2-127">You must have Write permissions to the **wwwroot** directory to run this sample.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="591f2-128">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="591f2-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="591f2-129">Aprire la finestra del prompt dei comandi SDK.</span><span class="sxs-lookup"><span data-stu-id="591f2-129">Open the SDK command window.</span></span> <span data-ttu-id="591f2-130">Nel percorso di esempio, eseguire Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="591f2-130">In the sample path, run Setup.bat.</span></span> <span data-ttu-id="591f2-131">Ciò crea le directory virtuali richieste per l'esempio e installa i certificati obbligatori con le autorizzazioni adeguate.</span><span class="sxs-lookup"><span data-stu-id="591f2-131">This creates the virtual directories required for the sample and installs the required certificates with appropriate permissions.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="591f2-132">Il file batch Setup.bat è progettato per essere eseguito da un prompt dei comandi di SDK di Windows.</span><span class="sxs-lookup"><span data-stu-id="591f2-132">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="591f2-133">e richiede che la variabile di ambiente MSSDK punti alla directory in cui è installato SDK.</span><span class="sxs-lookup"><span data-stu-id="591f2-133">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="591f2-134">Questa variabile di ambiente viene impostata automaticamente all'interno di un prompt dei comandi di SDK di Windows.</span><span class="sxs-lookup"><span data-stu-id="591f2-134">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span> <span data-ttu-id="591f2-135">In Windows Vista, è necessario assicurarsi che Compatibilità di gestione di IIS 6.0 sia installato perché la configurazione utilizza script di amministratore di IIS.</span><span class="sxs-lookup"><span data-stu-id="591f2-135">On Windows Vista, you must ensure that IIS 6.0 Management Compatibility is installed because the set up uses IIS administrator scripts.</span></span> <span data-ttu-id="591f2-136">L'esecuzione dello script di configurazione in Windows Vista richiede privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="591f2-136">Running the set-up script on Windows Vista requires administrator privileges.</span></span>  
  
2. <span data-ttu-id="591f2-137">Aprire FederationSample.sln in Visual Studio e scegliere Compila soluzione dal menu Compila .Open FederationSample.sln in Visual Studio and select **Build Solution** from the **Build** menu.</span><span class="sxs-lookup"><span data-stu-id="591f2-137">Open FederationSample.sln in Visual Studio and select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="591f2-138">Compila i file di progetto comuni, il servizio della libreria, gli STS della libreria, gli STS di HomeRealm e li distribuisce in IIS.</span><span class="sxs-lookup"><span data-stu-id="591f2-138">This builds the common project files, Bookstore service, Bookstore STS, HomeRealm STS, and deploys them in IIS.</span></span> <span data-ttu-id="591f2-139">Compila anche l'applicazione client della libreria e posiziona il file eseguibile BookStoreClient.exe nella cartella FederationSample\BookStoreClient\bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="591f2-139">This also builds the Bookstore client application and places the executable BookStoreClient.exe in the FederationSample\BookStoreClient\bin\Debug folder.</span></span>  
  
3. <span data-ttu-id="591f2-140">Fare doppio clic su BookStoreClient.exe.</span><span class="sxs-lookup"><span data-stu-id="591f2-140">Double-click BookStoreClient.exe.</span></span> <span data-ttu-id="591f2-141">Verrà visualizzata la finestra BookStoreClient.</span><span class="sxs-lookup"><span data-stu-id="591f2-141">The BookStoreClient window is displayed.</span></span>  
  
4. <span data-ttu-id="591f2-142">È possibile sfogliare i libri disponibili nella libreria facendo clic su **Sfoglia libri**.</span><span class="sxs-lookup"><span data-stu-id="591f2-142">You can browse the books available in the bookstore by clicking **Browse Books**.</span></span>  
  
5. <span data-ttu-id="591f2-143">Per acquistare un determinato libro, selezionalo nell'elenco e fai clic su **Acquista libro**.</span><span class="sxs-lookup"><span data-stu-id="591f2-143">To purchase a particular book, select the book in the list and click **Buy Book**.</span></span> <span data-ttu-id="591f2-144">L'applicazione si avvia e effettua l'autenticazione utilizzando l'autenticazione di Windows con il servizio token di protezione HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="591f2-144">The application starts up and authenticates using Windows authentication with the HomeRealm Security Token Service.</span></span>  
  
     <span data-ttu-id="591f2-145">L'esempio è configurato per consentire agli utenti di acquistare libri che costano 15$ o meno.</span><span class="sxs-lookup"><span data-stu-id="591f2-145">The sample is configured to allow users to purchase books that cost $15 or less.</span></span> <span data-ttu-id="591f2-146">Il tentativo di acquistare volumi che costano più di 15$ comporta il ricevimento da parte del client di un messaggio Accesso negato dal servizio della libreria.</span><span class="sxs-lookup"><span data-stu-id="591f2-146">Attempting to buy books that cost more than $15 results in the client getting an Access Denied message from the Book Store Service.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="591f2-147">L'esempio non aggiorna il limite di credito dell'utente dopo un acquisto.</span><span class="sxs-lookup"><span data-stu-id="591f2-147">The sample does not update the user’s credit limit after a purchase.</span></span> <span data-ttu-id="591f2-148">È possibile acquistare ripetutamente libri entro i limiti di credito (fissi) dell'utente.</span><span class="sxs-lookup"><span data-stu-id="591f2-148">You can repeatedly purchase books within the user’s (fixed) credit limit.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="591f2-149">Per eseguire la pulizia</span><span class="sxs-lookup"><span data-stu-id="591f2-149">To clean up</span></span>  
  
1. <span data-ttu-id="591f2-150">Eseguire Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="591f2-150">Run Cleanup.bat.</span></span> <span data-ttu-id="591f2-151">Ciò consente di eliminare le directory virtuali create durante l'installazione e di rimuovere inoltre i certificati installati durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="591f2-151">This deletes the virtual directories that were created during set up and also removes the certificates installed during setup.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="591f2-152">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="591f2-152">The samples may already be installed on your machine.</span></span> <span data-ttu-id="591f2-153">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="591f2-153">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="591f2-154">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="591f2-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="591f2-155">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="591f2-155">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Federation`  

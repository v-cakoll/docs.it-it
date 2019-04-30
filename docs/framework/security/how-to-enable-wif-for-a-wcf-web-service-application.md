---
title: "Procedura: Abilitare WIF per un'applicazione del servizio Web WCF"
ms.date: 03/30/2017
ms.assetid: bfc64b3d-64e9-4093-a6a4-72e933917af7
author: BrucePerlerMS
ms.openlocfilehash: 6af0336e19df4ba2a99a52f8726e78ed92f5a79e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940465"
---
# <a name="how-to-enable-wif-for-a-wcf-web-service-application"></a><span data-ttu-id="39435-102">Procedura: Abilitare WIF per un'applicazione del servizio Web WCF</span><span class="sxs-lookup"><span data-stu-id="39435-102">How To: Enable WIF for a WCF Web Service Application</span></span>
## <a name="applies-to"></a><span data-ttu-id="39435-103">Si applica a</span><span class="sxs-lookup"><span data-stu-id="39435-103">Applies To</span></span>  
  
- <span data-ttu-id="39435-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="39435-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
- <span data-ttu-id="39435-105">Microsoft® Windows® Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="39435-105">Microsoft® Windows® Communication Foundation (WCF)</span></span>  
  
## <a name="summary"></a><span data-ttu-id="39435-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="39435-106">Summary</span></span>  
 <span data-ttu-id="39435-107">In questa guida procedurale vengono fornite le procedure dettagliate per abilitare WIF in un servizio Web WCF.</span><span class="sxs-lookup"><span data-stu-id="39435-107">This How-To provides detailed step-by-step procedures for enabling WIF in a WCF web service.</span></span> <span data-ttu-id="39435-108">Vengono inoltre fornite le istruzioni su come testare l'applicazione per verificare il corretto funzionamento del servizio Web presentando delle attestazioni quando l'applicazione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="39435-108">It also provides instructions for how to test the application to verify that the web service is correctly presenting claims when the application is run.</span></span> <span data-ttu-id="39435-109">In questa guida procedurale non sono incluse le istruzioni dettagliate per la creazione di un servizio token di sicurezza (STS, Security Token Service); viene invece utilizzato il servizio token di sicurezza di sviluppo che viene fornito con lo strumento Identity and Access.</span><span class="sxs-lookup"><span data-stu-id="39435-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="39435-110">Il servizio token di sicurezza di sviluppo non esegue una reale autenticazione ed è finalizzato unicamente ai test.</span><span class="sxs-lookup"><span data-stu-id="39435-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="39435-111">Per completare questa guida procedurale sarà necessario installare Identity and Access Tool.</span><span class="sxs-lookup"><span data-stu-id="39435-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="39435-112">Può essere scaricato dal seguente percorso: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span><span class="sxs-lookup"><span data-stu-id="39435-112">It can be downloaded from the following location: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
## <a name="contents"></a><span data-ttu-id="39435-113">Sommario</span><span class="sxs-lookup"><span data-stu-id="39435-113">Contents</span></span>  
  
- <span data-ttu-id="39435-114">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="39435-114">Objectives</span></span>  
  
- <span data-ttu-id="39435-115">Panoramica</span><span class="sxs-lookup"><span data-stu-id="39435-115">Overview</span></span>  
  
- <span data-ttu-id="39435-116">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="39435-116">Summary of Steps</span></span>  
  
- <span data-ttu-id="39435-117">Passaggio 1: creare un semplice servizio WCF</span><span class="sxs-lookup"><span data-stu-id="39435-117">Step 1 – Create a Simple WCF Service</span></span>  
  
- <span data-ttu-id="39435-118">Passaggio 2: creare un'applicazione client per il servizio WCF</span><span class="sxs-lookup"><span data-stu-id="39435-118">Step 2 – Create a Client Application for the WCF Service</span></span>  
  
- <span data-ttu-id="39435-119">Passaggio 3: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="39435-119">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="39435-120">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="39435-120">Objectives</span></span>  
  
- <span data-ttu-id="39435-121">Creare un servizio WCF che richiede token pubblicati</span><span class="sxs-lookup"><span data-stu-id="39435-121">Create a WCF service that requires issued tokens</span></span>  
  
- <span data-ttu-id="39435-122">Creare un client WCF che richiede un token da un servizio token di sicurezza e lo passa al servizio WCF</span><span class="sxs-lookup"><span data-stu-id="39435-122">Create a WCF client that requests a token from an STS and passes it to the WCF service</span></span>  
  
## <a name="overview"></a><span data-ttu-id="39435-123">Panoramica</span><span class="sxs-lookup"><span data-stu-id="39435-123">Overview</span></span>  
 <span data-ttu-id="39435-124">In questa guida procedurale viene illustrato in che modo uno sviluppatore può utilizzare l'autenticazione federata durante lo sviluppo di servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="39435-124">This How-To is intended to demonstrate how a developer can use federated authentication when developing WCF services.</span></span> <span data-ttu-id="39435-125">Trai i vantaggi derivanti dall'utilizzo della federazione nei servizi WCF sono inclusi:</span><span class="sxs-lookup"><span data-stu-id="39435-125">Some of the benefits of using federation in WCF services include:</span></span>  
  
1. <span data-ttu-id="39435-126">Factoring della logica dell'autenticazione dal codice del servizio WCF</span><span class="sxs-lookup"><span data-stu-id="39435-126">Factoring authentication logic out of WCF service code</span></span>  
  
2. <span data-ttu-id="39435-127">Riutilizzo delle soluzioni esistenti di gestione delle identità</span><span class="sxs-lookup"><span data-stu-id="39435-127">Re-using existing identity management solutions</span></span>  
  
3. <span data-ttu-id="39435-128">Interoperabilità con altre soluzioni di identità</span><span class="sxs-lookup"><span data-stu-id="39435-128">Interoperability with other identity solutions</span></span>  
  
4. <span data-ttu-id="39435-129">Flessibilità e resilienza verso le modifiche future</span><span class="sxs-lookup"><span data-stu-id="39435-129">Flexibility and resilience to future changes</span></span>  
  
 <span data-ttu-id="39435-130">WIF e il corrispondente Identity and Access Tool semplificano lo sviluppo e il test di un servizio WCF utilizzando l'autenticazione con federazione, come mostrato nei passaggi che seguono.</span><span class="sxs-lookup"><span data-stu-id="39435-130">WIF and the associated Identity and Access tool make it easier to develop and test a WCF service using federated authentication, as the following steps demonstrate.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="39435-131">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="39435-131">Summary of Steps</span></span>  
  
- <span data-ttu-id="39435-132">Passaggio 1: creare un semplice servizio WCF</span><span class="sxs-lookup"><span data-stu-id="39435-132">Step 1 – Create a Simple WCF Service</span></span>  
  
- <span data-ttu-id="39435-133">Passaggio 2: creare un'applicazione client per il servizio WCF</span><span class="sxs-lookup"><span data-stu-id="39435-133">Step 2 – Create a Client Application for the WCF Service</span></span>  
  
- <span data-ttu-id="39435-134">Passaggio 3: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="39435-134">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-wcf-service"></a><span data-ttu-id="39435-135">Passaggio 1: creare un semplice servizio WCF</span><span class="sxs-lookup"><span data-stu-id="39435-135">Step 1 – Create a Simple WCF Service</span></span>  
 <span data-ttu-id="39435-136">In questo passaggio, verrà creato un nuovo servizio WCF che utilizza il servizio token di sicurezza di sviluppo incluso in Identity and Access Tool.</span><span class="sxs-lookup"><span data-stu-id="39435-136">In this step, you will create a new WCF service that uses the Development STS that is included with the Identity and Access tool.</span></span>  
  
#### <a name="to-create-a-simple-wcf-service"></a><span data-ttu-id="39435-137">Per creare un semplice servizio WCF</span><span class="sxs-lookup"><span data-stu-id="39435-137">To create a simple WCF service</span></span>  
  
1. <span data-ttu-id="39435-138">Avviare Visual Studio come amministratore in modalità con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="39435-138">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2. <span data-ttu-id="39435-139">In Visual Studio fare clic su **File**, **Nuovo** e quindi su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="39435-139">In Visual Studio, click **File**, click **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="39435-140">Nella finestra **Nuovo progetto** fare clic su **Applicazione servizio WCF**.</span><span class="sxs-lookup"><span data-stu-id="39435-140">In the **New Project** window, click **WCF Service Application**.</span></span>  
  
4. <span data-ttu-id="39435-141">In **Nome** immettere `TestService` e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="39435-141">In **Name**, enter `TestService` and press **OK**.</span></span>  
  
5. <span data-ttu-id="39435-142">Fare clic con il pulsante destro del mouse sul progetto **TestService** in **Esplora soluzioni** e quindi selezionare **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="39435-142">Right-click the **TestService** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
6. <span data-ttu-id="39435-143">Verrà visualizzata la finestra **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="39435-143">The **Identity and Access** window appears.</span></span> <span data-ttu-id="39435-144">In **Providers** (Provider) selezionare **Test your application with the Local Development STS** (Testare l'applicazione con il servizio token di sicurezza per lo sviluppo locale) e quindi fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="39435-144">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span> <span data-ttu-id="39435-145">Lo strumento Identity and Access configura il servizio per l'uso di WIF e per l'outsourcing dell'autenticazione al servizio token di sicurezza per lo sviluppo locale (**LocalSTS**) aggiungendo elementi di configurazione al file *Web.config*.</span><span class="sxs-lookup"><span data-stu-id="39435-145">The Identity and Access Tool configures the service to use WIF and to outsource authentication to the local development STS (**LocalSTS**) by adding configuration elements to the *Web.config* file.</span></span>  
  
7. <span data-ttu-id="39435-146">Nel file *Service1.svc.cs* aggiungere una direttiva `using` per lo spazio dei nomi **System.Security.Claims** e sostituire il codice esistente con il seguente, quindi salvare il file:</span><span class="sxs-lookup"><span data-stu-id="39435-146">In the *Service1.svc.cs* file, add a `using` directive for the **System.Security.Claims** namespace and replace the existing code with the following, then save the file:</span></span>  
  
    ```csharp  
    public class Service1 : IService1  
    {  
        public string ComputeResponse(string input)  
        {  
            // Get the caller's identity from ClaimsPrincipal.Current  
            ClaimsPrincipal claimsPrincipal = OperationContext.Current.ClaimsPrincipal;  
  
            // Start generating the output  
            StringBuilder builder = new StringBuilder();  
            builder.AppendLine("Computed by ClaimsAwareWebService");  
            builder.AppendLine("Input received from client:" + input);  
  
            if (claimsPrincipal != null)  
            {  
                // Display the claims from the caller. Do not use this code in a production application.  
                ClaimsIdentity identity = claimsPrincipal.Identity as ClaimsIdentity;  
                builder.AppendLine("Client Name:" + identity.Name);  
                builder.AppendLine("IsAuthenticated:" + identity.IsAuthenticated);  
                builder.AppendLine("The service received the following issued claims of the client:");  
  
                // Iterate over the caller’s claims and append to the output  
                foreach (Claim claim in claimsPrincipal.Claims)  
                {  
                    builder.AppendLine("ClaimType :" + claim.Type + "   ClaimValue:" + claim.Value);  
                }  
            }  
  
            return builder.ToString();  
        }  
    }  
    ```  
  
     <span data-ttu-id="39435-147">Il metodo `ComputeResponse` visualizza le proprietà di varie attestazioni che sono pubblicate da **LocalSTS**.</span><span class="sxs-lookup"><span data-stu-id="39435-147">The `ComputeResponse` method displays the properties of various claims that are issued by **LocalSTS**.</span></span>  
  
8. <span data-ttu-id="39435-148">Nel file *IService1.cs* sostituire il codice esistente con il seguente, quindi salvare il file:</span><span class="sxs-lookup"><span data-stu-id="39435-148">In the *IService1.cs* file, replace the existing code with the following, then save the file:</span></span>  
  
    ```csharp  
    [ServiceContract]  
    public interface IService1  
    {  
        [OperationContract]  
        string ComputeResponse(string input);  
    }  
    ```  
  
9. <span data-ttu-id="39435-149">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="39435-149">Build the project.</span></span>  
  
10. <span data-ttu-id="39435-150">Premere **CTRL+F5** per eseguire il servizio senza avviare il debugger.</span><span class="sxs-lookup"><span data-stu-id="39435-150">Press **Ctrl-F5** to run the service without starting the debugger.</span></span> <span data-ttu-id="39435-151">Verrà visualizzata una pagina Web per il servizio nella quale è possibile verificare che **LocalSTS** sia in esecuzione esaminando l'area di notifica (barra delle applicazioni).</span><span class="sxs-lookup"><span data-stu-id="39435-151">A Web page should open for the service and you can verify that **LocalSTS** is running by looking in the notification area (system tray).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="39435-152">Sia **TestService** sia **LocalSTS** devono essere in esecuzione quando viene aggiunto il riferimento del servizio all'applicazione client nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="39435-152">Both **TestService** and **LocalSTS** must be running when you add the service reference to the client application in the next step.</span></span>  
  
## <a name="step-2--create-a-client-application-for-the-wcf-service"></a><span data-ttu-id="39435-153">Passaggio 2: creare un'applicazione client per il servizio WCF</span><span class="sxs-lookup"><span data-stu-id="39435-153">Step 2 – Create a Client Application for the WCF Service</span></span>  
 <span data-ttu-id="39435-154">In questo passaggio, verrà creata un'applicazione console che utilizza il servizio STS di sviluppo per l'autenticazione con il servizio WCF creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="39435-154">In this step, you will create a console application that uses the Development STS to authenticate with the WCF service you created in the previous step.</span></span>  
  
#### <a name="to-create-a-client-application"></a><span data-ttu-id="39435-155">Per creare un'applicazione client</span><span class="sxs-lookup"><span data-stu-id="39435-155">To create a client application</span></span>  
  
1. <span data-ttu-id="39435-156">In Visual Studio fare clic con il pulsante destro del mouse sulla soluzione, scegliere **Aggiungi** e quindi fare clic su **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="39435-156">In Visual Studio, right-click on the solution, click **Add**, and then click **New Project**.</span></span>  
  
2. <span data-ttu-id="39435-157">Nella finestra **Aggiungi nuovo progetto** selezionare **Applicazione console** nell'elenco dei modelli di **Visual C#**, immettere `Client` e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="39435-157">In the **Add New Project** window, select **Console Application** from the **Visual C#** templates list, enter `Client`, and then press **OK**.</span></span> <span data-ttu-id="39435-158">Il nuovo progetto verrà creato nella cartella della soluzione.</span><span class="sxs-lookup"><span data-stu-id="39435-158">The new project will be created in your solution folder.</span></span>  
  
3. <span data-ttu-id="39435-159">Fare clic con il pulsante destro del mouse su **Riferimenti** nel progetto **Client** e quindi scegliere **Aggiungi riferimento al servizio**.</span><span class="sxs-lookup"><span data-stu-id="39435-159">Right-click on **References** under the **Client** project, and then click **Add Service Reference**.</span></span>  
  
4. <span data-ttu-id="39435-160">Nella finestra **Aggiungi riferimento al servizio** fare clic sulla freccia a discesa sul pulsante **Individua** e fare clic su **Servizi nella soluzione**.</span><span class="sxs-lookup"><span data-stu-id="39435-160">In the **Add Service Reference** window, click the drop-down arrow on the **Discover** button and click **Services in Solution**.</span></span> <span data-ttu-id="39435-161">Nel campo **Indirizzo** verrà automaticamente inserito il servizio WCF precedentemente creato e il campo **Spazio dei nomi** verrà impostato su **ServiceReference1**.</span><span class="sxs-lookup"><span data-stu-id="39435-161">The **Address** will automatically populate with the WCF service you created earlier, and the **Namespace** will be set to **ServiceReference1**.</span></span> <span data-ttu-id="39435-162">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="39435-162">Click **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="39435-163">Sia **TestService** sia **LocalSTS** devono essere in esecuzione quando viene aggiunto il riferimento del servizio al client.</span><span class="sxs-lookup"><span data-stu-id="39435-163">Both **TestService** and **LocalSTS** must be running when you add the service reference to the client.</span></span>  
  
5. <span data-ttu-id="39435-164">In Visual Studio verranno generate classi proxy per il servizio WCF e verranno aggiunte tutte le informazioni di riferimento necessarie.</span><span class="sxs-lookup"><span data-stu-id="39435-164">Visual Studio will generate proxy classes for the WCF service, and add all of the necessary reference information.</span></span> <span data-ttu-id="39435-165">Verranno inoltre aggiunti elementi al file *App.config* per configurare il client in modo da ottenere un token dal servizio token di sicurezza per l'autenticazione con il servizio.</span><span class="sxs-lookup"><span data-stu-id="39435-165">It will also add elements to the *App.config* file to configure the client to get a token from the STS to authenticate with the service.</span></span> <span data-ttu-id="39435-166">Al termine di questo processo verrà aperto il file **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="39435-166">When this process is finished, the **Program.cs** file will open.</span></span> <span data-ttu-id="39435-167">Aggiungere una direttiva `using` per **System.ServiceModel** e un'altra per **Client.ServiceReference1**, sostituire il metodo **Main** con il codice seguente e quindi salvare il file:</span><span class="sxs-lookup"><span data-stu-id="39435-167">Add a `using` directive for **System.ServiceModel** and another for **Client.ServiceReference1**, replace the **Main** method with the following code, then save the file:</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        // Create the client for the service  
        Service1Client client = new Service1Client();  
        Console.WriteLine("-------------WCF Client Application--------------\n");  
  
        while (!ShouldQuitApplication())  
        {  
            try  
            {  
                Console.WriteLine(client.ComputeResponse("Hello World"));  
            }  
            catch (CommunicationException e)  
            {  
                Console.WriteLine(e.Message);  
                Console.WriteLine(e.StackTrace);  
                Exception ex = e.InnerException;  
                while (ex != null)  
                {  
                    Console.WriteLine("===========================");  
                    Console.WriteLine(ex.Message);  
                    Console.WriteLine(ex.StackTrace);  
                    ex = ex.InnerException;  
                }  
            }  
            catch (TimeoutException)  
            {  
                Console.WriteLine("Timed out...");  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("An unexpected exception occurred.");  
                Console.WriteLine(e.StackTrace);  
            }  
        }  
  
        client.Close();  
  
        if (client != null)  
        {  
            client.Abort();  
        }  
    }  
  
    static bool ShouldQuitApplication()  
    {  
        Console.WriteLine("---------------------------------------------------------------------");  
        Console.WriteLine("Press Enter key to invoke service, any other key to quit application:");  
        Console.WriteLine("----------------------------------------------------------------------");  
  
        ConsoleKeyInfo keyInfo = Console.ReadKey();  
        if (keyInfo.Key == ConsoleKey.Enter)  
            return false;  
        return true;  
    }  
    ```  
  
6. <span data-ttu-id="39435-168">Aprire il file *App.config* e aggiungere il seguente codice XML come primo elemento figlio sotto l'elemento `<system.serviceModel>`, quindi salvare il file:</span><span class="sxs-lookup"><span data-stu-id="39435-168">Open the *App.config* file and add the following XML as the first child element under the `<system.serviceModel>` element, then save the file:</span></span>  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
         <behavior>  
           <clientCredentials>  
             <serviceCertificate>  
               <authentication certificateValidationMode="None"/>  
             </serviceCertificate>  
           </clientCredentials>  
         </behavior>  
       </endpointBehaviors>  
     </behaviors>  
    ```  
  
     <span data-ttu-id="39435-169">In questo modo viene disabilitata la convalida del certificato.</span><span class="sxs-lookup"><span data-stu-id="39435-169">This disables certificate validation.</span></span>  
  
7. <span data-ttu-id="39435-170">Fare clic con il pulsante destro del mouse sulla soluzione **TestService** e fare clic su **Imposta progetti di avvio**.</span><span class="sxs-lookup"><span data-stu-id="39435-170">Right-click the **TestService** solution and click on **Set StartUp Projects**.</span></span> <span data-ttu-id="39435-171">Verrà aperta la pagina delle proprietà **Progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="39435-171">The **Startup Project** property page opens.</span></span> <span data-ttu-id="39435-172">Nella pagina delle proprietà **Progetto di avvio** selezionare **Progetti di avvio multipli** e quindi fare clic sul campo **Azione** per ciascun progetto e scegliere **Avvio** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="39435-172">In the **Startup Project** property page, select **Multiple startup projects** then click in the **Action** field for each project and select **Start** from the drop-down menu.</span></span> <span data-ttu-id="39435-173">Fare clic su **OK** per salvare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="39435-173">Click **OK** to save the settings.</span></span>  
  
8. <span data-ttu-id="39435-174">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="39435-174">Build the solution.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="39435-175">Passaggio 3: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="39435-175">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="39435-176">In questo passaggio verrà eseguito il test dell'applicazione WCF abilitata per WIF e verrà verificata la visualizzazione delle attestazioni.</span><span class="sxs-lookup"><span data-stu-id="39435-176">In this step you will test your WIF-enabled WCF application and verify that claims are presented.</span></span>  
  
#### <a name="to-test-your-wif-enabled-wcf-application-for-claims"></a><span data-ttu-id="39435-177">Per eseguire il test sulle attestazioni dell'applicazione WCF abilitata per WIF</span><span class="sxs-lookup"><span data-stu-id="39435-177">To test your WIF-enabled WCF application for claims</span></span>  
  
1. <span data-ttu-id="39435-178">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="39435-178">Press **F5** to build and run the application.</span></span> <span data-ttu-id="39435-179">Dovrebbe essere visualizzata una finestra della console e il testo seguente: **Premere il tasto INVIO per richiamare il servizio e qualsiasi altro tasto per chiudere l'applicazione:**</span><span class="sxs-lookup"><span data-stu-id="39435-179">You should be presented with a console window, and the following text: **Press Enter key to invoke service, any other key to quit application:**</span></span>  
  
2. <span data-ttu-id="39435-180">Premere **INVIO**. Verranno visualizzate le seguenti informazioni sulle attestazioni nella console:</span><span class="sxs-lookup"><span data-stu-id="39435-180">Press **Enter**, and the following claims information should appear in the console:</span></span>  
  
    ```  
    Computed by Service1  
    Input received from client: Hello World  
    Client Name: Terry  
    IsAuthenticated: True  
    The service received the following issued claims of the client:  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name    ClaimValue:Terry  
    ClaimType :http://schema.xmlsoap.org/ws/2005/05/identity/claims/surname    ClaimValue:Adams  
    ClaimType :http://schemas.microsoft.com/ws/2008/06/identity/claims/role    ClaimValue:developer  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress    ClaimValue:terry@contoso.com  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="39435-181">Sia **TestService** che **LocalSTS** devono essere in esecuzione prima di premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="39435-181">Both **TestService** and **LocalSTS** must be running before you press **Enter**.</span></span> <span data-ttu-id="39435-182">Verrà visualizzata una pagina Web per il servizio nella quale è possibile verificare che **LocalSTS** sia in esecuzione esaminando l'area di notifica (barra delle applicazioni).</span><span class="sxs-lookup"><span data-stu-id="39435-182">A Web page should open for the service and you can verify that **LocalSTS** is running by looking in the notification area (system tray).</span></span>  
  
3. <span data-ttu-id="39435-183">La visualizzazione delle attestazioni nella console è la prova dell'avvenuta autenticazione con il servizio STS per la visualizzazione delle attestazioni dal servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="39435-183">If these claims appear in the console, you have successfully authenticated with the STS to display claims from the WCF service.</span></span>

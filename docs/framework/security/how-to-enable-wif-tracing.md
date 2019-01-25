---
title: 'Procedura: Abilitare la traccia WIF'
ms.date: 03/30/2017
ms.assetid: 271b6889-3454-46ff-96ab-9feb15e742ee
author: BrucePerlerMS
ms.openlocfilehash: ab59b0809008f212269e2c4b9745ccaec8c9af5d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605168"
---
# <a name="how-to-enable-wif-tracing"></a><span data-ttu-id="5ec05-102">Procedura: Abilitare la traccia WIF</span><span class="sxs-lookup"><span data-stu-id="5ec05-102">How To: Enable WIF Tracing</span></span>
## <a name="applies-to"></a><span data-ttu-id="5ec05-103">Si applica a</span><span class="sxs-lookup"><span data-stu-id="5ec05-103">Applies To</span></span>  
  
-   <span data-ttu-id="5ec05-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="5ec05-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="5ec05-105">Web Form ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="5ec05-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="5ec05-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="5ec05-106">Summary</span></span>  
 <span data-ttu-id="5ec05-107">Questo argomento include le procedure dettagliate per abilitare la traccia WIF in un'applicazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5ec05-107">This How-To provides detailed step-by-step procedures for enabling WIF tracing in an ASP.NET application.</span></span> <span data-ttu-id="5ec05-108">Sono inoltre disponibili istruzioni per testare l'applicazione per verificare che il listener e il log di traccia funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="5ec05-108">It also provides instructions testing the application to verify that the trace listener and log are working correctly.</span></span> <span data-ttu-id="5ec05-109">In questa guida procedurale non sono incluse le istruzioni dettagliate per la creazione di un servizio token di sicurezza (STS, Security Token Service); viene invece utilizzato il servizio token di sicurezza di sviluppo che viene fornito con lo strumento Identity and Access.</span><span class="sxs-lookup"><span data-stu-id="5ec05-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="5ec05-110">Il servizio token di sicurezza di sviluppo non esegue una reale autenticazione ed è finalizzato unicamente ai test.</span><span class="sxs-lookup"><span data-stu-id="5ec05-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="5ec05-111">Per completare questa guida procedurale sarà necessario installare Identity and Access Tool.</span><span class="sxs-lookup"><span data-stu-id="5ec05-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="5ec05-112">Può essere scaricato dal seguente percorso: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span><span class="sxs-lookup"><span data-stu-id="5ec05-112">It can be downloaded from the following location: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5ec05-113">L'abilitazione della traccia WIF per le applicazioni passive, ovvero le applicazioni che usano il protocollo WS-Federation, possono esporre potenzialmente l'applicazione ad attacchi Denial of Service (DoS) o alla divulgazione di informazioni a malintenzionati.</span><span class="sxs-lookup"><span data-stu-id="5ec05-113">Enabling WIF tracing for passive applications, that is, applications that use the WS-Federation protocol, can potentially expose the application to denial of service (DoS) attacks or to information disclosure to a malicious party.</span></span> <span data-ttu-id="5ec05-114">Sono inclusi sia i relying party passivi che i servizi token di sicurezza passivi.</span><span class="sxs-lookup"><span data-stu-id="5ec05-114">This includes both passive RPs and passive STSes.</span></span> <span data-ttu-id="5ec05-115">Per questo motivo, è consigliabile non abilitare la traccia WIF per relying party passivi o servizi token di sicurezza passivi in ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="5ec05-115">For this reason, we recommend that you not enable WIF tracing for passive RPs or STSes in a production environment.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="5ec05-116">Sommario</span><span class="sxs-lookup"><span data-stu-id="5ec05-116">Contents</span></span>  
  
-   <span data-ttu-id="5ec05-117">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="5ec05-117">Objectives</span></span>  
  
-   <span data-ttu-id="5ec05-118">Panoramica</span><span class="sxs-lookup"><span data-stu-id="5ec05-118">Overview</span></span>  
  
-   <span data-ttu-id="5ec05-119">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="5ec05-119">Summary of Steps</span></span>  
  
-   <span data-ttu-id="5ec05-120">Passaggio 1: creare una semplice applicazione Web Form ASP.NET e abilitare la traccia</span><span class="sxs-lookup"><span data-stu-id="5ec05-120">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
  
-   <span data-ttu-id="5ec05-121">Passaggio 2: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="5ec05-121">Step 2 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="5ec05-122">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="5ec05-122">Objectives</span></span>  
  
-   <span data-ttu-id="5ec05-123">Creare un'applicazione ASP.NET semplice che usa WIF e il servizio token di sicurezza per lo sviluppo locale dallo strumento Identity and Access</span><span class="sxs-lookup"><span data-stu-id="5ec05-123">Create a simple ASP.NET application that uses WIF and the Development STS from the Identity and Access Tool</span></span>  
  
-   <span data-ttu-id="5ec05-124">Abilitare la traccia e verificare che funzioni</span><span class="sxs-lookup"><span data-stu-id="5ec05-124">Enable tracing and verify that it is working</span></span>  
  
## <a name="overview"></a><span data-ttu-id="5ec05-125">Panoramica</span><span class="sxs-lookup"><span data-stu-id="5ec05-125">Overview</span></span>  
 <span data-ttu-id="5ec05-126">La traccia consente di eseguire il debug e la risoluzione di molti tipi di problemi con WIF, inclusi token, cookie, attestazioni, messaggi del protocollo e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="5ec05-126">Tracing enables you to debug and troubleshoot many types of issues with WIF, including tokens, cookies, claims, protocol messages, and more.</span></span> <span data-ttu-id="5ec05-127">La traccia WIF è simile alla traccia WCF. Ad esempio, è possibile scegliere il livello di dettaglio delle tracce per visualizzare i vari tipi di messaggi, da solo quelli critici a tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="5ec05-127">WIF tracing is similar to WCF tracing; for example, you can choose the verbosity of traces to display everything from critical messages to all messages.</span></span> <span data-ttu-id="5ec05-128">Le tracce WIF possono essere generate in file **xml** o in file **svclog** visualizzabili tramite il visualizzatore di tracce di servizi (Service Trace Viewer).</span><span class="sxs-lookup"><span data-stu-id="5ec05-128">WIF traces can be generated in **.xml** files or in **.svclog** files that are viewable by using the Service Trace Viewer Tool.</span></span> <span data-ttu-id="5ec05-129">Questo strumento è disponibile nel **bin** directory di Windows SDK percorso di installazione nel computer, ad esempio: **C:\Programmi\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**.</span><span class="sxs-lookup"><span data-stu-id="5ec05-129">This tool is located in the **bin** directory of the Windows SDK install path on your computer, for example: **C:\Program Files\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="5ec05-130">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="5ec05-130">Summary of Steps</span></span>  
  
-   <span data-ttu-id="5ec05-131">Passaggio 1: creare una semplice applicazione Web Form ASP.NET e abilitare la traccia</span><span class="sxs-lookup"><span data-stu-id="5ec05-131">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
  
-   <span data-ttu-id="5ec05-132">Passaggio 2: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="5ec05-132">Step 2 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-tracing"></a><span data-ttu-id="5ec05-133">Passaggio 1: creare una semplice applicazione Web Form ASP.NET e abilitare la traccia</span><span class="sxs-lookup"><span data-stu-id="5ec05-133">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
 <span data-ttu-id="5ec05-134">In questo passaggio verrà creata una nuova applicazione Web Form ASP.NET e si modificherà il file *Web.config* per abilitare la traccia.</span><span class="sxs-lookup"><span data-stu-id="5ec05-134">In this step, you will create a new ASP.NET Web Forms application and modify the *Web.config* file to enable tracing.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="5ec05-135">Per creare un'applicazione ASP.NET semplice</span><span class="sxs-lookup"><span data-stu-id="5ec05-135">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="5ec05-136">Avviare Visual Studio e fare clic su **File**, **Nuovo** e **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="5ec05-136">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="5ec05-137">Nella finestra **Nuovo progetto** fare clic su **Applicazione Web Form ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="5ec05-137">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="5ec05-138">In **Nome** immettere `TestApp` e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ec05-138">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="5ec05-139">Fare clic con il pulsante destro del mouse sul progetto **TestApp** in **Esplora soluzioni** e quindi scegliere **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="5ec05-139">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
5.  <span data-ttu-id="5ec05-140">Verrà visualizzata la finestra **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="5ec05-140">The **Identity and Access** window appears.</span></span> <span data-ttu-id="5ec05-141">In **Providers** (Provider) selezionare **Test your application with the Local Development STS** (Testare l'applicazione con il servizio token di sicurezza per lo sviluppo locale) e quindi fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="5ec05-141">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
6.  <span data-ttu-id="5ec05-142">Creare una nuova cartella denominata **registri** nella radice del **c:** unità, ad esempio illustrato: **C:\Logs.**</span><span class="sxs-lookup"><span data-stu-id="5ec05-142">Create a new folder in named **logs** in the root of the **C:** drive, like shown: **C:\logs**</span></span>  
  
7.  <span data-ttu-id="5ec05-143">Aggiungere l'elemento **\<system.diagnostics>** seguente al file di configurazione *Web.config* subito dopo l'elemento di chiusura **\</configSections>**, come illustrato:</span><span class="sxs-lookup"><span data-stu-id="5ec05-143">Add the following **\<system.diagnostics>** element to the *Web.config* configuration file immediately following the closing **\</configSections>** element, like shown:</span></span>  
  
    ```xml  
    <configuration>  
        <configSections>  
            ...
        </configSections>  
        <system.diagnostics>  
            <sources>  
                <source name="System.IdentityModel" switchValue="Verbose">  
                    <listeners>  
                        <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="C:\logs\WIF.xml" />  
                    </listeners>  
                </source>  
            </sources>  
            <trace autoflush="true" />  
        </system.diagnostics>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="5ec05-144">Il percorso di directory specificato nell'attributo **initializeData** deve esistere prima di poter avviare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="5ec05-144">The directory location specified in the **initializeData** attribute must exist before logging can begin.</span></span> <span data-ttu-id="5ec05-145">Se il percorso non esiste, non verrà creato alcun log.</span><span class="sxs-lookup"><span data-stu-id="5ec05-145">If the location does not exist, no logs will be created.</span></span>  
  
     <span data-ttu-id="5ec05-146">Le impostazioni di configurazione precedenti abilitano la traccia **Verbose** per WIF e salvano il log risultante nel file **C:logsWIF.xml**.</span><span class="sxs-lookup"><span data-stu-id="5ec05-146">The configuration settings above will enable **Verbose** tracing for WIF and save the resulting log to the **C:logsWIF.xml** file.</span></span>  
  
## <a name="step-2--test-your-solution"></a><span data-ttu-id="5ec05-147">Passaggio 2: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="5ec05-147">Step 2 – Test Your Solution</span></span>  
 <span data-ttu-id="5ec05-148">In questo passaggio si testerà l'applicazione ASP.NET abilitata per WIF per verificare che i log vengano registrati.</span><span class="sxs-lookup"><span data-stu-id="5ec05-148">In this step, you will test your WIF-enabled ASP.NET application to verify that logs are being recorded.</span></span>  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-successful-tracing"></a><span data-ttu-id="5ec05-149">Per testare il corretto funzionamento della traccia per l'applicazione ASP.NET abilitata per WIF</span><span class="sxs-lookup"><span data-stu-id="5ec05-149">To test your WIF-enabled ASP.NET application for successful tracing</span></span>  
  
1.  <span data-ttu-id="5ec05-150">Eseguire la soluzione premendo **F5**.</span><span class="sxs-lookup"><span data-stu-id="5ec05-150">Run the solution by pressing the **F5** key.</span></span> <span data-ttu-id="5ec05-151">Dovrebbe essere visualizzata la home page predefinita di ASP.NET e l'autenticazione dovrebbe avvenire automaticamente con il nome utente *Terry*, ovvero l'utente predefinito restituito dal servizio token di sicurezza per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="5ec05-151">You should be presented with the default ASP.NET Home Page and automatically authenticated with the username *Terry*, which is the default user that is returned by the Development STS.</span></span>  
  
2.  <span data-ttu-id="5ec05-152">Chiudere la finestra del browser e passare quindi alla cartella **C:\logs**.</span><span class="sxs-lookup"><span data-stu-id="5ec05-152">Close the browser window and then navigate to the **C:\logs** folder.</span></span> <span data-ttu-id="5ec05-153">Aprire il file **C:\logs\WIF.xml** con un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="5ec05-153">Open the **C:\logs\WIF.xml** file using a text editor.</span></span>  
  
3.  <span data-ttu-id="5ec05-154">Controllare il file **WIF.xml** e verificare che contenga voci che iniziano con **\<E2ETraceEvent>**.</span><span class="sxs-lookup"><span data-stu-id="5ec05-154">Inspect the **WIF.xml** file and verify that it contains entries starting with **\<E2ETraceEvent>**.</span></span> <span data-ttu-id="5ec05-155">Queste tracce conterranno elementi **\<TraceRecord >** con le descrizioni per l'attività di traccia, ad esempio **Convalida di SecurityToken**.</span><span class="sxs-lookup"><span data-stu-id="5ec05-155">These traces will contain **\<TraceRecord>** elements with descriptions for the traced activity, such as **Validating SecurityToken**.</span></span>

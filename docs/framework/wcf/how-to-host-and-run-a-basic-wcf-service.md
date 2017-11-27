---
title: 'Procedura: ospitare ed eseguire un servizio Windows Communication Foundation di base'
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f0368e2e605f3f5c5b5a7b0d8c05f7276d8df22d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="d1507-102">Procedura: ospitare ed eseguire un servizio Windows Communication Foundation di base</span><span class="sxs-lookup"><span data-stu-id="d1507-102">How to: Host and Run a Basic Windows Communication Foundation Service</span></span>
<span data-ttu-id="d1507-103">Questa è la terza delle sei attività necessarie per creare un'applicazione [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1507-103">This is the third of six tasks required to create a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="d1507-104">Per una panoramica di tutte e sei le attività, vedere il [esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="d1507-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="d1507-105">In questo argomento viene descritto come ospitare un servizio [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="d1507-105">This topic describes how to host a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service in a console application.</span></span> <span data-ttu-id="d1507-106">Questa procedura è costituita dai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1507-106">This procedure consists of the following steps:</span></span>  
  
-   <span data-ttu-id="d1507-107">Creare un progetto di applicazione console per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="d1507-107">Create a console application project to host the service.</span></span>  
  
-   <span data-ttu-id="d1507-108">Creare un host del servizio per il servizio.</span><span class="sxs-lookup"><span data-stu-id="d1507-108">Create a service host for the service.</span></span>  
  
-   <span data-ttu-id="d1507-109">Consentire lo scambio di metadati.</span><span class="sxs-lookup"><span data-stu-id="d1507-109">Enable metadata exchange.</span></span>  
  
-   <span data-ttu-id="d1507-110">Aprire l’host del servizio.</span><span class="sxs-lookup"><span data-stu-id="d1507-110">Open the service host.</span></span>  
  
 <span data-ttu-id="d1507-111">Nell'esempio riportato dopo la procedura, viene fornito un elenco completo del codice scritto per questa attività.</span><span class="sxs-lookup"><span data-stu-id="d1507-111">A complete listing of the code written in this task is provided in the example following the procedure.</span></span>  
  
## <a name="to-create-a-new-console-application-to-host-the-service"></a><span data-ttu-id="d1507-112">Per creare una nuova applicazione console per ospitare il servizio</span><span class="sxs-lookup"><span data-stu-id="d1507-112">To create a new console application to host the service</span></span>  
  
1.  <span data-ttu-id="d1507-113">Creare un nuovo progetto applicazione Console facendo clic su una soluzione di introduzione, se si seleziona, **Aggiungi**, **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="d1507-113">Create a new Console Application project by right-clicking on the Getting Started solution, selecting, **Add**, **New Project**.</span></span> <span data-ttu-id="d1507-114">Nel **Aggiungi nuovo progetto** sul lato sinistro della finestra di dialogo Seleziona **Windows** in **c#** o **VB**.</span><span class="sxs-lookup"><span data-stu-id="d1507-114">In the **Add New Project** dialog on the left hand side of the dialog select **Windows** under **C#** or **VB**.</span></span> <span data-ttu-id="d1507-115">Nella sezione centrale della finestra di dialogo selezionare **applicazione Console**.</span><span class="sxs-lookup"><span data-stu-id="d1507-115">In the center section of the dialog select **Console Application**.</span></span> <span data-ttu-id="d1507-116">Denominare il progetto GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="d1507-116">Name the project GettingStartedHost.</span></span>  
  
2.  <span data-ttu-id="d1507-117">Impostare il framework di destinazione del progetto GettingStartedHost su .NET Framework 4.5 facendo clic su **GettingStartedHost** in Esplora soluzioni e selezionando **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d1507-117">Set the target framework of the GettingStartedHost project to .NET Framework 4.5 by right clicking on **GettingStartedHost** in the Solution Explorer and selecting **Properties**.</span></span> <span data-ttu-id="d1507-118">Nella casella a discesa **Framework di destinazione** selezionare **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="d1507-118">In the dropdown box labeled **Target Framework** select **.NET Framework 4.5**.</span></span> <span data-ttu-id="d1507-119">Il framework di destinazione per un progetto VB è leggermente diverso. nella finestra di dialogo Proprietà progetto GettingStartedHost fare clic sul **compilare** scheda sul lato sinistro della schermata e quindi scegliere il **avanzate compilare Opzioni** pulsante nell'angolo inferiore sinistro della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d1507-119">Setting the target framework for a VB project is a little different, in the GettingStartedHost project properties dialog, click the **Compile** tab on the left-hand side of the screen, and then click the **Advanced Compile Options** button at the lower left-hand corner of the dialog.</span></span> <span data-ttu-id="d1507-120">Selezionare quindi **.NET Framework 4.5** nella casella a discesa **Framework di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="d1507-120">Then select **.NET Framework 4.5** in the dropdown box labeled **Target Framework**.</span></span>  
  
     <span data-ttu-id="d1507-121">Impostazione del framework di destinazione causerà [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] per ricaricare la soluzione, premere **OK** quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="d1507-121">Setting the target framework will cause [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] to reload the solution, press **OK** when prompted.</span></span>  
  
3.  <span data-ttu-id="d1507-122">Aggiungere un riferimento al progetto GettingStartedLib nel progetto GettingStartedHost facendo clic su di **riferimenti** cartella nel progetto GettingStartedHost in Esplora soluzioni e selezionare **Aggiungi riferimento** .</span><span class="sxs-lookup"><span data-stu-id="d1507-122">Add a reference to the GettingStartedLib project to the GettingStartedHost project by right clicking on the **References** folder under the GettingStartedHost project in the solution explorer and select **Add Reference**.</span></span> <span data-ttu-id="d1507-123">Nel **Aggiungi riferimento** finestra di dialogo Seleziona **soluzione** sul lato sinistro della finestra di dialogo e scegliere GettingStartedLib nella sezione centrale della finestra di dialogo e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d1507-123">In the **Add Reference** dialog, select **Solution** on the left-hand side of the dialog and select GettingStartedLib in the center section of the dialog and click **Add**.</span></span> <span data-ttu-id="d1507-124">In questo modo i tipi definiti in GettingStartedLib diventano disponibili nel progetto GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="d1507-124">This makes the types defined in GettingStartedLib available to the GettingStartedHost project.</span></span>  
  
4.  <span data-ttu-id="d1507-125">Aggiungere un riferimento a System. ServiceModel nel progetto GettingStartedHost facendo clic con il **riferimento** cartella nel progetto GettingStartedHost in Esplora soluzioni e selezionare **Aggiungi** Riferimento.</span><span class="sxs-lookup"><span data-stu-id="d1507-125">Add a reference to System.ServiceModel to the GettingStartedHost project by right-clicking the **Reference** folder under the GettingStartedHost project in Solution Explorer and select **Add** Reference.</span></span> <span data-ttu-id="d1507-126">Nel **Aggiungi riferimento** finestra di dialogo selezionare **Framework** sul lato sinistro della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d1507-126">In the **Add Reference** dialog select **Framework** on the left-hand side of the dialog.</span></span> <span data-ttu-id="d1507-127">Nella casella di testo di ricerca degli assembly digitare `System.ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="d1507-127">In the Search Assemblies textbox, type in `System.ServiceModel`.</span></span> <span data-ttu-id="d1507-128">Nella sezione centrale della finestra di dialogo selezionare **System. ServiceModel**, fare clic su di **Aggiungi** pulsante, quindi scegliere il **Chiudi** pulsante.</span><span class="sxs-lookup"><span data-stu-id="d1507-128">In the center section of the dialog select **System.ServiceModel**, click the **Add** button, and click the **Close** button.</span></span> <span data-ttu-id="d1507-129">Salvare la soluzione facendo clic sul pulsante Salva tutto sotto il menu principale.</span><span class="sxs-lookup"><span data-stu-id="d1507-129">Save the solution by clicking the Save All button below the main menu.</span></span>  
  
### <a name="to-host-the-service"></a><span data-ttu-id="d1507-130">Per ospitare il servizio</span><span class="sxs-lookup"><span data-stu-id="d1507-130">To host the service</span></span>  
  
-   <span data-ttu-id="d1507-131">Aprire il file Program.cs o Module.vb e immettere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d1507-131">Open the Program.cs or Module.vb file and enter the following code:</span></span>  
  
    ```csharp
    // program.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.ServiceModel;  
    using GettingStartedLib;  
    using System.ServiceModel.Description;   
  
    namespace GettingStartedHost  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                // Step 1 Create a URI to serve as the base address.  
                Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");  
  
                // Step 2 Create a ServiceHost instance  
                ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
  
                try  
                {  
                    // Step 3 Add a service endpoint.  
                    selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");  
  
                    // Step 4 Enable metadata exchange.  
                    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
                    smb.HttpGetEnabled = true;  
                    selfHost.Description.Behaviors.Add(smb);  
  
                    // Step 5 Start the service.  
                    selfHost.Open();  
                    Console.WriteLine("The service is ready.");  
                    Console.WriteLine("Press <ENTER> to terminate service.");  
                    Console.WriteLine();  
                    Console.ReadLine();  
  
                    // Close the ServiceHostBase to shutdown the service.  
                    selfHost.Close();  
                }  
                catch (CommunicationException ce)  
                {  
                    Console.WriteLine("An exception occurred: {0}", ce.Message);  
                    selfHost.Abort();  
                }  
            }  
        }  
    }  
    ```  
  
    ```vb
    'Module1.vb  
    Imports System  
    Imports System.ServiceModel  
    Imports System.ServiceModel.Description  
    Imports GettingStartedLibVB.GettingStartedLib  
  
    Module Service  
  
        Class Program  
            Shared Sub Main()  
                ' Step 1 Create a URI to serve as the base address  
                Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")  
  
                ' Step 2 Create a ServiceHost instance  
                Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)  
                Try  
  
                    ' Step 3 Add a service endpoint  
                    ' Add a service endpoint  
                    selfHost.AddServiceEndpoint( _  
                        GetType(ICalculator), _  
                        New WSHttpBinding(), _  
                        "CalculatorService")  
  
                    ' Step 4 Enable metadata exchange.  
                    Dim smb As New ServiceMetadataBehavior()  
                    smb.HttpGetEnabled = True  
                    selfHost.Description.Behaviors.Add(smb)  
  
                    ' Step 5 Start the service  
                    selfHost.Open()  
                    Console.WriteLine("The service is ready.")  
                    Console.WriteLine("Press <ENTER> to terminate service.")  
                    Console.WriteLine()  
                    Console.ReadLine()  
  
                    ' Close the ServiceHostBase to shutdown the service.  
                    selfHost.Close()  
                Catch ce As CommunicationException  
                    Console.WriteLine("An exception occurred: {0}", ce.Message)  
                    selfHost.Abort()  
                End Try  
            End Sub  
        End Class  
  
    End Module  
    ```  
  
    1.  <span data-ttu-id="d1507-132">Passaggio 1: viene creata un'istanza della classe URI per contenere l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="d1507-132">Step 1 - Creates an instance of the Uri class to hold the base address of the service.</span></span> <span data-ttu-id="d1507-133">I servizi vengono identificati con un URL contenente un indirizzo di base e un URI facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d1507-133">Services are identified by a URL which contains a base address and an optional URI.</span></span> <span data-ttu-id="d1507-134">L'indirizzo di base è il seguente formato: [Trasporto] :// [nome computer o dominio] [: facoltativo numero di porta] / [segmento URI facoltativo] indirizzo di base per il servizio di calcolatrice utilizza il trasporto HTTP, localhost, porta 8000 e il segmento URI "GettingStarted"</span><span class="sxs-lookup"><span data-stu-id="d1507-134">The base address is formatted as follows:[transport]://[machine-name or domain][:optional port #]/[optional URI segment]The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment "GettingStarted"</span></span>  
  
    2.  <span data-ttu-id="d1507-135">Passaggio 2: viene creata un'istanza della classe <xref:System.ServiceModel.ServiceHost> per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="d1507-135">Step 2 – Creates an instance of the <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="d1507-136">Il costruttore accetta due parametri, il tipo di classe che implementa il contratto di servizio e l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="d1507-136">The constructor takes two parameters, the type of the class that implements the service contract, and the base address of the service.</span></span>  
  
    3.  <span data-ttu-id="d1507-137">Passaggio 3: viene creata una <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` istanza.</span><span class="sxs-lookup"><span data-stu-id="d1507-137">Step 3 – Creates a <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` instance.</span></span> <span data-ttu-id="d1507-138">Un endpoint di un servizio è composto da un indirizzo, un'associazione e un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="d1507-138">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="d1507-139">Il <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` costruttore accetta pertanto un indirizzo, un'associazione e il tipo di interfaccia di contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="d1507-139">The <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint`  constructor therefore takes the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="d1507-140">Il contratto di servizio è `ICalculator`, definito e implementato nel tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="d1507-140">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="d1507-141">L'associazione utilizzata in questo esempio è <xref:System.ServiceModel.WSHttpBinding>, cioè un'associazione predefinita che viene utilizzata per la connessione agli endpoint conformi alle specifiche WS-*.</span><span class="sxs-lookup"><span data-stu-id="d1507-141">The binding used in this sample is <xref:System.ServiceModel.WSHttpBinding> which is a built-in binding that is used for connecting to endpoints that conform to the WS-* specifications.</span></span> <span data-ttu-id="d1507-142">Per ulteriori informazioni sulle associazioni di WCF, vedere [panoramica delle associazioni WCF](../../../docs/framework/wcf/bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d1507-142">For more information about WCF bindings, see [WCF Bindings Overview](../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="d1507-143">L'indirizzo viene accodato all'indirizzo di base per identificare l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d1507-143">The address is appended to the base address to identify the endpoint.</span></span> <span data-ttu-id="d1507-144">L'indirizzo specificato in questo codice è "CalculatorService", pertanto l'indirizzo completo per l'endpoint è `"http://localhost:8000/GettingStarted/CalculatorService"` aggiunta di un endpoint del servizio è facoltativa quando si utilizza .NET Framework 4.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="d1507-144">The address specified in this code is "CalculatorService" so the fully qualified address for the endpoint is `"http://localhost:8000/GettingStarted/CalculatorService"` Adding a service endpoint is optional when using .NET Framework 4.0 or later.</span></span> <span data-ttu-id="d1507-145">In queste versioni, se non viene aggiunto alcun endpoint nel codice o nella configurazione, ne viene automaticamente aggiunto uno predefinito per ogni combinazione di indirizzo di base e contratto implementata dal servizio.</span><span class="sxs-lookup"><span data-stu-id="d1507-145">In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="d1507-146">Per ulteriori informazioni sull'impostazione predefinita gli endpoint vedere [specificando un indirizzo Endpoint](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="d1507-146">For more information about default endpoints see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="d1507-147"> endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d1507-147"> default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="d1507-148">L'aggiunta dell'endpoint di un servizio è facoltativa quando si utilizza .NET Framework 4 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="d1507-148">Adding a service endpoint is optional when using .NET Framework 4 or later.</span></span> <span data-ttu-id="d1507-149">In queste versioni, se non viene aggiunto alcun endpoint nel codice o nella configurazione, ne viene automaticamente aggiunto uno predefinito per ogni combinazione di indirizzo di base e contratto implementata dal servizio.</span><span class="sxs-lookup"><span data-stu-id="d1507-149">In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="d1507-150">Per ulteriori informazioni sull'impostazione predefinita gli endpoint vedere [specificando un indirizzo Endpoint](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="d1507-150">For more information about default endpoints see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="d1507-151"> endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d1507-151"> default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
    4.  <span data-ttu-id="d1507-152">Passaggio 4: viene abilitato lo scambio di metadati.</span><span class="sxs-lookup"><span data-stu-id="d1507-152">Step 4 – Enable metadata exchange.</span></span> <span data-ttu-id="d1507-153">I client utilizzeranno lo scambio di metadati per generare i proxy che saranno utilizzati per chiamare le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="d1507-153">Clients will use metadata exchange to generate proxies that will be used to call the service operations.</span></span> <span data-ttu-id="d1507-154">Per abilitare lo scambio di metadati, creare un <xref:System.ServiceModel.Description.ServiceMetadataBehavior> dell'istanza, impostarlo del <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> proprietà `true`e aggiungere il comportamento per la <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  --> `System.ServiceModel.ServiceHost.Behaviors%2A` insieme del <xref:System.ServiceModel.ServiceHost> istanza.</span><span class="sxs-lookup"><span data-stu-id="d1507-154">To enable metadata exchange create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set it’s <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, and add the behavior to the <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A` collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>  
  
    5.  <span data-ttu-id="d1507-155">Passaggio 5: viene aperto l'oggetto <xref:System.ServiceModel.ServiceHost> per attendere i messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="d1507-155">Step 5 – Open the <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="d1507-156">Si noti che il codice attende che l'utente prema Invio.</span><span class="sxs-lookup"><span data-stu-id="d1507-156">Notice the code waits for the user to hit enter.</span></span> <span data-ttu-id="d1507-157">In caso contrario, l'applicazione verrà chiusa immediatamente e il servizio verrà arrestato. Si noti inoltre l'utilizzo di un blocco try/catch.</span><span class="sxs-lookup"><span data-stu-id="d1507-157">If you do not do this, the app will close immediately and the service will shut down.Also notice a  try/catch block used.</span></span> <span data-ttu-id="d1507-158">Dopo la creazione di un'istanza di <xref:System.ServiceModel.ServiceHost>, tutto l'altro codice viene inserito in un blocco try/catch.</span><span class="sxs-lookup"><span data-stu-id="d1507-158">After the <xref:System.ServiceModel.ServiceHost> has been instantiated, all other code is placed in a try/catch block.</span></span> <span data-ttu-id="d1507-159">Per ulteriori informazioni in modo sicuro intercettare le eccezioni generate da <xref:System.ServiceModel.ServiceHost>, vedere [evitare problemi con l'istruzione Using](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)</span><span class="sxs-lookup"><span data-stu-id="d1507-159">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Avoiding Problems with the Using Statement](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)</span></span>  
  
### <a name="to-verify-the-service-is-working"></a><span data-ttu-id="d1507-160">Per verificare il funzionamento del servizio</span><span class="sxs-lookup"><span data-stu-id="d1507-160">To verify the service is working</span></span>  
  
1.  <span data-ttu-id="d1507-161">Eseguire l'applicazione console GettingStartedHost da [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1507-161">Run the GettingStartedHost console application from inside [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span> <span data-ttu-id="d1507-162">In caso di esecuzione in [!INCLUDE[wv](../../../includes/wv-md.md)] e sistemi operativi successivi, il servizio deve essere eseguito con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="d1507-162">When running on [!INCLUDE[wv](../../../includes/wv-md.md)] and later operating systems, the service must be run with administrator privileges.</span></span> <span data-ttu-id="d1507-163">Poiché [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] è stato eseguito con privilegi di amministratore, anche GettingStartedHost viene eseguito con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="d1507-163">Because [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] was run with Administrator privileges, GettingStartedHost is also run with Administrator privileges.</span></span> <span data-ttu-id="d1507-164">È inoltre possibile avviare un nuovo prompt dei comandi che esegua il servizio con privilegi di amministratore e utilizzarlo per eseguire service.exe.</span><span class="sxs-lookup"><span data-stu-id="d1507-164">You can also start a new command prompt running it with Administrator privileges and run service.exe within it.</span></span>  
  
2.  <span data-ttu-id="d1507-165">Aprire Internet Explorer e passare alla pagina di debug del servizio in `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="d1507-165">Open Internet Explorer and browse to the service's debug page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1507-166">Esempio</span><span class="sxs-lookup"><span data-stu-id="d1507-166">Example</span></span>  
 <span data-ttu-id="d1507-167">Nell'esempio seguente sono inclusi il contratto di servizio e l'implementazione dai passaggi precedenti nell'esercitazione e l'hosting del servizio in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="d1507-167">The following example includes the service contract and implementation from previous steps in the tutorial and hosts the service in a console application.</span></span>  
  
 <span data-ttu-id="d1507-168">Per effettuare la compilazione con un compilatore da riga di comando, compilare IService1.cs e Service1. cs in una classe che fanno riferimento a libreria `System.ServiceModel.dll`.</span><span class="sxs-lookup"><span data-stu-id="d1507-168">To compile this with a command-line compiler, compile IService1.cs and Service1.cs into a class library referencing `System.ServiceModel.dll`.</span></span> <span data-ttu-id="d1507-169">Compilare inoltre Program.cs in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="d1507-169">And compile Program.cs to a console application.</span></span>  
  
```csharp
// IService1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
namespace GettingStartedLib  
{  
        [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
        public interface ICalculator  
        {  
            [OperationContract]  
            double Add(double n1, double n2);  
            [OperationContract]  
            double Subtract(double n1, double n2);  
            [OperationContract]  
            double Multiply(double n1, double n2);  
            [OperationContract]  
            double Divide(double n1, double n2);  
        }  
}  
```  
  
```csharp
// Service1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
namespace GettingStartedLib  
{  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            double result = n1 + n2;  
            Console.WriteLine("Received Add({0},{1})", n1, n2);  
            // Code added to write output to the console window.  
            Console.WriteLine("Return: {0}", result);  
            return result;  
        }  
  
        public double Subtract(double n1, double n2)  
        {  
            double result = n1 - n2;  
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);  
            Console.WriteLine("Return: {0}", result);  
            return result;  
        }  
  
        public double Multiply(double n1, double n2)  
        {  
            double result = n1 * n2;  
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);  
            Console.WriteLine("Return: {0}", result);  
            return result;  
        }  
  
        public double Divide(double n1, double n2)  
        {  
            double result = n1 / n2;  
            Console.WriteLine("Received Divide({0},{1})", n1, n2);  
            Console.WriteLine("Return: {0}", result);  
            return result;  
        }  
    }  
}  
```  
  
```csharp
//Program.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel;  
using GettingStartedLib;  
using System.ServiceModel.Description;   
  
namespace GettingStartedHost  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Step 1 of the address configuration procedure: Create a URI to serve as the base address.  
            Uri baseAddress = new Uri("http://localhost:8000/ServiceModelSamples/Service");  
  
            // Step 2 of the hosting procedure: Create ServiceHost  
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
  
            try  
            {  
                // Step 3 of the hosting procedure: Add a service endpoint.  
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");  
  
                // Step 4 of the hosting procedure: Enable metadata exchange.  
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
                smb.HttpGetEnabled = true;  
                selfHost.Description.Behaviors.Add(smb);  
  
                // Step 5 of the hosting procedure: Start (and then stop) the service.  
                selfHost.Open();  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                selfHost.Close();  
            }  
            catch (CommunicationException ce)  
            {  
                Console.WriteLine("An exception occurred: {0}", ce.Message);  
                selfHost.Abort();  
            }  
        }  
    }  
}  
```  
  
```vb
'IService1.vb  
Imports System  
Imports System.ServiceModel  
  
Namespace GettingStartedLib  
  
    <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _  
    Public Interface ICalculator  
  
        <OperationContract()> _  
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()> _  
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()> _  
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()> _  
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double  
    End Interface  
End Namespace  
```  
  
```vb
'Service1.vb  
Imports System  
Imports System.ServiceModel  
  
Namespace GettingStartedLib  
  
    Public Class CalculatorService  
        Implements ICalculator  
  
        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add  
            Dim result As Double = n1 + n2  
            ' Code added to write output to the console window.  
            Console.WriteLine("Received Add({0},{1})", n1, n2)  
            Console.WriteLine("Return: {0}", result)  
            Return result  
        End Function  
  
        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract  
            Dim result As Double = n1 - n2  
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)  
            Console.WriteLine("Return: {0}", result)  
            Return result  
  
        End Function  
  
        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply  
            Dim result As Double = n1 * n2  
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)  
            Console.WriteLine("Return: {0}", result)  
            Return result  
  
        End Function  
  
        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide  
            Dim result As Double = n1 / n2  
            Console.WriteLine("Received Divide({0},{1})", n1, n2)  
            Console.WriteLine("Return: {0}", result)  
            Return result  
  
        End Function  
    End Class  
End Namespace  
```  
  
```vb
'Module1.vb  
Imports System  
Imports System.ServiceModel  
Imports System.ServiceModel.Description  
Imports GettingStartedLibVB.GettingStartedLib  
  
Module Service  
  
    Class Program  
        Shared Sub Main()  
            ' Step 1 of the address configuration procedure: Create a URI to serve as the base address.  
            Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")  
  
            ' Step 2 of the hosting procedure: Create ServiceHost  
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)  
            Try  
  
                ' Step 3 of the hosting procedure: Add a service endpoint.  
                ' Add a service endpoint  
                selfHost.AddServiceEndpoint( _  
                    GetType(ICalculator), _  
                    New WSHttpBinding(), _  
                    "CalculatorService")  
  
                ' Step 4 of the hosting procedure: Enable metadata exchange.  
                ' Enable metadata exchange  
                Dim smb As New ServiceMetadataBehavior()  
                smb.HttpGetEnabled = True  
                selfHost.Description.Behaviors.Add(smb)  
  
                ' Step 5 of the hosting procedure: Start (and then stop) the service.  
                selfHost.Open()  
                Console.WriteLine("The service is ready.")  
                Console.WriteLine("Press <ENTER> to terminate service.")  
                Console.WriteLine()  
                Console.ReadLine()  
  
                ' Close the ServiceHostBase to shutdown the service.  
                selfHost.Close()  
            Catch ce As CommunicationException  
                Console.WriteLine("An exception occurred: {0}", ce.Message)  
                selfHost.Abort()  
            End Try  
        End Sub  
    End Class  
  
End Module  
```  
  
> [!NOTE]
>  <span data-ttu-id="d1507-170">Servizi come questo richiedono l'autorizzazione per registrare gli indirizzi HTTP nel computer per l'ascolto.</span><span class="sxs-lookup"><span data-stu-id="d1507-170">Services such as this one require permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="d1507-171">Gli account amministratore dispongono di questa autorizzazione, ma agli account senza privilegi di amministratore è necessario concedere l'autorizzazione per gli spazi dei nomi HTTP.</span><span class="sxs-lookup"><span data-stu-id="d1507-171">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="d1507-172">come configurare le prenotazioni dello spazio dei nomi, vedere [Configuring HTTP and HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="d1507-172"> how to configure namespace reservations, see [Configuring HTTP and HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="d1507-173">In caso di esecuzione in [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], il servizio.exe deve essere eseguito con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="d1507-173">When running under [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], the service.exe must be run with administrator privileges.</span></span>  
  
 <span data-ttu-id="d1507-174">Il servizio è ora in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d1507-174">Now the service is running.</span></span> <span data-ttu-id="d1507-175">Passare alla [procedura: creare un Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="d1507-175">Proceed to [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="d1507-176">Per ulteriori informazioni, vedere [esercitazione introduttiva di risoluzione dei problemi](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="d1507-176">For troubleshooting information, see [Troubleshooting the Getting Started Tutorial](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1507-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1507-177">See Also</span></span>  
 [<span data-ttu-id="d1507-178">Introduzione</span><span class="sxs-lookup"><span data-stu-id="d1507-178">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="d1507-179">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="d1507-179">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)

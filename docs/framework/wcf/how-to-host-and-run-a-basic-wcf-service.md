---
title: 'Esercitazione: ospitare ed eseguire un servizio Windows Communication Foundation di base'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 872844487578843492e05dd2abb87b50e0bec91c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291396"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="f741c-102">Esercitazione: ospitare ed eseguire un servizio Windows Communication Foundation di base</span><span class="sxs-lookup"><span data-stu-id="f741c-102">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="f741c-103">In questa esercitazione viene descritta la terza delle cinque attività necessarie per creare un'applicazione di base Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f741c-103">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="f741c-104">Per una panoramica delle esercitazioni, vedere [esercitazione: Introduzione alle applicazioni Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="f741c-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="f741c-105">L'attività successiva per la creazione di un'applicazione WCF consiste nell'ospitare un servizio WCF in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="f741c-105">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="f741c-106">Un servizio WCF espone uno o più *endpoint*, ognuno dei quali espone una o più operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="f741c-106">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="f741c-107">Un endpoint di servizio specifica le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f741c-107">A service endpoint specifies the following information:</span></span>

- <span data-ttu-id="f741c-108">Un indirizzo in cui è possibile trovare il servizio.</span><span class="sxs-lookup"><span data-stu-id="f741c-108">An address where you can find the service.</span></span>
- <span data-ttu-id="f741c-109">Associazione che contiene le informazioni che descrivono come un client deve comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="f741c-109">A binding that contains the information that describes how a client must communicate with the service.</span></span>
- <span data-ttu-id="f741c-110">Contratto che definisce la funzionalità fornita dal servizio ai propri client.</span><span class="sxs-lookup"><span data-stu-id="f741c-110">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="f741c-111">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="f741c-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="f741c-112">Creare e configurare un progetto di app console per l'hosting di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="f741c-112">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="f741c-113">Aggiungere il codice per ospitare il servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="f741c-113">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="f741c-114">Aggiornare il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f741c-114">Update the configuration file.</span></span>
> - <span data-ttu-id="f741c-115">Avviare il servizio WCF e verificare che sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f741c-115">Start the WCF service and verify it's running.</span></span>

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="f741c-116">Creare e configurare un progetto di app console per ospitare il servizio</span><span class="sxs-lookup"><span data-stu-id="f741c-116">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="f741c-117">Creare un progetto di app console in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="f741c-117">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="f741c-118">Dal menu **file** selezionare **Apri**  >  **progetto/soluzione** e passare alla soluzione **GettingStarted** creata in precedenza (*GettingStarted. sln*).</span><span class="sxs-lookup"><span data-stu-id="f741c-118">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="f741c-119">Seleziona **Apri**.</span><span class="sxs-lookup"><span data-stu-id="f741c-119">Select **Open**.</span></span>

    2. <span data-ttu-id="f741c-120">Scegliere **Esplora soluzioni**dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="f741c-120">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="f741c-121">Nella finestra di **Esplora soluzioni** selezionare la soluzione **GettingStarted** (nodo principale), quindi scegliere **Aggiungi**  >  **nuovo progetto** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="f741c-121">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="f741c-122">Nella finestra **Aggiungi nuovo progetto** sul lato sinistro selezionare la categoria **desktop di Windows** in **Visual C#** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="f741c-122">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="f741c-123">Selezionare il modello **applicazione console (.NET Framework)** e immettere *GettingStartedHost* per **nome**.</span><span class="sxs-lookup"><span data-stu-id="f741c-123">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="f741c-124">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="f741c-124">Select **OK**.</span></span>

2. <span data-ttu-id="f741c-125">Aggiungere un riferimento nel progetto **GettingStartedHost** al progetto **GettingStartedLib** :</span><span class="sxs-lookup"><span data-stu-id="f741c-125">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span>

    1. <span data-ttu-id="f741c-126">Nella finestra di **Esplora soluzioni** selezionare la cartella **riferimenti** nel progetto **GettingStartedHost** e quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="f741c-126">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="f741c-127">Nella finestra di dialogo **Aggiungi riferimento** fare clic su **soluzione**in **progetti** sul lato sinistro della finestra.</span><span class="sxs-lookup"><span data-stu-id="f741c-127">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span>

    3. <span data-ttu-id="f741c-128">Selezionare **GettingStartedLib** nella sezione centrale della finestra e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f741c-128">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span>

       <span data-ttu-id="f741c-129">Questa azione rende disponibili i tipi definiti nel progetto **GettingStartedLib** per il progetto **GettingStartedHost** .</span><span class="sxs-lookup"><span data-stu-id="f741c-129">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="f741c-130">Aggiungere un riferimento nel progetto **GettingStartedHost** all' <xref:System.ServiceModel> assembly:</span><span class="sxs-lookup"><span data-stu-id="f741c-130">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="f741c-131">Nella finestra di **Esplora soluzioni** selezionare la cartella **riferimenti** nel progetto **GettingStartedHost** e quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="f741c-131">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="f741c-132">Nella finestra **Aggiungi riferimento** , in **assembly** sul lato sinistro della finestra, selezionare **Framework**.</span><span class="sxs-lookup"><span data-stu-id="f741c-132">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="f741c-133">Selezionare **System. ServiceModel**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f741c-133">Select **System.ServiceModel**, and then select **OK**.</span></span>

    4. <span data-ttu-id="f741c-134">Salvare la soluzione selezionando **file**  >  **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="f741c-134">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="f741c-135">Aggiungere il codice per ospitare il servizio</span><span class="sxs-lookup"><span data-stu-id="f741c-135">Add code to host the service</span></span>

<span data-ttu-id="f741c-136">Per ospitare il servizio, aggiungere il codice per eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f741c-136">To host the service, you add code to do the following steps:</span></span>

1. <span data-ttu-id="f741c-137">Creare un URI per l'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="f741c-137">Create a URI for the base address.</span></span>
2. <span data-ttu-id="f741c-138">Creare un'istanza della classe per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="f741c-138">Create a class instance for hosting the service.</span></span>
3. <span data-ttu-id="f741c-139">Creare un endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="f741c-139">Create a service endpoint.</span></span>
4. <span data-ttu-id="f741c-140">Consentire lo scambio di metadati.</span><span class="sxs-lookup"><span data-stu-id="f741c-140">Enable metadata exchange.</span></span>
5. <span data-ttu-id="f741c-141">Aprire l'host del servizio per restare in attesa dei messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="f741c-141">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="f741c-142">Apportare le modifiche seguenti al codice:</span><span class="sxs-lookup"><span data-stu-id="f741c-142">Make the following changes to the code:</span></span>

1. <span data-ttu-id="f741c-143">Aprire il file **Program.cs** o **Module1. vb** nel progetto **GettingStartedHost** e sostituirne il codice con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f741c-143">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Description;
    using GettingStartedLib;

    namespace GettingStartedHost
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Step 1: Create a URI to serve as the base address.
                Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

                // Step 2: Create a ServiceHost instance.
                ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

                try
                {
                    // Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                    // Step 4: Enable metadata exchange.
                    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                    smb.HttpGetEnabled = true;
                    selfHost.Description.Behaviors.Add(smb);

                    // Step 5: Start the service.
                    selfHost.Open();
                    Console.WriteLine("The service is ready.");

                    // Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.");
                    Console.WriteLine();
                    Console.ReadLine();
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
    Imports System.ServiceModel
    Imports System.ServiceModel.Description
    Imports GettingStartedLib.GettingStartedLib

    Module Service

        Class Program
            Shared Sub Main()
                ' Step 1: Create a URI to serve as the base address.
                Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

                ' Step 2: Create a ServiceHost instance.
                Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
               Try

                    ' Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint( _
                        GetType(ICalculator), _
                        New WSHttpBinding(), _
                        "CalculatorService")

                    ' Step 4: Enable metadata exchange.
                    Dim smb As New ServiceMetadataBehavior()
                    smb.HttpGetEnabled = True
                    selfHost.Description.Behaviors.Add(smb)

                    ' Step 5: Start the service.
                    selfHost.Open()
                    Console.WriteLine("The service is ready.")

                    ' Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.")
                    Console.WriteLine()
                    Console.ReadLine()
                    selfHost.Close()

                Catch ce As CommunicationException
                    Console.WriteLine("An exception occurred: {0}", ce.Message)
                    selfHost.Abort()
                End Try
            End Sub
        End Class

    End Module
    ```

    <span data-ttu-id="f741c-144">Per informazioni sul funzionamento di questo codice, vedere la pagina relativa alla [procedura di hosting del programma](#service-hosting-program-steps).</span><span class="sxs-lookup"><span data-stu-id="f741c-144">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>

2. <span data-ttu-id="f741c-145">Aggiornare le proprietà del progetto:</span><span class="sxs-lookup"><span data-stu-id="f741c-145">Update the project properties:</span></span>

   1. <span data-ttu-id="f741c-146">Nella finestra di **Esplora soluzioni** selezionare la cartella **GettingStartedHost** e quindi selezionare **proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="f741c-146">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="f741c-147">Nella pagina delle proprietà di **GettingStartedHost** selezionare la scheda **applicazione** :</span><span class="sxs-lookup"><span data-stu-id="f741c-147">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="f741c-148">Per i progetti C#, selezionare **GettingStartedHost. Program** nell'elenco **oggetto di avvio** .</span><span class="sxs-lookup"><span data-stu-id="f741c-148">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="f741c-149">Per Visual Basic progetti, selezionare **Service. Program** dall'elenco **oggetto di avvio** .</span><span class="sxs-lookup"><span data-stu-id="f741c-149">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="f741c-150">Scegliere **Salva tutto**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="f741c-150">From the **File** menu, select **Save All**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="f741c-151">Verificare il funzionamento del servizio</span><span class="sxs-lookup"><span data-stu-id="f741c-151">Verify the service is working</span></span>

1. <span data-ttu-id="f741c-152">Compilare la soluzione, quindi eseguire l'applicazione console **GettingStartedHost** dall'interno di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f741c-152">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span>

    <span data-ttu-id="f741c-153">Il servizio deve essere eseguito con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="f741c-153">The service must be run with administrator privileges.</span></span> <span data-ttu-id="f741c-154">Poiché è stato aperto Visual Studio con privilegi di amministratore, quando si esegue **GettingStartedHost** in Visual Studio, l'applicazione viene eseguita anche con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="f741c-154">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="f741c-155">In alternativa, è possibile aprire un nuovo prompt dei comandi come amministratore (selezionare **more**  >  **Esegui come amministratore** dal menu di scelta rapida) ed eseguire **GettingStartedHost. exe** al suo interno.</span><span class="sxs-lookup"><span data-stu-id="f741c-155">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="f741c-156">Aprire un Web browser e passare alla pagina del servizio all'indirizzo `http://localhost:8000/GettingStarted/CalculatorService` .</span><span class="sxs-lookup"><span data-stu-id="f741c-156">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f741c-157">Per i servizi di questo tipo è necessaria l'autorizzazione appropriata per registrare gli indirizzi HTTP nel computer per l'ascolto.</span><span class="sxs-lookup"><span data-stu-id="f741c-157">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="f741c-158">Gli account amministratore dispongono di questa autorizzazione, ma agli account senza privilegi di amministratore è necessario concedere l'autorizzazione per gli spazi dei nomi HTTP.</span><span class="sxs-lookup"><span data-stu-id="f741c-158">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="f741c-159">Per altre informazioni su come configurare le prenotazioni dello spazio dei nomi, vedere [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md) (Configurazione di HTTP e HTTPS).</span><span class="sxs-lookup"><span data-stu-id="f741c-159">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span>

## <a name="service-hosting-program-steps"></a><span data-ttu-id="f741c-160">Passaggi del programma di hosting del servizio</span><span class="sxs-lookup"><span data-stu-id="f741c-160">Service hosting program steps</span></span>

<span data-ttu-id="f741c-161">I passaggi nel codice aggiunto per ospitare il servizio sono descritti di seguito:</span><span class="sxs-lookup"><span data-stu-id="f741c-161">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="f741c-162">**Passaggio 1**: creare un'istanza della `Uri` classe che contenga l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="f741c-162">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="f741c-163">Un URL che contiene un indirizzo di base dispone di un URI facoltativo che identifica un servizio.</span><span class="sxs-lookup"><span data-stu-id="f741c-163">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="f741c-164">L'indirizzo di base viene formattato come segue: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>` .</span><span class="sxs-lookup"><span data-stu-id="f741c-164">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="f741c-165">L'indirizzo di base per il servizio calcolatrice utilizza il trasporto HTTP, localhost, la porta 8000 e il segmento URI GettingStarted.</span><span class="sxs-lookup"><span data-stu-id="f741c-165">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="f741c-166">**Passaggio 2**: creare un'istanza della <xref:System.ServiceModel.ServiceHost> classe, che viene utilizzata per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="f741c-166">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="f741c-167">Il costruttore accetta due parametri: il tipo della classe che implementa il contratto di servizio e l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="f741c-167">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="f741c-168">**Passaggio 3**: creare un' <xref:System.ServiceModel.Description.ServiceEndpoint> istanza.</span><span class="sxs-lookup"><span data-stu-id="f741c-168">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="f741c-169">Un endpoint di un servizio è composto da un indirizzo, un'associazione e un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="f741c-169">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="f741c-170">Il <xref:System.ServiceModel.Description.ServiceEndpoint> costruttore è costituito dal tipo di interfaccia del contratto di servizio, da un'associazione e da un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="f741c-170">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="f741c-171">Il contratto di servizio è `ICalculator`, definito e implementato nel tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="f741c-171">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="f741c-172">L'associazione per questo esempio è <xref:System.ServiceModel.WSHttpBinding> , ovvero un'associazione incorporata e si connette agli endpoint conformi alle specifiche WS-\*.</span><span class="sxs-lookup"><span data-stu-id="f741c-172">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="f741c-173">Per ulteriori informazioni sulle associazioni WCF, vedere [Cenni preliminari sulle associazioni WCF](bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f741c-173">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="f741c-174">L'indirizzo viene aggiunto all'indirizzo di base per identificare l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="f741c-174">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="f741c-175">Il codice specifica l'indirizzo come CalculatorService e l'indirizzo completo per l'endpoint come `http://localhost:8000/GettingStarted/CalculatorService` .</span><span class="sxs-lookup"><span data-stu-id="f741c-175">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f741c-176">Per .NET Framework versione 4 e successive, l'aggiunta di un endpoint del servizio è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f741c-176">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="f741c-177">Per queste versioni, se non si aggiunge il codice o la configurazione, WCF aggiunge un endpoint predefinito per ogni combinazione di indirizzo di base e contratto implementato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="f741c-177">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="f741c-178">Per ulteriori informazioni sugli endpoint predefiniti, vedere [specifica di un indirizzo endpoint](specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="f741c-178">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="f741c-179">Per ulteriori informazioni sugli endpoint, le associazioni e i comportamenti predefiniti, vedere [Configurazione semplificata](simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f741c-179">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="f741c-180">**Passaggio 4**: abilitare lo scambio di metadati.</span><span class="sxs-lookup"><span data-stu-id="f741c-180">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="f741c-181">I client utilizzano lo scambio di metadati per generare proxy per chiamare le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="f741c-181">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="f741c-182">Per abilitare lo scambio di metadati, creare un' <xref:System.ServiceModel.Description.ServiceMetadataBehavior> istanza, impostarne la <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> proprietà su `true` e aggiungere l' `ServiceMetadataBehavior` oggetto alla <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> raccolta dell' <xref:System.ServiceModel.ServiceHost> istanza.</span><span class="sxs-lookup"><span data-stu-id="f741c-182">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="f741c-183">**Passaggio 5**: aprire <xref:System.ServiceModel.ServiceHost> per restare in attesa dei messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="f741c-183">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="f741c-184">L'applicazione attende la pressione del tasto **invio**.</span><span class="sxs-lookup"><span data-stu-id="f741c-184">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="f741c-185">Una volta creata l'applicazione <xref:System.ServiceModel.ServiceHost> , viene eseguito un blocco try/catch.</span><span class="sxs-lookup"><span data-stu-id="f741c-185">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="f741c-186">Per ulteriori informazioni su come rilevare in modo sicuro le eccezioni generate da <xref:System.ServiceModel.ServiceHost> , vedere [utilizzare Close and Abort per rilasciare le risorse client WCF](samples/use-close-abort-release-wcf-client-resources.md).</span><span class="sxs-lookup"><span data-stu-id="f741c-186">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f741c-187">Quando si aggiunge una libreria di servizi WCF, Visual Studio lo ospita se viene eseguito il debug avviando un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="f741c-187">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="f741c-188">Per evitare conflitti, è possibile impedire a Visual Studio di ospitare la libreria del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="f741c-188">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span>
>
> 1. <span data-ttu-id="f741c-189">Selezionare il progetto **GettingStartedLib** in **Esplora soluzioni** e scegliere **proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="f741c-189">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="f741c-190">Selezionare **opzioni WCF** e deselezionare **Avvia host del servizio WCF durante il debug di un altro progetto nella stessa soluzione**.</span><span class="sxs-lookup"><span data-stu-id="f741c-190">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f741c-191">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f741c-191">Next steps</span></span>

<span data-ttu-id="f741c-192">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="f741c-192">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="f741c-193">Creare e configurare un progetto di app console per l'hosting di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="f741c-193">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="f741c-194">Aggiungere il codice per ospitare il servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="f741c-194">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="f741c-195">Aggiornare il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f741c-195">Update the configuration file.</span></span>
> - <span data-ttu-id="f741c-196">Avviare il servizio WCF e verificare che sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f741c-196">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="f741c-197">Passare all'esercitazione successiva per apprendere come creare un client WCF.</span><span class="sxs-lookup"><span data-stu-id="f741c-197">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f741c-198">Esercitazione: creare un client WCF</span><span class="sxs-lookup"><span data-stu-id="f741c-198">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)

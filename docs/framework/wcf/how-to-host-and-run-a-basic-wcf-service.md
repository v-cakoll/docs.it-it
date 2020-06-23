---
title: 'Esercitazione: ospitare ed eseguire un servizio Windows Communication Foundation di base'
description: Informazioni su come ospitare un servizio WCF in un'applicazione console come parte di una serie di articoli che consentono di iniziare a creare un'applicazione WCF.
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 5318991087e71430523681d601d3b38c4513027b
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246129"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="42a46-103">Esercitazione: ospitare ed eseguire un servizio Windows Communication Foundation di base</span><span class="sxs-lookup"><span data-stu-id="42a46-103">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="42a46-104">In questa esercitazione viene descritta la terza delle cinque attività necessarie per creare un'applicazione di base Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="42a46-104">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="42a46-105">Per una panoramica delle esercitazioni, vedere [esercitazione: Introduzione alle applicazioni Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="42a46-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="42a46-106">L'attività successiva per la creazione di un'applicazione WCF consiste nell'ospitare un servizio WCF in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="42a46-106">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="42a46-107">Un servizio WCF espone uno o più *endpoint*, ognuno dei quali espone una o più operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="42a46-107">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="42a46-108">Un endpoint di servizio specifica le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="42a46-108">A service endpoint specifies the following information:</span></span>

- <span data-ttu-id="42a46-109">Un indirizzo in cui è possibile trovare il servizio.</span><span class="sxs-lookup"><span data-stu-id="42a46-109">An address where you can find the service.</span></span>
- <span data-ttu-id="42a46-110">Associazione che contiene le informazioni che descrivono come un client deve comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="42a46-110">A binding that contains the information that describes how a client must communicate with the service.</span></span>
- <span data-ttu-id="42a46-111">Contratto che definisce la funzionalità fornita dal servizio ai propri client.</span><span class="sxs-lookup"><span data-stu-id="42a46-111">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="42a46-112">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="42a46-112">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="42a46-113">Creare e configurare un progetto di app console per l'hosting di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="42a46-113">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="42a46-114">Aggiungere il codice per ospitare il servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="42a46-114">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="42a46-115">Aggiornare il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="42a46-115">Update the configuration file.</span></span>
> - <span data-ttu-id="42a46-116">Avviare il servizio WCF e verificare che sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="42a46-116">Start the WCF service and verify it's running.</span></span>

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="42a46-117">Creare e configurare un progetto di app console per ospitare il servizio</span><span class="sxs-lookup"><span data-stu-id="42a46-117">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="42a46-118">Creare un progetto di app console in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="42a46-118">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="42a46-119">Dal menu **file** selezionare **Apri**  >  **progetto/soluzione** e passare alla soluzione **GettingStarted** creata in precedenza (*GettingStarted. sln*).</span><span class="sxs-lookup"><span data-stu-id="42a46-119">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="42a46-120">Scegliere **Open**(Apri).</span><span class="sxs-lookup"><span data-stu-id="42a46-120">Select **Open**.</span></span>

    2. <span data-ttu-id="42a46-121">Scegliere **Esplora soluzioni**dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="42a46-121">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="42a46-122">Nella finestra di **Esplora soluzioni** selezionare la soluzione **GettingStarted** (nodo principale), quindi scegliere **Aggiungi**  >  **nuovo progetto** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="42a46-122">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="42a46-123">Nella finestra **Aggiungi nuovo progetto** sul lato sinistro selezionare la categoria **desktop di Windows** in **Visual C#** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="42a46-123">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="42a46-124">Selezionare il modello **applicazione console (.NET Framework)** e immettere *GettingStartedHost* per **nome**.</span><span class="sxs-lookup"><span data-stu-id="42a46-124">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="42a46-125">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="42a46-125">Select **OK**.</span></span>

2. <span data-ttu-id="42a46-126">Aggiungere un riferimento nel progetto **GettingStartedHost** al progetto **GettingStartedLib** :</span><span class="sxs-lookup"><span data-stu-id="42a46-126">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span>

    1. <span data-ttu-id="42a46-127">Nella finestra di **Esplora soluzioni** selezionare la cartella **riferimenti** nel progetto **GettingStartedHost** e quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="42a46-127">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="42a46-128">Nella finestra di dialogo **Aggiungi riferimento** fare clic su **soluzione**in **progetti** sul lato sinistro della finestra.</span><span class="sxs-lookup"><span data-stu-id="42a46-128">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span>

    3. <span data-ttu-id="42a46-129">Selezionare **GettingStartedLib** nella sezione centrale della finestra e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="42a46-129">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span>

       <span data-ttu-id="42a46-130">Questa azione rende disponibili i tipi definiti nel progetto **GettingStartedLib** per il progetto **GettingStartedHost** .</span><span class="sxs-lookup"><span data-stu-id="42a46-130">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="42a46-131">Aggiungere un riferimento nel progetto **GettingStartedHost** all' <xref:System.ServiceModel> assembly:</span><span class="sxs-lookup"><span data-stu-id="42a46-131">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="42a46-132">Nella finestra di **Esplora soluzioni** selezionare la cartella **riferimenti** nel progetto **GettingStartedHost** e quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="42a46-132">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="42a46-133">Nella finestra **Aggiungi riferimento** , in **assembly** sul lato sinistro della finestra, selezionare **Framework**.</span><span class="sxs-lookup"><span data-stu-id="42a46-133">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="42a46-134">Selezionare **System. ServiceModel**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="42a46-134">Select **System.ServiceModel**, and then select **OK**.</span></span>

    4. <span data-ttu-id="42a46-135">Salvare la soluzione selezionando **file**  >  **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="42a46-135">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="42a46-136">Aggiungere il codice per ospitare il servizio</span><span class="sxs-lookup"><span data-stu-id="42a46-136">Add code to host the service</span></span>

<span data-ttu-id="42a46-137">Per ospitare il servizio, aggiungere il codice per eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="42a46-137">To host the service, you add code to do the following steps:</span></span>

1. <span data-ttu-id="42a46-138">Creare un URI per l'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="42a46-138">Create a URI for the base address.</span></span>
2. <span data-ttu-id="42a46-139">Creare un'istanza della classe per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="42a46-139">Create a class instance for hosting the service.</span></span>
3. <span data-ttu-id="42a46-140">Creare un endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="42a46-140">Create a service endpoint.</span></span>
4. <span data-ttu-id="42a46-141">Consentire lo scambio di metadati.</span><span class="sxs-lookup"><span data-stu-id="42a46-141">Enable metadata exchange.</span></span>
5. <span data-ttu-id="42a46-142">Aprire l'host del servizio per restare in attesa dei messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="42a46-142">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="42a46-143">Apportare le modifiche seguenti al codice:</span><span class="sxs-lookup"><span data-stu-id="42a46-143">Make the following changes to the code:</span></span>

1. <span data-ttu-id="42a46-144">Aprire il file **Program.cs** o **Module1. vb** nel progetto **GettingStartedHost** e sostituirne il codice con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="42a46-144">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

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

    <span data-ttu-id="42a46-145">Per informazioni sul funzionamento di questo codice, vedere la pagina relativa alla [procedura di hosting del programma](#service-hosting-program-steps).</span><span class="sxs-lookup"><span data-stu-id="42a46-145">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>

2. <span data-ttu-id="42a46-146">Aggiornare le proprietà del progetto:</span><span class="sxs-lookup"><span data-stu-id="42a46-146">Update the project properties:</span></span>

   1. <span data-ttu-id="42a46-147">Nella finestra di **Esplora soluzioni** selezionare la cartella **GettingStartedHost** e quindi selezionare **proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="42a46-147">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="42a46-148">Nella pagina delle proprietà di **GettingStartedHost** selezionare la scheda **applicazione** :</span><span class="sxs-lookup"><span data-stu-id="42a46-148">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="42a46-149">Per i progetti C#, selezionare **GettingStartedHost. Program** nell'elenco **oggetto di avvio** .</span><span class="sxs-lookup"><span data-stu-id="42a46-149">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="42a46-150">Per Visual Basic progetti, selezionare **Service. Program** dall'elenco **oggetto di avvio** .</span><span class="sxs-lookup"><span data-stu-id="42a46-150">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="42a46-151">Scegliere **Salva tutto**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="42a46-151">From the **File** menu, select **Save All**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="42a46-152">Verificare il funzionamento del servizio</span><span class="sxs-lookup"><span data-stu-id="42a46-152">Verify the service is working</span></span>

1. <span data-ttu-id="42a46-153">Compilare la soluzione, quindi eseguire l'applicazione console **GettingStartedHost** dall'interno di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="42a46-153">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span>

    <span data-ttu-id="42a46-154">Il servizio deve essere eseguito con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="42a46-154">The service must be run with administrator privileges.</span></span> <span data-ttu-id="42a46-155">Poiché è stato aperto Visual Studio con privilegi di amministratore, quando si esegue **GettingStartedHost** in Visual Studio, l'applicazione viene eseguita anche con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="42a46-155">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="42a46-156">In alternativa, è possibile aprire un nuovo prompt dei comandi come amministratore (selezionare **più**  >  **Esegui come amministratore** dal menu di scelta rapida) ed eseguire **GettingStartedHost.exe** al suo interno.</span><span class="sxs-lookup"><span data-stu-id="42a46-156">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="42a46-157">Aprire un Web browser e passare alla pagina del servizio all'indirizzo `http://localhost:8000/GettingStarted/CalculatorService` .</span><span class="sxs-lookup"><span data-stu-id="42a46-157">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="42a46-158">Per i servizi di questo tipo è necessaria l'autorizzazione appropriata per registrare gli indirizzi HTTP nel computer per l'ascolto.</span><span class="sxs-lookup"><span data-stu-id="42a46-158">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="42a46-159">Gli account amministratore dispongono di questa autorizzazione, ma agli account senza privilegi di amministratore è necessario concedere l'autorizzazione per gli spazi dei nomi HTTP.</span><span class="sxs-lookup"><span data-stu-id="42a46-159">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="42a46-160">Per altre informazioni su come configurare le prenotazioni dello spazio dei nomi, vedere [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md) (Configurazione di HTTP e HTTPS).</span><span class="sxs-lookup"><span data-stu-id="42a46-160">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span>

## <a name="service-hosting-program-steps"></a><span data-ttu-id="42a46-161">Passaggi del programma di hosting del servizio</span><span class="sxs-lookup"><span data-stu-id="42a46-161">Service hosting program steps</span></span>

<span data-ttu-id="42a46-162">I passaggi nel codice aggiunto per ospitare il servizio sono descritti di seguito:</span><span class="sxs-lookup"><span data-stu-id="42a46-162">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="42a46-163">**Passaggio 1**: creare un'istanza della `Uri` classe che contenga l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="42a46-163">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="42a46-164">Un URL che contiene un indirizzo di base dispone di un URI facoltativo che identifica un servizio.</span><span class="sxs-lookup"><span data-stu-id="42a46-164">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="42a46-165">L'indirizzo di base viene formattato come segue: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>` .</span><span class="sxs-lookup"><span data-stu-id="42a46-165">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="42a46-166">L'indirizzo di base per il servizio calcolatrice utilizza il trasporto HTTP, localhost, la porta 8000 e il segmento URI GettingStarted.</span><span class="sxs-lookup"><span data-stu-id="42a46-166">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="42a46-167">**Passaggio 2**: creare un'istanza della <xref:System.ServiceModel.ServiceHost> classe, che viene utilizzata per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="42a46-167">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="42a46-168">Il costruttore accetta due parametri: il tipo della classe che implementa il contratto di servizio e l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="42a46-168">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="42a46-169">**Passaggio 3**: creare un' <xref:System.ServiceModel.Description.ServiceEndpoint> istanza.</span><span class="sxs-lookup"><span data-stu-id="42a46-169">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="42a46-170">Un endpoint di un servizio è composto da un indirizzo, un'associazione e un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="42a46-170">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="42a46-171">Il <xref:System.ServiceModel.Description.ServiceEndpoint> costruttore è costituito dal tipo di interfaccia del contratto di servizio, da un'associazione e da un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="42a46-171">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="42a46-172">Il contratto di servizio è `ICalculator`, definito e implementato nel tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="42a46-172">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="42a46-173">L'associazione per questo esempio è <xref:System.ServiceModel.WSHttpBinding> , ovvero un'associazione incorporata e si connette agli endpoint conformi alle specifiche WS-\*.</span><span class="sxs-lookup"><span data-stu-id="42a46-173">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="42a46-174">Per ulteriori informazioni sulle associazioni WCF, vedere [Cenni preliminari sulle associazioni WCF](bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="42a46-174">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="42a46-175">L'indirizzo viene aggiunto all'indirizzo di base per identificare l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="42a46-175">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="42a46-176">Il codice specifica l'indirizzo come CalculatorService e l'indirizzo completo per l'endpoint come `http://localhost:8000/GettingStarted/CalculatorService` .</span><span class="sxs-lookup"><span data-stu-id="42a46-176">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="42a46-177">Per .NET Framework versione 4 e successive, l'aggiunta di un endpoint del servizio è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="42a46-177">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="42a46-178">Per queste versioni, se non si aggiunge il codice o la configurazione, WCF aggiunge un endpoint predefinito per ogni combinazione di indirizzo di base e contratto implementato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="42a46-178">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="42a46-179">Per ulteriori informazioni sugli endpoint predefiniti, vedere [specifica di un indirizzo endpoint](specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="42a46-179">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="42a46-180">Per ulteriori informazioni sugli endpoint, le associazioni e i comportamenti predefiniti, vedere [Configurazione semplificata](simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="42a46-180">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="42a46-181">**Passaggio 4**: abilitare lo scambio di metadati.</span><span class="sxs-lookup"><span data-stu-id="42a46-181">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="42a46-182">I client utilizzano lo scambio di metadati per generare proxy per chiamare le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="42a46-182">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="42a46-183">Per abilitare lo scambio di metadati, creare un' <xref:System.ServiceModel.Description.ServiceMetadataBehavior> istanza, impostarne la <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> proprietà su `true` e aggiungere l' `ServiceMetadataBehavior` oggetto alla <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> raccolta dell' <xref:System.ServiceModel.ServiceHost> istanza.</span><span class="sxs-lookup"><span data-stu-id="42a46-183">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="42a46-184">**Passaggio 5**: aprire <xref:System.ServiceModel.ServiceHost> per restare in attesa dei messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="42a46-184">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="42a46-185">L'applicazione attende la pressione del tasto **invio**.</span><span class="sxs-lookup"><span data-stu-id="42a46-185">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="42a46-186">Una volta creata l'applicazione <xref:System.ServiceModel.ServiceHost> , viene eseguito un blocco try/catch.</span><span class="sxs-lookup"><span data-stu-id="42a46-186">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="42a46-187">Per ulteriori informazioni su come rilevare in modo sicuro le eccezioni generate da <xref:System.ServiceModel.ServiceHost> , vedere [utilizzare Close and Abort per rilasciare le risorse client WCF](samples/use-close-abort-release-wcf-client-resources.md).</span><span class="sxs-lookup"><span data-stu-id="42a46-187">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42a46-188">Quando si aggiunge una libreria di servizi WCF, Visual Studio lo ospita se viene eseguito il debug avviando un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="42a46-188">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="42a46-189">Per evitare conflitti, è possibile impedire a Visual Studio di ospitare la libreria del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="42a46-189">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span>
>
> 1. <span data-ttu-id="42a46-190">Selezionare il progetto **GettingStartedLib** in **Esplora soluzioni** e scegliere **proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="42a46-190">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="42a46-191">Selezionare **opzioni WCF** e deselezionare **Avvia host del servizio WCF durante il debug di un altro progetto nella stessa soluzione**.</span><span class="sxs-lookup"><span data-stu-id="42a46-191">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="42a46-192">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="42a46-192">Next steps</span></span>

<span data-ttu-id="42a46-193">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="42a46-193">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="42a46-194">Creare e configurare un progetto di app console per l'hosting di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="42a46-194">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="42a46-195">Aggiungere il codice per ospitare il servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="42a46-195">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="42a46-196">Aggiornare il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="42a46-196">Update the configuration file.</span></span>
> - <span data-ttu-id="42a46-197">Avviare il servizio WCF e verificare che sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="42a46-197">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="42a46-198">Passare all'esercitazione successiva per apprendere come creare un client WCF.</span><span class="sxs-lookup"><span data-stu-id="42a46-198">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="42a46-199">Esercitazione: creare un client WCF</span><span class="sxs-lookup"><span data-stu-id="42a46-199">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)

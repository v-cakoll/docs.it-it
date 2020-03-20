---
title: 'Esercitazione: Ospitare ed eseguire un servizio Windows Communication Foundation di baseTutorial: Host and run a basic Windows Communication Foundation service'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 30eb86987b83427b94c6fff22755cde3d73dd9f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184075"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="fa75c-102">Esercitazione: Ospitare ed eseguire un servizio Windows Communication Foundation di baseTutorial: Host and run a basic Windows Communication Foundation service</span><span class="sxs-lookup"><span data-stu-id="fa75c-102">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="fa75c-103">Questa esercitazione descrive la terza delle cinque attività necessarie per creare un'applicazione Windows Communication Foundation (WCF) di base.</span><span class="sxs-lookup"><span data-stu-id="fa75c-103">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="fa75c-104">Per una panoramica delle esercitazioni, vedere [Esercitazione: Introduzione alle applicazioni Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="fa75c-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="fa75c-105">L'attività successiva per la creazione di un'applicazione WCF consiste nell'ospitare un servizio WCF in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="fa75c-105">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="fa75c-106">Un servizio WCF espone uno o più *endpoint,* ognuno dei quali espone una o più operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="fa75c-106">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="fa75c-107">Un endpoint del servizio specifica le informazioni seguenti:A service endpoint specifies the following information:</span><span class="sxs-lookup"><span data-stu-id="fa75c-107">A service endpoint specifies the following information:</span></span>

- <span data-ttu-id="fa75c-108">Indirizzo in cui è possibile trovare il servizio.</span><span class="sxs-lookup"><span data-stu-id="fa75c-108">An address where you can find the service.</span></span>
- <span data-ttu-id="fa75c-109">Associazione che contiene le informazioni che descrivono come un client deve comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="fa75c-109">A binding that contains the information that describes how a client must communicate with the service.</span></span>
- <span data-ttu-id="fa75c-110">Contratto che definisce la funzionalità fornita dal servizio ai client.</span><span class="sxs-lookup"><span data-stu-id="fa75c-110">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="fa75c-111">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="fa75c-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="fa75c-112">Creare e configurare un progetto di app console per l'hosting di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="fa75c-112">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="fa75c-113">Aggiungere codice per ospitare il servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="fa75c-113">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="fa75c-114">Aggiornare il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fa75c-114">Update the configuration file.</span></span>
> - <span data-ttu-id="fa75c-115">Avviare il servizio WCF e verificare che sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fa75c-115">Start the WCF service and verify it's running.</span></span>

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="fa75c-116">Creare e configurare un progetto di app console per l'hosting del servizioCreate and configure a console app project for hosting the service</span><span class="sxs-lookup"><span data-stu-id="fa75c-116">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="fa75c-117">Creare un progetto di app console in Visual Studio:Create a console app project in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="fa75c-117">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="fa75c-118">Scegliere **Apri** > **progetto/soluzione** dal menu **File** e individuare la soluzione **GettingStarted** creata in precedenza (*GettingStarted.sln*).</span><span class="sxs-lookup"><span data-stu-id="fa75c-118">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="fa75c-119">Selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="fa75c-119">Select **Open**.</span></span>

    2. <span data-ttu-id="fa75c-120">Scegliere **Esplora soluzioni**dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="fa75c-120">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="fa75c-121">Nella finestra **Esplora soluzioni** selezionare la soluzione **GettingStarted** (nodo superiore), quindi scegliere **Aggiungi** > **nuovo progetto** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="fa75c-121">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="fa75c-122">Nella finestra **Aggiungi nuovo progetto,** sul lato sinistro, selezionare la categoria **Desktop di Windows** in Visual **Cè** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="fa75c-122">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="fa75c-123">Selezionare il modello **App console (.NET Framework)** e immettere *GettingStartedHost* come **Nome**.</span><span class="sxs-lookup"><span data-stu-id="fa75c-123">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="fa75c-124">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa75c-124">Select **OK**.</span></span>

2. <span data-ttu-id="fa75c-125">Aggiungere un riferimento nel progetto GettingStartedHost al progetto **GettingStartedLib:Add** a reference in the **GettingStartedHost** project to the GettingStartedLib project:</span><span class="sxs-lookup"><span data-stu-id="fa75c-125">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span>

    1. <span data-ttu-id="fa75c-126">Nella finestra **Esplora soluzioni** selezionare la cartella **Riferimenti** nel progetto **GettingStartedHost,** quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="fa75c-126">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="fa75c-127">Nella finestra di dialogo **Aggiungi riferimento,** in **Progetti** sul lato sinistro della finestra, selezionare **Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="fa75c-127">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span>

    3. <span data-ttu-id="fa75c-128">Selezionare **GettingStartedLib** nella sezione centrale della finestra, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa75c-128">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span>

       <span data-ttu-id="fa75c-129">Questa azione rende disponibili i tipi definiti nel progetto **GettingStartedLib** per il progetto **GettingStartedHost.**</span><span class="sxs-lookup"><span data-stu-id="fa75c-129">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="fa75c-130">Aggiungere un riferimento nel progetto GettingStartedHost all'assembly:Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span><span class="sxs-lookup"><span data-stu-id="fa75c-130">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="fa75c-131">Nella finestra **Esplora soluzioni** selezionare la cartella **Riferimenti** nel progetto **GettingStartedHost,** quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="fa75c-131">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="fa75c-132">Nella finestra **Aggiungi riferimento,** in **Assembly** sul lato sinistro della finestra, selezionare **Framework**.</span><span class="sxs-lookup"><span data-stu-id="fa75c-132">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="fa75c-133">Selezionare **System.ServiceModel**, quindi **scegliere OK**.</span><span class="sxs-lookup"><span data-stu-id="fa75c-133">Select **System.ServiceModel**, and then select **OK**.</span></span>

    4. <span data-ttu-id="fa75c-134">Salvare la soluzione selezionando Salva**tutto** **al file** > .</span><span class="sxs-lookup"><span data-stu-id="fa75c-134">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="fa75c-135">Aggiungere codice per ospitare il servizioAdd code to host the service</span><span class="sxs-lookup"><span data-stu-id="fa75c-135">Add code to host the service</span></span>

<span data-ttu-id="fa75c-136">Per ospitare il servizio, aggiungere il codice per eseguire la procedura seguente:To host the service, you add code to do the following steps:</span><span class="sxs-lookup"><span data-stu-id="fa75c-136">To host the service, you add code to do the following steps:</span></span>

1. <span data-ttu-id="fa75c-137">Creare un URI per l'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="fa75c-137">Create a URI for the base address.</span></span>
2. <span data-ttu-id="fa75c-138">Creare un'istanza della classe per l'hosting del servizio.</span><span class="sxs-lookup"><span data-stu-id="fa75c-138">Create a class instance for hosting the service.</span></span>
3. <span data-ttu-id="fa75c-139">Creare un endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="fa75c-139">Create a service endpoint.</span></span>
4. <span data-ttu-id="fa75c-140">Consentire lo scambio di metadati.</span><span class="sxs-lookup"><span data-stu-id="fa75c-140">Enable metadata exchange.</span></span>
5. <span data-ttu-id="fa75c-141">Aprire l'host del servizio per l'ascolto dei messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="fa75c-141">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="fa75c-142">Apportare le modifiche seguenti al codice:</span><span class="sxs-lookup"><span data-stu-id="fa75c-142">Make the following changes to the code:</span></span>

1. <span data-ttu-id="fa75c-143">Aprire il **file Program.cs** o **Module1.vb** nel progetto **GettingStartedHost** e sostituirne il codice con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fa75c-143">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

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
                    selfHost.Description.Behaviors.Add(smb)    ;

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

    <span data-ttu-id="fa75c-144">Per informazioni sul funzionamento di questo codice, vedere Passaggi del [programma di hosting](#service-hosting-program-steps)dei servizi.</span><span class="sxs-lookup"><span data-stu-id="fa75c-144">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>

2. <span data-ttu-id="fa75c-145">Aggiornare le proprietà del progetto:</span><span class="sxs-lookup"><span data-stu-id="fa75c-145">Update the project properties:</span></span>

   1. <span data-ttu-id="fa75c-146">Nella finestra **Esplora soluzioni** selezionare la cartella **GettingStartedHost** e quindi **scegliere Proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="fa75c-146">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="fa75c-147">Nella pagina delle proprietà GettingStartedHost selezionare la scheda **Applicazione:On** the **GettingStartedHost** properties page, select the Application tab:</span><span class="sxs-lookup"><span data-stu-id="fa75c-147">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="fa75c-148">Per i progetti in C, selezionare **GettingStartedHost.Program** dall'elenco **Oggetto di avvio.**</span><span class="sxs-lookup"><span data-stu-id="fa75c-148">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="fa75c-149">Per i progetti Visual Basic, selezionare **Service.Program** dall'elenco **Oggetto di avvio.**</span><span class="sxs-lookup"><span data-stu-id="fa75c-149">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="fa75c-150">Scegliere **Salva tutto**dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="fa75c-150">From the **File** menu, select **Save All**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="fa75c-151">Verificare che il servizio funzioni</span><span class="sxs-lookup"><span data-stu-id="fa75c-151">Verify the service is working</span></span>

1. <span data-ttu-id="fa75c-152">Compilare la soluzione e quindi eseguire l'applicazione console **GettingStartedHost** dall'interno di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fa75c-152">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span>

    <span data-ttu-id="fa75c-153">Il servizio deve essere eseguito con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="fa75c-153">The service must be run with administrator privileges.</span></span> <span data-ttu-id="fa75c-154">Poiché Visual Studio è stato aperto con privilegi di amministratore, quando si esegue **GettingStartedHost** in Visual Studio, l'applicazione viene eseguita anche con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="fa75c-154">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="fa75c-155">In alternativa, è possibile aprire un nuovo prompt dei comandi come amministratore (selezionare **Altro** > **esecuzione come amministratore** dal menu di scelta rapida) ed eseguire **GettingStartedHost.exe** al suo interno.</span><span class="sxs-lookup"><span data-stu-id="fa75c-155">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="fa75c-156">Aprire un Web browser e passare alla `http://localhost:8000/GettingStarted/CalculatorService`pagina del servizio all'indirizzo .</span><span class="sxs-lookup"><span data-stu-id="fa75c-156">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fa75c-157">Servizi come questo richiedono l'autorizzazione appropriata per registrare gli indirizzi HTTP sulla macchina per l'ascolto.</span><span class="sxs-lookup"><span data-stu-id="fa75c-157">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="fa75c-158">Gli account amministratore dispongono di questa autorizzazione, ma agli account senza privilegi di amministratore è necessario concedere l'autorizzazione per gli spazi dei nomi HTTP.</span><span class="sxs-lookup"><span data-stu-id="fa75c-158">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="fa75c-159">Per altre informazioni su come configurare le prenotazioni dello spazio dei nomi, vedere [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md) (Configurazione di HTTP e HTTPS).</span><span class="sxs-lookup"><span data-stu-id="fa75c-159">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span>

## <a name="service-hosting-program-steps"></a><span data-ttu-id="fa75c-160">Passaggi del programma di hosting dei serviziService hosting program steps</span><span class="sxs-lookup"><span data-stu-id="fa75c-160">Service hosting program steps</span></span>

<span data-ttu-id="fa75c-161">I passaggi nel codice aggiunto per ospitare il servizio sono descritti di seguito:The steps in the code you added to host the service are described as follows:</span><span class="sxs-lookup"><span data-stu-id="fa75c-161">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="fa75c-162">**Passaggio 1**: Creare `Uri` un'istanza della classe per contenere l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="fa75c-162">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="fa75c-163">Un URL che contiene un indirizzo di base ha un URI facoltativo che identifica un servizio.</span><span class="sxs-lookup"><span data-stu-id="fa75c-163">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="fa75c-164">L'indirizzo di base viene `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`formattato come segue: .</span><span class="sxs-lookup"><span data-stu-id="fa75c-164">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="fa75c-165">L'indirizzo di base per il servizio di calcolatrice utilizza il trasporto HTTP, localhost, la porta 8000 e il segmento URI GettingStarted.</span><span class="sxs-lookup"><span data-stu-id="fa75c-165">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="fa75c-166">**Passaggio 2**: Creare <xref:System.ServiceModel.ServiceHost> un'istanza della classe, che si utilizza per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="fa75c-166">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="fa75c-167">Il costruttore accetta due parametri: il tipo della classe che implementa il contratto di servizio e l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="fa75c-167">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="fa75c-168">**Passaggio 3:** Creare un'istanza. <xref:System.ServiceModel.Description.ServiceEndpoint></span><span class="sxs-lookup"><span data-stu-id="fa75c-168">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="fa75c-169">Un endpoint di un servizio è composto da un indirizzo, un'associazione e un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="fa75c-169">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="fa75c-170">Il <xref:System.ServiceModel.Description.ServiceEndpoint> costruttore è composto dal tipo di interfaccia del contratto di servizio, da un'associazione e da un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="fa75c-170">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="fa75c-171">Il contratto di servizio è `ICalculator`, definito e implementato nel tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="fa75c-171">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="fa75c-172">L'associazione per <xref:System.ServiceModel.WSHttpBinding>questo esempio è , che è un'associazione incorporata e si connette agli endpoint conformi alle specifiche di WS-.</span><span class="sxs-lookup"><span data-stu-id="fa75c-172">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="fa75c-173">Per altre informazioni sulle associazioni WCF, vedere [Cenni preliminari](bindings-overview.md)sulle associazioni WCF.</span><span class="sxs-lookup"><span data-stu-id="fa75c-173">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="fa75c-174">Aggiungere l'indirizzo all'indirizzo di base per identificare l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="fa75c-174">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="fa75c-175">Il codice specifica l'indirizzo come CalculatorService e l'indirizzo completo per l'endpoint come `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="fa75c-175">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fa75c-176">Per .NET Framework versione 4 e successive, l'aggiunta di un endpoint del servizio è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="fa75c-176">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="fa75c-177">Per queste versioni, se non si aggiunge il codice o la configurazione, WCF aggiunge un endpoint predefinito per ogni combinazione di indirizzo di base e contratto implementato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="fa75c-177">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="fa75c-178">Per ulteriori informazioni sugli endpoint predefiniti, vedere [Specifica di un indirizzo endpoint.](specifying-an-endpoint-address.md)</span><span class="sxs-lookup"><span data-stu-id="fa75c-178">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="fa75c-179">Per altre informazioni sugli endpoint, le associazioni e i comportamenti predefiniti, vedere [Configurazione semplificata](simplified-configuration.md) e [Configurazione semplificata per i servizi WCF.](samples/simplified-configuration-for-wcf-services.md)</span><span class="sxs-lookup"><span data-stu-id="fa75c-179">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="fa75c-180">**Passo 4**: Abilitare lo scambio di metadati.</span><span class="sxs-lookup"><span data-stu-id="fa75c-180">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="fa75c-181">I client utilizzano lo scambio di metadati per generare proxy per chiamare le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="fa75c-181">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="fa75c-182">Per abilitare lo <xref:System.ServiceModel.Description.ServiceMetadataBehavior> scambio dei <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> metadati, creare un'istanza, impostarne `true`la proprietà su e aggiungere l'oggetto `ServiceMetadataBehavior` all'insieme <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> dell'istanza. <xref:System.ServiceModel.ServiceHost></span><span class="sxs-lookup"><span data-stu-id="fa75c-182">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="fa75c-183">**Passo 5** <xref:System.ServiceModel.ServiceHost> : Aperto per ascoltare i messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="fa75c-183">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="fa75c-184">L'applicazione attende che si preme **Invio**.</span><span class="sxs-lookup"><span data-stu-id="fa75c-184">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="fa75c-185">Dopo l'istanza <xref:System.ServiceModel.ServiceHost>dell'applicazione , viene eseguito un blocco try/catch.</span><span class="sxs-lookup"><span data-stu-id="fa75c-185">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="fa75c-186">Per ulteriori informazioni sull'intercettazione <xref:System.ServiceModel.ServiceHost>sicura delle eccezioni generate da , vedere Usare Close and Abort per rilasciare le [risorse client WCF.](samples/use-close-abort-release-wcf-client-resources.md)</span><span class="sxs-lookup"><span data-stu-id="fa75c-186">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa75c-187">Quando si aggiunge una libreria di servizi WCF, Visual Studio la ospita automaticamente se si esegue il debug avviando un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="fa75c-187">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="fa75c-188">Per evitare conflitti, è possibile impedire a Visual Studio di ospitare la libreria del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="fa75c-188">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span>
>
> 1. <span data-ttu-id="fa75c-189">Selezionare il progetto **GettingStartedLib** in **Esplora soluzioni** e scegliere **Proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="fa75c-189">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="fa75c-190">Selezionare **Opzioni WCF** e deselezionare **Avvia host del servizio WCF durante il debug**di un altro progetto nella stessa soluzione .</span><span class="sxs-lookup"><span data-stu-id="fa75c-190">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fa75c-191">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="fa75c-191">Next steps</span></span>

<span data-ttu-id="fa75c-192">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="fa75c-192">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="fa75c-193">Creare e configurare un progetto di app console per l'hosting di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="fa75c-193">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="fa75c-194">Aggiungere codice per ospitare il servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="fa75c-194">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="fa75c-195">Aggiornare il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fa75c-195">Update the configuration file.</span></span>
> - <span data-ttu-id="fa75c-196">Avviare il servizio WCF e verificare che sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fa75c-196">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="fa75c-197">Passare all'esercitazione successiva per informazioni su come creare un client WCF.</span><span class="sxs-lookup"><span data-stu-id="fa75c-197">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fa75c-198">Esercitazione: Creare un client WCFTutorial: Create a WCF client</span><span class="sxs-lookup"><span data-stu-id="fa75c-198">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)

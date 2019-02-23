---
title: Come ospitare ed eseguire un servizio Windows Communication Foundation di base
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 73633c2c6119204f2fb608b32ae794a2e07b27d0
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747074"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="f622e-102">Come ospitare ed eseguire un servizio Windows Communication Foundation di base</span><span class="sxs-lookup"><span data-stu-id="f622e-102">How to host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="f622e-103">Questa è la terza delle sei attività necessarie per creare un'applicazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f622e-103">This is the third of six tasks required to create a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="f622e-104">Per una panoramica di tutte e sei le attività, vedere l'argomento [Esercitazione introduttiva](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="f622e-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](getting-started-tutorial.md) topic.</span></span>

<span data-ttu-id="f622e-105">In questo articolo viene descritto come ospitare un servizio Windows Communication Foundation (WCF) in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="f622e-105">This topic describes how to host a Windows Communication Foundation (WCF) service in a console application.</span></span> <span data-ttu-id="f622e-106">Questa procedura è costituita dai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f622e-106">This procedure consists of the following steps:</span></span>

- <span data-ttu-id="f622e-107">Creare un progetto di applicazione console per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="f622e-107">Create a console application project to host the service.</span></span>

- <span data-ttu-id="f622e-108">Creare un host del servizio per il servizio.</span><span class="sxs-lookup"><span data-stu-id="f622e-108">Create a service host for the service.</span></span>

- <span data-ttu-id="f622e-109">Consentire lo scambio di metadati.</span><span class="sxs-lookup"><span data-stu-id="f622e-109">Enable metadata exchange.</span></span>

- <span data-ttu-id="f622e-110">Aprire l’host del servizio.</span><span class="sxs-lookup"><span data-stu-id="f622e-110">Open the service host.</span></span>

<span data-ttu-id="f622e-111">Nell'esempio riportato dopo la procedura, viene fornito un elenco completo del codice scritto per questa attività.</span><span class="sxs-lookup"><span data-stu-id="f622e-111">A complete listing of the code written in this task is provided in the example following the procedure.</span></span>

## <a name="create-a-new-console-application-to-host-the-service"></a><span data-ttu-id="f622e-112">Creare una nuova applicazione console per ospitare il servizio</span><span class="sxs-lookup"><span data-stu-id="f622e-112">Create a new console application to host the service</span></span>

1. <span data-ttu-id="f622e-113">Creare un nuovo progetto di applicazione Console in Visual Studio facendo clic sulla soluzione di introduzione e selezionando **Add** > **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="f622e-113">Create a new Console Application project in Visual Studio by right-clicking on the Getting Started solution and selecting **Add** > **New Project**.</span></span> <span data-ttu-id="f622e-114">Nel **Aggiungi nuovo progetto** finestra di dialogo sul lato sinistro, seleziona la **Desktop di Windows** categoria sotto **Visual c#** oppure **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="f622e-114">In the **Add New Project** dialog, on the left-hand side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> <span data-ttu-id="f622e-115">Selezionare il **App Console (.NET Framework)** modello e quindi denominare il progetto **GettingStartedHost**.</span><span class="sxs-lookup"><span data-stu-id="f622e-115">Select the **Console App (.NET Framework)** template, and then name the project **GettingStartedHost**.</span></span>

2. <span data-ttu-id="f622e-116">Aggiungere un riferimento al progetto GettingStartedLib nel progetto GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="f622e-116">Add a reference to the GettingStartedLib project to the GettingStartedHost project.</span></span> <span data-ttu-id="f622e-117">Fare clic sui **riferimenti** cartella nel progetto GettingStartedHost in **Esplora soluzioni**e quindi selezionare **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="f622e-117">Right-click on the **References** folder under the GettingStartedHost project in **Solution Explorer**, and then select **Add Reference**.</span></span> <span data-ttu-id="f622e-118">Nel **Aggiungi riferimento** finestra di dialogo, seleziona **soluzione** sul lato sinistro della finestra di dialogo, scegliere GettingStartedLib nella sezione centrale della finestra di dialogo e quindi scegliere **Add**.</span><span class="sxs-lookup"><span data-stu-id="f622e-118">In the **Add Reference** dialog, select **Solution** on the left-hand side of the dialog, select GettingStartedLib in the center section of the dialog, and then choose **Add**.</span></span> <span data-ttu-id="f622e-119">In questo modo i tipi definiti in GettingStartedLib diventano disponibili nel progetto GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="f622e-119">This makes the types defined in GettingStartedLib available to the GettingStartedHost project.</span></span>

3. <span data-ttu-id="f622e-120">Aggiungere un riferimento a System. ServiceModel nel progetto GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="f622e-120">Add a reference to System.ServiceModel to the GettingStartedHost project.</span></span> <span data-ttu-id="f622e-121">Fare doppio clic il **riferimenti** cartella nel progetto GettingStartedHost in **Esplora soluzioni** e selezionare **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="f622e-121">Right-click the **References** folder under the GettingStartedHost project in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="f622e-122">Nel **Aggiungi riferimento** finestra di dialogo, seleziona **Framework** sul lato sinistro della finestra di dialogo sotto **assembly**.</span><span class="sxs-lookup"><span data-stu-id="f622e-122">In the **Add Reference** dialog, select **Framework** on the left-hand side of the dialog under **Assemblies**.</span></span> <span data-ttu-id="f622e-123">Individuare e selezionare **System. ServiceModel**, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="f622e-123">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> <span data-ttu-id="f622e-124">Salvare la soluzione selezionando **File** > **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="f622e-124">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="host-the-service"></a><span data-ttu-id="f622e-125">Host del servizio</span><span class="sxs-lookup"><span data-stu-id="f622e-125">Host the service</span></span>

<span data-ttu-id="f622e-126">Aprire il file Program.cs o Module.vb e immettere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f622e-126">Open the Program.cs or Module.vb file and enter the following code:</span></span>

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
Imports System.ServiceModel
Imports System.ServiceModel.Description
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 Create a URI to serve as the base address
            Dim baseAddress As New Uri("http://localhost:8000/GettingStarted")

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

<span data-ttu-id="f622e-127">**Passaggio 1** -crea un'istanza della classe Uri per contenere l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="f622e-127">**Step 1** - Creates an instance of the Uri class to hold the base address of the service.</span></span> <span data-ttu-id="f622e-128">I servizi vengono identificati con un URL contenente un indirizzo di base e un URI facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f622e-128">Services are identified by a URL which contains a base address and an optional URI.</span></span> <span data-ttu-id="f622e-129">L'indirizzo di base ha il formato seguente: [trasporto]://[nome-computer o dominio][:n. porta facoltativo]/[segmento URI facoltativo]. Nell'indirizzo di base per il servizio calcolatrice vengono utilizzati il trasporto HTTP, il localhost, la porta 8000 e il segmento URI "GettingStarted"</span><span class="sxs-lookup"><span data-stu-id="f622e-129">The base address is formatted as follows:[transport]://[machine-name or domain][:optional port #]/[optional URI segment]The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment "GettingStarted"</span></span>

<span data-ttu-id="f622e-130">**Passaggio 2** : crea un'istanza di <xref:System.ServiceModel.ServiceHost> classe per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="f622e-130">**Step 2** – Creates an instance of the <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="f622e-131">Il costruttore accetta due parametri, il tipo di classe che implementa il contratto di servizio e l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="f622e-131">The constructor takes two parameters, the type of the class that implements the service contract, and the base address of the service.</span></span>

<span data-ttu-id="f622e-132">**Passaggio 3** – consente di creare un <xref:System.ServiceModel.Description.ServiceEndpoint> istanza.</span><span class="sxs-lookup"><span data-stu-id="f622e-132">**Step 3** – Creates a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="f622e-133">Un endpoint di un servizio è composto da un indirizzo, un'associazione e un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="f622e-133">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="f622e-134">Il costruttore di <xref:System.ServiceModel.Description.ServiceEndpoint> accetta quindi il tipo di interfaccia del contratto di servizio, un'associazione e un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="f622e-134">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor therefore takes the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="f622e-135">Il contratto di servizio è `ICalculator`, definito e implementato nel tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="f622e-135">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="f622e-136">L'associazione utilizzata in questo esempio è <xref:System.ServiceModel.WSHttpBinding>, cioè un'associazione predefinita che viene utilizzata per la connessione agli endpoint conformi alle specifiche WS-\*.</span><span class="sxs-lookup"><span data-stu-id="f622e-136">The binding used in this sample is <xref:System.ServiceModel.WSHttpBinding> which is a built-in binding that is used for connecting to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="f622e-137">Per ulteriori informazioni sulle associazioni di WCF, vedere [Panoramica sulle associazioni di Windows Communication Foundation](bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f622e-137">For more information about WCF bindings, see [WCF Bindings Overview](bindings-overview.md).</span></span> <span data-ttu-id="f622e-138">L'indirizzo viene accodato all'indirizzo di base per identificare l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="f622e-138">The address is appended to the base address to identify the endpoint.</span></span> <span data-ttu-id="f622e-139">L'indirizzo specificato in questo codice è "CalculatorService" in modo che l'indirizzo completo per l'endpoint è `"http://localhost:8000/GettingStarted/CalculatorService"`.</span><span class="sxs-lookup"><span data-stu-id="f622e-139">The address specified in this code is "CalculatorService" so the fully qualified address for the endpoint is `"http://localhost:8000/GettingStarted/CalculatorService"`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f622e-140">L'aggiunta dell'endpoint di un servizio è facoltativa quando si utilizza .NET Framework 4 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="f622e-140">Adding a service endpoint is optional when using .NET Framework 4 or later.</span></span> <span data-ttu-id="f622e-141">In queste versioni, se non viene aggiunto alcun endpoint nel codice o nella configurazione, ne viene automaticamente aggiunto uno predefinito per ogni combinazione di indirizzo di base e contratto implementata dal servizio.</span><span class="sxs-lookup"><span data-stu-id="f622e-141">In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="f622e-142">Per altre informazioni sugli endpoint predefiniti, vedere [Specifica di un indirizzo endpoint](specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="f622e-142">For more information about default endpoints see [Specifying an Endpoint Address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="f622e-143">Per altre informazioni su endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](simplified-configuration.md) (Configurazione semplificata) e [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md) (Configurazione semplificata per servizi WCF).</span><span class="sxs-lookup"><span data-stu-id="f622e-143">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>

<span data-ttu-id="f622e-144">**Passaggio 4** : consentire lo scambio di metadati.</span><span class="sxs-lookup"><span data-stu-id="f622e-144">**Step 4** – Enable metadata exchange.</span></span> <span data-ttu-id="f622e-145">I client utilizzeranno lo scambio di metadati per generare i proxy che saranno utilizzati per chiamare le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="f622e-145">Clients will use metadata exchange to generate proxies that will be used to call the service operations.</span></span> <span data-ttu-id="f622e-146">Per abilitare lo scambio di metadati, creare un'istanza di <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, impostare la relativa proprietà <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> su `true` e aggiungere il comportamento alla raccolta <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> dell'istanza di <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="f622e-146">To enable metadata exchange create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set it’s <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, and add the behavior to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

<span data-ttu-id="f622e-147">**Passaggio 5** : aprire il <xref:System.ServiceModel.ServiceHost> in ascolto dei messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="f622e-147">**Step 5** – Open the <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="f622e-148">Si noti che il codice attende che l'utente prema Invio.</span><span class="sxs-lookup"><span data-stu-id="f622e-148">Notice the code waits for the user to hit enter.</span></span> <span data-ttu-id="f622e-149">In caso contrario, l'applicazione verrà chiusa immediatamente e il servizio verrà arrestato. Si noti inoltre l'utilizzo di un blocco try/catch.</span><span class="sxs-lookup"><span data-stu-id="f622e-149">If you do not do this, the app will close immediately and the service will shut down.Also notice a  try/catch block used.</span></span> <span data-ttu-id="f622e-150">Dopo la creazione di un'istanza di <xref:System.ServiceModel.ServiceHost>, tutto l'altro codice viene inserito in un blocco try/catch.</span><span class="sxs-lookup"><span data-stu-id="f622e-150">After the <xref:System.ServiceModel.ServiceHost> has been instantiated, all other code is placed in a try/catch block.</span></span> <span data-ttu-id="f622e-151">Per altre informazioni su una rilevazione sicura delle eccezioni generate da <xref:System.ServiceModel.ServiceHost>, vedere [utilizzare Chiudi e Interrompi per rilasciare le risorse del client WCF](samples/use-close-abort-release-wcf-client-resources.md)</span><span class="sxs-lookup"><span data-stu-id="f622e-151">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f622e-152">Quando si aggiunge una libreria di servizi WCF, Visual Studio possibile ospitarlo automaticamente quando esegue il debug avviando un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="f622e-152">When you add a WCF Service Library, Visual Studio can host it for you when you debug by starting a service host.</span></span> <span data-ttu-id="f622e-153">Per evitare conflitti è possibile disabilitare questa.</span><span class="sxs-lookup"><span data-stu-id="f622e-153">To avoid conflicts you can disable this.</span></span> 
> 1. <span data-ttu-id="f622e-154">Aprire le proprietà del progetto per GettingStartedLib.</span><span class="sxs-lookup"><span data-stu-id="f622e-154">Open Project Properties for GettingStartedLib.</span></span>
> 2. <span data-ttu-id="f622e-155">Passare a **opzioni WCF** e deselezionare **avviare durante il debug di Host servizio WCF**.</span><span class="sxs-lookup"><span data-stu-id="f622e-155">Go to **WCF Options** and uncheck **Start WCF Service Host when debugging**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="f622e-156">Verificare che il servizio sia in funzione</span><span class="sxs-lookup"><span data-stu-id="f622e-156">Verify the service is working</span></span>

1. <span data-ttu-id="f622e-157">Esegue la console GettingStartedHost all'applicazione dall'interno di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f622e-157">Run the GettingStartedHost console application from inside Visual Studio.</span></span>

   <span data-ttu-id="f622e-158">Il servizio deve essere eseguito con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="f622e-158">The service must be run with administrator privileges.</span></span> <span data-ttu-id="f622e-159">Visual Studio è stata aperta con privilegi di amministratore, anche GettingStartedHost viene eseguito con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="f622e-159">Because Visual Studio was opened with administrator privileges, GettingStartedHost is also run with administrator privileges.</span></span> <span data-ttu-id="f622e-160">È anche possibile aprire un nuovo prompt dei comandi usando **Esegui come amministratore** ed eseguire service.exe in esso contenuti.</span><span class="sxs-lookup"><span data-stu-id="f622e-160">You can also open a new command prompt using **Run as administrator** and run service.exe within it.</span></span>

2. <span data-ttu-id="f622e-161">Aprire un web browser e passare alla pagina di debug del servizio all'indirizzo `http://localhost:8000/GettingStarted/`.</span><span class="sxs-lookup"><span data-stu-id="f622e-161">Open a web browser and browse to the service's debug page at `http://localhost:8000/GettingStarted/`.</span></span> <span data-ttu-id="f622e-162">**Nota! Fine barra è significativa.**</span><span class="sxs-lookup"><span data-stu-id="f622e-162">**Note! Ending slash is significant.**</span></span>

## <a name="example"></a><span data-ttu-id="f622e-163">Esempio</span><span class="sxs-lookup"><span data-stu-id="f622e-163">Example</span></span>

<span data-ttu-id="f622e-164">Nell'esempio seguente sono inclusi il contratto di servizio e l'implementazione dai passaggi precedenti nell'esercitazione e l'hosting del servizio in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="f622e-164">The following example includes the service contract and implementation from previous steps in the tutorial and hosts the service in a console application.</span></span>

<span data-ttu-id="f622e-165">Per effettuare la compilazione con un compilatore da riga di comando, compilare IService1.cs e Service1.cs in una libreria di classi che fa riferimento a `System.ServiceModel.dll`.</span><span class="sxs-lookup"><span data-stu-id="f622e-165">To compile this with a command-line compiler, compile IService1.cs and Service1.cs into a class library that references `System.ServiceModel.dll`.</span></span> <span data-ttu-id="f622e-166">Compilare inoltre Program.cs come applicazione console.</span><span class="sxs-lookup"><span data-stu-id="f622e-166">Compile Program.cs as a console application.</span></span>

```csharp
using System;
using System.ServiceModel;

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
using System;
using System.ServiceModel;

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
            // Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

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
Imports System.ServiceModel
Imports System.ServiceModel.Description
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

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
> <span data-ttu-id="f622e-167">Servizi come questo richiedono l'autorizzazione per registrare gli indirizzi HTTP nel computer per l'ascolto.</span><span class="sxs-lookup"><span data-stu-id="f622e-167">Services such as this one require permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="f622e-168">Gli account amministratore dispongono di questa autorizzazione, ma agli account senza privilegi di amministratore è necessario concedere l'autorizzazione per gli spazi dei nomi HTTP.</span><span class="sxs-lookup"><span data-stu-id="f622e-168">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="f622e-169">Per altre informazioni su come configurare le prenotazioni dello spazio dei nomi, vedere [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md) (Configurazione di HTTP e HTTPS).</span><span class="sxs-lookup"><span data-stu-id="f622e-169">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="f622e-170">In caso di esecuzione in Visual Studio, il servizio.exe deve essere eseguito con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="f622e-170">When running under Visual Studio, the service.exe must be run with administrator privileges.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f622e-171">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f622e-171">Next steps</span></span>

<span data-ttu-id="f622e-172">Il servizio è ora in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f622e-172">Now the service is running.</span></span> <span data-ttu-id="f622e-173">Nell'attività successiva, si crea un client WCF.</span><span class="sxs-lookup"><span data-stu-id="f622e-173">In the next task, you create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f622e-174">Procedura: Creare un client WCF</span><span class="sxs-lookup"><span data-stu-id="f622e-174">How to: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)

<span data-ttu-id="f622e-175">Per altre informazioni, vedere [Troubleshooting the Getting Started Tutorial](troubleshooting-the-getting-started-tutorial.md) (Risoluzione dei problemi relativi all'esercitazione introduttiva).</span><span class="sxs-lookup"><span data-stu-id="f622e-175">For troubleshooting information, see [Troubleshooting the Getting Started Tutorial](troubleshooting-the-getting-started-tutorial.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f622e-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f622e-176">See also</span></span>

- [<span data-ttu-id="f622e-177">Introduzione</span><span class="sxs-lookup"><span data-stu-id="f622e-177">Getting Started</span></span>](samples/getting-started-sample.md)
- [<span data-ttu-id="f622e-178">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="f622e-178">Self-Host</span></span>](samples/self-host.md)
- [<span data-ttu-id="f622e-179">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="f622e-179">Hosting Services</span></span>](hosting-services.md)

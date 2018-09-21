---
title: 'Procedura: ospitare ed eseguire un servizio Windows Communication Foundation di base'
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: b79c3246b7c12a3a99a5c68586387fc30573dcb6
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2018
ms.locfileid: "46481923"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="0bc63-102">Procedura: ospitare ed eseguire un servizio Windows Communication Foundation di base</span><span class="sxs-lookup"><span data-stu-id="0bc63-102">How to: Host and Run a Basic Windows Communication Foundation Service</span></span>

<span data-ttu-id="0bc63-103">Questa è la terza delle sei attività necessarie per creare un'applicazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0bc63-103">This is the third of six tasks required to create a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="0bc63-104">Per una panoramica di tutte e sei le attività, vedere l'argomento [Esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="0bc63-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

<span data-ttu-id="0bc63-105">In questo articolo viene descritto come ospitare un servizio Windows Communication Foundation (WCF) in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="0bc63-105">This topic describes how to host a Windows Communication Foundation (WCF) service in a console application.</span></span> <span data-ttu-id="0bc63-106">Questa procedura è costituita dai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0bc63-106">This procedure consists of the following steps:</span></span>

- <span data-ttu-id="0bc63-107">Creare un progetto di applicazione console per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="0bc63-107">Create a console application project to host the service.</span></span>

- <span data-ttu-id="0bc63-108">Creare un host del servizio per il servizio.</span><span class="sxs-lookup"><span data-stu-id="0bc63-108">Create a service host for the service.</span></span>

- <span data-ttu-id="0bc63-109">Consentire lo scambio di metadati.</span><span class="sxs-lookup"><span data-stu-id="0bc63-109">Enable metadata exchange.</span></span>

- <span data-ttu-id="0bc63-110">Aprire l’host del servizio.</span><span class="sxs-lookup"><span data-stu-id="0bc63-110">Open the service host.</span></span>

<span data-ttu-id="0bc63-111">Nell'esempio riportato dopo la procedura, viene fornito un elenco completo del codice scritto per questa attività.</span><span class="sxs-lookup"><span data-stu-id="0bc63-111">A complete listing of the code written in this task is provided in the example following the procedure.</span></span>

## <a name="create-a-new-console-application-to-host-the-service"></a><span data-ttu-id="0bc63-112">Creare una nuova applicazione console per ospitare il servizio</span><span class="sxs-lookup"><span data-stu-id="0bc63-112">Create a new console application to host the service</span></span>

1. <span data-ttu-id="0bc63-113">Creare un nuovo progetto di applicazione Console in Visual Studio facendo clic sulla soluzione di introduzione e selezionando **Add** > **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="0bc63-113">Create a new Console Application project in Visual Studio by right-clicking on the Getting Started solution and selecting **Add** > **New Project**.</span></span> <span data-ttu-id="0bc63-114">Nel **Aggiungi nuovo progetto** finestra di dialogo sul lato sinistro, seleziona la **Desktop di Windows** categoria sotto **Visual c#** oppure **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="0bc63-114">In the **Add New Project** dialog, on the left-hand side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> <span data-ttu-id="0bc63-115">Selezionare il **App Console (.NET Framework)** modello e quindi denominare il progetto **GettingStartedHost**.</span><span class="sxs-lookup"><span data-stu-id="0bc63-115">Select the **Console App (.NET Framework)** template, and then name the project **GettingStartedHost**.</span></span>

2. <span data-ttu-id="0bc63-116">Aggiungere un riferimento al progetto GettingStartedLib nel progetto GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="0bc63-116">Add a reference to the GettingStartedLib project to the GettingStartedHost project.</span></span> <span data-ttu-id="0bc63-117">Fare clic sui **riferimenti** cartella nel progetto GettingStartedHost in **Esplora soluzioni**e quindi selezionare **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="0bc63-117">Right-click on the **References** folder under the GettingStartedHost project in **Solution Explorer**, and then select **Add Reference**.</span></span> <span data-ttu-id="0bc63-118">Nel **Aggiungi riferimento** finestra di dialogo, seleziona **soluzione** sul lato sinistro della finestra di dialogo, scegliere GettingStartedLib nella sezione centrale della finestra di dialogo e quindi scegliere **Add**.</span><span class="sxs-lookup"><span data-stu-id="0bc63-118">In the **Add Reference** dialog, select **Solution** on the left-hand side of the dialog, select GettingStartedLib in the center section of the dialog, and then choose **Add**.</span></span> <span data-ttu-id="0bc63-119">In questo modo i tipi definiti in GettingStartedLib diventano disponibili nel progetto GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="0bc63-119">This makes the types defined in GettingStartedLib available to the GettingStartedHost project.</span></span>

3. <span data-ttu-id="0bc63-120">Aggiungere un riferimento a System. ServiceModel nel progetto GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="0bc63-120">Add a reference to System.ServiceModel to the GettingStartedHost project.</span></span> <span data-ttu-id="0bc63-121">Fare doppio clic il **riferimenti** cartella nel progetto GettingStartedHost in **Esplora soluzioni** e selezionare **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="0bc63-121">Right-click the **References** folder under the GettingStartedHost project in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="0bc63-122">Nel **Aggiungi riferimento** finestra di dialogo, seleziona **Framework** sul lato sinistro della finestra di dialogo sotto **assembly**.</span><span class="sxs-lookup"><span data-stu-id="0bc63-122">In the **Add Reference** dialog, select **Framework** on the left-hand side of the dialog under **Assemblies**.</span></span> <span data-ttu-id="0bc63-123">Individuare e selezionare **System. ServiceModel**, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="0bc63-123">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> <span data-ttu-id="0bc63-124">Salvare la soluzione selezionando **File** > **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="0bc63-124">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="host-the-service"></a><span data-ttu-id="0bc63-125">Host del servizio</span><span class="sxs-lookup"><span data-stu-id="0bc63-125">Host the service</span></span>

<span data-ttu-id="0bc63-126">Aprire il file Program.cs o Module.vb e immettere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="0bc63-126">Open the Program.cs or Module.vb file and enter the following code:</span></span>

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

<span data-ttu-id="0bc63-127">**Passaggio 1** -crea un'istanza della classe Uri per contenere l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="0bc63-127">**Step 1** - Creates an instance of the Uri class to hold the base address of the service.</span></span> <span data-ttu-id="0bc63-128">I servizi vengono identificati con un URL contenente un indirizzo di base e un URI facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0bc63-128">Services are identified by a URL which contains a base address and an optional URI.</span></span> <span data-ttu-id="0bc63-129">L'indirizzo di base ha il formato seguente: [trasporto]://[nome-computer o dominio][:n. porta facoltativo]/[segmento URI facoltativo]. Nell'indirizzo di base per il servizio calcolatrice vengono utilizzati il trasporto HTTP, il localhost, la porta 8000 e il segmento URI "GettingStarted"</span><span class="sxs-lookup"><span data-stu-id="0bc63-129">The base address is formatted as follows:[transport]://[machine-name or domain][:optional port #]/[optional URI segment]The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment "GettingStarted"</span></span>

<span data-ttu-id="0bc63-130">**Passaggio 2** : crea un'istanza di <xref:System.ServiceModel.ServiceHost> classe per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="0bc63-130">**Step 2** – Creates an instance of the <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="0bc63-131">Il costruttore accetta due parametri, il tipo di classe che implementa il contratto di servizio e l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="0bc63-131">The constructor takes two parameters, the type of the class that implements the service contract, and the base address of the service.</span></span>

<span data-ttu-id="0bc63-132">**Passaggio 3** – consente di creare un <xref:System.ServiceModel.Description.ServiceEndpoint> istanza.</span><span class="sxs-lookup"><span data-stu-id="0bc63-132">**Step 3** – Creates a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="0bc63-133">Un endpoint di un servizio è composto da un indirizzo, un'associazione e un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="0bc63-133">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="0bc63-134">Il costruttore di <xref:System.ServiceModel.Description.ServiceEndpoint> accetta quindi il tipo di interfaccia del contratto di servizio, un'associazione e un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="0bc63-134">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor therefore takes the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="0bc63-135">Il contratto di servizio è `ICalculator`, definito e implementato nel tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="0bc63-135">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="0bc63-136">L'associazione utilizzata in questo esempio è <xref:System.ServiceModel.WSHttpBinding>, cioè un'associazione predefinita che viene utilizzata per la connessione agli endpoint conformi alle specifiche WS-\*.</span><span class="sxs-lookup"><span data-stu-id="0bc63-136">The binding used in this sample is <xref:System.ServiceModel.WSHttpBinding> which is a built-in binding that is used for connecting to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="0bc63-137">Per ulteriori informazioni sulle associazioni di WCF, vedere [Panoramica sulle associazioni di Windows Communication Foundation](../../../docs/framework/wcf/bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0bc63-137">For more information about WCF bindings, see [WCF Bindings Overview](../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="0bc63-138">L'indirizzo viene accodato all'indirizzo di base per identificare l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="0bc63-138">The address is appended to the base address to identify the endpoint.</span></span> <span data-ttu-id="0bc63-139">L'indirizzo specificato in questo codice è "CalculatorService" in modo che l'indirizzo completo per l'endpoint è `"http://localhost:8000/GettingStarted/CalculatorService"`.</span><span class="sxs-lookup"><span data-stu-id="0bc63-139">The address specified in this code is "CalculatorService" so the fully qualified address for the endpoint is `"http://localhost:8000/GettingStarted/CalculatorService"`.</span></span>

    > [!IMPORTANT]
    > Adding a service endpoint is optional when using .NET Framework 4 or later. In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service. For more information about default endpoints see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md). For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).

<span data-ttu-id="0bc63-140">**Passaggio 4** : consentire lo scambio di metadati.</span><span class="sxs-lookup"><span data-stu-id="0bc63-140">**Step 4** – Enable metadata exchange.</span></span> <span data-ttu-id="0bc63-141">I client utilizzeranno lo scambio di metadati per generare i proxy che saranno utilizzati per chiamare le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="0bc63-141">Clients will use metadata exchange to generate proxies that will be used to call the service operations.</span></span> <span data-ttu-id="0bc63-142">Per abilitare lo scambio di metadati, creare un'istanza di <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, impostare la relativa proprietà <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> su `true` e aggiungere il comportamento alla raccolta <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A` dell'istanza di <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="0bc63-142">To enable metadata exchange create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set it’s <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, and add the behavior to the <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A` collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

<span data-ttu-id="0bc63-143">**Passaggio 5** : aprire il <xref:System.ServiceModel.ServiceHost> in ascolto dei messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="0bc63-143">**Step 5** – Open the <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="0bc63-144">Si noti che il codice attende che l'utente prema Invio.</span><span class="sxs-lookup"><span data-stu-id="0bc63-144">Notice the code waits for the user to hit enter.</span></span> <span data-ttu-id="0bc63-145">In caso contrario, l'applicazione verrà chiusa immediatamente e il servizio verrà arrestato. Si noti inoltre l'utilizzo di un blocco try/catch.</span><span class="sxs-lookup"><span data-stu-id="0bc63-145">If you do not do this, the app will close immediately and the service will shut down.Also notice a  try/catch block used.</span></span> <span data-ttu-id="0bc63-146">Dopo la creazione di un'istanza di <xref:System.ServiceModel.ServiceHost>, tutto l'altro codice viene inserito in un blocco try/catch.</span><span class="sxs-lookup"><span data-stu-id="0bc63-146">After the <xref:System.ServiceModel.ServiceHost> has been instantiated, all other code is placed in a try/catch block.</span></span> <span data-ttu-id="0bc63-147">Per altre informazioni su una rilevazione sicura delle eccezioni generate da <xref:System.ServiceModel.ServiceHost>, vedere [Avoiding Problems with the Using Statement](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md) (Prevenzione dei problemi con l'istruzione Using)</span><span class="sxs-lookup"><span data-stu-id="0bc63-147">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Avoiding Problems with the Using Statement](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bc63-148">Modificare app. config in gettingstartedlib diventano in modo da riflettere le modifiche apportate nel codice:</span><span class="sxs-lookup"><span data-stu-id="0bc63-148">Edit App.config in GettingStartedLib to reflect the changes made in code:</span></span>
> 1. <span data-ttu-id="0bc63-149">Modificare la riga 14 per `<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="0bc63-149">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
> 2. <span data-ttu-id="0bc63-150">Modificare la riga 17 per `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="0bc63-150">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
> 3. <span data-ttu-id="0bc63-151">Modificare la riga 22 per `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="0bc63-151">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="0bc63-152">Verificare che il servizio sia in funzione</span><span class="sxs-lookup"><span data-stu-id="0bc63-152">Verify the service is working</span></span>

1. <span data-ttu-id="0bc63-153">Esegue la console GettingStartedHost all'applicazione dall'interno di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0bc63-153">Run the GettingStartedHost console application from inside Visual Studio.</span></span>

   <span data-ttu-id="0bc63-154">Il servizio deve essere eseguito con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="0bc63-154">The service must be run with administrator privileges.</span></span> <span data-ttu-id="0bc63-155">Visual Studio è stata aperta con privilegi di amministratore, anche GettingStartedHost viene eseguito con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="0bc63-155">Because Visual Studio was opened with administrator privileges, GettingStartedHost is also run with administrator privileges.</span></span> <span data-ttu-id="0bc63-156">È anche possibile aprire un nuovo prompt dei comandi usando **Esegui come amministratore** ed eseguire service.exe in esso contenuti.</span><span class="sxs-lookup"><span data-stu-id="0bc63-156">You can also open a new command prompt using **Run as administrator** and run service.exe within it.</span></span>

2. <span data-ttu-id="0bc63-157">Aprire un web browser e passare alla pagina di debug del servizio all'indirizzo `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="0bc63-157">Open a web browser and browse to the service's debug page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

## <a name="example"></a><span data-ttu-id="0bc63-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="0bc63-158">Example</span></span>

<span data-ttu-id="0bc63-159">Nell'esempio seguente sono inclusi il contratto di servizio e l'implementazione dai passaggi precedenti nell'esercitazione e l'hosting del servizio in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="0bc63-159">The following example includes the service contract and implementation from previous steps in the tutorial and hosts the service in a console application.</span></span>

<span data-ttu-id="0bc63-160">Per effettuare la compilazione con un compilatore da riga di comando, compilare IService1.cs e Service1.cs in una libreria di classi che fa riferimento a `System.ServiceModel.dll`.</span><span class="sxs-lookup"><span data-stu-id="0bc63-160">To compile this with a command-line compiler, compile IService1.cs and Service1.cs into a class library that references `System.ServiceModel.dll`.</span></span> <span data-ttu-id="0bc63-161">Compilare inoltre Program.cs come applicazione console.</span><span class="sxs-lookup"><span data-stu-id="0bc63-161">Compile Program.cs as a console application.</span></span>

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
> <span data-ttu-id="0bc63-162">Servizi come questo richiedono l'autorizzazione per registrare gli indirizzi HTTP nel computer per l'ascolto.</span><span class="sxs-lookup"><span data-stu-id="0bc63-162">Services such as this one require permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="0bc63-163">Gli account amministratore dispongono di questa autorizzazione, ma agli account senza privilegi di amministratore è necessario concedere l'autorizzazione per gli spazi dei nomi HTTP.</span><span class="sxs-lookup"><span data-stu-id="0bc63-163">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="0bc63-164">Per altre informazioni su come configurare le prenotazioni dello spazio dei nomi, vedere [Configuring HTTP and HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md) (Configurazione di HTTP e HTTPS).</span><span class="sxs-lookup"><span data-stu-id="0bc63-164">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="0bc63-165">In caso di esecuzione in Visual Studio, il servizio.exe deve essere eseguito con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="0bc63-165">When running under Visual Studio, the service.exe must be run with administrator privileges.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0bc63-166">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0bc63-166">Next steps</span></span>

<span data-ttu-id="0bc63-167">Il servizio è ora in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0bc63-167">Now the service is running.</span></span> <span data-ttu-id="0bc63-168">Nell'attività successiva, si crea un client WCF.</span><span class="sxs-lookup"><span data-stu-id="0bc63-168">In the next task, you create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0bc63-169">Procedura: creare un client WCF</span><span class="sxs-lookup"><span data-stu-id="0bc63-169">How to: Create a WCF client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)

<span data-ttu-id="0bc63-170">Per altre informazioni, vedere [Troubleshooting the Getting Started Tutorial](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md) (Risoluzione dei problemi relativi all'esercitazione introduttiva).</span><span class="sxs-lookup"><span data-stu-id="0bc63-170">For troubleshooting information, see [Troubleshooting the Getting Started Tutorial](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0bc63-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bc63-171">See also</span></span>

- [<span data-ttu-id="0bc63-172">Introduzione</span><span class="sxs-lookup"><span data-stu-id="0bc63-172">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="0bc63-173">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="0bc63-173">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
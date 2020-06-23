---
title: Esempio della guida introduttiva
description: Informazioni su come implementare un servizio tipico e un client tipico con WCF. Questo esempio è la base per tutti gli altri esempi di tecnologia di base.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- basic samples [WCF], getting started
ms.assetid: 967a3d94-0261-49ff-b85a-20bb07f1af20
ms.openlocfilehash: b23be1b33f227154b916429c063ec4106229bb3c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246233"
---
# <a name="getting-started-sample"></a><span data-ttu-id="824b8-104">Esempio della guida introduttiva</span><span class="sxs-lookup"><span data-stu-id="824b8-104">Getting Started Sample</span></span>

<span data-ttu-id="824b8-105">Nell'esempio Introduzione viene illustrato come implementare un servizio tipico e un client tipico utilizzando Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="824b8-105">The Getting Started sample demonstrates how to implement a typical service and a typical client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="824b8-106">Questo esempio è la base per tutti gli altri esempi di tecnologia di base.</span><span class="sxs-lookup"><span data-stu-id="824b8-106">This sample is the basis for all other basic technology samples.</span></span>

> [!NOTE]
> <span data-ttu-id="824b8-107">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="824b8-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="824b8-108">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="824b8-108">The samples may already be installed on your computer.</span></span> <span data-ttu-id="824b8-109">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="824b8-109">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="824b8-110">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="824b8-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="824b8-111">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="824b8-111">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\GettingStarted\GettingStarted`

<span data-ttu-id="824b8-112">Il servizio descrive le operazioni che esegue in un contratto di servizio che espone pubblicamente come metadati.</span><span class="sxs-lookup"><span data-stu-id="824b8-112">The service describes the operations it performs in a service contract that it exposes publicly as metadata.</span></span> <span data-ttu-id="824b8-113">Il servizio contiene inoltre il codice per implementare le operazioni.</span><span class="sxs-lookup"><span data-stu-id="824b8-113">The service also contains the code to implement the operations.</span></span>

<span data-ttu-id="824b8-114">Il client contiene una definizione del contratto di servizio e una classe proxy per accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="824b8-114">The client contains a definition of the service contract and a proxy class for accessing the service.</span></span> <span data-ttu-id="824b8-115">Il codice proxy viene generato dai metadati del servizio utilizzando lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="824b8-115">The proxy code is generated from the service metadata using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

<span data-ttu-id="824b8-116">In Windows Vista, il servizio è ospitato nel servizio Attivazione Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="824b8-116">On Windows Vista, the service is hosted in the Windows Activation Service (WAS).</span></span> <span data-ttu-id="824b8-117">In Windows XP e Windows Server 2003, è ospitato da Internet Information Services (IIS) e ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="824b8-117">On Windows XP and Windows Server 2003, it is hosted by Internet Information Services (IIS) and ASP.NET.</span></span> <span data-ttu-id="824b8-118">Ospitare un servizio in IIS o WAS consente l'attivazione automatica del servizio quando si esegue l'accesso per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="824b8-118">Hosting a service in IIS or WAS allows the service to be activated automatically when it is accessed for the first time.</span></span>

> [!NOTE]
> <span data-ttu-id="824b8-119">Se si preferisce iniziare a usare un esempio che ospita il servizio in un'applicazione console anziché IIS, vedere l'esempio [self-host](self-host.md) .</span><span class="sxs-lookup"><span data-stu-id="824b8-119">If you would prefer to get started with a sample that hosts the service in a console application instead of IIS, see the [Self-Host](self-host.md) sample.</span></span>

<span data-ttu-id="824b8-120">Il servizio e il client specificano i dettagli di accesso nelle impostazioni del file di configurazione, dettagli che forniscono flessibilità al momento della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="824b8-120">The service and client specify access details in configuration file settings, which provide flexibility at the time of deployment.</span></span> <span data-ttu-id="824b8-121">Questi dettagli comprendono una definizione dell'endpoint che specifica un indirizzo, un'associazione e un contratto.</span><span class="sxs-lookup"><span data-stu-id="824b8-121">This includes an endpoint definition that specifies an address, binding, and contract.</span></span> <span data-ttu-id="824b8-122">L'associazione specifica i dettagli di trasporto e di sicurezza per la modalità di accesso al servizio.</span><span class="sxs-lookup"><span data-stu-id="824b8-122">The binding specifies transport and security details for how the service is to be accessed.</span></span>

<span data-ttu-id="824b8-123">Il servizio configura un comportamento in fase di esecuzione per pubblicare i metadati.</span><span class="sxs-lookup"><span data-stu-id="824b8-123">The service configures a run-time behavior to publish its metadata.</span></span>

<span data-ttu-id="824b8-124">Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="824b8-124">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="824b8-125">Il contratto è definito dall'interfaccia `ICalculator` che espone operazioni matematiche (somma, sottrazione, moltiplicazione e divisione).</span><span class="sxs-lookup"><span data-stu-id="824b8-125">The contract is defined by the `ICalculator` interface, which exposes math operations (add, subtract, multiply, and divide).</span></span> <span data-ttu-id="824b8-126">Il client esegue richieste a un'operazione matematica specificata e il servizio risponde fornendo il risultato.</span><span class="sxs-lookup"><span data-stu-id="824b8-126">The client makes requests to a given math operation and the service replies with the result.</span></span> <span data-ttu-id="824b8-127">Il servizio implementa un contratto `ICalculator` definito nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="824b8-127">The service implements an `ICalculator` contract that is defined in the following code.</span></span>

```vb
' Define a service contract.
    <ServiceContract(Namespace:="http://Microsoft.Samples.GettingStarted")>
     Public Interface ICalculator
        <OperationContract()>
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
    End Interface
```

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
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
```

<span data-ttu-id="824b8-128">L'implementazione del servizio calcola e restituisce il risultato appropriato, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="824b8-128">The service implementation calculates and returns the appropriate result, as shown in the following example code.</span></span>

```vb
' Service class which implements the service contract.
Public Class CalculatorService
Implements ICalculator
Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
Return n1 + n2
End Function

Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
Return n1 - n2
End Function

Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
Return n1 * n2
End Function

Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
Return n1 / n2
End Function
End Class
```

```csharp
// Service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public double Subtract(double n1, double n2)
    {
        return n1 - n2;
    }
    public double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }
    public double Divide(double n1, double n2)
    {
        return n1 / n2;
    }
}
```

<span data-ttu-id="824b8-129">Il servizio espone un endpoint per comunicare con il servizio che viene definito mediante un file di configurazione (Web.config), come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="824b8-129">The service exposes an endpoint for communicating with the service, defined using a configuration file (Web.config), as shown in the following sample configuration.</span></span>

```xaml
<services>
    <service
        name="Microsoft.ServiceModel.Samples.CalculatorService"
        behaviorConfiguration="CalculatorServiceBehavior">
        <!-- ICalculator is exposed at the base address provided by
         host: http://localhost/servicemodelsamples/service.svc.  -->
       <endpoint address=""
              binding="wsHttpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
       ...
    </service>
</services>
```

<span data-ttu-id="824b8-130">Il servizio espone l'endpoint dell'indirizzo di base fornito dall'host IIS o WAS.</span><span class="sxs-lookup"><span data-stu-id="824b8-130">The service exposes the endpoint at the base address provided by the IIS or WAS host.</span></span> <span data-ttu-id="824b8-131">L'associazione è configurata con una classe <xref:System.ServiceModel.WSHttpBinding> standard che fornisce comunicazione HTTP e protocolli del servizio Web standard per l'indirizzamento e la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="824b8-131">The binding is configured with a standard <xref:System.ServiceModel.WSHttpBinding>, which provides HTTP communication and standard Web service protocols for addressing and security.</span></span> <span data-ttu-id="824b8-132">Il contratto rappresenta il `ICalculator` implementato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="824b8-132">The contract is the `ICalculator` implemented by the service.</span></span>

<span data-ttu-id="824b8-133">Come configurato, è possibile accedere al servizio `http://localhost/servicemodelsamples/service.svc` da un client nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="824b8-133">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.svc` by a client on the same computer.</span></span> <span data-ttu-id="824b8-134">Affinché i client presenti nei computer remoti accedano al servizio, è necessario specificare un nome di dominio completo anziché localhost.</span><span class="sxs-lookup"><span data-stu-id="824b8-134">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span>

<span data-ttu-id="824b8-135">Per impostazione predefinita il framework non espone metadati.</span><span class="sxs-lookup"><span data-stu-id="824b8-135">The framework does not expose metadata by default.</span></span> <span data-ttu-id="824b8-136">Di conseguenza, il servizio attiva <xref:System.ServiceModel.Description.ServiceMetadataBehavior> ed espone un endpoint di scambio di metadati (MEX) in `http://localhost/servicemodelsamples/service.svc/mex` .</span><span class="sxs-lookup"><span data-stu-id="824b8-136">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> and exposes a metadata exchange (MEX) endpoint at `http://localhost/servicemodelsamples/service.svc/mex`.</span></span> <span data-ttu-id="824b8-137">Nella configurazione seguente viene illustrata questa evenienza.</span><span class="sxs-lookup"><span data-stu-id="824b8-137">The following configuration demonstrates this.</span></span>

```xaml
<system.serviceModel>
  <services>
    <service
        name="Microsoft.ServiceModel.Samples.CalculatorService"
        behaviorConfiguration="CalculatorServiceBehavior">
      ...
      <!-- the mex endpoint is exposed at
       http://localhost/servicemodelsamples/service.svc/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>

  <!--For debugging purposes set the includeExceptionDetailInFaults
   attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True"/>
        <serviceDebug includeExceptionDetailInFaults="False" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```

<span data-ttu-id="824b8-138">Il client comunica utilizzando un tipo di contratto specificato utilizzando una classe client generata dallo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="824b8-138">The client communicates using a given contract type by using a client class that is generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="824b8-139">Questo client generato è contenuto nel file generatedClient.cs o generatedClient.vb.</span><span class="sxs-lookup"><span data-stu-id="824b8-139">This generated client is contained in the file generatedClient.cs or generatedClient.vb.</span></span> <span data-ttu-id="824b8-140">Questa utilità recupera metadati per un servizio specificato e genera un client che viene utilizzato dall'applicazione client per comunicare utilizzando un tipo di contratto specificato.</span><span class="sxs-lookup"><span data-stu-id="824b8-140">This utility retrieves metadata for a given service and generates a client for use by the client application to communicate using a given contract type.</span></span> <span data-ttu-id="824b8-141">Il servizio ospitato deve essere disponibile per generare il codice client, perché il servizio viene utilizzato per recuperare i metadati aggiornati.</span><span class="sxs-lookup"><span data-stu-id="824b8-141">The hosted service must be available to generate the client code, because the service is used to retrieve the updated metadata.</span></span>

 <span data-ttu-id="824b8-142">Eseguire il comando seguente dal prompt dei comandi SDK nella directory del client per generare il proxy tipizzato:</span><span class="sxs-lookup"><span data-stu-id="824b8-142">Run the following command from the SDK command prompt in the client directory to generate the typed proxy:</span></span>

```console
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs
```

<span data-ttu-id="824b8-143">Per generare il client in Visual Basic, immettere il codice seguente nel prompt dei comandi SDK:</span><span class="sxs-lookup"><span data-stu-id="824b8-143">To generate client in Visual Basic type the following from the SDK command prompt:</span></span>

`Svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb`

<span data-ttu-id="824b8-144">Utilizzando il client generato, il client può accedere a un endpoint del servizio specificato configurando l'indirizzo e l'associazione appropriati.</span><span class="sxs-lookup"><span data-stu-id="824b8-144">By using the generated client, the client can access a given service endpoint by configuring the appropriate address and binding.</span></span> <span data-ttu-id="824b8-145">Analogamente al servizio, il client utilizza un file di configurazione (App.config) per specificare l'endpoint con il quale desidera comunicare.</span><span class="sxs-lookup"><span data-stu-id="824b8-145">Like the service, the client uses a configuration file (App.config) to specify the endpoint with which it wants to communicate.</span></span> <span data-ttu-id="824b8-146">La configurazione dell'endpoint client è costituita da un indirizzo assoluto per l'endpoint del servizio, l'associazione e il contratto, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="824b8-146">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract, as shown in the following example.</span></span>

```xaml
<client>
     <endpoint
         address="http://localhost/servicemodelsamples/service.svc"
         binding="wsHttpBinding"
         contract=" Microsoft.ServiceModel.Samples.ICalculator" />
</client>
```

<span data-ttu-id="824b8-147">L'implementazione del client crea un'istanza del client e utilizza l'interfaccia tipizzata per avviare la comunicazione con il servizio, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="824b8-147">The client implementation instantiates the client and uses the typed interface to begin communicating with the service, as shown in the following example code.</span></span>

```vb
' Create a client
Dim client As New CalculatorClient()

' Call the Add service operation.
            Dim value1 = 100.0R
            Dim value2 = 15.99R
            Dim result = client.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

' Call the Subtract service operation.
value1 = 145.00R
value2 = 76.54R
result = client.Subtract(value1, value2)
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

' Call the Multiply service operation.
value1 = 9.00R
value2 = 81.25R
result = client.Multiply(value1, value2)
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

' Call the Divide service operation.
value1 = 22.00R
value2 = 7.00R
result = client.Divide(value1, value2)
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

'Closing the client gracefully closes the connection and cleans up resources
```

```csharp
// Create a client.
CalculatorClient client = new CalculatorClient();

// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = client.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

// Call the Subtract service operation.
value1 = 145.00D;
value2 = 76.54D;
result = client.Subtract(value1, value2);
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

// Call the Multiply service operation.
value1 = 9.00D;
value2 = 81.25D;
result = client.Multiply(value1, value2);
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

// Call the Divide service operation.
value1 = 22.00D;
value2 = 7.00D;
result = client.Divide(value1, value2);
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

//Closing the client releases all communication resources.
client.Close();
```

<span data-ttu-id="824b8-148">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="824b8-148">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="824b8-149">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="824b8-149">Press ENTER in the client window to shut down the client.</span></span>

```output
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

<span data-ttu-id="824b8-150">Nell'esempio della guida introduttiva viene illustrata la modalità standard per creare un servizio e un client.</span><span class="sxs-lookup"><span data-stu-id="824b8-150">The Getting Started sample shows the standard way to create a service and client.</span></span> <span data-ttu-id="824b8-151">L'altra build di [base](basic-sample.md) di questo esempio per illustrare le funzionalità specifiche del prodotto.</span><span class="sxs-lookup"><span data-stu-id="824b8-151">The other [Basic](basic-sample.md) build on this sample to demonstrate specific product features.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="824b8-152">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="824b8-152">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="824b8-153">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="824b8-153">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="824b8-154">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="824b8-154">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="824b8-155">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="824b8-155">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="824b8-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="824b8-156">See also</span></span>

- [<span data-ttu-id="824b8-157">Procedura: ospitare un servizio WCF in un'applicazione gestita</span><span class="sxs-lookup"><span data-stu-id="824b8-157">How to: Host a WCF Service in a Managed Application</span></span>](../how-to-host-a-wcf-service-in-a-managed-application.md)
- [<span data-ttu-id="824b8-158">Procedura: ospitare un servizio WCF in IIS</span><span class="sxs-lookup"><span data-stu-id="824b8-158">How to: Host a WCF Service in IIS</span></span>](../feature-details/how-to-host-a-wcf-service-in-iis.md)

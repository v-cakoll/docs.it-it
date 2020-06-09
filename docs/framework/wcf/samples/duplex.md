---
title: Duplex
ms.date: 03/30/2017
helpviewer_keywords:
- Duplex Service Contract
ms.assetid: bc5de6b6-1a63-42a3-919a-67d21bae24e0
ms.openlocfilehash: 77eab6a4975fc67c20558a53f399c7e709215587
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575199"
---
# <a name="duplex"></a><span data-ttu-id="31ac3-102">Duplex</span><span class="sxs-lookup"><span data-stu-id="31ac3-102">Duplex</span></span>

<span data-ttu-id="31ac3-103">Nell'esempio duplex viene illustrato come definire e implementare un contratto duplex.</span><span class="sxs-lookup"><span data-stu-id="31ac3-103">The Duplex sample demonstrates how to define and implement a duplex contract.</span></span> <span data-ttu-id="31ac3-104">Una comunicazione duplex ha luogo quando un client stabilisce una sessione con un servizio e fornisce a quest'ultimo un canale usabile per inviare messaggi al client.</span><span class="sxs-lookup"><span data-stu-id="31ac3-104">Duplex communication occurs when a client establishes a session with a service and gives the service a channel on which the service can send messages back to the client.</span></span> <span data-ttu-id="31ac3-105">Questo esempio è basato sul [Introduzione](getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="31ac3-105">This sample is based on the [Getting Started](getting-started-sample.md).</span></span> <span data-ttu-id="31ac3-106">Un contratto duplex è definito come una coppia di interfacce: un'interfaccia principale dal client al servizio e un'interfaccia di callback dal servizio al client.</span><span class="sxs-lookup"><span data-stu-id="31ac3-106">A duplex contract is defined as a pair of interfaces—a primary interface from the client to the service and a callback interface from the service to the client.</span></span> <span data-ttu-id="31ac3-107">In questo esempio, l'interfaccia `ICalculatorDuplex` consente al client di eseguire operazioni matematiche, calcolando il risultato in una sessione.</span><span class="sxs-lookup"><span data-stu-id="31ac3-107">In this sample, the `ICalculatorDuplex` interface allows the client to perform math operations, calculating the result over a session.</span></span> <span data-ttu-id="31ac3-108">Il servizio restituisce i risultati sull'interfaccia `ICalculatorDuplexCallback`.</span><span class="sxs-lookup"><span data-stu-id="31ac3-108">The service returns results on the `ICalculatorDuplexCallback` interface.</span></span> <span data-ttu-id="31ac3-109">Poiché occorre definire un contesto per correlare il set di messaggi scambiati fra il client e il servizio, i contratti duplex richiedono una sessione.</span><span class="sxs-lookup"><span data-stu-id="31ac3-109">A duplex contract requires a session, because a context must be established to correlate the set of messages being sent between the client and the service.</span></span>

> [!NOTE]
> <span data-ttu-id="31ac3-110">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="31ac3-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="31ac3-111">In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="31ac3-111">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="31ac3-112">Il contratto duplex è definito come segue:</span><span class="sxs-lookup"><span data-stu-id="31ac3-112">The duplex contract is defined as follows:</span></span>

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required,
                 CallbackContract=typeof(ICalculatorDuplexCallback))]
public interface ICalculatorDuplex
{
    [OperationContract(IsOneWay = true)]
    void Clear();
    [OperationContract(IsOneWay = true)]
    void AddTo(double n);
    [OperationContract(IsOneWay = true)]
    void SubtractFrom(double n);
    [OperationContract(IsOneWay = true)]
    void MultiplyBy(double n);
    [OperationContract(IsOneWay = true)]
    void DivideBy(double n);
}

public interface ICalculatorDuplexCallback
{
    [OperationContract(IsOneWay = true)]
    void Result(double result);
    [OperationContract(IsOneWay = true)]
    void Equation(string eqn);
}
```

<span data-ttu-id="31ac3-113">La classe `CalculatorService` implementa l'interfaccia `ICalculatorDuplex` primaria.</span><span class="sxs-lookup"><span data-stu-id="31ac3-113">The `CalculatorService` class implements the primary `ICalculatorDuplex` interface.</span></span> <span data-ttu-id="31ac3-114">Il servizio usa la modalità di istanza <xref:System.ServiceModel.InstanceContextMode.PerSession> per gestire il risultato per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="31ac3-114">The service uses the <xref:System.ServiceModel.InstanceContextMode.PerSession> instance mode to maintain the result for each session.</span></span> <span data-ttu-id="31ac3-115">Una proprietà privata denominata `Callback` viene usata per far accedere il canale callback al client.</span><span class="sxs-lookup"><span data-stu-id="31ac3-115">A private property named `Callback` is used to access the callback channel to the client.</span></span> <span data-ttu-id="31ac3-116">Il servizio usa il callback per inviare i messaggi al client tramite l'interfaccia callback.</span><span class="sxs-lookup"><span data-stu-id="31ac3-116">The service uses the callback for sending messages back to the client through the callback interface.</span></span>

```csharp
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]
public class CalculatorService : ICalculatorDuplex
{
    double result = 0.0D;
    string equation;

    public CalculatorService()
    {
        equation = result.ToString();
    }

    public void Clear()
    {
        Callback.Equation($"{equation} = {result}");
        equation = result.ToString();
    }

    public void AddTo(double n)
    {
        result += n;
        equation += $" + {n}";
        Callback.Result(result);
    }

    //...

    ICalculatorDuplexCallback Callback
    {
        get
        {
            return OperationContext.Current.GetCallbackChannel<ICalculatorDuplexCallback>();
        }
    }
}
```

<span data-ttu-id="31ac3-117">Il client deve fornire una classe che implementi l'interfaccia callback del contratto duplex per ricevere messaggi dal servizio.</span><span class="sxs-lookup"><span data-stu-id="31ac3-117">The client must provide a class that implements the callback interface of the duplex contract, for receiving messages from the service.</span></span> <span data-ttu-id="31ac3-118">Nell'esempio, viene definita una classe `CallbackHandler` per implementare l'interfaccia `ICalculatorDuplexCallback`.</span><span class="sxs-lookup"><span data-stu-id="31ac3-118">In the sample, a `CallbackHandler` class is defined to implement the `ICalculatorDuplexCallback` interface.</span></span>

```csharp
public class CallbackHandler : ICalculatorDuplexCallback
{
   public void Result(double result)
   {
      Console.WriteLine("Result({0})", result);
   }

   public void Equation(string equation)
   {
      Console.WriteLine("Equation({0}", equation);
   }
}
```

<span data-ttu-id="31ac3-119">Il proxy che viene generato per un contratto duplex richiede che venga fornito un <xref:System.ServiceModel.InstanceContext> dopo la costruzione.</span><span class="sxs-lookup"><span data-stu-id="31ac3-119">The proxy that is generated for a duplex contract requires a <xref:System.ServiceModel.InstanceContext> to be provided upon construction.</span></span> <span data-ttu-id="31ac3-120">La classe <xref:System.ServiceModel.InstanceContext> viene usata come sito per un oggetto che implementa l'interfaccia di callback e gestisce i messaggi restituiti dal servizio.</span><span class="sxs-lookup"><span data-stu-id="31ac3-120">This <xref:System.ServiceModel.InstanceContext> is used as the site for an object that implements the callback interface and handles messages that are sent back from the service.</span></span> <span data-ttu-id="31ac3-121">Una classe <xref:System.ServiceModel.InstanceContext> viene costruita con un'istanza della classe `CallbackHandler`.</span><span class="sxs-lookup"><span data-stu-id="31ac3-121">An <xref:System.ServiceModel.InstanceContext> is constructed with an instance of the `CallbackHandler` class.</span></span> <span data-ttu-id="31ac3-122">Questo oggetto gestisce i messaggi inviati dal servizio al client sull'interfaccia di callback.</span><span class="sxs-lookup"><span data-stu-id="31ac3-122">This object handles messages sent from the service to the client on the callback interface.</span></span>

```csharp
// Construct InstanceContext to handle messages on callback interface.
InstanceContext instanceContext = new InstanceContext(new CallbackHandler());

// Create a client.
CalculatorDuplexClient client = new CalculatorDuplexClient(instanceContext);

Console.WriteLine("Press <ENTER> to terminate client once the output is displayed.");
Console.WriteLine();

// Call the AddTo service operation.
double value = 100.00D;
client.AddTo(value);

// Call the SubtractFrom service operation.
value = 50.00D;
client.SubtractFrom(value);

// Call the MultiplyBy service operation.
value = 17.65D;
client.MultiplyBy(value);

// Call the DivideBy service operation.
value = 2.00D;
client.DivideBy(value);

// Complete equation.
client.Clear();

Console.ReadLine();

//Closing the client gracefully closes the connection and cleans up resources.
client.Close();
```

<span data-ttu-id="31ac3-123">La configurazione è stata modificata in modo da fornire un'associazione che supporta sia la comunicazione della sessione che la comunicazione duplex.</span><span class="sxs-lookup"><span data-stu-id="31ac3-123">The configuration has been modified to provide a binding that supports both session communication and duplex communication.</span></span> <span data-ttu-id="31ac3-124">L'elemento `wsDualHttpBinding` supporta la comunicazione della sessione e consente la comunicazione duplex fornendo connessioni HTTP doppie, una per ogni direzione.</span><span class="sxs-lookup"><span data-stu-id="31ac3-124">The `wsDualHttpBinding` supports session communication and allows duplex communication by providing dual HTTP connections, one for each direction.</span></span> <span data-ttu-id="31ac3-125">Nel servizio, l'unica differenza di configurazione è l'associazione usata.</span><span class="sxs-lookup"><span data-stu-id="31ac3-125">On the service, the only difference in configuration is the binding that is used.</span></span> <span data-ttu-id="31ac3-126">Nel client, è necessario configurare un indirizzo usabile dal server per la connessione al client, come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="31ac3-126">On the client, you must configure an address that the server can use to connect to the client as shown in the following sample configuration.</span></span>

```xml
<client>
  <endpoint name=""
            address="http://localhost/servicemodelsamples/service.svc"
            binding="wsDualHttpBinding"
            bindingConfiguration="DuplexBinding"
            contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />
</client>

<bindings>
  <!-- Configure a binding that support duplex communication. -->
  <wsDualHttpBinding>
    <binding name="DuplexBinding"
             clientBaseAddress="http://localhost:8000/myClient/">
    </binding>
  </wsDualHttpBinding>
</bindings>
```

<span data-ttu-id="31ac3-127">Quando si esegue l'esempio, vengono visualizzati i messaggi restituiti al client sull'interfaccia di callback inviata dal servizio.</span><span class="sxs-lookup"><span data-stu-id="31ac3-127">When you run the sample, you see the messages that are returned to the client on the callback interface that is sent from the service.</span></span> <span data-ttu-id="31ac3-128">Una volta completate tutte le operazioni, vengono visualizzati tutti i risultati intermedi, seguiti dall'intera equazione.</span><span class="sxs-lookup"><span data-stu-id="31ac3-128">Each intermediate result is displayed, followed by the entire equation upon the completion of all operations.</span></span> <span data-ttu-id="31ac3-129">Premere INVIO per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="31ac3-129">Press ENTER to shut down the client.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="31ac3-130">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="31ac3-130">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="31ac3-131">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="31ac3-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="31ac3-132">Per compilare l'edizione C#, C++ o Visual Basic .NET della soluzione, seguire le istruzioni in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="31ac3-132">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="31ac3-133">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="31ac3-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="31ac3-134">Quando si esegue il client in una configurazione a più computer, assicurarsi di sostituire "localhost" sia nell'attributo dell'elemento `address` [ \<endpoint> \<client> dell'](../../configure-apps/file-schema/wcf/endpoint-of-client.md) elemento che nell' `clientBaseAddress` attributo dell'elemento [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) dell' [\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md) elemento con il nome del computer appropriato, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="31ac3-134">When running the client in a cross-machine configuration, be sure to replace "localhost" in both the `address` attribute of the [\<endpoint> of \<client>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element and the `clientBaseAddress` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element of the [\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md) element with the name of the appropriate machine, as shown in the following:</span></span>

    ```xml
    <client>
        <endpoint name = ""
        address="http://service_machine_name/servicemodelsamples/service.svc"
        ... />
    </client>
    ...
    <wsDualHttpBinding>
        <binding name="DuplexBinding" clientBaseAddress="http://client_machine_name:8000/myClient/">
        </binding>
    </wsDualHttpBinding>
    ```

> [!IMPORTANT]
> <span data-ttu-id="31ac3-135">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="31ac3-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="31ac3-136">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="31ac3-136">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="31ac3-137">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="31ac3-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="31ac3-138">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="31ac3-138">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Duplex`

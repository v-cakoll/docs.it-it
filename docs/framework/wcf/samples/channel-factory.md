---
title: Channel Factory
ms.date: 03/30/2017
ms.assetid: 09b53aa1-b13c-476c-a461-e82fcacd2a8b
ms.openlocfilehash: 2aa44c4ef274fa548d490b0d8a648457a7b1e03b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600659"
---
# <a name="channel-factory"></a><span data-ttu-id="84262-102">Channel Factory</span><span class="sxs-lookup"><span data-stu-id="84262-102">Channel Factory</span></span>

<span data-ttu-id="84262-103">In questo esempio viene illustrato in che modo un'applicazione client può creare un canale con la classe <xref:System.ServiceModel.ChannelFactory> anziché un client generato.</span><span class="sxs-lookup"><span data-stu-id="84262-103">This sample demonstrates how a client application can create a channel with the <xref:System.ServiceModel.ChannelFactory> class instead of a generated client.</span></span> <span data-ttu-id="84262-104">Questo esempio si basa sul [Introduzione](getting-started-sample.md) che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="84262-104">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span>

> [!NOTE]
> <span data-ttu-id="84262-105">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="84262-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="84262-106">In questo esempio viene utilizzata la classe <xref:System.ServiceModel.ChannelFactory%601> per creare un canale a un endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="84262-106">This sample uses the <xref:System.ServiceModel.ChannelFactory%601> class to create a channel to a service endpoint.</span></span> <span data-ttu-id="84262-107">In genere, per creare un canale per un endpoint di servizio si genera un tipo di client con lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) e si crea un'istanza del tipo generato.</span><span class="sxs-lookup"><span data-stu-id="84262-107">Typically, to create a channel to a service endpoint you generate a client type with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) and create an instance of the generated type.</span></span> <span data-ttu-id="84262-108">È anche possibile creare un canale utilizzando la classe <xref:System.ServiceModel.ChannelFactory%601>, come illustrato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="84262-108">You can also create a channel by using the <xref:System.ServiceModel.ChannelFactory%601> class, as demonstrated in this sample.</span></span> <span data-ttu-id="84262-109">Il servizio creato dal codice di esempio seguente è identico al servizio nel [Introduzione](getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="84262-109">The service created by the following sample code is identical to the service in the [Getting Started](getting-started-sample.md).</span></span>

```csharp
EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");
WSHttpBinding binding = new WSHttpBinding();
ChannelFactory<ICalculator> factory = new
                    ChannelFactory<ICalculator>(binding, address);
ICalculator channel = factory.CreateChannel();
```

> [!IMPORTANT]
> <span data-ttu-id="84262-110">Se si esegue questo esempio in uno scenario a più computer, è necessario sostituire "localhost" nel codice precedente con il nome completo del computer che sta eseguendo il servizio.</span><span class="sxs-lookup"><span data-stu-id="84262-110">If you are running this sample in a cross-machine scenario, you must replace "localhost" in the preceding code with the fully-qualified name of the machine that is running the service.</span></span> <span data-ttu-id="84262-111">In questo esempio non viene utilizzata la configurazione per impostare l'indirizzo dell'endpoint, pertanto questa operazione deve essere eseguita nel codice.</span><span class="sxs-lookup"><span data-stu-id="84262-111">This sample does not use configuration to set the endpoint address, so this must be done in code.</span></span>

<span data-ttu-id="84262-112">Quando il canale è stato creato, le operazioni del servizio possono essere richiamate in modo analogo a un client generato.</span><span class="sxs-lookup"><span data-stu-id="84262-112">Once the channel is created, service operations can be invoked just as with a generated client.</span></span>

```csharp
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = channel.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```

<span data-ttu-id="84262-113">Per chiudere il canale, è necessario prima eseguirne il cast a un'interfaccia <xref:System.ServiceModel.IClientChannel>.</span><span class="sxs-lookup"><span data-stu-id="84262-113">To close the channel, it must first be cast to an <xref:System.ServiceModel.IClientChannel> interface.</span></span> <span data-ttu-id="84262-114">Ciò è necessario in quanto il canale generato viene dichiarato nell'applicazione client utilizzando l'interfaccia `ICalculator` che dispone di metodi quali `Add` e `Subtract` ma non `Close`.</span><span class="sxs-lookup"><span data-stu-id="84262-114">This is because the channel as generated is declared in the client application using the `ICalculator` interface, which has methods like `Add` and `Subtract` but not `Close`.</span></span> <span data-ttu-id="84262-115">Il metodo `Close` ha origine sull'interfaccia <xref:System.ServiceModel.ICommunicationObject>.</span><span class="sxs-lookup"><span data-stu-id="84262-115">The `Close` method originates on the <xref:System.ServiceModel.ICommunicationObject> interface.</span></span>

```csharp
// Close the channel.
 ((IClientChannel)client).Close();
```

<span data-ttu-id="84262-116">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="84262-116">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="84262-117">Premere INVIO nella finestra del client per arrestare l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="84262-117">Press ENTER in the client window to shut down the client application.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="84262-118">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="84262-118">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="84262-119">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="84262-119">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="84262-120">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="84262-120">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span> <span data-ttu-id="84262-121">Si noti che in questo esempio non viene abilitata la pubblicazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="84262-121">Note that this sample does not enable metadata publishing.</span></span> <span data-ttu-id="84262-122">Per rigenerare il tipo client, è necessario innanzitutto abilitare la pubblicazione dei metadati per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="84262-122">You must first enable metadata publishing for this sample to regenerate the client type.</span></span>

3. <span data-ttu-id="84262-123">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="84262-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

### <a name="to-run-the-sample-cross-machine"></a><span data-ttu-id="84262-124">Per eseguire l'esempio su più computer</span><span class="sxs-lookup"><span data-stu-id="84262-124">To run the sample cross machine</span></span>

1. <span data-ttu-id="84262-125">Sostituire "localhost" nel codice seguente con il nome completo del computer che sta eseguendo il servizio.</span><span class="sxs-lookup"><span data-stu-id="84262-125">Replace "localhost" in the following code with the fully-qualified name of the machine that is running the service.</span></span>

    ```csharp
    EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");
    ```

> [!IMPORTANT]
> <span data-ttu-id="84262-126">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="84262-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="84262-127">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="84262-127">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="84262-128">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="84262-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="84262-129">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="84262-129">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ChannelFactory`

---
title: Estensione del controllo sulla gestione e sulla segnalazione degli errori
ms.date: 03/30/2017
ms.assetid: 45f996a7-fa00-45cb-9d6f-b368f5778aaa
ms.openlocfilehash: c7ca8d85220d65905bc4d9d220de366c331504a4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600542"
---
# <a name="extending-control-over-error-handling-and-reporting"></a><span data-ttu-id="6a926-102">Estensione del controllo sulla gestione e sulla segnalazione degli errori</span><span class="sxs-lookup"><span data-stu-id="6a926-102">Extending Control Over Error Handling and Reporting</span></span>
<span data-ttu-id="6a926-103">In questo esempio viene illustrato come estendere il controllo sulla gestione degli errori e la segnalazione degli errori in un servizio Windows Communication Foundation (WCF) utilizzando l' <xref:System.ServiceModel.Dispatcher.IErrorHandler> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6a926-103">This sample demonstrates how to extend control over error handling and error reporting in a Windows Communication Foundation (WCF) service using the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="6a926-104">L'esempio è basato sul [Introduzione](getting-started-sample.md) con codice aggiuntivo aggiunto al servizio per la gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="6a926-104">The sample is based on the [Getting Started](getting-started-sample.md) with some additional code added to the service to handle errors.</span></span> <span data-ttu-id="6a926-105">Il client forza diverse condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="6a926-105">The client forces several error conditions.</span></span> <span data-ttu-id="6a926-106">Il servizio intercetta gli errori e li registra in un file.</span><span class="sxs-lookup"><span data-stu-id="6a926-106">The service intercepts the errors and logs them in a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a926-107">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6a926-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="6a926-108">I servizi possono intercettare gli errori, eseguire l'elaborazione e influire sulla segnalazione degli errori utilizzando l'interfaccia <xref:System.ServiceModel.Dispatcher.IErrorHandler>.</span><span class="sxs-lookup"><span data-stu-id="6a926-108">Services can intercept errors, perform processing, and affect how errors are reported using the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="6a926-109">L'interfaccia dispone di due metodi che possono essere implementati: <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> e <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>.</span><span class="sxs-lookup"><span data-stu-id="6a926-109">The interface has two methods that can be implemented: <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> and <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>.</span></span> <span data-ttu-id="6a926-110">Il metodo <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> consente di aggiungere, modificare o sopprimere un messaggio di errore generato in risposta a un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6a926-110">The <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> method allows you to add, modify, or suppress a fault message that is generated in response to an exception.</span></span> <span data-ttu-id="6a926-111">Se si verifica un errore, il metodo <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> consente l'elaborazione dell'errore e controlla se è possibile eseguire una gestione aggiuntiva degli errori.</span><span class="sxs-lookup"><span data-stu-id="6a926-111">The <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> method allows error processing to take place in the event of an error and controls whether additional error handling can run.</span></span>  
  
 <span data-ttu-id="6a926-112">In questo esempio, il tipo `CalculatorErrorHandler` implementa l'interfaccia <xref:System.ServiceModel.Dispatcher.IErrorHandler>.</span><span class="sxs-lookup"><span data-stu-id="6a926-112">In this sample, the `CalculatorErrorHandler` type implements the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="6a926-113">Nel campo</span><span class="sxs-lookup"><span data-stu-id="6a926-113">In the</span></span>  
  
 <span data-ttu-id="6a926-114">metodo <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>, `CalculatorErrorHandler` scrive un registro dell'errore nel file di testo Error.txt in c:\logs.</span><span class="sxs-lookup"><span data-stu-id="6a926-114"><xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> method, the `CalculatorErrorHandler` writes a log of the error to an Error.txt text file in c:\logs.</span></span> <span data-ttu-id="6a926-115">Si noti che nell'esempio l'errore viene registrato e non soppresso, in modo da poter essere segnalato al client.</span><span class="sxs-lookup"><span data-stu-id="6a926-115">Note that the sample logs the fault and does not suppress it, allowing it to be reported back to the client.</span></span>  
  
```csharp
public class CalculatorErrorHandler : IErrorHandler
{
    // Provide a fault. The Message fault parameter can be replaced, or set to
    // null to suppress reporting a fault.

    public void ProvideFault(Exception error, MessageVersion version, ref Message fault)
    {
    }

    // HandleError. Log an error, then allow the error to be handled as usual.
    // Return true if the error is considered as already handled

    public bool HandleError(Exception error)
    {
        using (TextWriter tw = File.AppendText(@"c:\logs\error.txt"))
        {
            if (error != null)
            {
                tw.WriteLine("Exception: " + error.GetType().Name + " - " + error.Message);
            }
            tw.Close();
        }
        return true;
    }
}  
```  
  
 <span data-ttu-id="6a926-116">`ErrorBehaviorAttribute` funge da meccanismo per registrare un gestore di errori con un servizio.</span><span class="sxs-lookup"><span data-stu-id="6a926-116">The `ErrorBehaviorAttribute` exists as a mechanism to register an error handler with a service.</span></span> <span data-ttu-id="6a926-117">Questo attributo accetta un solo parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="6a926-117">This attribute takes a single type parameter.</span></span> <span data-ttu-id="6a926-118">Tale tipo deve implementare l'interfaccia <xref:System.ServiceModel.Dispatcher.IErrorHandler> e deve disporre di un costruttore pubblico vuoto.</span><span class="sxs-lookup"><span data-stu-id="6a926-118">That type should implement the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface and should have a public, empty constructor.</span></span> <span data-ttu-id="6a926-119">L'attributo crea quindi un'istanza di quel tipo di gestore errori e la installa nel servizio.</span><span class="sxs-lookup"><span data-stu-id="6a926-119">The attribute then instantiates an instance of that error handler type and installs it into the service.</span></span> <span data-ttu-id="6a926-120">Questa operazione viene eseguita implementando l'interfaccia <xref:System.ServiceModel.Description.IServiceBehavior> e quindi utilizzando il metodo <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> per aggiungere istanze del gestore errori al servizio.</span><span class="sxs-lookup"><span data-stu-id="6a926-120">It does this by implementing the <xref:System.ServiceModel.Description.IServiceBehavior> interface and then using the <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> method to add instances of the error handler to the service.</span></span>  
  
```csharp
// This attribute can be used to install a custom error handler for a service.  
public class ErrorBehaviorAttribute : Attribute, IServiceBehavior  
{  
    Type errorHandlerType;  
  
    public ErrorBehaviorAttribute(Type errorHandlerType)  
    {  
        this.errorHandlerType = errorHandlerType;  
    }  
  
    void IServiceBehavior.Validate(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
    }  
  
    void IServiceBehavior.AddBindingParameters(ServiceDescription description, ServiceHostBase serviceHostBase, System.Collections.ObjectModel.Collection<ServiceEndpoint> endpoints, BindingParameterCollection parameters)  
    {  
    }  
  
    void IServiceBehavior.ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
        IErrorHandler errorHandler;  
  
        try  
        {  
            errorHandler = (IErrorHandler)Activator.CreateInstance(errorHandlerType);  
        }  
        catch (MissingMethodException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must have a public empty constructor.", e);  
        }  
        catch (InvalidCastException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must implement System.ServiceModel.Dispatcher.IErrorHandler.", e);  
        }  
  
        foreach (ChannelDispatcherBase channelDispatcherBase in serviceHostBase.ChannelDispatchers)  
        {  
            ChannelDispatcher channelDispatcher = channelDispatcherBase as ChannelDispatcher;  
            channelDispatcher.ErrorHandlers.Add(errorHandler);  
        }
    }  
}  
```  
  
 <span data-ttu-id="6a926-121">Nell'esempio viene implementato un servizio calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="6a926-121">The sample implements a calculator service.</span></span> <span data-ttu-id="6a926-122">Il client causa deliberatamente due errori nel servizio fornendo parametri con valori non validi.</span><span class="sxs-lookup"><span data-stu-id="6a926-122">The client deliberately causes two errors to occur on the service by providing parameters with illegal values.</span></span> <span data-ttu-id="6a926-123">`CalculatorErrorHandler` utilizza l'interfaccia <xref:System.ServiceModel.Dispatcher.IErrorHandler> per registrare gli errori in un file locale e quindi consente che siano segnalati al client.</span><span class="sxs-lookup"><span data-stu-id="6a926-123">The `CalculatorErrorHandler` uses the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface to log the errors to a local file and then allows them to be reported back to the client.</span></span> <span data-ttu-id="6a926-124">Il client forza una divisione per zero e una condizione di argomento esterno all'intervallo.</span><span class="sxs-lookup"><span data-stu-id="6a926-124">The client forces a divide by zero and an argument-out-of-range condition.</span></span>  
  
```csharp
try
{  
    Console.WriteLine("Forcing an error in Divide");  
    // Call the Divide service operation - trigger a divide by 0 error.  
    value1 = 22;  
    value2 = 0;  
    result = proxy.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
}  
catch (FaultException e)  
{  
    Console.WriteLine("FaultException: " + e.GetType().Name + " - " + e.Message);  
}  
catch (Exception e)  
{  
    Console.WriteLine("Exception: " + e.GetType().Name + " - " + e.Message);  
}  
```  
  
 <span data-ttu-id="6a926-125">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="6a926-125">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="6a926-126">Viene visualizzata la divisione per zero e le condizioni di argomento esterno all'intervallo segnalate come errori.</span><span class="sxs-lookup"><span data-stu-id="6a926-126">You see the division by zero and the argument-out-of-range conditions being reported as faults.</span></span> <span data-ttu-id="6a926-127">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="6a926-127">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Forcing an error in Divide  
FaultException: FaultException - Invalid Argument: The second argument must not be zero.  
Forcing an error in Factorial  
FaultException: FaultException - Invalid Argument: The argument must be greater than zero.  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="6a926-128">Il file c:\logs\errors.txt contiene le informazioni registrate sugli errori dal servizio.</span><span class="sxs-lookup"><span data-stu-id="6a926-128">The file c:\logs\errors.txt contains the information logged about the errors by the service.</span></span> <span data-ttu-id="6a926-129">Si noti che per la scrittura del servizio nella directory è necessario assicurarsi che il processo in cui è in esecuzione il servizio (in genere ASP.NET o servizio di rete) disponga delle autorizzazioni per scrivere nella directory.</span><span class="sxs-lookup"><span data-stu-id="6a926-129">Note that for the service to write to the directory you must make sure that the process under which the service is running (typically ASP.NET or Network Service) has permission to write to the directory.</span></span>  
  
```txt
Fault: Reason = Invalid Argument: The second argument must not be zero.  
Fault: Reason = Invalid Argument: The argument must be greater than zero.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6a926-130">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="6a926-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="6a926-131">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6a926-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="6a926-132">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6a926-132">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="6a926-133">Assicurarsi di aver creato la directory c:\logs per il file error.txt.</span><span class="sxs-lookup"><span data-stu-id="6a926-133">Ensure you have created the c:\logs directory for the error.txt file.</span></span> <span data-ttu-id="6a926-134">In alternativa, modificare il nome file utilizzato in `CalculatorErrorHandler.HandleError`.</span><span class="sxs-lookup"><span data-stu-id="6a926-134">Or modify the file name used in `CalculatorErrorHandler.HandleError`.</span></span>  
  
4. <span data-ttu-id="6a926-135">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6a926-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6a926-136">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="6a926-136">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6a926-137">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="6a926-137">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="6a926-138">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="6a926-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6a926-139">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="6a926-139">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\ErrorHandling`  

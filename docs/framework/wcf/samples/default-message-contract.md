---
title: Impostazione predefinita dei contratti di messaggio
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Message Contract
ms.assetid: 5a200b78-1a46-4104-b7fb-da6dbab33893
caps.latest.revision: "35"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d1219f2c1a173f454827c7450e66d90a500d87e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="default-message-contract"></a><span data-ttu-id="b8762-102">Impostazione predefinita dei contratti di messaggio</span><span class="sxs-lookup"><span data-stu-id="b8762-102">Default Message Contract</span></span>
<span data-ttu-id="b8762-103">L'esempio Impostazione predefinita dei contratti di messaggio illustra un servizio in cui un messaggio personalizzato definito dall'utente viene passato da e verso le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="b8762-103">The Default Message Contract sample demonstrates a service where a custom user-defined message is passed to and from service operations.</span></span> <span data-ttu-id="b8762-104">Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un'interfaccia come servizio tipizzato.</span><span class="sxs-lookup"><span data-stu-id="b8762-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator interface as a typed service.</span></span> <span data-ttu-id="b8762-105">Anziché le singole operazioni del servizio per l'addizione, sottrazione, moltiplicazione e divisione utilizzato nel [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md), in questo esempio passa un messaggio personalizzato che contiene entrambi gli operandi e l'operatore e restituisce il risultato del calcolo aritmetico.</span><span class="sxs-lookup"><span data-stu-id="b8762-105">Instead of the individual service operations for addition, subtraction, multiplication, and division used in the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), this sample passes a custom message that contains both the operands and the operator, and returns the result of the arithmetic calculation.</span></span>  
  
 <span data-ttu-id="b8762-106">Il client è un programma console (estensione exe) e la libreria (estensione dll) del servizio è ospitata su Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="b8762-106">The client is a console program (.exe) and the service library (.dll) is hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="b8762-107">L'attività del client è visibile nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="b8762-107">Client activity is visible in the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8762-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b8762-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="b8762-109">Nel servizio, viene definita una sola operazione del servizio che accetta e restituisce messaggi personalizzati di tipo `MyMessage`.</span><span class="sxs-lookup"><span data-stu-id="b8762-109">In the service, a single service operation is defined that accepts and returns custom messages of type `MyMessage`.</span></span> <span data-ttu-id="b8762-110">Benché in questo esempio i messaggi di richiesta e risposta siano dello stesso tipo, potrebbero ovviamente essere contratti di messaggio diversi se necessario.</span><span class="sxs-lookup"><span data-stu-id="b8762-110">Although in this sample the request and response messages are of the same type, they could of course be different message contracts if necessary.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract(Action="http://test/MyMessage_action",  
                  ReplyAction="http://test/MyMessage_action")]  
    MyMessage Calculate(MyMessage request);  
}  
```  
  
 <span data-ttu-id="b8762-111">Il messaggio personalizzato `MyMessage` viene definito in una classe annotata con gli attributi <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute> e <xref:System.ServiceModel.MessageBodyMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b8762-111">The custom message `MyMessage` is defined in a class annotated with <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes.</span></span> <span data-ttu-id="b8762-112">In questo esempio viene utilizzato solo il terzo costruttore.</span><span class="sxs-lookup"><span data-stu-id="b8762-112">Only the third constructor is used in this sample.</span></span> <span data-ttu-id="b8762-113">L'utilizzo dei contratti di messaggio consentono di esercitare pieno controllo sui messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="b8762-113">Using message contracts allows you to exercise full control over the SOAP message.</span></span> <span data-ttu-id="b8762-114">In questo esempio, l'attributo <xref:System.ServiceModel.MessageHeaderAttribute> viene utilizzato per inserire `Operation` in un'intestazione SOAP.</span><span class="sxs-lookup"><span data-stu-id="b8762-114">In this sample, the <xref:System.ServiceModel.MessageHeaderAttribute> attribute is used to put `Operation` in a SOAP header.</span></span> <span data-ttu-id="b8762-115">Gli operandi `N1`, `N2` e `Result` appaiono all'interno del corpo SOAP perché hanno l'attributo <xref:System.ServiceModel.MessageBodyMemberAttribute> applicato.</span><span class="sxs-lookup"><span data-stu-id="b8762-115">The operands `N1`, `N2` and the `Result` appear within the SOAP body because they have the <xref:System.ServiceModel.MessageBodyMemberAttribute> attribute applied.</span></span>  
  
```  
[MessageContract]  
public class MyMessage  
{  
    private string operation;  
    private double n1;  
    private double n2;  
    private double result;  
  
    //Constructor - create an empty message.  
  
    public MyMessage() {}  
  
    //Constructor - create a message and populate its members.  
  
    public MyMessage(double n1, double n2, string operation,   
                     double result)  
    {  
        this.n1 = n1;  
        this.n2 = n2;  
        this.operation = operation;  
        this.result = result;  
    }  
  
    //Constructor - create a message from another message.  
  
    public MyMessage(MyMessage message)  
    {  
        this.n1 = message.n1;  
        this.n2 = message.n2;  
        this.operation = message.operation;  
        this.result = message.result;  
    }  
  
    [MessageHeader]  
    public string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [MessageBodyMember]  
    public double N1  
    {  
        get { return n1; }  
        set { n1 = value; }  
    }  
  
    [MessageBodyMember]  
    public double N2  
    {  
        get { return n2; }  
        set { n2 = value; }  
    }  
  
    [MessageBodyMember]  
    public double Result  
    {  
        get { return result; }  
        set { result = value; }  
    }  
}  
```  
  
 <span data-ttu-id="b8762-116">La classe di implementazione contiene il codice per l'operazione del servizio  `Calculate`.</span><span class="sxs-lookup"><span data-stu-id="b8762-116">The implementation class contains the code for the `Calculate` service operation.</span></span> <span data-ttu-id="b8762-117">La classe `CalculateService` ottiene gli operandi e l'operatore dal messaggio di richiesta e crea un messaggio di risposta che contiene il risultato del calcolo richiesto, come mostra il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b8762-117">The `CalculateService` class obtains the operands and operator from the request message and creates a response message that contains the result of the requested calculation, as shown in the following sample code.</span></span>  
  
```  
// Service class which implements the service contract.  
public class CalculatorService : ICalculator  
{  
    // Perform a calculation.  
  
    public MyMessage Calculate(MyMessage request)  
    {  
        MyMessage response = new MyMessage(request);  
        switch (request.Operation)  
        {  
            case "+":  
                response.Result = request.N1 + request.N2;  
                break;  
            case "-":  
                response.Result = request.N1 - request.N2;  
                break;  
            case "*":  
                response.Result = request.N1 * request.N2;  
                break;  
            case "/":  
                response.Result = request.N1 / request.N2;  
                break;  
            default:  
                response.Result = 0.0D;  
                break;  
        }  
        return response;  
    }  
}  
```  
  
 <span data-ttu-id="b8762-118">Il codice client generato per il client è stato creato con il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) strumento.</span><span class="sxs-lookup"><span data-stu-id="b8762-118">The generated client code for the client was created with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool.</span></span> <span data-ttu-id="b8762-119">Lo strumento crea automaticamente i tipi di contratto del messaggio nel codice client generato se necessario.</span><span class="sxs-lookup"><span data-stu-id="b8762-119">The tool automatically creates message contract types in the generated client code if necessary.</span></span> <span data-ttu-id="b8762-120">L'opzione di comando `/messageContract` può essere specificata per forzare la generazione di contratti del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b8762-120">The `/messageContract` command option may be specified to force the generation of message contracts.</span></span>  
  
```  
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" /o:client\generatedClient.cs http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="b8762-121">Nell'esempio di codice seguente viene mostrato un client che utilizza il messaggio `MyMessage`.</span><span class="sxs-lookup"><span data-stu-id="b8762-121">The following sample code demonstrates the client using the `MyMessage` message.</span></span>  
  
```  
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
// Perform addition using a typed message.  
  
MyMessage request = new MyMessage();  
request.N1 = 100D;  
request.N2 = 15.99D;  
request.Operation = "+";  
MyMessage response = ((ICalculator)client).Calculate(request);  
Console.WriteLine("Add({0},{1}) = {2}", request.N1, request.N2, response.Result);  
```  
  
 <span data-ttu-id="b8762-122">Quando si esegue l'esempio, i calcoli vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="b8762-122">When you run the sample, the calculations are displayed in the client console window.</span></span> <span data-ttu-id="b8762-123">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="b8762-123">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="b8762-124">In questa fase, messaggi personalizzati definiti dall'utente vengono passati tra il client e l'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="b8762-124">At this point, custom user-defined messages have passed between the client and the service operation.</span></span> <span data-ttu-id="b8762-125">Il contratto del messaggio definisce che gli operandi e risultati sono nel corpo del messaggio e che l'operatore è in un'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b8762-125">The message contract defined that the operands and results were in the message body and that the operator was in a message header.</span></span> <span data-ttu-id="b8762-126">La registrazione dei messaggi può essere configurata per osservare questa struttura del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b8762-126">Message logging can be configured to observe this message structure.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b8762-127">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b8762-127">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b8762-128">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b8762-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="b8762-129">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b8762-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="b8762-130">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b8762-130">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b8762-131">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="b8762-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b8762-132">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="b8762-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b8762-133">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8762-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b8762-134">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="b8762-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Default`  
  
## <a name="see-also"></a><span data-ttu-id="b8762-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8762-135">See Also</span></span>

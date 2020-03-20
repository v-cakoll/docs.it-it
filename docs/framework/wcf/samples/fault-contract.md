---
title: Contratto di errore
ms.date: 03/30/2017
ms.assetid: b31b140e-dc3b-408b-b3c7-10b6fe769725
ms.openlocfilehash: c8e93f73d150132c9d6750b81ba2ade944808d40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183658"
---
# <a name="fault-contract"></a><span data-ttu-id="354b0-102">Contratto di errore</span><span class="sxs-lookup"><span data-stu-id="354b0-102">Fault Contract</span></span>
<span data-ttu-id="354b0-103">Nell'esempio di contratto di errore viene illustrato come comunicare informazioni relative all'errore da un servizio a un client.</span><span class="sxs-lookup"><span data-stu-id="354b0-103">The Fault Contract sample demonstrates how to communicate error information from a service to a client.</span></span> <span data-ttu-id="354b0-104">L'esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md), con codice aggiuntivo aggiunto al servizio per convertire un'eccezione interna in un errore.</span><span class="sxs-lookup"><span data-stu-id="354b0-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), with some additional code added to the service to convert an internal exception to a fault.</span></span> <span data-ttu-id="354b0-105">Il client tenta di eseguire una divisione per zero per imporre una condizione di errore al servizio.</span><span class="sxs-lookup"><span data-stu-id="354b0-105">The client attempts to perform division by zero to force an error condition on the service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="354b0-106">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="354b0-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="354b0-107">Il contratto della calcolatrice è stato modificato per includere un <xref:System.ServiceModel.FaultContractAttribute>, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="354b0-107">The calculator contract has been modified to include a <xref:System.ServiceModel.FaultContractAttribute> as shown in the following sample code.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
    [OperationContract]  
    int Subtract(int n1, int n2);  
    [OperationContract]  
    int Multiply(int n1, int n2);  
    [OperationContract]  
    [FaultContract(typeof(MathFault))]  
    int Divide(int n1, int n2);  
}  
```  
  
 <span data-ttu-id="354b0-108">L'attributo <xref:System.ServiceModel.FaultContractAttribute> indica che l'operazione `Divide` può restituire un errore di tipo `MathFault`.</span><span class="sxs-lookup"><span data-stu-id="354b0-108">The <xref:System.ServiceModel.FaultContractAttribute> attribute indicates that the `Divide` operation may return a fault of type `MathFault`.</span></span> <span data-ttu-id="354b0-109">Un errore può essere di qualsiasi tipo che può essere serializzato.</span><span class="sxs-lookup"><span data-stu-id="354b0-109">A fault can be of any type that can be serialized.</span></span> <span data-ttu-id="354b0-110">In questo caso, `MathFault` è un contratto dati, come segue:</span><span class="sxs-lookup"><span data-stu-id="354b0-110">In this case, the `MathFault` is a data contract, as follows:</span></span>  
  
```csharp
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public class MathFault  
{
    private string operation;  
    private string problemType;  
  
    [DataMember]  
    public string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [DataMember]
    public string ProblemType  
    {  
        get { return problemType; }  
        set { problemType = value; }  
    }  
}  
```  
  
 <span data-ttu-id="354b0-111">Il metodo `Divide` genera un'eccezione <xref:System.ServiceModel.FaultException%601> quando si verifica un'eccezione di divisione per zero, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="354b0-111">The `Divide` method throws a <xref:System.ServiceModel.FaultException%601> exception when a divide by zero exception occurs as shown in the following sample code.</span></span> <span data-ttu-id="354b0-112">Questa eccezione comporta che un errore venga inviato al client.</span><span class="sxs-lookup"><span data-stu-id="354b0-112">This exception results in a fault being sent to the client.</span></span>  
  
```csharp
public int Divide(int n1, int n2)  
{  
    try  
    {  
        return n1 / n2;  
    }  
    catch (DivideByZeroException)  
    {  
        MathFault mf = new MathFault();  
        mf.operation = "division";  
        mf.problemType = "divide by zero";  
        throw new FaultException<MathFault>(mf);  
    }  
}  
```  
  
 <span data-ttu-id="354b0-113">Il codice client forza un errore richiedendo una divisione per zero.</span><span class="sxs-lookup"><span data-stu-id="354b0-113">The client code forces an error by requesting a division by zero.</span></span> <span data-ttu-id="354b0-114">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="354b0-114">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="354b0-115">Viene visualizzata la divisione per zero segnalata come un errore.</span><span class="sxs-lookup"><span data-stu-id="354b0-115">You see the division by zero being reported as a fault.</span></span> <span data-ttu-id="354b0-116">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="354b0-116">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
FaultException<MathFault>: Math fault while doing division. Problem: divide by zero  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="354b0-117">Il client esegue questa operazione rilevando l'eccezione `FaultException<MathFault>` appropriata:</span><span class="sxs-lookup"><span data-stu-id="354b0-117">The client does this by catching the appropriate `FaultException<MathFault>` exception:</span></span>  
  
```csharp
catch (FaultException<MathFault> e)  
{  
    Console.WriteLine("FaultException<MathFault>: Math fault while doing " + e.Detail.operation + ". Problem: " + e.Detail.problemType);  
    client.Abort();  
}  
```  
  
 <span data-ttu-id="354b0-118">Per impostazione predefinita, i dettagli delle eccezioni impreviste non vengono inviati al client per evitare che i dettagli dell'implementazione del servizio escano dal limite protetto del servizio.</span><span class="sxs-lookup"><span data-stu-id="354b0-118">By default, the details of unexpected exceptions are not sent to the client to prevent details of the service implementation from escaping the secure boundary of the service.</span></span> <span data-ttu-id="354b0-119">`FaultContract` rappresenta un modo per descrivere gli errori di un contratto e contrassegnare certi tipi di eccezioni come appropriati per essere trasmessi al client.</span><span class="sxs-lookup"><span data-stu-id="354b0-119">`FaultContract` provides a way to describe faults in a contract and mark certain types of exceptions as appropriate for transmission to the client.</span></span> <span data-ttu-id="354b0-120">`FaultException<T>` rappresenta il meccanismo in fase di esecuzione per l'invio di errori agli utenti.</span><span class="sxs-lookup"><span data-stu-id="354b0-120">`FaultException<T>` provides the run-time mechanism for sending faults to consumers.</span></span>  
  
 <span data-ttu-id="354b0-121">È anche utile per visualizzare i dettagli interni di un errore del servizio durante l'esecuzione del debug.</span><span class="sxs-lookup"><span data-stu-id="354b0-121">However, it is useful to see the internal details of a service failure when debugging.</span></span> <span data-ttu-id="354b0-122">Per disattivare il comportamento protetto precedentemente descritto, è possibile indicare che i dettagli di ogni eccezione non gestita del server devono essere inclusi nell'errore inviato al client.</span><span class="sxs-lookup"><span data-stu-id="354b0-122">To turn off the secure behavior previously described, you can indicate that the details of every unhandled exception on the server should be included in the fault that is sent to the client.</span></span> <span data-ttu-id="354b0-123">Questa operazione viene eseguita impostando <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="354b0-123">This is accomplished by setting <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A> to `true`.</span></span> <span data-ttu-id="354b0-124">È possibile impostarlo nel codice o nella configurazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="354b0-124">You can either set it in code, or in configuration as shown in the following sample.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="True" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="354b0-125">Inoltre, il comportamento deve essere associato `behaviorConfiguration` al servizio impostando l'attributo del servizio nel file di configurazione su "CalculatorServiceBehavior".</span><span class="sxs-lookup"><span data-stu-id="354b0-125">Further, the behavior must be associated with the service by setting the `behaviorConfiguration` attribute of the service in the configuration file to "CalculatorServiceBehavior".</span></span>  
  
 <span data-ttu-id="354b0-126">Per intercettare questi errori nel client, è necessario intercettare l'oggetto <xref:System.ServiceModel.FaultException> non generico.</span><span class="sxs-lookup"><span data-stu-id="354b0-126">To catch such faults on the client, the non-generic <xref:System.ServiceModel.FaultException> must be caught.</span></span>  
  
 <span data-ttu-id="354b0-127">Questo comportamento deve essere usato solo a scopo di debug e non deve essere mai attivato in produzione.</span><span class="sxs-lookup"><span data-stu-id="354b0-127">This behavior should only be used for debugging purposes and should never be enabled in production.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="354b0-128">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="354b0-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="354b0-129">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="354b0-129">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="354b0-130">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="354b0-130">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="354b0-131">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="354b0-131">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="354b0-132">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="354b0-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="354b0-133">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="354b0-133">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="354b0-134">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="354b0-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="354b0-135">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="354b0-135">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Faults`  

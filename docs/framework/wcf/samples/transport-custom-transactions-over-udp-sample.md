---
title: "Trasporto: transazioni personalizzate nell'esempio UDP"
ms.date: 03/30/2017
ms.assetid: 6cebf975-41bd-443e-9540-fd2463c3eb23
ms.openlocfilehash: ba9fb91623606d3aaba5ba56784b20bb92d343a7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143798"
---
# <a name="transport-custom-transactions-over-udp-sample"></a><span data-ttu-id="88dbd-102">Trasporto: transazioni personalizzate nell'esempio UDP</span><span class="sxs-lookup"><span data-stu-id="88dbd-102">Transport: Custom Transactions over UDP Sample</span></span>
<span data-ttu-id="88dbd-103">Questo esempio è basato sull'esempio [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) in Windows Communication Foundation (WCF)[Transport Extensibility](../../../../docs/framework/wcf/samples/transport-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="88dbd-103">This sample is based on the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample in the Windows Communication Foundation (WCF)[Transport Extensibility](../../../../docs/framework/wcf/samples/transport-extensibility.md).</span></span> <span data-ttu-id="88dbd-104">Estende l'esempio Trasporto di UDP per supportare flussi di transazioni personalizzate e illustra l'utilizzo della proprietà <xref:System.ServiceModel.Channels.TransactionMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="88dbd-104">It extends the UDP Transport sample to support custom transaction flow and demonstrates the use of the <xref:System.ServiceModel.Channels.TransactionMessageProperty> property.</span></span>  
  
## <a name="code-changes-in-the-udp-transport-sample"></a><span data-ttu-id="88dbd-105">Modifiche al codice nell'esempio Trasporto di UDP</span><span class="sxs-lookup"><span data-stu-id="88dbd-105">Code Changes in the UDP Transport Sample</span></span>  
 <span data-ttu-id="88dbd-106">Per illustrare il flusso della transazione l'esempio modifica il contratto di servizio affinché `ICalculatorContract` richieda un ambito della transazione per `CalculatorService.Add()`.</span><span class="sxs-lookup"><span data-stu-id="88dbd-106">To demonstrate transaction flow, the sample changes the service contract for `ICalculatorContract` to require a transaction scope for `CalculatorService.Add()`.</span></span> <span data-ttu-id="88dbd-107">L'esempio aggiunge anche un parametro `System.Guid` supplementare al contratto dell'operazione `Add`.</span><span class="sxs-lookup"><span data-stu-id="88dbd-107">The sample also adds an extra `System.Guid` parameter to the contract of the `Add` operation.</span></span> <span data-ttu-id="88dbd-108">Questo parametro viene utilizzato per passare l'identificatore della transazione client al servizio.</span><span class="sxs-lookup"><span data-stu-id="88dbd-108">This parameter is used to pass the identifier of the client transaction to the service.</span></span>  
  
```csharp  
class CalculatorService : IDatagramContract, ICalculatorContract  
{  
    [OperationBehavior(TransactionScopeRequired=true)]  
    public int Add(int x, int y, Guid clientTransactionId)  
    {  
        if(Transaction.Current.TransactionInformation.DistributedIdentifier == clientTransactionId)  
    {  
        Console.WriteLine("The client transaction has flowed to the service");  
    }  
    else  
    {  
     Console.WriteLine("The client transaction has NOT flowed to the service");  
    }  
  
    Console.WriteLine("   adding {0} + {1}", x, y);
    return (x + y);  
    }  
  
    [...]  
}  
```  
  
 <span data-ttu-id="88dbd-109">Nell'esempio [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) vengono utilizzati pacchetti UDP per passare messaggi tra un client e un servizio.</span><span class="sxs-lookup"><span data-stu-id="88dbd-109">The [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample uses UDP packets to pass messages between a client and a service.</span></span> <span data-ttu-id="88dbd-110">[L'esempio di trasporto: trasporto personalizzato](../../../../docs/framework/wcf/samples/transport-custom-transactions-over-udp-sample.md) utilizza lo stesso meccanismo per il trasporto dei messaggi, ma quando viene eseguito il flusso di una transazione, viene inserito nel pacchetto UDP insieme al messaggio codificato.</span><span class="sxs-lookup"><span data-stu-id="88dbd-110">The [Transport: Custom Transport Sample](../../../../docs/framework/wcf/samples/transport-custom-transactions-over-udp-sample.md) uses the same mechanism to transport messages, but when a transaction is flowed, it is inserted into the UDP packet along with the encoded message.</span></span>  
  
```csharp  
byte[] txmsgBuffer = TransactionMessageBuffer.WriteTransactionMessageBuffer(txPropToken, messageBuffer);  
  
int bytesSent = this.socket.SendTo(txmsgBuffer, 0, txmsgBuffer.Length, SocketFlags.None, this.remoteEndPoint);  
```  
  
 <span data-ttu-id="88dbd-111">`TransactionMessageBuffer.WriteTransactionMessageBuffer` è un metodo di supporto che contiene nuove funzionalità che consentono di unire il token di propagazione della transazione corrente con l'entità del messaggio e di posizionarlo in un buffer.</span><span class="sxs-lookup"><span data-stu-id="88dbd-111">`TransactionMessageBuffer.WriteTransactionMessageBuffer` is a helper method that contains new functionality to merge the propagation token for the current transaction with the message entity and place it into a buffer.</span></span>  
  
 <span data-ttu-id="88dbd-112">Per il trasporto del flusso di transazioni personalizzato, l'implementazione client deve sapere quali operazioni del servizio richiedono il flusso delle transazioni e passare queste informazioni a WCF.</span><span class="sxs-lookup"><span data-stu-id="88dbd-112">For custom transaction flow transport, the client implementation must know what service operations require transaction flow and to pass this information to WCF.</span></span> <span data-ttu-id="88dbd-113">Ci deve anche essere un meccanismo per trasmettere la transazione utente al livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="88dbd-113">There should also be a mechanism for transmitting the user transaction to the transport layer.</span></span> <span data-ttu-id="88dbd-114">In questo esempio vengono utilizzati "controlli messaggi WCF" per ottenere queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="88dbd-114">This sample uses "WCF message inspectors" to obtain this information.</span></span> <span data-ttu-id="88dbd-115">Il controllo messaggi del client qui implementato, denominato `TransactionFlowInspector`, esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="88dbd-115">The client message inspector implemented here, which is called `TransactionFlowInspector`, performs the following tasks:</span></span>  
  
- <span data-ttu-id="88dbd-116">Determina se una transazione deve essere propagata per un'azione del messaggio specificata mediante `IsTxFlowRequiredForThisOperation()`.</span><span class="sxs-lookup"><span data-stu-id="88dbd-116">Determines whether a transaction must be flowed for a given message action (this takes place in `IsTxFlowRequiredForThisOperation()`).</span></span>  
  
- <span data-ttu-id="88dbd-117">Allega la transazione di ambiente corrente al messaggio utilizzando `TransactionFlowProperty`, se una transazione deve essere propagata (ciò viene realizzato in `BeforeSendRequest()`).</span><span class="sxs-lookup"><span data-stu-id="88dbd-117">Attaches the current ambient transaction to the message using `TransactionFlowProperty`, if a transaction is required to be flowed (this is done in `BeforeSendRequest()`).</span></span>  
  
```csharp  
public class TransactionFlowInspector : IClientMessageInspector  
{  
   void IClientMessageInspector.AfterReceiveReply(ref           System.ServiceModel.Channels.Message reply, object correlationState)  
  {  
  }  
  
   public object BeforeSendRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel)  
   {  
       // obtain the tx propagation token  
       byte[] propToken = null;
       if (Transaction.Current != null && IsTxFlowRequiredForThisOperation(request.Headers.Action))  
       {  
           try  
           {  
               propToken = TransactionInterop.GetTransmitterPropagationToken(Transaction.Current);  
           }  
           catch (TransactionException e)  
           {  
              throw new CommunicationException("TransactionInterop.GetTransmitterPropagationToken failed.", e);  
           }  
       }  
  
      // set the propToken on the message in a TransactionFlowProperty  
       TransactionFlowProperty.Set(propToken, request);  
  
       return null;
    }  
  }  
  
  static bool IsTxFlowRequiredForThisOperation(String action)  
 {  
       // In general, this should contain logic to identify which operations (actions)      require transaction flow.  
      [...]  
 }  
}  
```  
  
 <span data-ttu-id="88dbd-118">L'oggetto `TransactionFlowInspector` viene passato al framework utilizzando un comportamento personalizzato, ovvero `TransactionFlowBehavior`.</span><span class="sxs-lookup"><span data-stu-id="88dbd-118">The `TransactionFlowInspector` itself is passed to the framework using a custom behavior: the `TransactionFlowBehavior`.</span></span>  
  
```csharp  
public class TransactionFlowBehavior : IEndpointBehavior  
{  
       public void AddBindingParameters(ServiceEndpoint endpoint,            System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
      {  
      }  
  
       public void ApplyClientBehavior(ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.ClientRuntime clientRuntime)  
      {  
            TransactionFlowInspector inspector = new TransactionFlowInspector();  
            clientRuntime.MessageInspectors.Add(inspector);  
      }  
  
      public void ApplyDispatchBehavior(ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.EndpointDispatcher endpointDispatcher)  
     {  
     }  
  
      public void Validate(ServiceEndpoint endpoint)  
      {  
      }  
}  
```  
  
 <span data-ttu-id="88dbd-119">Con il meccanismo precedente in opera, il codice utente crea un `TransactionScope` prima di chiamare l'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="88dbd-119">With the preceding mechanism in place, the user code creates a `TransactionScope` before calling the service operation.</span></span> <span data-ttu-id="88dbd-120">Il controllo messaggi assicura che la transazione venga passata al trasporto in caso debba essere propagata all'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="88dbd-120">The message inspector ensures that the transaction is passed to the transport in case it is required to be flowed to the service operation.</span></span>  
  
```csharp  
CalculatorContractClient calculatorClient = new CalculatorContractClient("SampleProfileUdpBinding_ICalculatorContract");  
calculatorClient.Endpoint.Behaviors.Add(new TransactionFlowBehavior());
  
try  
{  
       for (int i = 0; i < 5; ++i)  
      {  
              // call the 'Add' service operation under a transaction scope  
             using (TransactionScope ts = new TransactionScope())  
             {  
        [...]  
        Console.WriteLine(calculatorClient.Add(i, i * 2));  
         }  
      }
       calculatorClient.Close();  
}  
catch (TimeoutException)  
{  
    calculatorClient.Abort();  
}  
catch (CommunicationException)  
{  
    calculatorClient.Abort();  
}  
catch (Exception)  
{  
    calculatorClient.Abort();  
    throw;  
}  
```  
  
 <span data-ttu-id="88dbd-121">Al momento della ricezione di un pacchetto UDP da parte del client, il servizio lo deserializza per estrarre il messaggio e se possibile una transazione.</span><span class="sxs-lookup"><span data-stu-id="88dbd-121">Upon receiving a UDP packet from the client, the service deserializes it to extract the message and possibly a transaction.</span></span>  
  
```csharp  
count = listenSocket.EndReceiveFrom(result, ref dummy);  
  
// read the transaction and message                       TransactionMessageBuffer.ReadTransactionMessageBuffer(buffer, count, out transaction, out msg);  
```  
  
 <span data-ttu-id="88dbd-122">`TransactionMessageBuffer.ReadTransactionMessageBuffer()` è il metodo di supporto che inverte il processo di serializzazione eseguito da `TransactionMessageBuffer.WriteTransactionMessageBuffer()`.</span><span class="sxs-lookup"><span data-stu-id="88dbd-122">`TransactionMessageBuffer.ReadTransactionMessageBuffer()` is the helper method that reverses the serialization process performed by `TransactionMessageBuffer.WriteTransactionMessageBuffer()`.</span></span>  
  
 <span data-ttu-id="88dbd-123">Se una transazione è stata propagata, viene aggiunta al messaggio in `TransactionMessageProperty`.</span><span class="sxs-lookup"><span data-stu-id="88dbd-123">If a transaction was flowed in, it is appended to the message in the `TransactionMessageProperty`.</span></span>  
  
```csharp  
message = MessageEncoderFactory.Encoder.ReadMessage(msg, bufferManager);  
  
if (transaction != null)  
{  
       TransactionMessageProperty.Set(transaction, message);  
}  
```  
  
 <span data-ttu-id="88dbd-124">Ciò assicura che il dispatcher raccolga la transazione al momento della distribuzione e l'utilizzi per chiamare l'operazione del servizio indirizzata dal messaggio.</span><span class="sxs-lookup"><span data-stu-id="88dbd-124">This ensures that the dispatcher picks up the transaction at dispatch time and uses it when calling the service operation addressed by the message.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="88dbd-125">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="88dbd-125">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="88dbd-126">Per compilare la soluzione, seguire le istruzioni in [Compilazione di Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="88dbd-126">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="88dbd-127">L'esempio corrente deve essere eseguito in modo simile all'esempio [Transport: UDP.](../../../../docs/framework/wcf/samples/transport-udp.md)</span><span class="sxs-lookup"><span data-stu-id="88dbd-127">The current sample should be run similarly to the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span> <span data-ttu-id="88dbd-128">Per eseguirlo, avviare il servizio con UdpTestService.exe.</span><span class="sxs-lookup"><span data-stu-id="88dbd-128">To run it, start the service with UdpTestService.exe.</span></span> <span data-ttu-id="88dbd-129">Se si esegue Windows Vista, è necessario avviare il servizio con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="88dbd-129">If you are running Windows Vista, you must start the service with elevated privileges.</span></span> <span data-ttu-id="88dbd-130">A tale scopo, fare clic con il pulsante destro del mouse su UdpTestService.exe in Esplora file e **scegliere Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="88dbd-130">To do so, right-click UdpTestService.exe in File Explorer and click **Run as administrator**.</span></span>  
  
3. <span data-ttu-id="88dbd-131">Si otterrà l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="88dbd-131">This produces the following output.</span></span>  
  
    ```console  
    Testing Udp From Code.  
    Service is started from code...  
    Press <ENTER> to terminate the service and start service from config...  
    ```  
  
4. <span data-ttu-id="88dbd-132">A questo punto è possibile avviare il client eseguendo UdpTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="88dbd-132">At this time, you can start the client by running UdpTestClient.exe.</span></span> <span data-ttu-id="88dbd-133">L'output prodotto dal client è il seguente:</span><span class="sxs-lookup"><span data-stu-id="88dbd-133">The output produced by the client is as follows.</span></span>  
  
    ```console
    0  
    3  
    6  
    9  
    12  
    Press <ENTER> to complete test.  
    ```  
  
5. <span data-ttu-id="88dbd-134">L'output del servizio è analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="88dbd-134">The service output is as follows.</span></span>  
  
    ```console
    Hello, world!  
    Hello, world!  
    Hello, world!  
    Hello, world!  
    Hello, world!  
    The client transaction has flowed to the service  
       adding 0 + 0  
    The client transaction has flowed to the service  
       adding 1 + 2  
    The client transaction has flowed to the service  
       adding 2 + 4  
    The client transaction has flowed to the service  
       adding 3 + 6  
    The client transaction has flowed to the service  
       adding 4 + 8  
    ```  
  
6. <span data-ttu-id="88dbd-135">L'applicazione di servizio visualizza messaggio `The client transaction has flowed to the service` se può far corrispondere all'identificatore della transazione inviato dal client, nel parametro `clientTransactionId` dell'operazione `CalculatorService.Add()`, l'identificatore della transazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="88dbd-135">The service application displays the message `The client transaction has flowed to the service` if it can match the transaction identifier sent by the client, in the `clientTransactionId` parameter of the `CalculatorService.Add()` operation, to the identifier of the service transaction.</span></span> <span data-ttu-id="88dbd-136">Una corrispondenza viene ottenuta solo se la transazione client è stata propagata al servizio.</span><span class="sxs-lookup"><span data-stu-id="88dbd-136">A match is obtained only if the client transaction has flowed to the service.</span></span>  
  
7. <span data-ttu-id="88dbd-137">Per eseguire l'applicazione client su endpoint pubblicati utilizzando la configurazione, premere INVIO nella finestra dell'applicazione di servizio e quindi eseguire nuovamente il client di prova.</span><span class="sxs-lookup"><span data-stu-id="88dbd-137">To run the client application against endpoints published using configuration, press ENTER on the service application window and then run the test client again.</span></span> <span data-ttu-id="88dbd-138">Nel servizio, si dovrebbe vedere l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="88dbd-138">You should see the following output on the service.</span></span>  
  
    ```console  
    Testing Udp From Config.  
    Service is started from config...  
    Press <ENTER> to terminate the service and exit...  
    ```  
  
8. <span data-ttu-id="88dbd-139">L'esecuzione del client sul servizio produce un output simile a quello precedente.</span><span class="sxs-lookup"><span data-stu-id="88dbd-139">Running the client against the service now produces similar output as before.</span></span>  
  
9. <span data-ttu-id="88dbd-140">Per rigenerare il codice client e la configurazione utilizzando Svcutil.exe, avviare l'applicazione del servizio, quindi eseguire i seguenti comandi Svcutil.exe dalla directory radice dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="88dbd-140">To regenerate the client code and configuration using Svcutil.exe, start the service application and then run the following Svcutil.exe command from the root directory of the sample.</span></span>  
  
    ```console  
    svcutil http://localhost:8000/udpsample/ /reference:UdpTransport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
    ```  
  
10. <span data-ttu-id="88dbd-141">Si noti che Svcutil.exe non genera la configurazione dell'estensione dell'associazione per `sampleProfileUdpBinding` ma è necessario aggiungerla manualmente.</span><span class="sxs-lookup"><span data-stu-id="88dbd-141">Note that Svcutil.exe does not generate the binding extension configuration for the `sampleProfileUdpBinding`; you must add it manually.</span></span>  
  
    ```xml  
    <configuration>  
        <system.serviceModel>
            …  
            <extensions>  
                <!-- This was added manually because svcutil.exe does not add this extension to the file -->  
                <bindingExtensions>  
                    <add name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
                </bindingExtensions>  
            </extensions>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
> [!IMPORTANT]
> <span data-ttu-id="88dbd-142">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="88dbd-142">The samples may already be installed on your machine.</span></span> <span data-ttu-id="88dbd-143">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="88dbd-143">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="88dbd-144">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="88dbd-144">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="88dbd-145">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="88dbd-145">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transactions\TransactionMessagePropertyUDPTransport`  
  
## <a name="see-also"></a><span data-ttu-id="88dbd-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88dbd-146">See also</span></span>

- [<span data-ttu-id="88dbd-147">Trasporto UDP</span><span class="sxs-lookup"><span data-stu-id="88dbd-147">Transport: UDP</span></span>](../../../../docs/framework/wcf/samples/transport-udp.md)

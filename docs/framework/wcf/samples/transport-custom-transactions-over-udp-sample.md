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
# <a name="transport-custom-transactions-over-udp-sample"></a>Trasporto: transazioni personalizzate nell'esempio UDP
Questo esempio è basato sull'esempio [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) in Windows Communication Foundation (WCF)[Transport Extensibility](../../../../docs/framework/wcf/samples/transport-extensibility.md). Estende l'esempio Trasporto di UDP per supportare flussi di transazioni personalizzate e illustra l'utilizzo della proprietà <xref:System.ServiceModel.Channels.TransactionMessageProperty>.  
  
## <a name="code-changes-in-the-udp-transport-sample"></a>Modifiche al codice nell'esempio Trasporto di UDP  
 Per illustrare il flusso della transazione l'esempio modifica il contratto di servizio affinché `ICalculatorContract` richieda un ambito della transazione per `CalculatorService.Add()`. L'esempio aggiunge anche un parametro `System.Guid` supplementare al contratto dell'operazione `Add`. Questo parametro viene utilizzato per passare l'identificatore della transazione client al servizio.  
  
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
  
 Nell'esempio [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) vengono utilizzati pacchetti UDP per passare messaggi tra un client e un servizio. [L'esempio di trasporto: trasporto personalizzato](../../../../docs/framework/wcf/samples/transport-custom-transactions-over-udp-sample.md) utilizza lo stesso meccanismo per il trasporto dei messaggi, ma quando viene eseguito il flusso di una transazione, viene inserito nel pacchetto UDP insieme al messaggio codificato.  
  
```csharp  
byte[] txmsgBuffer = TransactionMessageBuffer.WriteTransactionMessageBuffer(txPropToken, messageBuffer);  
  
int bytesSent = this.socket.SendTo(txmsgBuffer, 0, txmsgBuffer.Length, SocketFlags.None, this.remoteEndPoint);  
```  
  
 `TransactionMessageBuffer.WriteTransactionMessageBuffer` è un metodo di supporto che contiene nuove funzionalità che consentono di unire il token di propagazione della transazione corrente con l'entità del messaggio e di posizionarlo in un buffer.  
  
 Per il trasporto del flusso di transazioni personalizzato, l'implementazione client deve sapere quali operazioni del servizio richiedono il flusso delle transazioni e passare queste informazioni a WCF. Ci deve anche essere un meccanismo per trasmettere la transazione utente al livello di trasporto. In questo esempio vengono utilizzati "controlli messaggi WCF" per ottenere queste informazioni. Il controllo messaggi del client qui implementato, denominato `TransactionFlowInspector`, esegue le attività seguenti:  
  
- Determina se una transazione deve essere propagata per un'azione del messaggio specificata mediante `IsTxFlowRequiredForThisOperation()`.  
  
- Allega la transazione di ambiente corrente al messaggio utilizzando `TransactionFlowProperty`, se una transazione deve essere propagata (ciò viene realizzato in `BeforeSendRequest()`).  
  
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
  
 L'oggetto `TransactionFlowInspector` viene passato al framework utilizzando un comportamento personalizzato, ovvero `TransactionFlowBehavior`.  
  
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
  
 Con il meccanismo precedente in opera, il codice utente crea un `TransactionScope` prima di chiamare l'operazione del servizio. Il controllo messaggi assicura che la transazione venga passata al trasporto in caso debba essere propagata all'operazione del servizio.  
  
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
  
 Al momento della ricezione di un pacchetto UDP da parte del client, il servizio lo deserializza per estrarre il messaggio e se possibile una transazione.  
  
```csharp  
count = listenSocket.EndReceiveFrom(result, ref dummy);  
  
// read the transaction and message                       TransactionMessageBuffer.ReadTransactionMessageBuffer(buffer, count, out transaction, out msg);  
```  
  
 `TransactionMessageBuffer.ReadTransactionMessageBuffer()` è il metodo di supporto che inverte il processo di serializzazione eseguito da `TransactionMessageBuffer.WriteTransactionMessageBuffer()`.  
  
 Se una transazione è stata propagata, viene aggiunta al messaggio in `TransactionMessageProperty`.  
  
```csharp  
message = MessageEncoderFactory.Encoder.ReadMessage(msg, bufferManager);  
  
if (transaction != null)  
{  
       TransactionMessageProperty.Set(transaction, message);  
}  
```  
  
 Ciò assicura che il dispatcher raccolga la transazione al momento della distribuzione e l'utilizzi per chiamare l'operazione del servizio indirizzata dal messaggio.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Per compilare la soluzione, seguire le istruzioni in [Compilazione di Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2. L'esempio corrente deve essere eseguito in modo simile all'esempio [Transport: UDP.](../../../../docs/framework/wcf/samples/transport-udp.md) Per eseguirlo, avviare il servizio con UdpTestService.exe. Se si esegue Windows Vista, è necessario avviare il servizio con privilegi elevati. A tale scopo, fare clic con il pulsante destro del mouse su UdpTestService.exe in Esplora file e **scegliere Esegui come amministratore**.  
  
3. Si otterrà l'output seguente:  
  
    ```console  
    Testing Udp From Code.  
    Service is started from code...  
    Press <ENTER> to terminate the service and start service from config...  
    ```  
  
4. A questo punto è possibile avviare il client eseguendo UdpTestClient.exe. L'output prodotto dal client è il seguente:  
  
    ```console
    0  
    3  
    6  
    9  
    12  
    Press <ENTER> to complete test.  
    ```  
  
5. L'output del servizio è analogo al seguente:  
  
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
  
6. L'applicazione di servizio visualizza messaggio `The client transaction has flowed to the service` se può far corrispondere all'identificatore della transazione inviato dal client, nel parametro `clientTransactionId` dell'operazione `CalculatorService.Add()`, l'identificatore della transazione del servizio. Una corrispondenza viene ottenuta solo se la transazione client è stata propagata al servizio.  
  
7. Per eseguire l'applicazione client su endpoint pubblicati utilizzando la configurazione, premere INVIO nella finestra dell'applicazione di servizio e quindi eseguire nuovamente il client di prova. Nel servizio, si dovrebbe vedere l'output seguente.  
  
    ```console  
    Testing Udp From Config.  
    Service is started from config...  
    Press <ENTER> to terminate the service and exit...  
    ```  
  
8. L'esecuzione del client sul servizio produce un output simile a quello precedente.  
  
9. Per rigenerare il codice client e la configurazione utilizzando Svcutil.exe, avviare l'applicazione del servizio, quindi eseguire i seguenti comandi Svcutil.exe dalla directory radice dell'esempio.  
  
    ```console  
    svcutil http://localhost:8000/udpsample/ /reference:UdpTransport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
    ```  
  
10. Si noti che Svcutil.exe non genera la configurazione dell'estensione dell'associazione per `sampleProfileUdpBinding` ma è necessario aggiungerla manualmente.  
  
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
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transactions\TransactionMessagePropertyUDPTransport`  
  
## <a name="see-also"></a>Vedere anche

- [Trasporto UDP](../../../../docs/framework/wcf/samples/transport-udp.md)

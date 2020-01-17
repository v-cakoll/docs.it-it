---
title: Integrazione di componenti transazionali di Enterprise Services
ms.date: 03/30/2017
ms.assetid: 05dab277-b8b2-48cf-b40c-826be128b175
ms.openlocfilehash: 5914f76639adc3ff569a3bfb8d6eb1db14313e76
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76211942"
---
# <a name="integrating-enterprise-services-transactional-components"></a>Integrazione di componenti transazionali di Enterprise Services

Windows Communication Foundation (WCF) fornisce un meccanismo automatico per l'integrazione con Enterprise Services. vedere [integrazione con applicazioni com+](integrating-with-com-plus-applications.md). Può tuttavia essere necessario disporre della flessibilità di sviluppare servizi che utilizzano internamente componenti transazionali ospitati all'interno di Enterprise Services. Poiché la funzionalità transazioni WCF è basata sull'infrastruttura di <xref:System.Transactions>, il processo di integrazione di Enterprise Services con WCF è identico a quello per la specifica dell'interoperabilità tra <xref:System.Transactions> e Enterprise Services, come descritto in [interoperabilità con le transazioni di Enterprise Services e com+](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms229974(v=vs.85)).  
  
 Per fornire il livello desiderato di interoperabilità tra la transazione propagata in ingresso e la transazione in contesto COM+, l'implementazione del servizio deve creare un'istanza della classe <xref:System.Transactions.TransactionScope> e deve utilizzare il valore appropriato ricavato dall'enumerazione <xref:System.Transactions.EnterpriseServicesInteropOption>.  
  
## <a name="integrating-enterprise-services-with-a-service-operation"></a>Integrazione di Enterprise Services con un'operazione del servizio  
 Nel codice seguente viene illustrata un'operazione, con propagazione transazionale Allowed, che crea una classe <xref:System.Transactions.TransactionScope> con l'opzione <xref:System.Transactions.EnterpriseServicesInteropOption.Full>. In questo scenario vengono applicate le condizioni seguenti:  
  
- Se il client propaga una transazione, l'operazione, inclusa la chiamata al componente Enterprise Services, viene eseguita all'interno dell'ambito di tale transazione. L'utilizzo di <xref:System.Transactions.EnterpriseServicesInteropOption.Full> garantisce la sincronizzazione della transazione con il contesto <xref:System.EnterpriseServices>, il che significa che la transazione di ambiente per <xref:System.Transactions> e <xref:System.EnterpriseServices> è la stessa.  
  
- Se il client non propaga una transazione, l'impostazione di <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> su `true` crea un nuovo ambito di transazione per l'operazione. Analogamente, l'utilizzo di <xref:System.Transactions.EnterpriseServicesInteropOption.Full> garantisce che la transazione dell'operazione sia la stessa transazione utilizzata all'interno del contesto del componente <xref:System.EnterpriseServices>.  
  
 Eventuali chiamate aggiuntive al metodo avvengono anch'esse nell'ambito della stessa transazione dell'operazione.  
  
```csharp
[ServiceContract()]  
public interface ICustomerServiceContract  
{  
   [OperationContract]  
   [TransactionFlow(TransactionFlowOption.Allowed)]  
   void UpdateCustomerNameOperation(int customerID, string newCustomerName);  
}  
  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CustomerService : ICustomerServiceContract  
{  
   [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
   public void UpdateCustomerNameOperation(int customerID, string newCustomerName)  
   {  
   // Create a transaction scope with full ES interop  
      using (TransactionScope ts = new TransactionScope(  
                     TransactionScopeOption.Required,  
                     new TransactionOptions(),  
                     EnterpriseServicesInteropOption.Full))  
      {  
         // Create an Enterprise Services component  
         // Call UpdateCustomer method on an Enterprise Services   
         // component   
  
         // Call UpdateOtherCustomerData method on an Enterprise   
         // Services component   
         ts.Complete();  
      }  
  
      // Do UpdateAdditionalData on an non-Enterprise Services  
      // component  
   }  
}  
```  
  
 Se non è necessaria alcuna sincronizzazione tra la transazione corrente di un'operazione e le chiamate ai componenti Enterprise Services transazionali, utilizzare l'opzione <xref:System.Transactions.EnterpriseServicesInteropOption.None> quando si crea l'istanza di <xref:System.Transactions.TransactionScope>.  
  
## <a name="integrating-enterprise-services-with-a-client"></a>Integrazione di Enterprise Services con un client  
 Nell'esempio seguente viene illustrato il codice client utilizzando un'istanza della classe <xref:System.Transactions.TransactionScope> con l'impostazione <xref:System.Transactions.EnterpriseServicesInteropOption.Full> In questo scenario, le chiamate alle operazioni del servizio che supportano la propagazione transazionale avvengono nell'ambito della stessa transazione delle chiamate ai componenti Enterprise Services.  
  
```csharp
static void Main()  
{  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
  
    // Create a transaction scope with full ES interop  
    using (TransactionScope ts = new TransactionScope(  
          TransactionScopeOption.Required,  
          new TransactionOptions(),  
          EnterpriseServicesInteropOption.Full))  
    {  
        // Call Add calculator service operation  
  
        // Create an Enterprise Services component  
  
        // Call UpdateCustomer method on an Enterprise Services   
        // component   
  
        ts.Complete();  
    }  
  
    // Closing the client gracefully closes the connection and   
    // cleans up resources  
    client.Close();  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Integrazione con applicazioni COM+](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [Integrazione con applicazioni COM](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications.md)

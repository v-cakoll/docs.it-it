---
title: Servizi e transazioni
ms.date: 03/30/2017
helpviewer_keywords:
- service contracts [WCF], designing services and transactions
ms.assetid: 864813ff-2709-4376-912d-f5c8d318c460
ms.openlocfilehash: 5078e12ed5c68556a1d1d04d01c90440b57c1407
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736403"
---
# <a name="services-and-transactions"></a>Servizi e transazioni
Le applicazioni di Windows Communication Foundation (WCF) è possono avviare una transazione dall'interno di un client e coordinarla all'interno dell'operazione di servizio. I client possono avviare una transazione e richiamare varie operazioni di servizio nonché fare in modo che per queste ultime venga eseguito il commit o il rollback come unità singola.  
  
 È possibile attivare il comportamento della transazione nel contratto di servizio specificando un elemento <xref:System.ServiceModel.ServiceBehaviorAttribute> e impostando le proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> e <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> per operazioni di servizio che richiedono transazioni client. Il parametro <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> specifica se la transazione in cui viene eseguito il metodo viene completata automaticamente nel caso in cui non venga generata alcuna eccezione non gestita. Per altre informazioni su questi attributi, vedere [attributi delle transazioni ServiceModel](../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).  
  
 Il lavoro eseguito nelle operazioni di servizio e curato da un gestore di risorse, ad esempio la registrazione di aggiornamenti del database, fa parte della transazione del client.  
  
 Nell'esempio seguente viene dimostrato l'utilizzo degli attributi <xref:System.ServiceModel.ServiceBehaviorAttribute> e <xref:System.ServiceModel.OperationBehaviorAttribute> per controllare il comportamento della transazione dal lato del servizio.  
  
```csharp
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService: ICalculatorLog  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                           TransactionAutoComplete = true)]  
    public double Add(double n1, double n2)  
    {  
        recordToLog($"Added {n1} to {n2}");
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                               TransactionAutoComplete = true)]  
    public double Subtract(double n1, double n2)  
    {  
        recordToLog($"Subtracted {n1} from {n2}");
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                       TransactionAutoComplete = true)]  
    public double Multiply(double n1, double n2)  
    {  
        recordToLog($"Multiplied {n1} by {n2}");
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                       TransactionAutoComplete = true)]  
    public double Divide(double n1, double n2)  
    {  
        recordToLog($"Divided {n1} by {n2}", n1, n2);
        return n1 / n2;  
    }  
  
}  
```  
  
 È possibile attivare transazioni e delle transazioni del flusso tramite la configurazione del client e le associazioni di usare il protocollo WS-AtomicTransaction e impostazione di servizio di [ \<transactionFlow >](../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) elemento `true`, come mostrato Nell'esempio di configurazione seguente.  
  
```xml  
<client>  
    <endpoint address="net.tcp://localhost/ServiceModelSamples/service"   
          binding="netTcpBinding"   
          bindingConfiguration="netTcpBindingWSAT"   
          contract="Microsoft.ServiceModel.Samples.ICalculatorLog" />  
</client>  
  
<bindings>  
    <netTcpBinding>  
        <binding name="netTcpBindingWSAT"  
                transactionFlow="true"  
                transactionProtocol="WSAtomicTransactionOctober2004" />  
     </netTcpBinding>  
</bindings>  
```  
  
 I client possono iniziare una transazione creando un elemento <xref:System.Transactions.TransactionScope> e richiamando operazioni di servizio nell'ambito della transazione.  
  
```csharp
using (TransactionScope ts = new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    //Do work here  
    ts.Complete();  
}  
```  
  
## <a name="see-also"></a>Vedere anche
- [Supporto transazionale in System.ServiceModel](../../../docs/framework/wcf/feature-details/transactional-support-in-system-servicemodel.md)
- [Modelli di transazione](../../../docs/framework/wcf/feature-details/transaction-models.md)
- [Flusso delle transazioni WS](../../../docs/framework/wcf/samples/ws-transaction-flow.md)

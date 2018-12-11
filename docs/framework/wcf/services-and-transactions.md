---
title: Servizi e transazioni
ms.date: 03/30/2017
helpviewer_keywords:
- service contracts [WCF], designing services and transactions
ms.assetid: 864813ff-2709-4376-912d-f5c8d318c460
ms.openlocfilehash: 2e37a42b3767d279da0d742ba9958ceb6628aab1
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236973"
---
# <a name="services-and-transactions"></a><span data-ttu-id="2d7a8-102">Servizi e transazioni</span><span class="sxs-lookup"><span data-stu-id="2d7a8-102">Services and Transactions</span></span>
<span data-ttu-id="2d7a8-103">Le applicazioni di Windows Communication Foundation (WCF) è possono avviare una transazione dall'interno di un client e coordinarla all'interno dell'operazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="2d7a8-103">Windows Communication Foundation (WCF) applications can initiate a transaction from within a client and coordinate the transaction within the service operation.</span></span> <span data-ttu-id="2d7a8-104">I client possono avviare una transazione e richiamare varie operazioni di servizio nonché fare in modo che per queste ultime venga eseguito il commit o il rollback come unità singola.</span><span class="sxs-lookup"><span data-stu-id="2d7a8-104">Clients can initiate a transaction and invoke several service operations and ensure that the service operations are either committed or rolled back as a single unit.</span></span>  
  
 <span data-ttu-id="2d7a8-105">È possibile attivare il comportamento della transazione nel contratto di servizio specificando un elemento <xref:System.ServiceModel.ServiceBehaviorAttribute> e impostando le proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> e <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> per operazioni di servizio che richiedono transazioni client.</span><span class="sxs-lookup"><span data-stu-id="2d7a8-105">You can enable the transaction behavior in the service contract by specifying a <xref:System.ServiceModel.ServiceBehaviorAttribute> and setting its <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> and <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> properties for service operations that require client transactions.</span></span> <span data-ttu-id="2d7a8-106">Il parametro <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> specifica se la transazione in cui viene eseguito il metodo viene completata automaticamente nel caso in cui non venga generata alcuna eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="2d7a8-106">The <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> parameter specifies whether the transaction in which the method executes is automatically completed if no unhandled exceptions are thrown.</span></span> <span data-ttu-id="2d7a8-107">Per altre informazioni su questi attributi, vedere [attributi delle transazioni ServiceModel](../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="2d7a8-107">For more information about these attributes, see [ServiceModel Transaction Attributes](../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).</span></span>  
  
 <span data-ttu-id="2d7a8-108">Il lavoro eseguito nelle operazioni di servizio e curato da un gestore di risorse, ad esempio la registrazione di aggiornamenti del database, fa parte della transazione del client.</span><span class="sxs-lookup"><span data-stu-id="2d7a8-108">The work that is performed in the service operations and managed by a resource manager, such as logging database updates, is part of the client’s transaction.</span></span>  
  
 <span data-ttu-id="2d7a8-109">Nell'esempio seguente viene dimostrato l'utilizzo degli attributi <xref:System.ServiceModel.ServiceBehaviorAttribute> e <xref:System.ServiceModel.OperationBehaviorAttribute> per controllare il comportamento della transazione dal lato del servizio.</span><span class="sxs-lookup"><span data-stu-id="2d7a8-109">The following sample demonstrates usage of the <xref:System.ServiceModel.ServiceBehaviorAttribute> and <xref:System.ServiceModel.OperationBehaviorAttribute> attributes to control service-side transaction behavior.</span></span>  
  
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
  
 <span data-ttu-id="2d7a8-110">È possibile attivare transazioni e delle transazioni del flusso tramite la configurazione del client e le associazioni di usare il protocollo WS-AtomicTransaction e impostazione di servizio di [ \<transactionFlow >](../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) elemento `true`, come mostrato Nell'esempio di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="2d7a8-110">You can enable transactions and transaction flow by configuring the client and service bindings to use the WS-AtomicTransaction protocol, and setting the [\<transactionFlow>](../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) element to `true`, as shown in the following sample configuration.</span></span>  
  
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
  
 <span data-ttu-id="2d7a8-111">I client possono iniziare una transazione creando un elemento <xref:System.Transactions.TransactionScope> e richiamando operazioni di servizio nell'ambito della transazione.</span><span class="sxs-lookup"><span data-stu-id="2d7a8-111">Clients can begin a transaction by creating a <xref:System.Transactions.TransactionScope> and invoking service operations within the scope of the transaction.</span></span>  
  
```csharp
using (TransactionScope ts = new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    //Do work here  
    ts.Complete();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d7a8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d7a8-112">See Also</span></span>  
 [<span data-ttu-id="2d7a8-113">Supporto transazionale in System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2d7a8-113">Transactional Support in System.ServiceModel</span></span>](../../../docs/framework/wcf/feature-details/transactional-support-in-system-servicemodel.md)  
 [<span data-ttu-id="2d7a8-114">Modelli di transazione</span><span class="sxs-lookup"><span data-stu-id="2d7a8-114">Transaction Models</span></span>](../../../docs/framework/wcf/feature-details/transaction-models.md)  
 [<span data-ttu-id="2d7a8-115">Flusso delle transazioni WS</span><span class="sxs-lookup"><span data-stu-id="2d7a8-115">WS Transaction Flow</span></span>](../../../docs/framework/wcf/samples/ws-transaction-flow.md)

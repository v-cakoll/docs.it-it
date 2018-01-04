---
title: Transazioni del flusso di lavoro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d9cc01d929421b8065a3df21374150bc68fd968
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-transactions"></a><span data-ttu-id="5c500-102">Transazioni del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="5c500-102">Workflow Transactions</span></span>
<span data-ttu-id="5c500-103">In [!INCLUDE[wf1](../../../includes/wf1-md.md)] è disponibile il supporto per partecipare alle transazioni <xref:System.Transactions> tramite l'attività <xref:System.Activities.Statements.TransactionScope> per definire l'ambito di un'unità transazionale di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5c500-103">[!INCLUDE[wf1](../../../includes/wf1-md.md)] provides support for participating in <xref:System.Transactions> transactions by using the <xref:System.Activities.Statements.TransactionScope> activity to scope a transacted unit of work.</span></span> <span data-ttu-id="5c500-104">Mentre l'oggetto <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> deve essere completato in modo esplicito, l'attività <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> effettua le chiamate in modo implicito sulla transazione in seguito al corretto completamento.</span><span class="sxs-lookup"><span data-stu-id="5c500-104">While the <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> must be explicitly completed the <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> activity implicitly calls complete on the transaction upon successful completion.</span></span> <span data-ttu-id="5c500-105">Qualsiasi attività contenuta nell'elemento <xref:System.Activities.Statements.TransactionScope.Body%2A> dell'attività <xref:System.Activities.Statements.TransactionScope> partecipa alla transazione.</span><span class="sxs-lookup"><span data-stu-id="5c500-105">Any activities that are contained in the <xref:System.Activities.Statements.TransactionScope.Body%2A> of the <xref:System.Activities.Statements.TransactionScope> activity participate in the transaction.</span></span> <span data-ttu-id="5c500-106">WF può propagare transazioni in un flusso di lavoro tramite l'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="5c500-106">WF can to flow transactions into a workflow through the use of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="5c500-107">Analogamente all'attività <xref:System.Activities.Statements.TransactionScope>, qualsiasi attività contenuta nella proprietà <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> partecipa alla transazione.</span><span class="sxs-lookup"><span data-stu-id="5c500-107">Like the <xref:System.Activities.Statements.TransactionScope> activity, any activity contained in the <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> participates in the transaction.</span></span> <span data-ttu-id="5c500-108">WF assicura che nelle attività che dipendono dall'oggetto <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> possano essere usati entrambi gli oggetti <xref:System.Activities.Statements.TransactionScope> e <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="5c500-108">WF ensures that activities dependent on <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> works with both <xref:System.Activities.Statements.TransactionScope> and <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="5c500-109">Se le attività fornite dal sistema non soddisfano tutti i requisiti, possono essere compilate attività personalizzate tramite l'oggetto <xref:System.Activities.RuntimeTransactionHandle> per abilitare scenari di controllo di transazioni e flussi avanzati.</span><span class="sxs-lookup"><span data-stu-id="5c500-109">If the system-provided activities do not address all requirements, custom activities can be built using the <xref:System.Activities.RuntimeTransactionHandle> to enable advanced flow and transaction control scenarios.</span></span>  
  
 <span data-ttu-id="5c500-110">Nell'esempio seguente, tratto dal [TransactionScope di base](../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md) esempio, viene creato un flusso di lavoro costituito da un <xref:System.Activities.Statements.Sequence> attività contenente attività figlio tra un <xref:System.Activities.Statements.TransactionScope> attività.</span><span class="sxs-lookup"><span data-stu-id="5c500-110">In the following example, taken from the [Basic TransactionScope](../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md) sample, a workflow is constructed consisting of a <xref:System.Activities.Statements.Sequence> activity that contains child activities including a <xref:System.Activities.Statements.TransactionScope> activity.</span></span> <span data-ttu-id="5c500-111">Le attività <xref:System.Activities.Statements.TransactionScope.Body%2A> di <xref:System.Activities.Statements.TransactionScope> vengono eseguite nella transazione inizializzata dall'attività <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="5c500-111">The <xref:System.Activities.Statements.TransactionScope.Body%2A> activities of the <xref:System.Activities.Statements.TransactionScope> execute under the transaction initialized by the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
```csharp  
static Activity ScenarioOne()  
{  
    return new Sequence  
    {  
        Activities =  
        {  
            new WriteLine { Text = "    Begin workflow" },  
  
            new TransactionScope  
            {  
                Body = new Sequence  
                {  
                    Activities =   
                    {  
                        new WriteLine { Text = "    Begin TransactionScope" },  
  
                        new PrintTransactionId(),  
  
                        new TransactionScopeTest(),  
  
                        new WriteLine { Text = "    End TransactionScope" },  
                    },  
                },  
            },  
  
            new WriteLine { Text = "    End workflow" },  
        }  
    };  
}  
```  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="5c500-112">base [transazioni](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) esempi e lo scenario basato su [transazioni](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) esempi.</span><span class="sxs-lookup"><span data-stu-id="5c500-112"> the basic [Transactions](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) samples, and the scenario based [Transactions](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) samples.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="5c500-113">informazioni sull'utilizzo <xref:System.ServiceModel.Activities.TransactedReceiveScope>, vedere [propagazione di transazioni all'interno e all'esterno di servizi flusso di lavoro](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="5c500-113"> about using <xref:System.ServiceModel.Activities.TransactedReceiveScope>, see [Flowing Transactions into and out of Workflow Services](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c500-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c500-114">See Also</span></span>  
 <xref:System.Activities.Statements.TransactionScope>  
 <xref:System.Transactions.TransactionScope>  
 <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>

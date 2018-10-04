---
title: Transazioni del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
ms.openlocfilehash: e2a0c301abac562904e976fe09e5a68697b191e5
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48779959"
---
# <a name="workflow-transactions"></a><span data-ttu-id="e7326-102">Transazioni del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e7326-102">Workflow Transactions</span></span>

<span data-ttu-id="e7326-103">In [!INCLUDE[wf1](../../../includes/wf1-md.md)] è disponibile il supporto per partecipare alle transazioni <xref:System.Transactions> tramite l'attività <xref:System.Activities.Statements.TransactionScope> per definire l'ambito di un'unità transazionale di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e7326-103">[!INCLUDE[wf1](../../../includes/wf1-md.md)] provides support for participating in <xref:System.Transactions> transactions by using the <xref:System.Activities.Statements.TransactionScope> activity to scope a transacted unit of work.</span></span> <span data-ttu-id="e7326-104">Mentre l'oggetto <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> deve essere completato in modo esplicito, l'attività <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> effettua le chiamate in modo implicito sulla transazione in seguito al corretto completamento.</span><span class="sxs-lookup"><span data-stu-id="e7326-104">While the <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> must be explicitly completed the <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> activity implicitly calls complete on the transaction upon successful completion.</span></span> <span data-ttu-id="e7326-105">Qualsiasi attività contenuta nell'elemento <xref:System.Activities.Statements.TransactionScope.Body%2A> dell'attività <xref:System.Activities.Statements.TransactionScope> partecipa alla transazione.</span><span class="sxs-lookup"><span data-stu-id="e7326-105">Any activities that are contained in the <xref:System.Activities.Statements.TransactionScope.Body%2A> of the <xref:System.Activities.Statements.TransactionScope> activity participate in the transaction.</span></span> <span data-ttu-id="e7326-106">WF può propagare transazioni in un flusso di lavoro tramite l'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="e7326-106">WF can to flow transactions into a workflow through the use of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="e7326-107">Analogamente all'attività <xref:System.Activities.Statements.TransactionScope>, qualsiasi attività contenuta nella proprietà <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> partecipa alla transazione.</span><span class="sxs-lookup"><span data-stu-id="e7326-107">Like the <xref:System.Activities.Statements.TransactionScope> activity, any activity contained in the <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> participates in the transaction.</span></span> <span data-ttu-id="e7326-108">WF assicura che nelle attività che dipendono dall'oggetto <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> possano essere usati entrambi gli oggetti <xref:System.Activities.Statements.TransactionScope> e <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="e7326-108">WF ensures that activities dependent on <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> works with both <xref:System.Activities.Statements.TransactionScope> and <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="e7326-109">Se le attività fornite dal sistema non soddisfano tutti i requisiti, possono essere compilate attività personalizzate tramite l'oggetto <xref:System.Activities.RuntimeTransactionHandle> per abilitare scenari di controllo di transazioni e flussi avanzati.</span><span class="sxs-lookup"><span data-stu-id="e7326-109">If the system-provided activities do not address all requirements, custom activities can be built using the <xref:System.Activities.RuntimeTransactionHandle> to enable advanced flow and transaction control scenarios.</span></span>  
  
<span data-ttu-id="e7326-110">Nell'esempio seguente viene creato un flusso di lavoro costituito da un <xref:System.Activities.Statements.Sequence> attività che contiene attività figlio inclusa un' <xref:System.Activities.Statements.TransactionScope> attività.</span><span class="sxs-lookup"><span data-stu-id="e7326-110">In the following example, a workflow is constructed consisting of a <xref:System.Activities.Statements.Sequence> activity that contains child activities including a <xref:System.Activities.Statements.TransactionScope> activity.</span></span> <span data-ttu-id="e7326-111">Le attività <xref:System.Activities.Statements.TransactionScope.Body%2A> di <xref:System.Activities.Statements.TransactionScope> vengono eseguite nella transazione inizializzata dall'attività <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="e7326-111">The <xref:System.Activities.Statements.TransactionScope.Body%2A> activities of the <xref:System.Activities.Statements.TransactionScope> execute under the transaction initialized by the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
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
  
<span data-ttu-id="e7326-112">Per altre informazioni, vedere l'argomento sull'uso <xref:System.ServiceModel.Activities.TransactedReceiveScope>, vedere [transazioni che passano da e verso i servizi del flusso di lavoro](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="e7326-112">For more information, see about using <xref:System.ServiceModel.Activities.TransactedReceiveScope>, see [Flowing Transactions into and out of Workflow Services](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7326-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7326-113">See Also</span></span>  
 <xref:System.Activities.Statements.TransactionScope>  
 <xref:System.Transactions.TransactionScope>  
 <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>

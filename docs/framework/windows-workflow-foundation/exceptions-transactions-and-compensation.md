---
title: Eccezioni, transazioni e compensazione
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
ms.openlocfilehash: 346b07cd89c4071088676235d457930637b71549
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512210"
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="61b57-102">Eccezioni, transazioni e compensazione</span><span class="sxs-lookup"><span data-stu-id="61b57-102">Exceptions, Transactions, and Compensation</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="61b57-103"> offre diversi meccanismi differenti per la gestione di condizioni di errore di runtime nei flussi di lavoro,</span><span class="sxs-lookup"><span data-stu-id="61b57-103"> provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="61b57-104">all'interno dei quali è possibile usare una combinazione di gestori di eccezioni, transazioni, annullamento e compensazione per gestire e risolvere normalmente condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="61b57-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="61b57-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="61b57-105">In This Section</span></span>  
 [<span data-ttu-id="61b57-106">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="61b57-106">Exceptions</span></span>](../../../docs/framework/windows-workflow-foundation/exceptions.md)  
 <span data-ttu-id="61b57-107">Viene illustrato come usare l'attività <xref:System.Activities.Statements.TryCatch> per la gestione delle eccezioni in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="61b57-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="61b57-108">Transazioni</span><span class="sxs-lookup"><span data-stu-id="61b57-108">Transactions</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)  
 <span data-ttu-id="61b57-109">Viene illustrato come usare l'attività <xref:System.Activities.Statements.TransactionScope> per l'uso delle transazioni in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="61b57-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="61b57-110">Compensazione</span><span class="sxs-lookup"><span data-stu-id="61b57-110">Compensation</span></span>](../../../docs/framework/windows-workflow-foundation/compensation.md)  
 <span data-ttu-id="61b57-111">Viene illustrata la compensazione nei flussi di lavoro e viene mostrato come usare le attività di compensazione quali <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate> e <xref:System.Activities.Statements.Confirm>.</span><span class="sxs-lookup"><span data-stu-id="61b57-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="61b57-112">Annullamento</span><span class="sxs-lookup"><span data-stu-id="61b57-112">Cancellation</span></span>](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="61b57-113">Viene descritto come eseguire la gestione dell'annullamento in flussi di lavoro usando attività predefinite e attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="61b57-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="61b57-114">Esecuzione del debug dei flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="61b57-114">Debugging Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/debugging-workflows.md)  
 <span data-ttu-id="61b57-115">Viene illustrato come eseguire il debug dei flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="61b57-115">Describes how to debug workflows.</span></span>

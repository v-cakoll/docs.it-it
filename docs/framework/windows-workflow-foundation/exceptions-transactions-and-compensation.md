---
title: Eccezioni, transazioni e compensazione
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
ms.openlocfilehash: c4d66e252561ad7b896ff8092e80013c51bd463c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709471"
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="30b1f-102">Eccezioni, transazioni e compensazione</span><span class="sxs-lookup"><span data-stu-id="30b1f-102">Exceptions, Transactions, and Compensation</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)] <span data-ttu-id="30b1f-103">offre diversi meccanismi differenti per la gestione di condizioni di errore di runtime nei flussi di lavoro,</span><span class="sxs-lookup"><span data-stu-id="30b1f-103">provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="30b1f-104">all'interno dei quali è possibile usare una combinazione di gestori di eccezioni, transazioni, annullamento e compensazione per gestire e risolvere normalmente condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="30b1f-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="30b1f-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="30b1f-105">In This Section</span></span>  
 [<span data-ttu-id="30b1f-106">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="30b1f-106">Exceptions</span></span>](exceptions.md)  
 <span data-ttu-id="30b1f-107">Viene illustrato come usare l'attività <xref:System.Activities.Statements.TryCatch> per la gestione delle eccezioni in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="30b1f-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="30b1f-108">Transazioni</span><span class="sxs-lookup"><span data-stu-id="30b1f-108">Transactions</span></span>](workflow-transactions.md)  
 <span data-ttu-id="30b1f-109">Viene illustrato come usare l'attività <xref:System.Activities.Statements.TransactionScope> per l'uso delle transazioni in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="30b1f-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="30b1f-110">Compensazione</span><span class="sxs-lookup"><span data-stu-id="30b1f-110">Compensation</span></span>](compensation.md)  
 <span data-ttu-id="30b1f-111">Viene illustrata la compensazione nei flussi di lavoro e viene mostrato come usare le attività di compensazione quali <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate> e <xref:System.Activities.Statements.Confirm>.</span><span class="sxs-lookup"><span data-stu-id="30b1f-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="30b1f-112">Annullamento</span><span class="sxs-lookup"><span data-stu-id="30b1f-112">Cancellation</span></span>](modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="30b1f-113">Viene descritto come eseguire la gestione dell'annullamento in flussi di lavoro usando attività predefinite e attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="30b1f-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="30b1f-114">Esecuzione del debug dei flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="30b1f-114">Debugging Workflows</span></span>](debugging-workflows.md)  
 <span data-ttu-id="30b1f-115">Viene illustrato come eseguire il debug dei flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="30b1f-115">Describes how to debug workflows.</span></span>

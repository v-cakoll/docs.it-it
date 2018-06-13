---
title: Transactions2
ms.date: 03/30/2017
ms.assetid: 51212219-a39e-448e-bff3-10064ff5de64
ms.openlocfilehash: 361022851d971c0b9350899e1fee6a27c557d666
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514595"
---
# <a name="transactions"></a><span data-ttu-id="e655e-102">Transazioni</span><span class="sxs-lookup"><span data-stu-id="e655e-102">Transactions</span></span>
<span data-ttu-id="e655e-103">In questa sezione è contenuti esempi che illustrano transazioni del flusso di lavoro in Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="e655e-103">This section contains samples that demonstrate workflow transactions in Windows Workflow Foundation (WF).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e655e-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="e655e-104">In This Section</span></span>  
 [<span data-ttu-id="e655e-105">TransactionScope di base</span><span class="sxs-lookup"><span data-stu-id="e655e-105">Basic TransactionScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 <span data-ttu-id="e655e-106">Sono costituiti da quattro scenari che illustrano come annidare istanze di <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="e655e-106">Consists of four scenarios that show how to nest <xref:System.Activities.Statements.TransactionScope> instances.</span></span>  
  
 [<span data-ttu-id="e655e-107">Uso di TransactedReceiveScope</span><span class="sxs-lookup"><span data-stu-id="e655e-107">Use of TransactedReceiveScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 <span data-ttu-id="e655e-108">Viene illustrato come propagare una transazione da un client a un server usando <xref:System.Activities.Statements.TransactionScope> per creare una nuova transazione nel client e un oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope> per ricevere un messaggio con una transazione propagata, esaminando la durata della transazione nel server.</span><span class="sxs-lookup"><span data-stu-id="e655e-108">Demonstrates how to flow a transaction from a client to a server using <xref:System.Activities.Statements.TransactionScope> to create a new transaction on the client and a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to receive a message with a flowed transaction and scope the lifetime of the transaction on the server.</span></span>  
  
 [<span data-ttu-id="e655e-109">Annidamento di TransactionScope all'interno di un servizio</span><span class="sxs-lookup"><span data-stu-id="e655e-109">Nesting of TransactionScope within a service</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 <span data-ttu-id="e655e-110">È costituito da due scenari che illustrano come gestire le istanze dell'attività <xref:System.Activities.Statements.TransactionScope> all'interno di un servizio.</span><span class="sxs-lookup"><span data-stu-id="e655e-110">Consists of two scenarios that show how to handle <xref:System.Activities.Statements.TransactionScope> activity instances within a service.</span></span>

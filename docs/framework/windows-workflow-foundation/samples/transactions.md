---
title: Transactions2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51212219-a39e-448e-bff3-10064ff5de64
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c7611ce26c1a3b9150a60ced7b4931cc1282eecd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="transactions"></a><span data-ttu-id="6a52e-102">Transazioni</span><span class="sxs-lookup"><span data-stu-id="6a52e-102">Transactions</span></span>
<span data-ttu-id="6a52e-103">Contenuto della sezione sono inclusi esempi che illustrano transazioni del flusso di lavoro in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a52e-103">This section contains samples that demonstrate workflow transactions in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6a52e-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6a52e-104">In This Section</span></span>  
 [<span data-ttu-id="6a52e-105">TransactionScope di base</span><span class="sxs-lookup"><span data-stu-id="6a52e-105">Basic TransactionScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 <span data-ttu-id="6a52e-106">Sono costituiti da quattro scenari che illustrano come annidare istanze di <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="6a52e-106">Consists of four scenarios that show how to nest <xref:System.Activities.Statements.TransactionScope> instances.</span></span>  
  
 [<span data-ttu-id="6a52e-107">Utilizzo di TransactedReceiveScope</span><span class="sxs-lookup"><span data-stu-id="6a52e-107">Use of TransactedReceiveScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 <span data-ttu-id="6a52e-108">Viene illustrato come propagare una transazione da un client a un server usando <xref:System.Activities.Statements.TransactionScope> per creare una nuova transazione nel client e un oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope> per ricevere un messaggio con una transazione propagata, esaminando la durata della transazione nel server.</span><span class="sxs-lookup"><span data-stu-id="6a52e-108">Demonstrates how to flow a transaction from a client to a server using <xref:System.Activities.Statements.TransactionScope> to create a new transaction on the client and a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to receive a message with a flowed transaction and scope the lifetime of the transaction on the server.</span></span>  
  
 [<span data-ttu-id="6a52e-109">Annidamento di TransactionScope all'interno di un servizio</span><span class="sxs-lookup"><span data-stu-id="6a52e-109">Nesting of TransactionScope within a service</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 <span data-ttu-id="6a52e-110">È costituito da due scenari che illustrano come gestire le istanze dell'attività <xref:System.Activities.Statements.TransactionScope> all'interno di un servizio.</span><span class="sxs-lookup"><span data-stu-id="6a52e-110">Consists of two scenarios that show how to handle <xref:System.Activities.Statements.TransactionScope> activity instances within a service.</span></span>

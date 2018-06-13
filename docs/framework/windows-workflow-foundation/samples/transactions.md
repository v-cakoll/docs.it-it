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
# <a name="transactions"></a>Transazioni
In questa sezione è contenuti esempi che illustrano transazioni del flusso di lavoro in Windows Workflow Foundation (WF).  
  
## <a name="in-this-section"></a>In questa sezione  
 [TransactionScope di base](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 Sono costituiti da quattro scenari che illustrano come annidare istanze di <xref:System.Activities.Statements.TransactionScope>.  
  
 [Uso di TransactedReceiveScope](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 Viene illustrato come propagare una transazione da un client a un server usando <xref:System.Activities.Statements.TransactionScope> per creare una nuova transazione nel client e un oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope> per ricevere un messaggio con una transazione propagata, esaminando la durata della transazione nel server.  
  
 [Annidamento di TransactionScope all'interno di un servizio](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 È costituito da due scenari che illustrano come gestire le istanze dell'attività <xref:System.Activities.Statements.TransactionScope> all'interno di un servizio.

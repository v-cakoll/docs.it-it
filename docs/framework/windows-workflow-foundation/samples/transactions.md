---
title: Transactions2
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51212219-a39e-448e-bff3-10064ff5de64
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 53389822f635151d15c2ae205c5a421a331c063b
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
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

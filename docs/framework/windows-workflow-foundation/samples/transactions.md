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
# <a name="transactions"></a>Transazioni
Contenuto della sezione sono inclusi esempi che illustrano transazioni del flusso di lavoro in [!INCLUDE[wf](../../../../includes/wf-md.md)].  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [TransactionScope di base](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 Sono costituiti da quattro scenari che illustrano come annidare istanze di <xref:System.Activities.Statements.TransactionScope>.  
  
 [Utilizzo di TransactedReceiveScope](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 Viene illustrato come propagare una transazione da un client a un server usando <xref:System.Activities.Statements.TransactionScope> per creare una nuova transazione nel client e un oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope> per ricevere un messaggio con una transazione propagata, esaminando la durata della transazione nel server.  
  
 [Annidamento di TransactionScope all'interno di un servizio](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 È costituito da due scenari che illustrano come gestire le istanze dell'attività <xref:System.Activities.Statements.TransactionScope> all'interno di un servizio.

---
title: Supporto delle transazioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7c1d438a83f090795a158ade1dfdbb7d2b2df863
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="transaction-support"></a>Supporto delle transazioni
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]supporta tre modelli di transazione distinti. Di seguito sono elencati tali modelli nell'ordine di esecuzione dei controlli.  
  
## <a name="explicit-local-transaction"></a>Transazione locale esplicita  
 Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, se la proprietà <xref:System.Data.Linq.DataContext.Transaction%2A> è impostata su una transazione (`IDbTransaction`), la chiamata <xref:System.Data.Linq.DataContext.SubmitChanges%2A> viene eseguita nel contesto della stessa transazione.  
  
 È compito del programmatore eseguire il commit o il rollback della transazione dopo che ne è stata completata l'esecuzione. La connessione corrispondente alla transazione deve essere la stessa usata per costruire <xref:System.Data.Linq.DataContext>. Se si usa una connessione diversa, viene generata un'eccezione.  
  
## <a name="explicit-distributable-transaction"></a>Transazione distribuibile esplicita  
 È possibile chiamare [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] API (inclusi, a titolo esemplificativo, <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) nell'ambito di un oggetto attivo <xref:System.Transactions.Transaction>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]rileva che la chiamata è nell'ambito di una transazione e non crea una nuova transazione. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]evita la chiusura della connessione in questo caso. Nel contesto di tale transazione è possibile eseguire query ed esecuzioni di <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
## <a name="implicit-transaction"></a>Transazione implicita  
 Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] controlla se la chiamata si trova nell'ambito di un <xref:System.Transactions.Transaction> o se il `Transaction` proprietà (`IDbTransaction`) è impostato su una transazione locale avviata dall'utente. Se trovata alcuna transazione, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] avvia una transazione locale (`IDbTransaction`) e lo usa per eseguire i comandi SQL generati. Dopo aver completato correttamente l'esecuzione di tutti i comandi SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] esegue il commit della transazione locale e lo restituisce.  
  
## <a name="see-also"></a>Vedere anche  
 [Informazioni generali](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [Procedura: racchiudere tra parentesi quadre gli invii di dati tramite transazioni](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)

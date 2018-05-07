---
title: Supporto delle transazioni
ms.date: 03/30/2017
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
ms.openlocfilehash: ff4d65c37e2d7f76c8c9f0de1de9717c8dca7b27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="transaction-support"></a>Supporto delle transazioni
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supporta tre modelli di transazione distinti. Di seguito sono elencati tali modelli nell'ordine di esecuzione dei controlli.  
  
## <a name="explicit-local-transaction"></a>Transazione locale esplicita  
 Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, se la proprietà <xref:System.Data.Linq.DataContext.Transaction%2A> è impostata su una transazione (`IDbTransaction`), la chiamata <xref:System.Data.Linq.DataContext.SubmitChanges%2A> viene eseguita nel contesto della stessa transazione.  
  
 È compito del programmatore eseguire il commit o il rollback della transazione dopo che ne è stata completata l'esecuzione. La connessione corrispondente alla transazione deve essere la stessa usata per costruire <xref:System.Data.Linq.DataContext>. Se si usa una connessione diversa, viene generata un'eccezione.  
  
## <a name="explicit-distributable-transaction"></a>Transazione distribuibile esplicita  
 È possibile chiamare [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] API (inclusi, a titolo esemplificativo, <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) nell'ambito di un oggetto attivo <xref:System.Transactions.Transaction>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] rileva che la chiamata si trova nell'ambito di una transazione e non crea una nuova transazione. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Inoltre non viene chiusa la connessione in questo caso. Nel contesto di tale transazione è possibile eseguire query ed esecuzioni di <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
## <a name="implicit-transaction"></a>Transazione implicita  
 Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] controlla se la chiamata si trova nell'ambito di un <xref:System.Transactions.Transaction> o se il `Transaction` proprietà (`IDbTransaction`) è impostato su una transazione locale avviata dall'utente. Se trovata alcuna transazione, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] avvia una transazione locale (`IDbTransaction`) e lo usa per eseguire i comandi SQL generati. Dopo aver completato correttamente l'esecuzione di tutti i comandi SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] esegue il commit della transazione locale e lo restituisce.  
  
## <a name="see-also"></a>Vedere anche  
 [Informazioni di base](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [Procedura: racchiudere tra parentesi quadre gli invii di dati utilizzando transazioni](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)

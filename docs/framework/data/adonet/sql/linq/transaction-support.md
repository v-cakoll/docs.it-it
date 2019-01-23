---
title: Supporto delle transazioni
ms.date: 03/30/2017
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
ms.openlocfilehash: f53a6081102991c73543b4cd76365f7e2c0faf89
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517201"
---
# <a name="transaction-support"></a>Supporto delle transazioni
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supporta tre modelli distinti. Di seguito sono elencati tali modelli nell'ordine di esecuzione dei controlli.  
  
## <a name="explicit-local-transaction"></a>Transazione locale esplicita  
 Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, se la proprietà <xref:System.Data.Linq.DataContext.Transaction%2A> è impostata su una transazione (`IDbTransaction`), la chiamata <xref:System.Data.Linq.DataContext.SubmitChanges%2A> viene eseguita nel contesto della stessa transazione.  
  
 È compito del programmatore eseguire il commit o il rollback della transazione dopo che ne è stata completata l'esecuzione. La connessione corrispondente alla transazione deve essere la stessa usata per costruire <xref:System.Data.Linq.DataContext>. Se si usa una connessione diversa, viene generata un'eccezione.  
  
## <a name="explicit-distributable-transaction"></a>Transazione distribuibile esplicita  
 È possibile chiamare [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] API (tra cui esemplificativo <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) nell'ambito di un oggetto attivo <xref:System.Transactions.Transaction>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] rileva che la chiamata è nell'ambito di una transazione e non crea una nuova transazione. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] inoltre evita la chiusura della connessione in questo caso. Nel contesto di tale transazione è possibile eseguire query ed esecuzioni di <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
## <a name="implicit-transaction"></a>Transazione implicita  
 Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verifica se la chiamata è nell'ambito di un <xref:System.Transactions.Transaction> oppure se il `Transaction` proprietà (`IDbTransaction`) è impostato su una transazione locale avviata dall'utente. Se non viene trovata nessuna transazione [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] avvia una transazione locale (`IDbTransaction`) e lo usa per eseguire i comandi SQL generati. Quando tutti i comandi SQL che sia stati completati, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] esegue il commit della transazione locale e restituisce.  
  
## <a name="see-also"></a>Vedere anche
- [Informazioni di base](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [Procedura: Tra parentesi quadre gli invii di dati tramite transazioni](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)

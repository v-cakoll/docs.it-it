---
title: Supporto delle transazioni
ms.date: 03/30/2017
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
ms.openlocfilehash: 9c7128ef432fa609b8d628bc74caebe790058ede
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792271"
---
# <a name="transaction-support"></a>Supporto delle transazioni
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]supporta tre modelli di transazione distinti. Di seguito sono elencati tali modelli nell'ordine di esecuzione dei controlli.  
  
## <a name="explicit-local-transaction"></a>Transazione locale esplicita  
 Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, se la proprietà <xref:System.Data.Linq.DataContext.Transaction%2A> è impostata su una transazione (`IDbTransaction`), la chiamata <xref:System.Data.Linq.DataContext.SubmitChanges%2A> viene eseguita nel contesto della stessa transazione.  
  
 È compito del programmatore eseguire il commit o il rollback della transazione dopo che ne è stata completata l'esecuzione. La connessione corrispondente alla transazione deve essere la stessa usata per costruire <xref:System.Data.Linq.DataContext>. Se si usa una connessione diversa, viene generata un'eccezione.  
  
## <a name="explicit-distributable-transaction"></a>Transazione distribuibile esplicita  
 È possibile chiamare [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] le API (incluso <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, ma non limitato) nell'ambito di un oggetto <xref:System.Transactions.Transaction>attivo. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]rileva che la chiamata si trova nell'ambito di una transazione e non crea una nuova transazione. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Inoltre, in questo caso, evita di chiudere la connessione. Nel contesto di tale transazione è possibile eseguire query ed esecuzioni di <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
## <a name="implicit-transaction"></a>Transazione implicita  
 Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verifica se la chiamata si trova nell'ambito di un oggetto <xref:System.Transactions.Transaction> o se la `Transaction` proprietà (`IDbTransaction`) è impostata su una transazione locale avviata dall'utente. Se non trova alcuna transazione, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] avvia una transazione locale (`IDbTransaction`) e la usa per eseguire i comandi SQL generati. Una volta completati tutti i comandi SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il commit della transazione locale e viene restituito.  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni di base](background-information.md)
- [Procedura: Invii di dati tra parentesi quadre tramite transazioni](how-to-bracket-data-submissions-by-using-transactions.md)

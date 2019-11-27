---
title: Altre strutture di controllo
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: 758df361f421684655147ae288af3f350e53c4d7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348139"
---
# <a name="other-control-structures-visual-basic"></a>Altre strutture di controllo (Visual Basic)
Visual Basic fornisce strutture di controllo che consentono di eliminare una risorsa o ridurre il numero di volte in cui è necessario ripetere un riferimento a un oggetto.  
  
## <a name="usingend-using-construction"></a>Uso di... Termina usando la costruzione  
 La costruzione `Using...End Using` stabilisce un blocco di istruzioni all'interno del quale si utilizza una risorsa, ad esempio una connessione SQL. Facoltativamente, è possibile acquisire la risorsa con l'istruzione `Using`. Quando si esce dal blocco `Using`, Visual Basic Elimina automaticamente la risorsa in modo che sia disponibile per l'uso da parte di altro codice. La risorsa deve essere locale e eliminabile. Per altre informazioni, vedere [Istruzione using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>Con... Termina con costruzione  
 La costruzione di `With...End With` consente di specificare un riferimento a un oggetto una volta, quindi di eseguire una serie di istruzioni che accedono ai relativi membri. In questo modo è possibile semplificare il codice e migliorare le prestazioni in quanto Visual Basic non è necessario ristabilire il riferimento per ogni istruzione che vi accede. Per ulteriori informazioni, vedere [con... Termina con l'istruzione](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>Vedere anche

- [Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Strutture decisionali](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Strutture di controllo annidate](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Istruzione Using](../../../../visual-basic/language-reference/statements/using-statement.md)
- [Istruzione With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)

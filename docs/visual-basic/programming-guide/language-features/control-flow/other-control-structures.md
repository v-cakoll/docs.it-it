---
title: Altre strutture di controllo (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: a383d0c95de5286cce722c05bd8888d5acffb173
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590000"
---
# <a name="other-control-structures-visual-basic"></a>Altre strutture di controllo (Visual Basic)
Visual Basic fornisce strutture di controllo che consentono di eliminare una risorsa o ridurre il numero di volte in cui che è necessario ripetere un riferimento all'oggetto.  
  
## <a name="usingend-using-construction"></a>Usando... Usando la costruzione di fine  
 Il `Using...End Using` costruzione stabilisce un blocco di istruzioni all'interno del quale Usa una risorsa, ad esempio una connessione SQL. Facoltativamente, è possibile acquisire la risorsa con il `Using` istruzione. Quando si esce dal `Using` blocco, Visual Basic Elimina in modo automatico della risorsa in modo che sia disponibile per altro codice da usare. La risorsa deve essere locale e disposable. Per altre informazioni, vedere [Istruzione using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>Con... Terminare con costruzione  
 Il `With...End With` costruzione consente di specificare un riferimento all'oggetto una sola volta e quindi eseguire una serie di istruzioni che accedono ai membri. Ciò può semplificare il codice e migliorare le prestazioni perché non dispone di Visual Basic ristabilire il riferimento per ogni istruzione che vi accede. Per altre informazioni, vedere [con... Terminare con istruzione](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>Vedere anche
- [Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Strutture decisionali](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Strutture di controllo annidate](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Istruzione Using](../../../../visual-basic/language-reference/statements/using-statement.md)
- [Istruzione With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)

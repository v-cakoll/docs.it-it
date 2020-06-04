---
title: Altre strutture di controllo
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: c6d80b237c7c3512c2904547842fdeb3c69bef68
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402018"
---
# <a name="other-control-structures-visual-basic"></a>Altre strutture di controllo (Visual Basic)
Visual Basic fornisce strutture di controllo che consentono di eliminare una risorsa o ridurre il numero di volte in cui è necessario ripetere un riferimento a un oggetto.  
  
## <a name="usingend-using-construction"></a>Uso di... Termina usando la costruzione  
 La `Using...End Using` costruzione stabilisce un blocco di istruzioni all'interno del quale si utilizza una risorsa, ad esempio una connessione SQL. Facoltativamente, è possibile acquisire la risorsa con l' `Using` istruzione. Quando si esce dal `Using` blocco, Visual Basic Elimina automaticamente la risorsa in modo che sia disponibile per l'uso da parte di altro codice. La risorsa deve essere locale e eliminabile. Per ulteriori informazioni, vedere [istruzione using](../../../language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>Con... Termina con costruzione  
 La `With...End With` costruzione consente di specificare un riferimento a un oggetto una volta, quindi di eseguire una serie di istruzioni che accedono ai relativi membri. In questo modo è possibile semplificare il codice e migliorare le prestazioni in quanto Visual Basic non è necessario ristabilire il riferimento per ogni istruzione che vi accede. Per ulteriori informazioni, vedere [con... Termina con l'istruzione](../../../language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>Vedere anche

- [Flusso di controllo](index.md)
- [Strutture decisionali](decision-structures.md)
- [Strutture di ciclo](loop-structures.md)
- [Strutture di controllo annidate](nested-control-structures.md)
- [Istruzione using](../../../language-reference/statements/using-statement.md)
- [Istruzione With...End With](../../../language-reference/statements/with-end-with-statement.md)

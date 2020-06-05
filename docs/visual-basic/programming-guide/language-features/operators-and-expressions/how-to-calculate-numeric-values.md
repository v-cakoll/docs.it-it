---
title: 'Procedura: calcolare valori numerici'
ms.date: 07/20/2015
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
ms.openlocfilehash: 94b02693f308dcfcfa6983f2750a26d9d419f7be
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403459"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>Procedura: calcolare valori numerici (Visual Basic)
È possibile calcolare i valori numerici tramite l'utilizzo di espressioni numeriche. Un' *espressione numerica* è un'espressione che contiene valori letterali, costanti e variabili che rappresentano valori numerici e operatori che agiscono su tali valori.  
  
## <a name="calculating-numeric-values"></a>Calcolo dei valori numerici  
  
#### <a name="to-calculate-a-numeric-value"></a>Per calcolare un valore numerico  
  
- Combinare uno o più valori letterali numerici, costanti e variabili in un'espressione numerica. Nell'esempio seguente vengono illustrate alcune espressioni numeriche valide.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     Le prime tre righe mostrano un valore letterale, una costante e una variabile. Ognuno di essi costituisce un'espressione numerica valida. La riga finale mostra una combinazione di una variabile con due valori letterali.  
  
     Si noti che un'espressione numerica non costituisce un'istruzione Visual Basic completa da sola. È necessario utilizzare l'espressione come parte di un'istruzione completa.  
  
#### <a name="to-store-a-numeric-value"></a>Per archiviare un valore numerico  
  
- È possibile utilizzare un'istruzione di assegnazione per assegnare il valore rappresentato da un'espressione numerica a una variabile, come illustrato nell'esempio riportato di seguito.  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     Nell'esempio precedente, il valore dell'espressione sul lato destro dell'operatore EQUAL ( `=` ) viene assegnato alla variabile `j` sul lato sinistro dell'operatore, quindi `j` restituisce 276.  
  
     Per altre informazioni, vedere [Istruzioni](../../../language-reference/statements/index.md).  
  
## <a name="multiple-operators"></a>Più operatori  
 Se l'espressione numerica contiene più di un operatore, l'ordine in cui vengono valutate dipende dalle regole di precedenza degli operatori. Per eseguire l'override delle regole di precedenza degli operatori, racchiudere le espressioni tra parentesi, come nell'esempio precedente; le espressioni racchiuse vengono valutate per prime.  
  
#### <a name="to-override-normal-operator-precedence"></a>Per eseguire l'override della normale precedenza degli operatori  
  
- Utilizzare le parentesi per racchiudere le operazioni che si desidera eseguire per prime. Nell'esempio seguente vengono illustrati due risultati diversi con gli stessi operandi e operatori.  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     Nell'esempio precedente, il calcolo per `j` esegue prima l'operatore di addizione ( `+` ) perché le parentesi che racchiudono `(67 + i)` sostituiscono la precedenza normale e il valore assegnato a `j` è 276 (4 volte 69). Il calcolo per `k` esegue gli operatori con la precedenza normale ( `*` prima `+` ) e il valore assegnato a `k` è 270 (268 più 2).  
  
     Per ulteriori informazioni, vedere [precedenza degli operatori in Visual Basic](../../../language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Vedere anche

- [Operatori ed espressioni](index.md)
- [Confronto di valori](value-comparisons.md)
- [Istruzioni](../../../language-reference/statements/index.md)
- [Precedenza tra gli operatori in Visual Basic](../../../language-reference/operators/operator-precedence.md)
- [Operatori aritmetici](../../../language-reference/operators/arithmetic-operators.md)
- [Combinazione efficace di operatori](efficient-combination-of-operators.md)

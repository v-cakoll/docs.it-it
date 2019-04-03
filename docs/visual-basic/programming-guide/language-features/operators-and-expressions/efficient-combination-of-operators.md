---
title: Combinazione efficace di operatori (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- expressions [Visual Basic], parentheses
- operators [Visual Basic], associativity
- expressions [Visual Basic], operators
- operators [Visual Basic], precedence
- Visual Basic code, operators
- Visual Basic code, expressions
- operators [Visual Basic], complex expressions
- expressions [Visual Basic], complex
- parentheses [Visual Basic], complex expressions
- numeric expressions
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
ms.openlocfilehash: 8f5dd6c56b3e4576b9d798e0e5e10b2996f558dc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841257"
---
# <a name="efficient-combination-of-operators-visual-basic"></a>Combinazione efficace di operatori (Visual Basic)
Le espressioni complesse possono contenere molti operatori diversi. Questa condizione è illustrata nell'esempio seguente.  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 Per creare espressioni complesse come quello nell'esempio precedente richiede una conoscenza approfondita delle regole di precedenza degli operatori. Per altre informazioni, vedere [precedenza degli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="parenthetical-expressions"></a>Espressioni tra parentesi  
 Spesso è necessario di operazioni in un ordine diverso da quello determinato dalla precedenza degli operatori. Si osservi l'esempio riportato di seguito.  
  
 `x = z * y + 4`  
  
 Moltiplica l'esempio precedente `z` dal `y`, quindi aggiunge il risultato a `4`. Tuttavia, se si desidera aggiungere `y` e `4` prima di moltiplicando il risultato da `z`, è possibile eseguire l'override di precedenza degli operatori normale usando le parentesi. Racchiudendo un'espressione tra parentesi, si forza quell'espressione da valutare in primo luogo, indipendentemente dalla precedenza degli operatori. Per forzare l'esempio precedente per eseguire prima l'addizione, è necessario riscriverla come nell'esempio seguente.  
  
 `x = z * (y + 4)`  
  
 Nell'esempio precedente viene aggiunto `y` e `4`, quindi moltiplica tale somma per `z`.  
  
### <a name="nested-parenthetical-expressions"></a>Espressioni tra parentesi nidificate  
 È possibile annidare le espressioni in più livelli di parentesi per ignorare la precedenza ulteriormente. Le espressioni di annidamento più profondo racchiuso tra parentesi vengono valutate per primi, seguito da quello successivo di annidamento più profondo, e così via fino al minimo di nidificazione e infine le espressioni all'esterno delle parentesi. Questa condizione è illustrata nell'esempio seguente.  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 Nell'esempio precedente, `z + 2` viene valutato per primo, quindi le altre espressioni tra parentesi. Elevamento a potenza, che normalmente ha precedenza maggiore rispetto ad addizione e moltiplicazione, viene valutato per ultimo in questo esempio perché le altre espressioni sono racchiuse tra parentesi.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori aritmetici in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Operatori di confronto in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operatori logici e bit per bit in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Operatori logici e bit per bit (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Espressioni booleane](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Confronto di valori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Procedura: Calcolare valori numerici](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [Precedenza tra gli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)

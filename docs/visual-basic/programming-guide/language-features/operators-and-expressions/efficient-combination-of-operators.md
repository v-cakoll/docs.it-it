---
title: Combinazione efficace di operatori
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
ms.openlocfilehash: 83ad53e4c75490a75eba0f80a6bf0f078aa4d426
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348974"
---
# <a name="efficient-combination-of-operators-visual-basic"></a>Combinazione efficace di operatori (Visual Basic)
Le espressioni complesse possono contenere molti operatori diversi. Questa condizione è illustrata nell'esempio seguente.  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 La creazione di espressioni complesse come quella nell'esempio precedente richiede una conoscenza approfondita delle regole di precedenza degli operatori. Per ulteriori informazioni, vedere [precedenza degli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="parenthetical-expressions"></a>Espressioni parentesi  
 Spesso si desidera che le operazioni procedano in un ordine diverso rispetto a quello determinato dalla precedenza degli operatori. Si osservi l'esempio riportato di seguito.  
  
 `x = z * y + 4`  
  
 Nell'esempio precedente viene moltiplicato `z` per `y`, quindi viene aggiunto il risultato a `4`. Tuttavia, se si desidera aggiungere `y` e `4` prima di moltiplicare il risultato per `z`, è possibile eseguire l'override della normale precedenza degli operatori utilizzando le parentesi. Racchiudendo un'espressione tra parentesi, si impone la valutazione iniziale di tale espressione, indipendentemente dalla precedenza degli operatori. Per forzare l'esempio precedente a eseguire prima l'aggiunta, è possibile riscriverla come nell'esempio seguente.  
  
 `x = z * (y + 4)`  
  
 Nell'esempio precedente vengono aggiunti `y` e `4`, quindi la somma viene moltiplicata per `z`.  
  
### <a name="nested-parenthetical-expressions"></a>Espressioni parentesi annidate  
 È possibile annidare le espressioni in più livelli di parentesi per ignorare ulteriormente la precedenza. Le espressioni più profondamente annidate tra parentesi vengono valutate per prime, seguite dalla successiva nidificazione più approfondita e così via fino al meno annidato e infine le espressioni all'esterno delle parentesi. Questa condizione è illustrata nell'esempio seguente.  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 Nell'esempio precedente `z + 2` viene valutato per primo, quindi le altre espressioni parentesi. L'elevamento a potenza, che in genere ha una precedenza più alta rispetto all'addizione o alla moltiplicazione, viene valutato per ultimo in questo esempio perché le altre espressioni sono racchiuse tra parentesi.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori aritmetici in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Operatori di confronto in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operatori logici e bit per bit in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Operatori logici/bit per bit (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Espressioni booleane](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Confronto di valori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Procedura: Calcolare valori numerici](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [Precedenza tra gli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)

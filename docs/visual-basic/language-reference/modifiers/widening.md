---
title: Widening
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: 1c9aa78549ca6e41c9fe54c12e0aaec8e7cc30cb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347836"
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)
Indica che un operatore di conversione (`CType`) converte una classe o una struttura in un tipo che può conservare tutti i valori possibili della classe o della struttura originale.  
  
## <a name="converting-with-the-widening-keyword"></a>Conversione con la parola chiave Widen  
 La procedura di conversione deve specificare `Public Shared` oltre al `Widening`.  
  
 Le conversioni verso un tipo di dati più ampio hanno sempre esito positivo in fase di esecuzione e non subiscono mai Gli esempi sono `Single` `Double`, `Char` `String`e un tipo derivato al relativo tipo di base. Questa ultima conversione viene ampliata perché il tipo derivato contiene tutti i membri del tipo di base e pertanto è un'istanza del tipo di base.  
  
 Il codice consumer non deve usare `CType` per le conversioni verso un tipo di oggetto più ampio, anche se `Option Strict` è `On`.  
  
 Il `Widening` parola chiave può essere usato in questo contesto:  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 Per le definizioni di operatori di conversione verso un tipo di informazioni più piccolo e più piccolo, vedere [procedura: definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>Vedere anche

- [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Procedura: Definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)

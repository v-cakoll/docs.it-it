---
title: Narrowing
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: b252f7939e812f31103d4bd98ffd50953679f042
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351469"
---
# <a name="narrowing-visual-basic"></a>Narrowing (Visual Basic)
Indica che un operatore di conversione (`CType`) converte una classe o una struttura in un tipo che potrebbe non essere in grado di contenere alcuni dei possibili valori della classe o della struttura originale.  
  
## <a name="converting-with-the-narrowing-keyword"></a>Conversione con la parola chiave Narrowing  
 La procedura di conversione deve specificare `Public Shared` oltre al `Narrowing`.  
  
 Le conversioni verso un tipo di dati più piccolo non vengono sempre eseguite in fase di esecuzione e possono avere esito negativo o causare una perdita di dati. Gli esempi sono `Long` `Integer`, `String` `Date`e un tipo di base a un tipo derivato. Questa ultima conversione si restringe perché il tipo di base potrebbe non contenere tutti i membri del tipo derivato e pertanto non è un'istanza del tipo derivato.  
  
 Se `Option Strict` è `On`, il codice consumer deve utilizzare `CType` per tutte le conversioni verso un tipo di caratteri più piccolo.  
  
 Il `Narrowing` parola chiave può essere usato in questo contesto:  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Widening](../../../visual-basic/language-reference/modifiers/widening.md)
- [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)

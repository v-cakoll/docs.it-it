---
title: Narrowing (Visual Basic)
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
ms.openlocfilehash: eb5f021371291483b8eb2a13727a9fda94540638
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838849"
---
# <a name="narrowing-visual-basic"></a>Narrowing (Visual Basic)
Indica che un operatore di conversione (`CType`) converte una classe o struttura in un tipo che potrebbe non essere in grado di contenere alcuni dei possibili valori della classe o struttura originale.  
  
## <a name="converting-with-the-narrowing-keyword"></a>Conversione di Narrowing (parola chiave)  
 Routine di conversione deve specificare `Public Shared` oltre a `Narrowing`.  
  
 Conversioni di Narrowing non sempre riuscire in fase di esecuzione e può avere esito negativo o comportano una perdita di dati. Sono esempi `Long` al `Integer`, `String` a `Date`e un tipo di base a un tipo derivato. Questa conversione ultimo è narrowing perché il tipo di base potrebbe non contenere tutti i membri del tipo derivato e pertanto non è un'istanza del tipo derivato.  
  
 Se `Option Strict` viene `On`, il codice deve usare `CType` per tutte le conversioni di narrowing.  
  
 Il `Narrowing` parola chiave può essere usata in questo contesto:  
  
 [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Widening](../../../visual-basic/language-reference/modifiers/widening.md)
- [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Funzione CType](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)

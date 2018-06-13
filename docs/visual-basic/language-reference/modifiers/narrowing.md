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
ms.openlocfilehash: 54a18d0cc10e42829b48b0ef75bb77ab0d47b45f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597458"
---
# <a name="narrowing-visual-basic"></a>Narrowing (Visual Basic)
Indica che un operatore di conversione (`CType`) converte una classe o struttura in un tipo che potrebbe non essere in grado di contenere alcuni dei possibili valori della classe o della struttura originale.  
  
## <a name="converting-with-the-narrowing-keyword"></a>La conversione con la parola chiave Narrowing  
 Routine di conversione deve specificare `Public Shared` oltre a `Narrowing`.  
  
 Conversioni di restrizione non sempre esito positivo in fase di esecuzione e può non riuscire o comportare la perdita di dati. Esempi sono `Long` a `Integer`, `String` a `Date`e un tipo di base a un tipo derivato. Questa conversione ultima è narrowing perché il tipo di base potrebbe non contenere tutti i membri del tipo derivato e pertanto non è un'istanza del tipo derivato.  
  
 Se `Option Strict` è `On`, l'utilizzo di codice è necessario utilizzare `CType` per tutte le conversioni di restrizione.  
  
 Il `Narrowing` parola chiave può essere utilizzata in questo contesto:  
  
 [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Funzione CType](../../../visual-basic/language-reference/functions/ctype-function.md)  
 [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)

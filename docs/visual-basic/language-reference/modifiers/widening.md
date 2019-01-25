---
title: Widening (Visual Basic)
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
ms.openlocfilehash: 3b9d1ec15c6c2000fb0842abe25848f853cdf986
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703709"
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)
Indica che un operatore di conversione (`CType`) converte una classe o struttura in un tipo che può contenere tutti i possibili valori della classe o struttura originale.  
  
## <a name="converting-with-the-widening-keyword"></a>La conversione con la parola chiave Widening  
 Routine di conversione deve specificare `Public Shared` oltre a `Widening`.  
  
 Le conversioni di ampliamento sempre eseguite correttamente in fase di esecuzione e non comportano perdita di dati. Sono esempi `Single` al `Double`, `Char` a `String`e un tipo derivato al tipo di base. Questa conversione ultimo è grande perché il tipo derivato contiene tutti i membri del tipo di base e pertanto rappresenta un'istanza del tipo di base.  
  
 Il codice consumer non deve utilizzare `CType` per la conversione di ampliamento, anche se `Option Strict` è `On`.  
  
 Il `Widening` parola chiave può essere usata in questo contesto:  
  
 [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 Ad esempio le definizioni di ampliamento e restrizione gli operatori di conversione, vedere [come: Definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Funzione CType](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Procedura: Definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)

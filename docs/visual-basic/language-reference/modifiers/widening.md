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
ms.openlocfilehash: 69040bf48b44a54f7a231738b88db1cbc716ebb3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359903"
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)
Indica che un operatore di conversione ( `CType` ) converte una classe o una struttura in un tipo che può conservare tutti i valori possibili della classe o della struttura originale.  
  
## <a name="converting-with-the-widening-keyword"></a>Conversione con la parola chiave Widen  
 La procedura di conversione deve specificare `Public Shared` oltre a `Widening` .  
  
 Le conversioni verso un tipo di dati più ampio hanno sempre esito positivo in fase di esecuzione e non subiscono mai Gli esempi `Single` sono `Double` , `Char` a `String` e un tipo derivato al relativo tipo di base. Questa ultima conversione viene ampliata perché il tipo derivato contiene tutti i membri del tipo di base e pertanto è un'istanza del tipo di base.  
  
 Il codice consumer non deve usare per le conversioni verso un tipo di oggetto più `CType` ampio, anche se `Option Strict` è `On` .  
  
 La `Widening` parola chiave può essere usata in questo contesto:  
  
 [Operator Statement](../statements/operator-statement.md)  
  
 Per le definizioni di operatori di conversione verso un tipo di informazioni più piccolo e più piccolo, vedere [procedura: definire un operatore di conversione](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>Vedere anche

- [Operator Statement](../statements/operator-statement.md)
- [Narrowing](narrowing.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Procedura: definire un operatore](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType Function](../functions/ctype-function.md)
- [Option Strict Statement](../statements/option-strict-statement.md)
- [Procedura: Definire un operatore di conversione](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)

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
ms.openlocfilehash: f7724053e3732c909523e4e2d3b65bb1918c29d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362359"
---
# <a name="narrowing-visual-basic"></a>Narrowing (Visual Basic)
Indica che un operatore di conversione ( `CType` ) converte una classe o una struttura in un tipo che potrebbe non essere in grado di contenere alcuni dei possibili valori della classe o della struttura originale.  
  
## <a name="converting-with-the-narrowing-keyword"></a>Conversione con la parola chiave Narrowing  
 La procedura di conversione deve specificare `Public Shared` oltre a `Narrowing` .  
  
 Le conversioni verso un tipo di dati più piccolo non vengono sempre eseguite in fase di esecuzione e possono avere esito negativo o causare una perdita di dati. Gli esempi `Long` sono `Integer` , `String` a `Date` e un tipo di base a un tipo derivato. Questa ultima conversione si restringe perché il tipo di base potrebbe non contenere tutti i membri del tipo derivato e pertanto non è un'istanza del tipo derivato.  
  
 Se `Option Strict` è `On` , il codice consumer deve utilizzare `CType` per tutte le conversioni verso un tipo di caratteri più piccolo.  
  
 La `Narrowing` parola chiave può essere usata in questo contesto:  
  
 [Operator Statement](../statements/operator-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Operator Statement](../statements/operator-statement.md)
- [Widening](widening.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Procedura: definire un operatore](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType Function](../functions/ctype-function.md)
- [Option Strict Statement](../statements/option-strict-statement.md)

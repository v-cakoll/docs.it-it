---
title: Impossibile dedurre il tipo di '<variablename>' perché i limiti del ciclo e la clausola STEP non eseguono la conversione nello stesso tipo
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: c3086f79fb71693810bc8f14e8c0f493aa1e6515
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512713"
---
# <a name="type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a>Non è possibile\<dedurre il tipo di ' variablename >' perché i limiti del ciclo e la variabile Step non si ampliano allo stesso tipo

È stato scritto un `For...Next` ciclo in cui il compilatore non può dedurre un tipo di dati per la variabile di controllo del ciclo perché sono soddisfatte le condizioni seguenti:

- Il tipo di dati della variabile di controllo del ciclo non è specificato con una clausola `As` .

- I limiti del ciclo e la clausola step contengono almeno due tipi di dati.

- Non esistono conversioni standard tra i tipi di dati.

 Pertanto, il compilatore non può dedurre il tipo di dati della variabile di controllo di un ciclo.

 Nell'esempio seguente, la variabile Step è un carattere e i limiti del ciclo sono entrambi numeri interi. Poiché non esiste una conversione standard tra i caratteri e i numeri interi, questo errore viene segnalato.

```vb
Dim stepVar = "1"c
Dim m = 0
Dim n = 20

' Not valid.
' For i = 1 To 10 Step stepVar
    ' Loop processing
' Next
```

**ID errore:** BC30982

## <a name="to-correct-this-error"></a>Per correggere l'errore

- Modificare i tipi di limiti del ciclo e la variabile Step in modo che almeno uno di essi sia un tipo a cui gli altri si ampliano. Nell'esempio precedente, modificare il tipo di `stepVar` in. `Integer`

  ```vb
  Dim stepVar = 1
  ```

  -oppure-

  ```vb
  Dim stepVar As Integer = 1
  ```

- Utilizzare le funzioni di conversione esplicita per convertire i limiti del ciclo e la variabile Step nei tipi appropriati. Nell'esempio precedente, applicare la `Val` funzione a. `stepVar`

  ```vb
  For i = 1 To 10 Step Val(stepVar)
      ' Loop processing
  Next
  ```

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Istruzione Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)

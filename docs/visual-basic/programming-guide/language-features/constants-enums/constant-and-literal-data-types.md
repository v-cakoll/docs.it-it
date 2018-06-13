---
title: Tipi di dati costanti e letterali (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 8d110ec17bcdb03f339d779b2950ba56d77957cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649848"
---
# <a name="constant-and-literal-data-types-visual-basic"></a>Tipi di dati costanti e letterali (Visual Basic)
Un valore letterale è un valore espresso come se stesso, anziché come valore di una variabile o il risultato di un'espressione, ad esempio il numero 3 oppure la stringa "Hello". Una costante è un nome significativo che prende il posto di un valore letterale e mantiene lo stesso valore in tutto il programma, anziché una variabile, il cui valore può essere modificato.  
  
 Quando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) è `Off` e [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) è `On`, è necessario dichiarare tutte le costanti in modo esplicito con un tipo di dati. Nell'esempio seguente, il tipo di dati `MyByte` in modo esplicito è dichiarato come tipo di dati `Byte`:  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 Quando `Option Infer` è `On` o `Option Strict` è `Off`, è possibile dichiarare una costante senza specificare un tipo di dati con un `As` clausola. Il compilatore determina il tipo della costante dal tipo dell'espressione. Viene eseguito il cast di un valore letterale integer numerico per impostazione predefinita per il `Integer` tipo di dati. Tipo di dati predefinito per numeri a virgola mobile sono `Double`e le parole chiave `True` e `False` specificare un `Boolean` costante.  
  
## <a name="literals-and-type-coercion"></a>Valori letterali e coercizione di tipi  
 In alcuni casi, è possibile forzare un valore letterale a un tipo di dati specifico. ad esempio, quando si assegna un valore letterale integrale particolarmente elevato a una variabile di tipo `Decimal`. Nell'esempio seguente genera un errore:  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 L'errore deriva dalla rappresentazione del valore letterale. Il `Decimal` tipo di dati può contenere un valore così elevato, ma il valore letterale è rappresentato in modo implicito come una `Long`, che non è possibile.  
  
 È possibile assegnare un valore letterale in un particolare tipo di dati in due modi: aggiungendo un carattere di tipo o inserendolo in caratteri di contenimento. Un carattere o caratteri di contenimento devono immediatamente precedere e/o seguire il valore letterale, senza spazi o caratteri di qualsiasi tipo.  
  
 Per correggere l'esempio precedente, è possibile aggiungere il `D` tipo di carattere per il valore letterale, in modo che essere rappresentato come un `Decimal`:  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 Nell'esempio seguente viene illustrato l'uso corretto di caratteri di tipo e che lo contiene:  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 La seguente tabella sono riportati i caratteri che lo contiene e i caratteri di tipo disponibile in Visual Basic.  
  
|Tipo di dati|Carattere di inclusione|Carattere di tipo aggiunto|  
|---|---|---|  
|`Boolean`|(nessuno)|(nessuno)|  
|`Byte`|(nessuno)|(nessuno)|  
|`Char`|"|C|  
|`Date`|#|(nessuno)|  
|`Decimal`|(nessuno)|D o @|  
|`Double`|(nessuno)|R o #|  
|`Integer`|(nessuno)|I o %|  
|`Long`|(nessuno)|L o &|  
|`Short`|(nessuno)|S|  
|`Single`|(nessuno)|F o!|  
|`String`|"|(nessuno)|  
  
## <a name="see-also"></a>Vedere anche  
 [Costanti definite dall'utente](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)  
 [Procedura: Dichiarare una costante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)  
 [Cenni preliminari sulle costanti](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Istruzione Option Explicit](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Cenni preliminari sulle enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [Procedura: dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)

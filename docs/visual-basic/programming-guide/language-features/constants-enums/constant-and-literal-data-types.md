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
ms.openlocfilehash: 1d030f8058cd497212c20bca8f064f2bedc99fce
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507817"
---
# <a name="constant-and-literal-data-types-visual-basic"></a>Tipi di dati costanti e letterali (Visual Basic)
Un valore letterale è un valore espresso come se stessa anziché come valore di una variabile o il risultato di un'espressione, ad esempio il numero 3 oppure la stringa "Hello". Una costante è un nome significativo che prende il posto di un valore letterale e mantiene lo stesso valore in tutto il programma, a differenza di una variabile, il cui valore può essere modificato.  
  
 Quando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) viene `Off` e [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) è `On`, è necessario dichiarare in modo esplicito tutte le costanti con un tipo di dati. Nell'esempio seguente, il tipo di dati `MyByte` viene dichiarato in modo esplicito come tipo di dati `Byte`:  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 Quando `Option Infer` viene `On` oppure `Option Strict` viene `Off`, è possibile dichiarare una costante senza specificare un tipo di dati con un `As` clausola. Il compilatore determina il tipo della costante dal tipo dell'espressione. Viene eseguito il cast di un valore letterale integer numerico per impostazione predefinita per il `Integer` tipo di dati. Tipo di dati predefinito per numeri a virgola mobile sono `Double`e le parole chiave `True` e `False` specificare un `Boolean` costante.  
  
## <a name="literals-and-type-coercion"></a>Valori letterali e coercizione dei tipi  
 In alcuni casi, è possibile forzare un valore letterale per un particolare tipo di dati; ad esempio, quando si assegna un valore letterale integrale particolarmente elevato a una variabile di tipo `Decimal`. Nell'esempio seguente genera un errore:  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 L'errore deriva dalla rappresentazione del valore letterale. Il `Decimal` tipo di dati può contenere un valore così elevato, ma il valore letterale è rappresentato in modo implicito come una `Long`, che non è possibile.  
  
 È possibile assegnare un valore letterale in un particolare tipo di dati in due modi: aggiungendo un carattere tipo oppure inserendoli all'interno di caratteri di inclusione. Un carattere o racchiudere i caratteri deve immediatamente preceduto e/o seguire il valore letterale, senza spazi o caratteri di qualsiasi tipo.  
  
 Per garantire il funzionamento dell'esempio precedente, è possibile aggiungere il `D` tipo di carattere per il valore letterale, in modo che essere rappresentato come un `Decimal`:  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 Nell'esempio seguente illustra l'uso corretto di caratteri che la contiene e caratteri di tipo:  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 La seguente tabella mostra i caratteri che la contiene e i caratteri di tipo disponibili in Visual Basic.  
  
|Tipo di dati|Carattere di inclusione|Carattere di tipo accodati|  
|---|---|---|  
|`Boolean`|(nessuno)|(nessuno)|  
|`Byte`|(nessuno)|(nessuno)|  
|`Char`|"|C|  
|`Date`|#|(nessuno)|  
|`Decimal`|(nessuno)|1!d oppure @|  
|`Double`|(nessuno)|R o n|  
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
 [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md)  
 [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)

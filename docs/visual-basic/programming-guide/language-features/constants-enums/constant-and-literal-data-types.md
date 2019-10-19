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
ms.openlocfilehash: 9db7fa3f36021a39fafe6cf3da5af7070f0b5b0d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582968"
---
# <a name="constant-and-literal-data-types-visual-basic"></a>Tipi di dati costanti e letterali (Visual Basic)
Un valore letterale è un valore espresso come se stesso anziché come valore di una variabile oppure il risultato di un'espressione, ad esempio il numero 3 o la stringa "Hello". Una costante è un nome significativo che prende il posto di un valore letterale e mantiene lo stesso valore in tutto il programma, anziché una variabile, il cui valore può cambiare.  
  
 Quando [Option deduce](../../../../visual-basic/language-reference/statements/option-infer-statement.md) è `Off` e [option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) è `On`, è necessario dichiarare in modo esplicito tutte le costanti con un tipo di dati. Nell'esempio seguente il tipo di dati di `MyByte` viene dichiarato in modo esplicito come tipo di dati `Byte`:  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 Quando `Option Infer` è `On` o `Option Strict` è `Off`, è possibile dichiarare una costante senza specificare un tipo di dati con una clausola `As`. Il compilatore determina il tipo della costante dal tipo dell'espressione. Per impostazione predefinita, viene eseguito il cast di un valore letterale integer numerico al tipo di dati `Integer`. Il tipo di dati predefinito per i numeri a virgola mobile è `Double` e le parole chiave `True` e `False` specificano una costante `Boolean`.  
  
## <a name="literals-and-type-coercion"></a>Valori letterali e coercizione del tipo  
 In alcuni casi, potrebbe essere necessario forzare un valore letterale in un tipo di dati specifico. ad esempio, quando si assegna un valore letterale integrale particolarmente grande a una variabile di tipo `Decimal`. Nell'esempio seguente viene generato un errore:  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 Errore risultante dalla rappresentazione del valore letterale. Il tipo di dati `Decimal` può avere un valore di grandi dimensioni, ma il valore letterale viene rappresentato in modo implicito come `Long`, che non può.  
  
 È possibile assegnare un valore letterale a un particolare tipo di dati in due modi: aggiungendovi un carattere di tipo o inserendolo all'interno di caratteri di inclusione. Un carattere di tipo o caratteri di inclusione devono immediatamente precedere e/o seguire il valore letterale, senza spazi o caratteri di qualsiasi tipo.  
  
 Per far funzionare l'esempio precedente, è possibile aggiungere il carattere del tipo di `D` al valore letterale, che ne determina la rappresentazione come `Decimal`:  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 Nell'esempio seguente viene illustrato il corretto utilizzo di caratteri di tipo e caratteri di inclusione:  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 Nella tabella seguente vengono illustrati i caratteri di inclusione e i caratteri di tipo disponibili in Visual Basic.  
  
|Tipo di dati|Carattere di inclusione|Carattere tipo aggiunto|  
|---|---|---|  
|`Boolean`|(nessuno)|(nessuno)|  
|`Byte`|(nessuno)|(nessuno)|  
|`Char`|"|C|  
|`Date`|#|(nessuno)|  
|`Decimal`|(nessuno)|D o @|  
|`Double`|(nessuno)|R o #|  
|`Integer`|(nessuno)|I o%|  
|`Long`|(nessuno)|L o &|  
|`Short`|(nessuno)|S|  
|`Single`|(nessuno)|F o!|  
|`String`|"|(nessuno)|  
  
## <a name="see-also"></a>Vedere anche

- [Costanti definite dall'utente](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)
- [Procedura: Dichiarare una costante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)
- [Cenni preliminari sulle costanti](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Istruzione Option Explicit](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Cenni preliminari sulle enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Procedura: dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md)
- [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)

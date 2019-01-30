---
title: Copiando il valore del parametro 'ByRef' '<parametername>' nell'argomento corrispondente viene eseguita la conversione dal tipo '<typename1>' a '<typename2>', più piccolo
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: c5d427495e8eedae9dc0163c97401338fb6d0bbd
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276614"
---
# <a name="copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a>Quando il valore del parametro 'ByRef' '\<nomeparametro >' nell'argomento corrispondente viene convertito dal tipo '\<NomeTipo1 >' nel tipo '\<in NomeTipo2 >'
Una routine viene chiamata con un argomento che può ampliarsi nel tipo di parametro corrispondente e la conversione dal parametro per l'argomento è di restrizione.  
  
 Quando si definisce una classe o una struttura, è possibile definire uno o più operatori di conversione per convertire il tipo della classe o della struttura in altri tipi. È anche possibile definire operatori di conversione inversi per riconvertire gli altri tipi nel tipo della classe o della struttura originale. Quando si usa il tipo di classe o struttura in una chiamata di routine, Visual Basic possono usare gli operatori di conversione per convertire il tipo di argomento al tipo di parametro corrispondente.  
  
 Se si passa l'argomento [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic copia a volte il valore dell'argomento in una variabile locale nella routine invece di passare un riferimento. In tal caso, quando la procedura termina, Visual Basic deve quindi copiare il valore della variabile locale nell'argomento nel codice chiamante.  
  
 Se un valore dell'argomento `ByRef` viene copiato nella routine e l'argomento e il parametro sono dello stesso tipo, non è necessaria alcuna conversione. Ma se i tipi sono diversi, Visual Basic deve convertire in entrambe le direzioni. Se uno dei tipi è il tipo di classe o struttura, Visual Basic è necessario convertirlo da e verso l'altro tipo. Se una di queste conversioni è grande, potrebbe essere narrowing la conversione inversa.  
  
 **ID errore:** BC32053  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se possibile, usare un argomento chiamante dello stesso tipo del parametro di routine, in modo che Visual Basic non è necessario eseguire alcuna conversione.  
  
-   Se è necessario chiamare la routine con un tipo di argomento diverso dal tipo del parametro, ma non è necessario restituire un valore nell'argomento chiamante, definire il parametro in modo che sia [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) invece che `ByRef`.  
  
-   Se è necessario restituire un valore nell'argomento chiamante, definire l'operatore di conversione inverso come [Widening](../../../visual-basic/language-reference/modifiers/widening.md), se possibile.  
  
## <a name="see-also"></a>Vedere anche
- [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Parametri e argomenti delle routine](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Passaggio di argomenti per valore e per riferimento](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Procedura: Definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Conversioni di tipi in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)

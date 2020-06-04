---
title: Copiando il valore del parametro 'ByRef' '<parametername>' nell'argomento corrispondente viene eseguita la conversione dal tipo '<typename1>' a '<typename2>', più piccolo
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: bac5f9a88df719bc64a8b0541f65e5912275866e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409751"
---
# <a name="copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a>Copiando il valore del parametro 'ByRef' '\<parametername>' nell'argomento corrispondente viene eseguita la conversione dal tipo '\<typename1>' a '\<typename2>', più piccolo
Una routine viene chiamata con un argomento che viene ampliato al tipo di parametro corrispondente e la conversione dal parametro all'argomento è più restrittiva.  
  
 Quando si definisce una classe o una struttura, è possibile definire uno o più operatori di conversione per convertire il tipo della classe o della struttura in altri tipi. È anche possibile definire operatori di conversione inversi per riconvertire gli altri tipi nel tipo della classe o della struttura originale. Quando si usa il tipo di classe o struttura in una chiamata di procedura, Visual Basic possibile usare questi operatori di conversione per convertire il tipo di un argomento nel tipo del parametro corrispondente.  
  
 Se si passa l'argomento [ByRef](../modifiers/byref.md), Visual Basic talvolta copia il valore dell'argomento in una variabile locale nella routine invece di passare un riferimento. In tal caso, quando la procedura viene restituita, Visual Basic necessario copiare nuovamente il valore della variabile locale nell'argomento nel codice chiamante.  
  
 Se un valore dell'argomento `ByRef` viene copiato nella routine e l'argomento e il parametro sono dello stesso tipo, non è necessaria alcuna conversione. Tuttavia, se i tipi sono diversi, Visual Basic necessario eseguire la conversione in entrambe le direzioni. Se uno dei tipi è il tipo della classe o della struttura, Visual Basic necessario convertirlo in e da un altro tipo. Se una di queste conversioni viene ampliata, la conversione inversa potrebbe essere più restrittiva.  
  
 **ID errore:** BC32053  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se possibile, usare un argomento chiamante dello stesso tipo del parametro della routine, in modo che Visual Basic non debba eseguire alcuna conversione.  
  
- Se è necessario chiamare la routine con un tipo di argomento diverso dal tipo del parametro, ma non è necessario restituire un valore nell'argomento chiamante, definire il parametro in modo che sia [ByVal](../modifiers/byval.md) invece che `ByRef`.  
  
- Se è necessario restituire un valore nell'argomento chiamante, definire l'operatore di conversione inverso come più [ampio](../modifiers/widening.md), se possibile.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](../../programming-guide/language-features/procedures/index.md)
- [Parametri e argomenti delle routine](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Passaggio di argomenti per valore e per riferimento](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Routine di operatore](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Operator Statement](../statements/operator-statement.md)
- [Procedura: definire un operatore](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Procedura: Definire un operatore di conversione](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Conversioni di tipi in Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)

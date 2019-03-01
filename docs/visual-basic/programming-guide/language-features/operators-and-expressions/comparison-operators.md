---
title: Operatori di confronto in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- comparison operators [Visual Basic], comparing objects
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- string comparison [Visual Basic], operators
- objects [Visual Basic], comparing
- numbers [Visual Basic], comparing
- Visual Basic code, operators
- string comparison [Visual Basic]
- numeric values [Visual Basic], comparing
- comparison operators [Visual Basic], comparing numeric values
- operators [Visual Basic], comparison
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
ms.openlocfilehash: cd7ee90e749be76012cf7143787bc6f1d096da03
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969375"
---
# <a name="comparison-operators-in-visual-basic"></a>Operatori di confronto in Visual Basic
Questi operatori confrontano due espressioni e restituire un `Boolean` valore che rappresenta la relazione tra i relativi valori. Sono disponibili gli operatori per il confronto di valori numerici, gli operatori di confronto di stringhe e gli operatori di confronto di oggetti. Di seguito vengono esaminati tutti i tre tipi di operatori.  
  
## <a name="comparing-numeric-values"></a>Confronto di valori numerici  
 Visual Basic consente di confrontare valori numerici usando gli operatori di confronto numerici sei. Ogni operatore accetta come operandi due espressioni che restituiscono valori numerici. Nella tabella seguente vengono elencati gli operatori e vengono illustrati esempi di ognuno.  
  
|Operatore|Condizione verificata|Esempi|  
|--------------|----------------------|--------------|  
|`=` (Uguaglianza)|È il valore della prima espressione è uguale al valore del secondo?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>` (Disuguaglianza)|Il valore della prima espressione non è uguale al valore del secondo?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<` (Minore di)|È il valore della prima espressione minore del valore del secondo?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>` (Maggiore di)|È maggiore del valore del secondo il valore della prima espressione?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=` (Minore o uguale a)|Il valore della prima espressione è minore o uguale al valore del secondo?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=` (Maggiore o uguale a)|È il valore della prima espressione maggiore o uguale a quello del secondo?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## <a name="comparing-strings"></a>Confronto di stringhe  
 Visual Basic vengono confrontate le stringhe usando il [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md) , nonché gli operatori di confronto numerico. Il `Like` operatore consente di specificare un modello. La stringa viene quindi confrontata con il modello, e se corrisponde, il risultato è `True`. In caso contrario, il risultato è `False`. Operatori numerici consentono di confrontare `String` valori in base al relativo ordine di ordinamento, come illustrato nell'esempio seguente.  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 Il risultato dell'esempio precedente è `True` perché il primo carattere nella prima stringa precede il primo carattere nella stringa del secondo. Se i primi caratteri pari, il confronto potrebbe continuare al carattere successivo in entrambe le stringhe e così via. È anche possibile testare l'uguaglianza di stringhe usando l'operatore di uguaglianza, come illustrato nell'esempio seguente.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 Se una stringa è un prefisso di un altro, ad esempio "aa" e "aaa", viene considerata la stringa di lunghezza superiore alla stringa più corta. Questa condizione è illustrata nell'esempio seguente.  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 L'ordinamento è basato su un confronto binario o un confronto di testo a seconda dell'impostazione di `Option Compare`. Per altre informazioni, vedere [istruzione Option Compare](../../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="comparing-objects"></a>Confronto tra oggetti  
 Visual Basic consente di confrontare due variabili di riferimento di oggetto con il [operatore Is](../../../../visual-basic/language-reference/operators/is-operator.md) e il [operatore IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md). È possibile usare uno di questi operatori per determinare se due variabili di riferimento si riferiscono alla stessa istanza dell'oggetto. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#65)]  
  
 Nell'esempio precedente, `x Is y` restituisca `True`, perché entrambe le variabili fanno riferimento alla stessa istanza. Si confronti questo risultato con l'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#66)]  
  
 Nell'esempio precedente, `x Is y` restituisca `False`, perché anche se le variabili fanno riferimento agli oggetti dello stesso tipo, fanno riferimento a diverse istanze di quel tipo.  
  
 Quando si vuole testare per due oggetti non sta puntando alla stessa istanza, il `IsNot` operatore consente di evitare una combinazione di grammaticalmente impropria `Not` e `Is`. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#67)]  
  
 Nell'esempio precedente, `If a IsNot b` equivale a `If Not a Is b`.  
  
### <a name="comparing-object-type"></a>Confronto tra il tipo di oggetto  
 È possibile verificare se un oggetto è di un determinato tipo con il `TypeOf`... `Is` espressione. La sintassi è la seguente:  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 Quando `typename` specifica un tipo di interfaccia, il `TypeOf`... `Is` espressione restituisce `True` se l'oggetto implementa il tipo di interfaccia. Quando `typename` è un tipo di classe, l'espressione restituisce `True` se l'oggetto è un'istanza della classe specificata o di una classe che deriva dalla classe specificata. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#68)]  
  
 Nell'esempio precedente, il `TypeOf x Is Control` espressione viene valutata `True` perché il tipo di `x` viene `Button`, che eredita da `Control`.  
  
 Per altre informazioni, vedere [operatore TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="see-also"></a>Vedere anche
- [Confronto di valori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Operatori di confronto](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Operatori](../../../../visual-basic/language-reference/operators/index.md)
- [Operatori aritmetici in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Operatori di concatenazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Operatori logici e bit per bit in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)

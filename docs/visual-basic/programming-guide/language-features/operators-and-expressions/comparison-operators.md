---
title: Operatori di confronto
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
ms.openlocfilehash: 7a93928ff95e307c64149da7ab21476ffd4fa77d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388829"
---
# <a name="comparison-operators-in-visual-basic"></a>Operatori di confronto in Visual Basic
Gli operatori di confronto confrontano due espressioni e restituiscono un `Boolean` valore che rappresenta la relazione dei rispettivi valori. Sono disponibili operatori per il confronto di valori numerici, operatori per il confronto di stringhe e operatori per il confronto di oggetti. Tutti e tre i tipi di operatori sono descritti in questo documento.  
  
## <a name="comparing-numeric-values"></a>Confronto di valori numerici  
 Visual Basic confronta i valori numerici con sei operatori di confronto numerici. Ogni operatore accetta come operandi due espressioni che restituiscono valori numerici. La tabella seguente elenca gli operatori e Mostra esempi di ciascuno di essi.  
  
|Operatore|Condizione testata|Esempi|  
|--------------|----------------------|--------------|  
|`=`Uguaglianza|Valore della prima espressione uguale al valore del secondo?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>`Disuguaglianza|Il valore della prima espressione è diverso dal valore della seconda?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<`(Minore di)|Il valore della prima espressione è minore del valore della seconda?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>`(Maggiore di)|Il valore della prima espressione è maggiore del valore del secondo?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=`(Minore o uguale a)|Il valore della prima espressione è minore o uguale al valore del secondo?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=`(Maggiore o uguale a)|Il valore della prima espressione è maggiore o uguale al valore del secondo?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## <a name="comparing-strings"></a>Confronto di stringhe  
 Visual Basic confronta le stringhe usando l' [operatore like](../../../language-reference/operators/like-operator.md) , nonché gli operatori di confronto numerici. L' `Like` operatore consente di specificare un modello. La stringa viene quindi confrontata con il modello e, se corrisponde, il risultato è `True` . In caso contrario, il risultato è `False`. Gli operatori numerici consentono di confrontare `String` i valori in base al relativo ordinamento, come illustrato nell'esempio riportato di seguito.  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 Il risultato nell'esempio precedente è `True` dato dal fatto che il primo carattere nella prima stringa Ordina prima del primo carattere nella seconda stringa. Se i primi caratteri fossero uguali, il confronto continuerà a essere il carattere successivo in entrambe le stringhe e così via. È anche possibile testare l'uguaglianza delle stringhe usando l'operatore di uguaglianza, come illustrato nell'esempio seguente.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 Se una stringa è un prefisso di un altro, ad esempio "AA" e "AAA", la stringa più lunga viene considerata maggiore della stringa più breve. Questa condizione è illustrata nell'esempio seguente.  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 L'ordinamento è basato su un confronto binario o su un confronto testuale a seconda dell'impostazione di `Option Compare` . Per altre informazioni, vedere [istruzione Option Compare](../../../language-reference/statements/option-compare-statement.md).  
  
## <a name="comparing-objects"></a>Confronto di oggetti  
 Visual Basic confronta due variabili di riferimento a oggetti con l' [operatore is](../../../language-reference/operators/is-operator.md) e l' [operatore](../../../language-reference/operators/isnot-operator.md)non. È possibile utilizzare uno di questi operatori per determinare se due variabili di riferimento fanno riferimento alla stessa istanza dell'oggetto. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#65)]  
  
 Nell'esempio precedente `x Is y` restituisce `True` , perché entrambe le variabili fanno riferimento alla stessa istanza. Confrontare questo risultato con l'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#66)]  
  
 Nell'esempio precedente, `x Is y` restituisce `False` perché, sebbene le variabili facciano riferimento a oggetti dello stesso tipo, fanno riferimento a istanze diverse di quel tipo.  
  
 Quando si desidera testare due oggetti che non puntano alla stessa istanza, l' `IsNot` operatore consente di evitare una combinazione grammaticale di `Not` e `Is` . Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#67)]  
  
 Nell'esempio precedente, `If a IsNot b` è equivalente a `If Not a Is b` .  
  
### <a name="comparing-object-type"></a>Confronto del tipo di oggetto  
 È possibile verificare se un oggetto è di un tipo particolare con l' `TypeOf` espressione.... `Is` La sintassi è la seguente:  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 Quando `typename` specifica un tipo di interfaccia, l' `TypeOf` espressione... `Is` restituisce `True` se l'oggetto implementa il tipo di interfaccia. Quando `typename` è un tipo di classe, l'espressione restituisce `True` se l'oggetto è un'istanza della classe specificata o di una classe che deriva dalla classe specificata. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#68)]  
  
 Nell'esempio precedente, l' `TypeOf x Is Control` espressione restituisce `True` perché il tipo di `x` è `Button` , che eredita da `Control` .  
  
 Per ulteriori informazioni, vedere [operatore typeof](../../../language-reference/operators/typeof-operator.md).  
  
## <a name="see-also"></a>Vedere anche

- [Confronto di valori](value-comparisons.md)
- [Operatori di confronto](../../../language-reference/operators/comparison-operators.md)
- [Operatori](../../../language-reference/operators/index.md)
- [Operatori aritmetici in Visual Basic](arithmetic-operators.md)
- [Operatori di concatenazione in Visual Basic](concatenation-operators.md)
- [Operatori logici e bit per bit in Visual Basic](logical-and-bitwise-operators.md)

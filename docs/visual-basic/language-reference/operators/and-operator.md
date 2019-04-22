---
title: Operatore And (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
ms.openlocfilehash: 7e25f25677fa684427bdaf00cea73916ffbad655
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818618"
---
# <a name="and-operator-visual-basic"></a>Operatore And (Visual Basic)
Esegue una congiunzione logica su due `Boolean` espressioni oppure una congiunzione bit per bit su due espressioni numeriche.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi `Boolean` o espressione numerica. Confronto di valori booleani `result` è la congiunzione logica di due `Boolean` valori. Operazioni bit per bit, `result` è un valore numerico che rappresenta la combinazione bit per bit di due schemi di bit numerici.  
  
 `expression1`  
 Obbligatorio. Qualsiasi `Boolean` o espressione numerica.  
  
 `expression2`  
 Obbligatorio. Qualsiasi `Boolean` o espressione numerica.  
  
## <a name="remarks"></a>Note  
 Confronto di valori booleani `result` viene `True` se e solo se entrambi `expression1` e `expression2` restituiscono `True`. La tabella seguente illustra come `result` è determinata.  
  
|Se `expression1` è|E `expression2` è|Il valore di `result` è|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  In un confronto booleano, il `And` operatore valuta sempre entrambe le espressioni, che potrebbe includere effettua le chiamate di procedura. Il [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) esegue *corto circuito*, che significa che se `expression1` viene `False`, quindi `expression2` non viene valutato.  
  
 Quando applicata a valori numerici, il `And` operatore esegue un confronto bit per bit dei bit di due espressioni numeriche e imposta il bit nel corrispondente `result` in base alla tabella riportata di seguito.  
  
|Se in bit in `expression1` è|E il bit in `expression2` è|Il bit nel `result` è|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
>  Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto a altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit devono essere racchiuso tra parentesi per garantire risultati accurati.  
  
## <a name="data-types"></a>Tipi di dati  
 Se gli operandi sono costituiti da uno `Boolean` espressione e un'espressione numerica, Visual Basic converte il `Boolean` espressione in un valore numerico (-1 per `True` e 0 per `False`) ed esegue un'operazione OR bit per bit.  
  
 Per un confronto booleano, il tipo di dati del risultato è `Boolean`. Per un confronto bit per bit, il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`. Vedere la tabella "Relazionale e confronti bit per bit" nella [Data Types of operatore Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
> [!NOTE]
>  Il `And` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `And` operatore per eseguire una congiunzione logica su due espressioni. Il risultato è un `Boolean` valore che indica se entrambe le espressioni sono `True`.  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 Nell'esempio precedente produce i risultati dei `True` e `False`, rispettivamente.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `And` operatore per eseguire la congiunzione logica tra i singoli bit di due espressioni numeriche. Il bit nel risultato viene impostato se i bit corrispondenti negli operandi sono entrambe impostate su 1.  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 Nell'esempio precedente produce i risultati di 8, 2 e 0, rispettivamente.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici e bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatore AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)

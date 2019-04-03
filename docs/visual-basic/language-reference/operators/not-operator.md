---
title: Operatore Not (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: 4e54fdca9123ad5595eb9a8c5e2ac5bc303a8f6a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824213"
---
# <a name="not-operator-visual-basic"></a>Operatore Not (Visual Basic)
Esegue una negazione logica su un `Boolean` espressione oppure una negazione bit per bit di un'espressione numerica.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi `Boolean` o espressione numerica.  
  
 `expression`  
 Obbligatorio. Qualsiasi `Boolean` o espressione numerica.  
  
## <a name="remarks"></a>Note  
 Per la `Boolean` espressioni, la tabella seguente illustra come `result` è determinata.  
  
|Se `expression` è|Il valore di `result` è|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 Per le espressioni numeriche, il `Not` operatore inverte i valori di bit di qualsiasi espressione numerica e imposta il bit nel corrispondente `result` in base alla tabella riportata di seguito.  
  
|Se in bit in `expression` è|Il bit nel `result` è|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
>  Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto a altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit devono essere racchiusi tra parentesi per garantire un'esecuzione accurata.  
  
## <a name="data-types"></a>Tipi di dati  
 Per una negazione booleana, il tipo di dati del risultato è `Boolean`. Per una negazione bit per bit, il tipo di dati del risultato è uguale a quello di `expression`. Tuttavia, se espressione è `Decimal`, il risultato è `Long`.  
  
## <a name="overloading"></a>Overload  
 Il `Not` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando l'operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Not` operatore per eseguire la negazione logica su un `Boolean` espressione. Il risultato è un `Boolean` valore che rappresenta l'opposto del valore dell'espressione.  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 Nell'esempio precedente produce i risultati dei `False` e `True`, rispettivamente.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Not` operatore per eseguire la negazione logica dei singoli bit di un'espressione numerica. Il bit nel risultato viene impostato per l'operazione inversa del bit corrispondente nel modello dell'operando, tra cui il bit di segno.  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 Nell'esempio precedente produce i risultati di – 11, –9 e –7, rispettivamente.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici e bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)

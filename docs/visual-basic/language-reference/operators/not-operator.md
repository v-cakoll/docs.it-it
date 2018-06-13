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
ms.openlocfilehash: 332cee57c8d25d7f51737e01e70ba515d50bd6e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604393"
---
# <a name="not-operator-visual-basic"></a>Operatore Not (Visual Basic)
Esegue una negazione logica su un `Boolean` espressione oppure una negazione bit per bit su un'espressione numerica.  
  
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
 Per `Boolean` espressioni, la tabella seguente illustra come `result` è determinata.  
  
|Se `expression` è|Il valore di `result` è|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 Le espressioni numeriche, di `Not` operatore inverte i valori di bit di qualsiasi espressione numerica e imposta il bit nel corrispondente `result` in base alla tabella seguente.  
  
|Se in bit in `expression` è|Il bit `result` è|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
>  Poiché gli operatori logici e bit per bit hanno una precedenza inferiore a altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit devono essere racchiuse tra parentesi per garantire un'esecuzione accurata.  
  
## <a name="data-types"></a>Tipi di dati  
 Per una negazione booleana, il tipo di dati del risultato è `Boolean`. Per una negazione bit per bit, il tipo di dati del risultato è uguale a quello di `expression`. Tuttavia, se l'espressione è `Decimal`, il risultato è `Long`.  
  
## <a name="overloading"></a>Overload  
 Il `Not` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando l'operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Not` operatore per eseguire la negazione logica su un `Boolean` espressione. Il risultato è un `Boolean` valore che rappresenta l'opposto del valore dell'espressione.  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 Nell'esempio precedente produce i risultati di `False` e `True`, rispettivamente.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Not` operatore per eseguire la negazione logica dei singoli bit di un'espressione numerica. Il bit nel risultato viene impostato per l'operazione inversa del bit corrispondente nel modello dell'operando, compreso il bit di segno.  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 Nell'esempio precedente produce risultati di – 11 – 9 e –7, rispettivamente.  
  
## <a name="see-also"></a>Vedere anche  
 [Operatori logici e bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)

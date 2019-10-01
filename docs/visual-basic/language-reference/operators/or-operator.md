---
title: Operatore Or (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
ms.openlocfilehash: 03decb4ad32e8ff2c03e3b64a272bce779282973
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701230"
---
# <a name="or-operator-visual-basic"></a>Operatore Or (Visual Basic)
Esegue una disgiunzione logica di due espressioni `Boolean` oppure una disgiunzione bit per bit di due espressioni numeriche.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Espressione `Boolean` qualsiasi o numerica. Per il confronto `Boolean`, `result` è la disgiunzione logica inclusiva di due valori `Boolean`. Per le operazioni bit per bit, `result` è un valore numerico che rappresenta la disgiunzione bit per bit inclusiva di due modelli di bit numerici.  
  
 `expression1`  
 Obbligatorio. Espressione `Boolean` qualsiasi o numerica.  
  
 `expression2`  
 Obbligatorio. Espressione `Boolean` qualsiasi o numerica.  
  
## <a name="remarks"></a>Note  
 Per il confronto `Boolean`, `result` è `False` se e solo se sia `expression1` che `expression2` restituiscono `False`. Nella tabella seguente viene illustrato il modo in cui viene determinato `result`.  
  
|Se `expression1` è|E `expression2` è|Il valore di `result` è|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> In un confronto `Boolean`, l'operatore `Or` valuta sempre entrambe le espressioni, che possono includere l'esecuzione di chiamate di routine. L' [operatore OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md) esegue un *corto circuito*, il che significa che se `expression1` è `True`, `expression2` non viene valutato.  
  
 Per le operazioni bit per bit, l'operatore `Or` esegue un confronto bit per bit dei bit posizionati in modo identico in due espressioni numeriche e imposta il bit corrispondente in `result` in base alla tabella seguente.  
  
|Se bit in `expression1` è|E bit in `expression2` è|Il bit in `result` è|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
> Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto ad altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit deve essere racchiusa tra parentesi per garantire un'esecuzione accurata.  
  
## <a name="data-types"></a>Tipi di dati  
 Se gli operandi sono costituiti da un'espressione `Boolean` e da un'espressione numerica, Visual Basic converte l'espressione `Boolean` in un valore numerico (-1 per `True` e 0 per `False`) ed esegue un'operazione bit per bit.  
  
 Per un confronto `Boolean`, il tipo di dati del risultato è `Boolean`. Per un confronto bit per bit, il tipo di dati result è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`. Vedere la tabella "confronto relazionale e bit per bit" in [tipi di dati dei risultati dell'operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Overload  
 L'operatore `Or` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `Or` per eseguire una disgiunzione logica inclusiva su due espressioni. Il risultato è un valore `Boolean` che indica se una delle due espressioni è `True`.  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 Nell'esempio precedente vengono prodotti rispettivamente i risultati `True`, `True` e `False`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `Or` per eseguire la disgiunzione logica inclusiva sui singoli bit di due espressioni numeriche. Il bit nel modello di risultato viene impostato se uno dei bit corrispondenti negli operandi è impostato su 1.  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 Nell'esempio precedente vengono prodotti rispettivamente i risultati 10, 14 e 14.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici/bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatore OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)

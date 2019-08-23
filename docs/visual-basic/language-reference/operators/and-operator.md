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
ms.openlocfilehash: a1802d3a7018b1b6190ff5601eba055e16e62371
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913163"
---
# <a name="and-operator-visual-basic"></a>Operatore And (Visual Basic)
Esegue una congiunzione logica di `Boolean` due espressioni o una congiunzione bit per bit di due espressioni numeriche.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Richiesto. Espressione `Boolean` qualsiasi o numerica. Per il confronto booleano, `result` è la congiunzione logica di due `Boolean` valori. Per le operazioni bit `result` per bit, è un valore numerico che rappresenta la combinazione bit per bit di due schemi di bit numerici.  
  
 `expression1`  
 Richiesto. Espressione `Boolean` qualsiasi o numerica.  
  
 `expression2`  
 Richiesto. Espressione `Boolean` qualsiasi o numerica.  
  
## <a name="remarks"></a>Note  
 Per il confronto booleano `True` , `result` è `expression1` se e solo `True`se `expression2` e restituiscono. Nella tabella seguente viene illustrato come `result` determinare.  
  
|Se `expression1` è|E `expression2` è|Il valore di `result` è|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> In un confronto booleano, `And` l'operatore valuta sempre entrambe le espressioni, che possono includere l'esecuzione di chiamate di routine. L' [operatore AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) esegue un *corto circuito*, il che significa che se `expression1` è `False`, `expression2` non viene valutato.  
  
 Quando viene applicato a valori numerici `And` , l'operatore esegue un confronto bit per bit dei bit posizionati in modo identico in due espressioni `result` numeriche e imposta il bit corrispondente in in base alla tabella seguente.  
  
|Se il bit `expression1` in è|E bit in `expression2` è|Il bit in `result` è|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
> Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto ad altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit deve essere racchiusa tra parentesi per garantire risultati accurati.  
  
## <a name="data-types"></a>Tipi di dati  
 Se gli operandi sono costituiti da `Boolean` un'espressione e da un'espressione numerica, `Boolean` Visual Basic converte l'espressione in un valore numerico ( `True` -1 per `False`e 0 per) ed esegue un'operazione bit per bit.  
  
 Per un confronto booleano, il tipo di dati del risultato `Boolean`è. Per un confronto bit per bit, il tipo di dati result è un tipo numerico appropriato per i `expression1` tipi `expression2`di dati di e. Vedere la tabella "confronto relazionale e bit per bit" in [tipi di dati dei risultati dell'operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
> [!NOTE]
> L' `And` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato `And` l'operatore per eseguire una congiunzione logica di due espressioni. Il risultato è un `Boolean` valore che indica se entrambe le espressioni sono. `True`  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 Nell'esempio precedente vengono restituiti i `True` risultati `False`di e, rispettivamente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato `And` l'operatore per eseguire congiunzioni logiche sui singoli bit di due espressioni numeriche. Il bit nel modello di risultato viene impostato se i bit corrispondenti negli operandi sono entrambi impostati su 1.  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 Nell'esempio precedente vengono prodotti rispettivamente i risultati 8, 2 e 0.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici/bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatore AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)

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
ms.openlocfilehash: bd6ebbf5f53a7cf187b5d8ce7630080d44d46df2
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591623"
---
# <a name="and-operator-visual-basic"></a>Operatore And (Visual Basic)
Esegue una congiunzione logica di due espressioni `Boolean` oppure una congiunzione bit per bit di due espressioni numeriche.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Espressione `Boolean` qualsiasi o numerica. Per il confronto booleano, `result` è la congiunzione logica di due valori `Boolean`. Per le operazioni bit per bit, `result` è un valore numerico che rappresenta la combinazione bit per bit di due modelli di bit numerici.  
  
 `expression1`  
 Obbligatorio. Espressione `Boolean` qualsiasi o numerica.  
  
 `expression2`  
 Obbligatorio. Espressione `Boolean` qualsiasi o numerica.  
  
## <a name="remarks"></a>Note  
 Per il confronto booleano, `result` è `True` se e solo se `expression1` e `expression2` restituiscono `True`. Nella tabella seguente viene illustrato il modo in cui viene determinato `result`.  
  
|Se `expression1` è|E `expression2` è|Il valore di `result` è|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> In un confronto booleano, l'operatore `And` valuta sempre entrambe le espressioni, che possono includere l'esecuzione di chiamate di routine. L' [operatore AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) esegue un *corto circuito*, il che significa che se `expression1` è `False`, `expression2` non viene valutato.  
  
 Quando viene applicato a valori numerici, l'operatore `And` esegue un confronto bit per bit di bit posizionati in modo identico in due espressioni numeriche e imposta il bit corrispondente in `result` in base alla tabella seguente.  
  
|Se bit in `expression1` è|E bit in `expression2` è|Il bit in `result` è|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
> Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto ad altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit deve essere racchiusa tra parentesi per garantire risultati accurati.  
  
## <a name="data-types"></a>Tipi di dati  
 Se gli operandi sono costituiti da un'espressione `Boolean` e da un'espressione numerica, Visual Basic converte l'espressione `Boolean` in un valore numerico (-1 per `True` e 0 per `False`) ed esegue un'operazione bit per bit.  
  
 Per un confronto booleano, il tipo di dati del risultato è `Boolean`. Per un confronto bit per bit, il tipo di dati result è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`. Vedere la tabella "confronto relazionale e bit per bit" in [tipi di dati dei risultati dell'operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
> [!NOTE]
> L'operatore `And` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `And` per eseguire una congiunzione logica di due espressioni. Il risultato è un valore `Boolean` che indica se entrambe le espressioni sono `True`.  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 Nell'esempio precedente vengono prodotti rispettivamente i risultati `True` e `False`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `And` per eseguire congiunzioni logiche sui singoli bit di due espressioni numeriche. Il bit nel modello di risultato viene impostato se i bit corrispondenti negli operandi sono entrambi impostati su 1.  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 Nell'esempio precedente vengono prodotti rispettivamente i risultati 8, 2 e 0.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici/bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatore AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)

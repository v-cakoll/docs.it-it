---
title: Operatore And
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
ms.openlocfilehash: c2b135d27e14816c011a4f70793543aa835d960a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371947"
---
# <a name="and-operator-visual-basic"></a>Operatore And (Visual Basic)
Esegue una congiunzione logica di due `Boolean` espressioni o una congiunzione bit per bit di due espressioni numeriche.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi espressione `Boolean` o numerica. Per il confronto booleano, `result` è la congiunzione logica di due `Boolean` valori. Per le operazioni bit per bit, `result` è un valore numerico che rappresenta la combinazione bit per bit di due schemi di bit numerici.  
  
 `expression1`  
 Obbligatorio. Qualsiasi espressione `Boolean` o numerica.  
  
 `expression2`  
 Obbligatorio. Qualsiasi espressione `Boolean` o numerica.  
  
## <a name="remarks"></a>Commenti  
 Per il confronto booleano, `result` è `True` se e solo se `expression1` e `expression2` restituiscono `True` . Nella tabella seguente viene illustrato come `result` determinare.  
  
|Se `expression1` è |E `expression2` è|Il valore di `result` è|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> In un confronto booleano, l' `And` operatore valuta sempre entrambe le espressioni, che possono includere l'esecuzione di chiamate di routine. L' [operatore AndAlso](andalso-operator.md) esegue un *corto circuito*, il che significa che se `expression1` è `False` , `expression2` non viene valutato.  
  
 Quando viene applicato a valori numerici, l' `And` operatore esegue un confronto bit per bit dei bit posizionati in modo identico in due espressioni numeriche e imposta il bit corrispondente in in `result` base alla tabella seguente.  
  
|Se il bit in `expression1` è|E bit in `expression2` è|Il bit in `result` è|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
> Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto ad altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit deve essere racchiusa tra parentesi per garantire risultati accurati.  
  
## <a name="data-types"></a>Tipi di dati  
 Se gli operandi sono costituiti da un'espressione e da un' `Boolean` espressione numerica, Visual Basic converte l' `Boolean` espressione in un valore numerico (-1 per `True` e 0 per `False` ) ed esegue un'operazione bit per bit.  
  
 Per un confronto booleano, il tipo di dati del risultato è `Boolean` . Per un confronto bit per bit, il tipo di dati result è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2` . Vedere la tabella "confronto relazionale e bit per bit" in [tipi di dati dei risultati dell'operatore](data-types-of-operator-results.md).  
  
> [!NOTE]
> L' `And` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato l' `And` operatore per eseguire una congiunzione logica di due espressioni. Il risultato è un `Boolean` valore che indica se entrambe le espressioni sono `True` .  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 Nell'esempio precedente vengono restituiti i risultati di `True` e `False` , rispettivamente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l' `And` operatore per eseguire congiunzioni logiche sui singoli bit di due espressioni numeriche. Il bit nel modello di risultato viene impostato se i bit corrispondenti negli operandi sono entrambi impostati su 1.  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 Nell'esempio precedente vengono prodotti rispettivamente i risultati 8, 2 e 0.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici e bit per bit (Visual Basic)](logical-bitwise-operators.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Operatore AndAlso](andalso-operator.md)
- [Operatori logici e bit per bit in Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)

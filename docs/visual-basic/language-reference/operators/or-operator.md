---
title: Operatore Or
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
ms.openlocfilehash: 657b2a473b23789a8ba25fbd11c6b83538fa7803
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401420"
---
# <a name="or-operator-visual-basic"></a>Operatore Or (Visual Basic)
Esegue una disgiunzione logica di due `Boolean` espressioni o una disgiunzione bit per bit di due espressioni numeriche.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi espressione `Boolean` o numerica. Per `Boolean` il confronto, `result` è la disgiunzione logica inclusiva di due `Boolean` valori. Per le operazioni bit per bit, `result` è un valore numerico che rappresenta la disgiunzione bit per bit inclusiva di due modelli di bit numerici.  
  
 `expression1`  
 Obbligatorio. Qualsiasi espressione `Boolean` o numerica.  
  
 `expression2`  
 Obbligatorio. Qualsiasi espressione `Boolean` o numerica.  
  
## <a name="remarks"></a>Commenti  
 Per il `Boolean` confronto, `result` è `False` se e solo se `expression1` e `expression2` restituiscono `False` . Nella tabella seguente viene illustrato come `result` determinare.  
  
|Se `expression1` è |E `expression2` è|Il valore di `result` è|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> In un `Boolean` confronto, l' `Or` operatore valuta sempre entrambe le espressioni, che possono includere l'esecuzione di chiamate di routine. L' [operatore OrElse](orelse-operator.md) esegue un *corto circuito*, il che significa che se `expression1` è `True` , `expression2` non viene valutato.  
  
 Per le operazioni bit per bit, l' `Or` operatore esegue un confronto bit per bit dei bit posizionati in modo identico in due espressioni numeriche e imposta il bit corrispondente in in `result` base alla tabella seguente.  
  
|Se il bit in `expression1` è|E bit in `expression2` è|Il bit in `result` è|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
> Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto ad altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit deve essere racchiusa tra parentesi per garantire un'esecuzione accurata.  
  
## <a name="data-types"></a>Tipi di dati  
 Se gli operandi sono costituiti da un'espressione e da un' `Boolean` espressione numerica, Visual Basic converte l' `Boolean` espressione in un valore numerico (-1 per `True` e 0 per `False` ) ed esegue un'operazione bit per bit.  
  
 Per un `Boolean` confronto, il tipo di dati del risultato è `Boolean` . Per un confronto bit per bit, il tipo di dati result è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2` . Vedere la tabella "confronto relazionale e bit per bit" in [tipi di dati dei risultati dell'operatore](data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Overload  
 L' `Or` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l' `Or` operatore per eseguire una disgiunzione logica inclusiva su due espressioni. Il risultato è un `Boolean` valore che indica se una delle due espressioni è `True` .  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 Nell'esempio precedente vengono prodotti rispettivamente i risultati di `True` , `True` e `False` .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l' `Or` operatore per eseguire la disgiunzione logica inclusiva sui singoli bit di due espressioni numeriche. Il bit nel modello di risultato viene impostato se uno dei bit corrispondenti negli operandi è impostato su 1.  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 Nell'esempio precedente vengono prodotti rispettivamente i risultati 10, 14 e 14.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici e bit per bit (Visual Basic)](logical-bitwise-operators.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Operatore OrElse](orelse-operator.md)
- [Operatori logici e bit per bit in Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)

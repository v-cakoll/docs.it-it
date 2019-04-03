---
title: Operatore Xor (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
ms.openlocfilehash: 0cba3a995fb1ab774c8a5308e58f0b6905fc23f3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827068"
---
# <a name="xor-operator-visual-basic"></a>Operatore Xor (Visual Basic)
Esegue un'esclusione logica su due `Boolean` espressioni, oppure un'esclusione bit per bit su due espressioni numeriche.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi `Boolean` o variabile numerica. Confronto di valori booleani `result` è l'esclusione logica (disgiunzione logica esclusiva) di due `Boolean` valori. Operazioni bit per bit, `result` è un valore numerico che rappresenta l'esclusione bit per bit (disgiunzione bit per bit esclusiva) di due schemi di bit numerici.  
  
 `expression1`  
 Obbligatorio. Qualsiasi `Boolean` o espressione numerica.  
  
 `expression2`  
 Obbligatorio. Qualsiasi `Boolean` o espressione numerica.  
  
## <a name="remarks"></a>Note  
 Confronto di valori booleani `result` viene `True` se e solo se esattamente uno dei `expression1` e `expression2` restituisce `True`. Vale a dire, se e solo se `expression1` e `expression2` valutare opposti `Boolean` valori. La tabella seguente illustra come `result` è determinata.  
  
|Se `expression1` è|E `expression2` è|Il valore di `result` è|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  In un confronto booleano, il `Xor` operatore valuta sempre entrambe le espressioni, che potrebbe includere effettua le chiamate di procedura. Non vi è alcun equivalente di corto circuito a `Xor`, perché il risultato dipende sempre da entrambi gli operandi. Per la *corto circuito* operatori logici, vedere [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) e [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
 Operazioni bit per bit, il `Xor` operatore esegue un confronto bit per bit dei bit di due espressioni numeriche e imposta il bit nel corrispondente `result` in base alla tabella riportata di seguito.  
  
|Se in bit in `expression1` è|E il bit in `expression2` è|Il bit nel `result` è|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|0|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto a altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit devono essere racchiusi tra parentesi per garantire un'esecuzione accurata.  
  
 Ad esempio, 5 `Xor` 3 è 6. Per visualizzare il motivo per cui si tratta comunque, convertire in rappresentazioni binarie, 101 e 011 5 e 3. Usare quindi la tabella precedente per determinare che Xor 101 011 è 110, ovvero la rappresentazione binaria del numero decimale 6.  
  
## <a name="data-types"></a>Tipi di dati  
 Se gli operandi sono costituiti da uno `Boolean` espressione e un'espressione numerica, Visual Basic converte il `Boolean` espressione in un valore numerico (-1 per `True` e 0 per `False`) ed esegue un'operazione OR bit per bit.  
  
 Per un `Boolean` è il tipo di dati del risultato del confronto, `Boolean`. Per un confronto bit per bit, il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`. Vedere la tabella "Relazionale e confronti bit per bit" nella [Data Types of operatore Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Overload  
 Il `Xor` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore su una classe o struttura, assicurarsi che comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Xor` operatore per eseguire l'esclusione logica (disgiunzione logica esclusiva) di due espressioni. Il risultato è un `Boolean` valore che indica se esattamente una delle espressioni è `True`.  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 L'esempio precedente produce i risultati dei `False`, `True`, e `False`, rispettivamente.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Xor` operatore per eseguire l'esclusione logica (disgiunzione logica esclusiva) sui singoli bit di due espressioni numeriche. Il bit nel risultato viene impostato se esattamente uno dei bit corrispondenti in operandi è impostato su 1.  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 L'esempio precedente produce i risultati di 2, 12 e 14, rispettivamente.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici e bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)

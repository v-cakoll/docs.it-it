---
title: Operatore Or (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4c9429eb2bdeb86bfa73786433231fdc22a230d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="or-operator-visual-basic"></a>Operatore Or (Visual Basic)
Esegue una disgiunzione logica tra due `Boolean` espressioni oppure una disgiunzione bit per bit tra due espressioni numeriche.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi `Boolean` o espressione numerica. Per `Boolean` confronto, `result` è la disgiunzione logica di due `Boolean` valori. Operazioni bit per bit, `result` è un valore numerico che rappresenta la disgiunzione bit per bit di due schemi di bit numerici.  
  
 `expression1`  
 Obbligatorio. Qualsiasi `Boolean` o espressione numerica.  
  
 `expression2`  
 Obbligatorio. Qualsiasi `Boolean` o espressione numerica.  
  
## <a name="remarks"></a>Note  
 Per `Boolean` confronto, `result` è `False` se e solo se entrambi `expression1` e `expression2` restituiscono `False`. Nella tabella seguente viene illustrato come `result` è determinata.  
  
|Se `expression1` è|E `expression2` è|Il valore di `result` è|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  In un `Boolean` confronto, il `Or` operatore valuta sempre entrambe le espressioni, che potrebbe includere chiamate di procedura. Il [operatore OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md) esegue *corto circuito*, che significa che se `expression1` è `True`, quindi `expression2` non viene valutato.  
  
 Operazioni bit per bit, il `Or` operatore esegue un confronto bit per bit di bit in due espressioni numeriche e imposta il bit nel corrispondente `result` in base alla tabella seguente.  
  
|Se in bit in `expression1` è|E il bit in `expression2` è|Il bit `result` è|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Poiché gli operatori logici e bit per bit hanno una precedenza inferiore a altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit devono essere racchiuse tra parentesi per garantire un'esecuzione accurata.  
  
## <a name="data-types"></a>Riepilogo dei tipi di dati  
 Se gli operandi sono costituiti da uno `Boolean` espressione e un'espressione numerica, Visual Basic converte il `Boolean` espressione in un valore numerico (– 1 per `True` e 0 per `False`) ed esegue un'operazione bit per bit.  
  
 Per un `Boolean` è il tipo di dati del risultato del confronto, `Boolean`. Per un confronto bit per bit, il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`. Vedere la tabella "Confronti relazionali e bit per bit" in [tipi di dati di risultati di operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Overload  
 Il `Or` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Or` operatore per eseguire una disgiunzione logica inclusiva su due espressioni. Il risultato è un `Boolean` valore che rappresenta se una delle due espressioni è `True`.  
  
 [!code-vb[VbVbalrOperators#35](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_1.vb)]  
  
 Nell'esempio precedente produce i risultati di `True`, `True`, e `False`, rispettivamente.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Or` operatore per eseguire la disgiunzione logica inclusiva su singoli bit di due espressioni numeriche. Il bit nel risultato viene impostato se uno dei bit corrispondenti negli operandi è impostato su 1.  
  
 [!code-vb[VbVbalrOperators#36](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_2.vb)]  
  
 Nell'esempio precedente produce risultati di 10, 14 e 14, rispettivamente.  
  
## <a name="see-also"></a>Vedere anche  
 [Operatori logici e bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatore OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md)  
 [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)

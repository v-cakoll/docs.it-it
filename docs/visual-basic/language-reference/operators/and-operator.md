---
title: Operatore And (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.And
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83e1f9df11152f88ef0db24a794026d6f5888a2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="and-operator-visual-basic"></a>Operatore And (Visual Basic)
Esegue una congiunzione logica su due `Boolean` espressioni oppure una congiunzione bit per bit su due espressioni numeriche.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi `Boolean` o espressione numerica. Confronto di valori booleani, `result` rappresenta la congiunzione logica di due `Boolean` valori. Operazioni bit per bit, `result` è un valore numerico che rappresenta la congiunzione bit per bit di due schemi di bit numerici.  
  
 `expression1`  
 Obbligatorio. Qualsiasi `Boolean` o espressione numerica.  
  
 `expression2`  
 Obbligatorio. Qualsiasi `Boolean` o espressione numerica.  
  
## <a name="remarks"></a>Note  
 Confronto di valori booleani, `result` è `True` se e solo se entrambi `expression1` e `expression2` restituiscono `True`. Nella tabella seguente viene illustrato come `result` è determinata.  
  
|Se `expression1` è|E `expression2` è|Il valore di `result` è|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  In un confronto booleano, il `And` operatore valuta sempre entrambe le espressioni, che potrebbe includere chiamate di procedura. Il [Operatore AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) esegue *corto circuito*, che significa che se `expression1` è `False`, quindi `expression2` non viene valutato.  
  
 Quando applicato a valori numerici, di `And` operatore esegue un confronto bit per bit di bit in due espressioni numeriche e imposta il bit nel corrispondente `result` in base alla tabella seguente.  
  
|Se in bit in `expression1` è|E il bit in `expression2` è|Il bit `result` è|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
>  Poiché gli operatori logici e bit per bit hanno una precedenza inferiore a altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit devono essere racchiuse tra parentesi per garantire risultati accurati.  
  
## <a name="data-types"></a>Riepilogo dei tipi di dati  
 Se gli operandi sono costituiti da uno `Boolean` espressione e un'espressione numerica, Visual Basic converte il `Boolean` espressione in un valore numerico (– 1 per `True` e 0 per `False`) ed esegue un'operazione bit per bit.  
  
 Per un confronto booleano, il tipo di dati del risultato è `Boolean`. Per un confronto bit per bit, il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`. Vedere la tabella "Confronti relazionali e bit per bit" in [tipi di dati di risultati di operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
> [!NOTE]
>  Il `And` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `And` operatore per eseguire una congiunzione logica tra due espressioni. Il risultato è un `Boolean` valore che indica se entrambe le espressioni sono `True`.  
  
 [!code-vb[VbVbalrOperators#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_1.vb)]  
  
 Nell'esempio precedente produce i risultati di `True` e `False`, rispettivamente.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `And` operatore per eseguire la congiunzione logica tra i singoli bit di due espressioni numeriche. Il bit nel risultato viene impostato se i bit corrispondenti negli operandi sono entrambe impostate su 1.  
  
 [!code-vb[VbVbalrOperators#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_2.vb)]  
  
 Nell'esempio precedente produce risultati di 8, 2 e 0, rispettivamente.  
  
## <a name="see-also"></a>Vedere anche  
 [Operatori logici e bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatore AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md)  
 [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)

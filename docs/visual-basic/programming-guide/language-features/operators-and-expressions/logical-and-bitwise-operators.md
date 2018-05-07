---
title: Operatori logici e bit per bit in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- operators [Visual Basic], logical
- AndAlso operator [Visual Basic]
- Not operator [Visual Basic], Boolean expressions
- Xor operator [Visual Basic], Boolean expressions
- And operator [Visual Basic], logical operators
- logical operators [Visual Basic]
- expressions [Visual Basic], Boolean
- Or operator [Visual Basic], logical operators
- Visual Basic code, operators
- short-circuiting [Visual Basic], logical operators
- logical operators [Visual Basic], short-circuiting
- Visual Basic code, expressions
- logical operators [Visual Basic], binary
- OrElse operator [Visual Basic]
- logical operators [Visual Basic], unary
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
ms.openlocfilehash: 371d28629b39fb2808ca018ea69da3306a31f50c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Operatori logici e bit per bit in Visual Basic
Gli operatori logici confrontano `Boolean` espressioni e restituire un `Boolean` risultato. Il `And`, `Or`, `AndAlso`, `OrElse`, e `Xor` gli operatori sono *binario* perché accettano due operandi, mentre il `Not` operatore *unario* poiché accetta un singolo operando. Alcuni di questi operatori possono inoltre eseguire operazioni logiche bit per bit su valori integrali.  
  
## <a name="unary-logical-operator"></a>Operatore logico unario  
 Il [operatore Not](../../../../visual-basic/language-reference/operators/not-operator.md) esegue logico *negazione* su un `Boolean` espressione. Restituisce l'opposto logico del relativo operando. Se l'espressione restituisce `True`, quindi `Not` restituisce `False`; se l'espressione restituisce `False`, quindi `Not` restituisce `True`. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#77](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_1.vb)]  
  
## <a name="binary-logical-operators"></a>Operatori logici binari  
 Il [operatore e](../../../../visual-basic/language-reference/operators/and-operator.md) esegue logico *insieme* su due `Boolean` espressioni. Se entrambe le espressioni restituiscono `True`, quindi `And` restituisce `True`. Se almeno una delle espressioni restituisce `False`, quindi `And` restituisce `False`.  
  
 Il [operatore o](../../../../visual-basic/language-reference/operators/or-operator.md) esegue logico *disgiunzione* o *inclusione* su due `Boolean` espressioni. Se un'espressione restituisce `True`, o entrambi restituiscono `True`, quindi `Or` restituisce `True`. Se nessuna delle due espressioni restituisce `True`, `Or` restituisce `False`.  
  
 Il [operatore Xor](../../../../visual-basic/language-reference/operators/xor-operator.md) esegue logico *esclusione* su due `Boolean` espressioni. Se esattamente un'espressione viene valutata `True`, ma non ad entrambi, `Xor` restituisce `True`. Se entrambe le espressioni restituiscono `True` o entrambi restituiscono `False`, `Xor` restituisce `False`.  
  
 Nell'esempio seguente viene illustrato il `And`, `Or`, e `Xor` operatori.  
  
 [!code-vb[VbVbalrOperators#78](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_2.vb)]  
  
## <a name="short-circuiting-logical-operations"></a>Corto circuito di operazioni logiche  
 Il [AndAlso (operatore)](../../../../visual-basic/language-reference/operators/andalso-operator.md) è molto simile al `And` operatore, in quanto esegue inoltre congiunzione logica su due `Boolean` espressioni. La differenza principale tra i due è che `AndAlso` presenta *corto circuito* comportamento. Se la prima espressione in un `AndAlso` espressione viene valutata `False`, quindi la seconda espressione non viene valutata in quanto non può alterare il risultato finale e `AndAlso` restituisce `False`.  
  
 Analogamente, il [operatore OrElse](../../../../visual-basic/language-reference/operators/orelse-operator.md) esegue una congiunzione logica su due `Boolean` espressioni. Se la prima espressione in un `OrElse` espressione viene valutata `True`, quindi la seconda espressione non viene valutata in quanto non può alterare il risultato finale e `OrElse` restituisce `True`.  
  
### <a name="short-circuiting-trade-offs"></a>Short-circuit  
 Corto circuito può migliorare le prestazioni non valutando un'espressione che non è possibile modificare il risultato dell'operazione logica. Tuttavia, se tale espressione esegue operazioni aggiuntive, corto circuito ignora tali azioni. Ad esempio, se l'espressione include una chiamata a un `Function` procedure, che procedure non viene chiamata se l'espressione è esegue un corto circuito, e qualsiasi altro codice contenuto nel `Function` non viene eseguito. Pertanto, la funzione potrebbe essere eseguita solo occasionalmente e potrebbe non essere completata correttamente. La logica di programma potrebbe dipendere dal codice nel `Function`.  
  
 Nell'esempio seguente viene illustrata la differenza tra `And`, `Or`e le relative controparti di corto circuite.  
  
 [!code-vb[VbVbalrOperators#81](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_3.vb)]  
  
 [!code-vb[VbVbalrOperators#80](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_4.vb)]  
  
 [!code-vb[VbVbalrOperators#79](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_5.vb)]  
  
 Nell'esempio precedente, si noti che alcune importanti codice all'interno di `checkIfValid()` non viene eseguito quando la chiamata è esegue un corto circuita. Il primo `If` istruzione chiama `checkIfValid()` anche se `12 > 45` restituisce `False`perché `And` non di corto circuito. Il secondo `If` istruzione non chiama `checkIfValid()`, perché quando `12 > 45` restituisce `False`, `AndAlso` provoca un corto circuito la seconda espressione. Il terzo `If` istruzione chiama `checkIfValid()` anche se `12 < 45` restituisce `True`perché `Or` non di corto circuito. Il quarto `If` istruzione non chiama `checkIfValid()`, perché quando `12 < 45` restituisce `True`, `OrElse` provoca un corto circuito la seconda espressione.  
  
## <a name="bitwise-operations"></a>Operazioni bit per bit  
 Le operazioni bit per bit restituiscono due valori integrali in forma binaria (base 2). Si confrontano i bit in posizioni corrispondenti e quindi assegnare valori in base al confronto. Nell'esempio seguente viene illustrato il `And` operatore.  
  
 [!code-vb[VbVbalrConcepts#2](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/logical-and-bitwise-operators_6.vb)]  
  
 Nell'esempio precedente imposta il valore di `x` su 1. Ciò si verifica per i motivi seguenti:  
  
-   I valori vengono considerati come binari:  
  
     3 in formato binario = 011  
  
     5 in formato binario = 101  
  
-   Il `And` operatore confronta le rappresentazioni binarie, una posizione binaria (bit) alla volta. Se entrambi i bit in una determinata posizione sono 1, 1 viene inserito in tale posizione nel risultato. Se un bit è 0, 0 viene inserito in tale posizione nel risultato. Nell'esempio precedente si procede come indicato di seguito:  
  
     011 (3 in formato binario)  
  
     101 (5 in formato binario)  
  
     001 (il risultato in formato binario)  
  
-   Il risultato viene considerato come separatore decimale. Il valore 001 è la rappresentazione binaria di 1, in modo `x` = 1.  
  
 Bit per bit `Or` operazione è simile, ad eccezione del fatto che se uno o entrambi i bit confrontati è 1, 1 viene assegnato al bit del risultato. `Xor` Assegna un 1 per il bit di risultato se uno dei bit confrontati (non entrambi) è 1. `Not` accetta un singolo operando e inverte tutti i bit, incluso il bit di segno e assegna tale valore al risultato. Ciò significa che per i numeri positivi firmati, `Not` restituisce sempre un valore negativo e per i numeri negativi `Not` restituisce sempre un valore positivo o zero.  
  
 Il `AndAlso` e `OrElse` operatori non supportano operazioni bit per bit.  
  
> [!NOTE]
>  Operazioni bit per bit possono essere eseguite solo su tipi integrali. Valori a virgola mobile devono essere convertiti in tipi integrali affinché possa continuare l'operazione bit per bit.  
  
## <a name="see-also"></a>Vedere anche  
 [Operatori logici e bit per bit (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Espressioni booleane](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [Operatori aritmetici in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Operatori di confronto in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Operatori di concatenazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [Combinazione efficace di operatori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)

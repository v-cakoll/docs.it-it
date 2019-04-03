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
ms.openlocfilehash: ac47b6d7fa4861d18646a23f442caccc4062852f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819307"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Operatori logici e bit per bit in Visual Basic
Confrontano gli operatori logici `Boolean` espressioni e restituire un `Boolean` risultato. Il `And`, `Or`, `AndAlso`, `OrElse`, e `Xor` gli operatori sono *binario* perché accettano due operandi, mentre il `Not` operatore è *unario* quanto accetta un singolo operando. Alcuni di questi operatori possono anche eseguire operazioni logiche bit per bit sui valori integrali.  
  
## <a name="unary-logical-operator"></a>Operatore logico unario  
 Il [operatore Not](../../../../visual-basic/language-reference/operators/not-operator.md) esegue la logica *negazione* su un `Boolean` espressione. Restituisce l'opposto logico del relativo operando. Se l'espressione viene valutata `True`, quindi `Not` restituisce `False`; se l'espressione restituirà `False`, quindi `Not` restituisce `True`. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>Operatori logici binari  
 Il [operatore And](../../../../visual-basic/language-reference/operators/and-operator.md) esegue la logica *combinazione* su due `Boolean` espressioni. Se entrambe le espressioni restituiscono `True`, quindi `And` restituisce `True`. Se almeno una delle espressioni viene valutata `False`, quindi `And` restituisce `False`.  
  
 Il [o operatore](../../../../visual-basic/language-reference/operators/or-operator.md) esegue la logica *disgiunzione* oppure *inclusione* su due `Boolean` espressioni. Se delle espressioni viene valutata `True`, o entrambi restituiscono `True`, quindi `Or` restituisce `True`. Se nessuna delle due espressioni viene valutata `True`, `Or` restituisce `False`.  
  
 Il [operatore Xor](../../../../visual-basic/language-reference/operators/xor-operator.md) esegue la logica *esclusione* su due `Boolean` espressioni. Se esattamente una espressione viene valutata `True`, ma non entrambi, `Xor` restituisce `True`. Se entrambe le espressioni restituiscono `True` o entrambi restituiscono `False`, `Xor` restituisce `False`.  
  
 Nell'esempio seguente viene illustrato il `And`, `Or`, e `Xor` operatori.  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>Operazioni di logiche di corto circuito  
 Il [AndAlso Operator](../../../../visual-basic/language-reference/operators/andalso-operator.md) è molto simile al `And` operatore, in quanto esegue inoltre congiunzione logica su due `Boolean` espressioni. La differenza principale tra i due è che `AndAlso` esibisce *corto circuito* comportamento. Se la prima espressione in un' `AndAlso` espressione viene valutata `False`, quindi la seconda espressione non viene valutata in quanto non può alterare il risultato finale, e `AndAlso` restituisce `False`.  
  
 Analogamente, il [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md) esegue la congiunzione logica su due `Boolean` espressioni. Se la prima espressione in un' `OrElse` espressione viene valutata `True`, quindi la seconda espressione non viene valutata in quanto non può alterare il risultato finale, e `OrElse` restituisce `True`.  
  
### <a name="short-circuiting-trade-offs"></a>Short-circuit  
 Corto circuito può migliorare le prestazioni non valuta un'espressione che non è possibile modificare il risultato dell'operazione logica. Tuttavia, se tale espressione consente di eseguire azioni aggiuntive, corto circuito ignora tali azioni. Ad esempio, se l'espressione include una chiamata a un `Function` routine, che procedure non viene chiamata se l'espressione è esegue un corto circuito e qualsiasi altro codice contenuto nel `Function` non viene eseguito. Pertanto, la funzione potrebbe essere eseguito solo occasionalmente e non può essere testata correttamente. O la logica di programma potrebbe dipendere dal codice nel `Function`.  
  
 Nell'esempio seguente viene illustrata la differenza tra `And`, `Or`e le relative controparti di corto circuite.  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 Nell'esempio precedente, si noti che alcune importante codice all'interno di `checkIfValid()` non viene eseguito quando si esegue un corto circuita della chiamata. Il primo `If` istruzione chiama `checkIfValid()` anche se `12 > 45` restituisce `False`, in quanto `And` non corto circuito. La seconda `If` istruzione non chiama `checkIfValid()`, perché quando `12 > 45` restituisce `False`, `AndAlso` provoca un corto circuito della seconda espressione. La terza `If` istruzione chiama `checkIfValid()` anche se `12 < 45` restituisce `True`, in quanto `Or` non corto circuito. Il quarto `If` istruzione non chiama `checkIfValid()`, perché quando `12 < 45` restituisce `True`, `OrElse` provoca un corto circuito della seconda espressione.  
  
## <a name="bitwise-operations"></a>Operazioni bit per bit  
 Operazioni bit per bit restituiscono due valori integrali in forma binaria (in base 2). Si confrontano i bit nelle posizioni corrispondenti e quindi assegnare valori basati sul confronto. Nell'esempio seguente viene illustrato il `And` operatore.  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 Nell'esempio precedente imposta il valore di `x` su 1. Ciò si verifica per i motivi seguenti:  
  
-   I valori vengono considerati come file binario:  
  
     3 in formato binario = 011  
  
     5 in formato binario = 101  
  
-   Il `And` operatore confronta le rappresentazioni binarie, una posizione binaria (bit) alla volta. Se entrambi i bit in una determinata posizione sono 1, 1 viene inserito in tale posizione nel risultato. Se un bit è 0, 0 viene inserito in tale posizione nel risultato. Nell'esempio precedente funziona nel modo seguente:  
  
     011 (3 in formato binario)  
  
     101 (5 in formato binario)  
  
     001 (il risultato in formato binario)  
  
-   Il risultato viene considerato come numero decimale. Il valore 001 è la rappresentazione binaria di 1, pertanto `x` = 1.  
  
 Bit per bit `Or` operazione è simile, ad eccezione del fatto che un valore 1 viene assegnato al bit del risultato se uno o entrambi i bit confrontati è 1. `Xor` Assegna un valore 1 per il bit del risultato se esattamente uno dei bit confrontati (non entrambi) è 1. `Not` accetta un singolo operando e inverte tutti i bit, tra cui il bit di segno e assegna tale valore sul risultato. Ciò significa che per la firma di numeri negativi e positivi `Not` restituisce sempre un valore negativo e per i numeri negativi `Not` restituisce sempre un valore positivo o zero.  
  
 Il `AndAlso` e `OrElse` operatori non supportano le operazioni bit per bit.  
  
> [!NOTE]
>  Operazioni bit per bit possono essere eseguite solo sui tipi integrali. Valori a virgola mobile devono essere convertiti in tipi integrali affinché possa continuare l'operazione bit per bit.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici e bit per bit (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Espressioni booleane](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Operatori aritmetici in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Operatori di confronto in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operatori di concatenazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Combinazione efficace di operatori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)

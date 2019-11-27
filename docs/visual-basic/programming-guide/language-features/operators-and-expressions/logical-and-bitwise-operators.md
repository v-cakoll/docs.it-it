---
title: Operatori logici e bit per bit
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
ms.openlocfilehash: 55a246c0d56501a409ebbc7d0d0aa39ae9fa1770
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343598"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Operatori logici e bit per bit in Visual Basic
Gli operatori logici confrontano le espressioni `Boolean` e restituiscono un risultato `Boolean`. Gli operatori `And`, `Or`, `AndAlso`, `OrElse`e `Xor` sono *binari* perché accettano due operandi, mentre l'operatore `Not` è *unario* perché accetta un solo operando. Alcuni di questi operatori possono anche eseguire operazioni logiche bit per bit sui valori integrali.  
  
## <a name="unary-logical-operator"></a>Operatore logico unario  
 L' [operatore not](../../../../visual-basic/language-reference/operators/not-operator.md) esegue una *negazione* logica su un'espressione `Boolean`. Produce l'opposto logico del relativo operando. Se l'espressione restituisce `True`, `Not` restituisce `False`; Se l'espressione restituisce `False`, `Not` restituisce `True`. Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>Operatori logici binari  
 L' [operatore and](../../../../visual-basic/language-reference/operators/and-operator.md) esegue una *congiunzione* logica su due espressioni `Boolean`. Se entrambe le espressioni restituiscono `True`, `And` restituisce `True`. Se almeno una delle espressioni restituisce `False`, `And` restituisce `False`.  
  
 L' [operatore OR](../../../../visual-basic/language-reference/operators/or-operator.md) esegue una *disgiunzione* logica o un' *inclusione* su due espressioni `Boolean`. Se una delle due espressioni restituisce `True`o entrambi restituiscono `True`, `Or` restituisce `True`. Se nessuna delle due espressioni restituisce `True`, `Or` restituisce `False`.  
  
 L' [operatore XOR](../../../../visual-basic/language-reference/operators/xor-operator.md) esegue l' *esclusione* logica su due espressioni `Boolean`. Se esattamente un'espressione restituisce `True`, ma non entrambi, `Xor` restituisce `True`. Se entrambe le espressioni restituiscono `True` o entrambe restituiscono `False`, `Xor` restituisce `False`.  
  
 Nell'esempio seguente vengono illustrati gli operatori `And`, `Or`e `Xor`.  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>Operazioni logiche di corto circuito  
 L' [operatore AndAlso](../../../../visual-basic/language-reference/operators/andalso-operator.md) è molto simile all'operatore `And`, in quanto esegue anche una congiunzione logica su due espressioni di `Boolean`. La differenza principale tra i due è che `AndAlso` presenta un comportamento di *corto circuito* . Se la prima espressione in un'espressione `AndAlso` restituisce `False`, la seconda espressione non viene valutata perché non è in grado di modificare il risultato finale e `AndAlso` restituisce `False`.  
  
 Analogamente, l' [operatore OrElse](../../../../visual-basic/language-reference/operators/orelse-operator.md) esegue una disgiunzione logica di corto circuito su due espressioni `Boolean`. Se la prima espressione in un'espressione `OrElse` restituisce `True`, la seconda espressione non viene valutata perché non è in grado di modificare il risultato finale e `OrElse` restituisce `True`.  
  
### <a name="short-circuiting-trade-offs"></a>Compromessi di corto circuito  
 Il cortocircuito può migliorare le prestazioni non valutando un'espressione che non può modificare il risultato dell'operazione logica. Tuttavia, se l'espressione esegue azioni aggiuntive, il cortocircuito ignora tali azioni. Se, ad esempio, l'espressione include una chiamata a una routine `Function`, tale routine non viene chiamata se l'espressione è di corto circuito e qualsiasi codice aggiuntivo contenuto nell'`Function` non viene eseguito. La funzione potrebbe pertanto essere eseguita solo occasionalmente e potrebbe non essere testata correttamente. In alternativa, la logica del programma potrebbe dipendere dal codice nel `Function`.  
  
 Nell'esempio seguente viene illustrata la differenza tra `And`, `Or`e le relative controparti di corto circuito.  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 Nell'esempio precedente, si noti che il codice importante all'interno `checkIfValid()` non viene eseguito quando la chiamata è di corto circuito. La prima istruzione `If` chiama `checkIfValid()` anche se `12 > 45` restituisce `False`, perché `And` non esegue un corto circuito. La seconda istruzione `If` non chiama `checkIfValid()`, perché quando `12 > 45` restituisce `False`, `AndAlso` esegue il cortocircuito della seconda espressione. La terza istruzione `If` chiama `checkIfValid()` anche se `12 < 45` restituisce `True`, perché `Or` non esegue un corto circuito. La quarta istruzione `If` non chiama `checkIfValid()`, perché quando `12 < 45` restituisce `True`, `OrElse` esegue il cortocircuito della seconda espressione.  
  
## <a name="bitwise-operations"></a>Operazioni bit per bit  
 Le operazioni bit per bit valutano due valori integrali nel form binario (base 2). Consentono di confrontare i bit nelle posizioni corrispondenti e quindi assegnare i valori in base al confronto. Nell'esempio seguente viene illustrato l'operatore `And`.  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 Nell'esempio precedente il valore di `x` viene impostato su 1. Ciò si verifica per i motivi seguenti:  
  
- I valori vengono considerati binari:  
  
     3 in formato binario = 011  
  
     5 in formato binario = 101  
  
- L'operatore `And` Confronta le rappresentazioni binarie, una posizione binaria (bit) alla volta. Se entrambi i bit in una determinata posizione sono pari a 1, il valore 1 viene posizionato in tale posizione nel risultato. Se uno dei due bit è 0, un valore 0 viene posizionato in tale posizione nel risultato. Nell'esempio precedente questo approccio funziona come segue:  
  
     011 (3 in formato binario)  
  
     101 (5 in formato binario)  
  
     001 (risultato in formato binario)  
  
- Il risultato viene trattato come decimale. Il valore 001 è la rappresentazione binaria di 1, quindi `x` = 1.  
  
 L'operazione di `Or` bit per bit è simile, ad eccezione del fatto che un valore 1 viene assegnato al bit del risultato se uno o entrambi i bit confrontati sono pari a 1. `Xor` assegna un valore 1 al bit del risultato se esattamente uno dei bit confrontati (non entrambi) è 1. `Not` accetta un solo operando e inverte tutti i bit, incluso il bit di segno, e assegna tale valore al risultato. Ciò significa che per i numeri positivi con segno, `Not` restituisce sempre un valore negativo e per i numeri negativi `Not` restituisce sempre un valore positivo o zero.  
  
 Gli operatori `AndAlso` e `OrElse` non supportano operazioni bit per bit.  
  
> [!NOTE]
> Le operazioni bit per bit possono essere eseguite solo su tipi integrali. È necessario convertire i valori a virgola mobile in tipi integrali prima di procedere con un'operazione bit per bit.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici/bit per bit (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Espressioni booleane](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Operatori aritmetici in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Operatori di confronto in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operatori di concatenazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Combinazione efficace di operatori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)

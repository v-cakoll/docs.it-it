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
ms.openlocfilehash: 40076b2ad6606b4c565bcd39dbeea9e55da47211
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963309"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Operatori logici e bit per bit in Visual Basic
Gli operatori logici `Boolean` confrontano `Boolean` le espressioni e restituiscono un risultato. Gli `And`operatori `Or`, ,`AndAlso` `Not` , `OrElse`e sono`Xor` *binari* perché accettano due operandi, mentre l'operatore è unario perché accetta un solo operando. Alcuni di questi operatori possono anche eseguire operazioni logiche bit per bit sui valori integrali.  
  
## <a name="unary-logical-operator"></a>Operatore logico unario  
 L' [operatore not](../../../../visual-basic/language-reference/operators/not-operator.md) esegue una *negazione* logica su `Boolean` un'espressione. Produce l'opposto logico del relativo operando. `True`Se l'espressione restituisce `Not` , restituisce `False`; `False` sel'`True`espressione restituisce, restituisce.`Not` Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>Operatori logici binari  
 L' [operatore and](../../../../visual-basic/language-reference/operators/and-operator.md) esegue una *congiunzione* logica `Boolean` di due espressioni. Se entrambe le espressioni `True`restituiscono `And` , restituisce `True`. Se almeno una delle espressioni `False`restituisce `And` , restituisce `False`.  
  
 L' [operatore OR](../../../../visual-basic/language-reference/operators/or-operator.md) esegue una disgiunzione logica o un' `Boolean` *inclusione* su due espressioni. Se `True`una delle due espressioni restituisce o entrambi `True`restituiscono, `Or` restituisce `True`. Se nessuna delle due espressioni `True`restituisce, `Or` restituisce. `False`  
  
 L' [operatore XOR](../../../../visual-basic/language-reference/operators/xor-operator.md) esegue l' *esclusione* logica su `Boolean` due espressioni. Se esattamente un'espressione `True`restituisce, ma non entrambi, `Xor` restituisce `True`. Se entrambe `True` le espressioni restituiscono o restituiscono entrambe a `False` `False`, `Xor` restituisce.  
  
 Nell'esempio seguente vengono illustrati `And`gli `Or`operatori, `Xor` e.  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>Operazioni logiche di corto circuito  
 L' [operatore AndAlso](../../../../visual-basic/language-reference/operators/andalso-operator.md) è molto simile all' `And` operatore, in quanto esegue anche la congiunzione logica di due `Boolean` espressioni. La differenza principale tra i due è che `AndAlso` presenta un comportamento di *corto circuito* . Se la prima espressione in un' `AndAlso` espressione restituisce `False`, la seconda espressione non viene valutata perché non può modificare il risultato finale e `AndAlso` restituisce `False`.  
  
 Analogamente, l' [operatore OrElse](../../../../visual-basic/language-reference/operators/orelse-operator.md) esegue una disgiunzione logica di corto circuito `Boolean` su due espressioni. Se la prima espressione in un' `OrElse` espressione restituisce `True`, la seconda espressione non viene valutata perché non può modificare il risultato finale e `OrElse` restituisce `True`.  
  
### <a name="short-circuiting-trade-offs"></a>Compromessi di corto circuito  
 Il cortocircuito può migliorare le prestazioni non valutando un'espressione che non può modificare il risultato dell'operazione logica. Tuttavia, se l'espressione esegue azioni aggiuntive, il cortocircuito ignora tali azioni. Se, ad esempio, l'espressione include una chiamata a `Function` una routine, la routine non viene chiamata se l'espressione è di corto circuito e qualsiasi codice aggiuntivo contenuto nell'oggetto `Function` non viene eseguito. La funzione potrebbe pertanto essere eseguita solo occasionalmente e potrebbe non essere testata correttamente. In alternativa `Function`, la logica del programma potrebbe dipendere dal codice in.  
  
 Nell'esempio seguente viene illustrata la differenza `And`tra `Or`, e le relative controparti di corto circuito.  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 Nell'esempio precedente, si noti che un codice importante all' `checkIfValid()` interno di non viene eseguito quando la chiamata è di corto circuito. La prima `If` istruzione chiama `checkIfValid()` anche se `12 > 45` restituisce `False`, perché `And` non esegue un corto circuito. La seconda `If` istruzione non chiama `checkIfValid()`, perché quando `12 > 45` restituisce `False`, `AndAlso` esegue il cortocircuito della seconda espressione. La terza `If` istruzione chiama `checkIfValid()` anche se `12 < 45` restituisce `True`, perché `Or` non esegue un corto circuito. La quarta `If` istruzione non chiama `checkIfValid()`, perché quando `12 < 45` restituisce `True`, `OrElse` esegue il cortocircuito della seconda espressione.  
  
## <a name="bitwise-operations"></a>Operazioni bit per bit  
 Le operazioni bit per bit valutano due valori integrali nel form binario (base 2). Consentono di confrontare i bit nelle posizioni corrispondenti e quindi assegnare i valori in base al confronto. Nell'esempio seguente viene illustrato l' `And` operatore.  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 Nell'esempio precedente il valore di `x` viene impostato su 1. Ciò si verifica per i motivi seguenti:  
  
- I valori vengono considerati binari:  
  
     3 in formato binario = 011  
  
     5 in formato binario = 101  
  
- L' `And` operatore confronta le rappresentazioni binarie, una posizione binaria (bit) alla volta. Se entrambi i bit in una determinata posizione sono pari a 1, il valore 1 viene posizionato in tale posizione nel risultato. Se uno dei due bit è 0, un valore 0 viene posizionato in tale posizione nel risultato. Nell'esempio precedente questo approccio funziona come segue:  
  
     011 (3 in formato binario)  
  
     101 (5 in formato binario)  
  
     001 (risultato in formato binario)  
  
- Il risultato viene trattato come decimale. Il valore 001 è la rappresentazione binaria di 1, `x` quindi = 1.  
  
 L'operazione `Or` bit per bit è simile, ad eccezione del fatto che un valore 1 viene assegnato al bit del risultato se uno o entrambi i bit confrontati sono pari a 1. `Xor`assegna un valore 1 al bit del risultato se esattamente uno dei bit confrontati (non entrambi) è 1. `Not`accetta un solo operando e inverte tutti i bit, incluso il bit di segno, e assegna tale valore al risultato. Ciò significa che per i numeri positivi con `Not` segno, restituisce sempre un valore negativo e per i `Not` numeri negativi restituisce sempre un valore positivo o zero.  
  
 Gli `AndAlso` operatori `OrElse` e non supportano operazioni bit per bit.  
  
> [!NOTE]
> Le operazioni bit per bit possono essere eseguite solo su tipi integrali. È necessario convertire i valori a virgola mobile in tipi integrali prima di procedere con un'operazione bit per bit.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici/bit per bit (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Espressioni booleane](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Operatori aritmetici in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Operatori di confronto in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operatori di concatenazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Combinazione efficace di operatori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)

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
ms.openlocfilehash: 19d3511363f19319c2bd8ce872b62c1462b1370f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403408"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Operatori logici e bit per bit in Visual Basic
Gli operatori logici confrontano `Boolean` le espressioni e restituiscono un `Boolean` risultato. Gli `And` `Or` operatori,, `AndAlso` , `OrElse` e `Xor` sono *binari* perché accettano due operandi, mentre l' `Not` operatore è *unario* perché accetta un solo operando. Alcuni di questi operatori possono anche eseguire operazioni logiche bit per bit sui valori integrali.  
  
## <a name="unary-logical-operator"></a>Operatore logico unario  
 L' [operatore not](../../../language-reference/operators/not-operator.md) esegue una *negazione* logica su un' `Boolean` espressione. Produce l'opposto logico del relativo operando. Se l'espressione restituisce `True` , `Not` restituisce `False` ; se l'espressione restituisce `False` , `Not` restituisce `True` . Questa condizione è illustrata nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>Operatori logici binari  
 L' [operatore and](../../../language-reference/operators/and-operator.md) esegue una *congiunzione* logica di due `Boolean` espressioni. Se entrambe le espressioni restituiscono `True` , `And` restituisce `True` . Se almeno una delle espressioni restituisce `False` , `And` restituisce `False` .  
  
 L' [operatore OR](../../../language-reference/operators/or-operator.md) esegue una *disgiunzione* logica o un' *inclusione* su due `Boolean` espressioni. Se una delle due espressioni restituisce `True` o entrambi restituiscono `True` , `Or` restituisce `True` . Se nessuna delle due espressioni `True` restituisce, `Or` restituisce `False` .  
  
 L' [operatore XOR](../../../language-reference/operators/xor-operator.md) esegue l' *esclusione* logica su due `Boolean` espressioni. Se esattamente un'espressione `True` restituisce, ma non entrambi, `Xor` restituisce `True` . Se entrambe le espressioni restituiscono o restituiscono `True` entrambe a `False` , `Xor` restituisce `False` .  
  
 Nell'esempio seguente vengono illustrati `And` gli `Or` operatori, e `Xor` .  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>Operazioni logiche di corto circuito  
 L' [operatore AndAlso](../../../language-reference/operators/andalso-operator.md) è molto simile all' `And` operatore, in quanto esegue anche la congiunzione logica di due `Boolean` espressioni. La differenza principale tra i due è che `AndAlso` presenta un comportamento di *corto circuito* . Se la prima espressione in un' `AndAlso` espressione restituisce `False` , la seconda espressione non viene valutata perché non può modificare il risultato finale e `AndAlso` restituisce `False` .  
  
 Analogamente, l' [operatore OrElse](../../../language-reference/operators/orelse-operator.md) esegue una disgiunzione logica di corto circuito su due `Boolean` espressioni. Se la prima espressione in un' `OrElse` espressione restituisce `True` , la seconda espressione non viene valutata perché non può modificare il risultato finale e `OrElse` restituisce `True` .  
  
### <a name="short-circuiting-trade-offs"></a>Compromessi di corto circuito  
 Il cortocircuito può migliorare le prestazioni non valutando un'espressione che non può modificare il risultato dell'operazione logica. Tuttavia, se l'espressione esegue azioni aggiuntive, il cortocircuito ignora tali azioni. Se, ad esempio, l'espressione include una chiamata a una `Function` routine, la routine non viene chiamata se l'espressione è di corto circuito e qualsiasi codice aggiuntivo contenuto nell'oggetto non viene `Function` eseguito. La funzione potrebbe pertanto essere eseguita solo occasionalmente e potrebbe non essere testata correttamente. In alternativa, la logica del programma potrebbe dipendere dal codice in `Function` .  
  
 Nell'esempio seguente viene illustrata la differenza tra `And` , `Or` e le relative controparti di corto circuito.  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 Nell'esempio precedente, si noti che un codice importante all'interno di non viene `checkIfValid()` eseguito quando la chiamata è di corto circuito. La prima `If` istruzione chiama `checkIfValid()` anche se `12 > 45` restituisce `False` , perché non `And` esegue un corto circuito. La seconda `If` istruzione non chiama `checkIfValid()` , perché quando `12 > 45` restituisce, esegue il cortocircuito `False` `AndAlso` della seconda espressione. La terza `If` istruzione chiama `checkIfValid()` anche se `12 < 45` restituisce `True` , perché non `Or` esegue un corto circuito. La quarta `If` istruzione non chiama `checkIfValid()` , perché quando `12 < 45` restituisce, esegue il cortocircuito `True` `OrElse` della seconda espressione.  
  
## <a name="bitwise-operations"></a>Operazioni bit per bit  
 Le operazioni bit per bit valutano due valori integrali nel form binario (base 2). Consentono di confrontare i bit nelle posizioni corrispondenti e quindi assegnare i valori in base al confronto. Nell'esempio seguente viene illustrato l' `And` operatore.  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 Nell'esempio precedente il valore di viene impostato `x` su 1. Ciò si verifica per i motivi seguenti:  
  
- I valori vengono considerati binari:  
  
     3 in formato binario = 011  
  
     5 in formato binario = 101  
  
- L' `And` operatore confronta le rappresentazioni binarie, una posizione binaria (bit) alla volta. Se entrambi i bit in una determinata posizione sono pari a 1, il valore 1 viene posizionato in tale posizione nel risultato. Se uno dei due bit è 0, un valore 0 viene posizionato in tale posizione nel risultato. Nell'esempio precedente questo approccio funziona come segue:  
  
     011 (3 in formato binario)  
  
     101 (5 in formato binario)  
  
     001 (risultato in formato binario)  
  
- Il risultato viene trattato come decimale. Il valore 001 è la rappresentazione binaria di 1, quindi `x` = 1.  
  
 L'operazione bit per bit `Or` è simile, ad eccezione del fatto che un valore 1 viene assegnato al bit del risultato se uno o entrambi i bit confrontati sono pari a 1. `Xor`assegna un valore 1 al bit del risultato se esattamente uno dei bit confrontati (non entrambi) è 1. `Not`accetta un solo operando e inverte tutti i bit, incluso il bit di segno, e assegna tale valore al risultato. Ciò significa che per i numeri positivi con segno, `Not` restituisce sempre un valore negativo e per i numeri negativi `Not` restituisce sempre un valore positivo o zero.  
  
 Gli `AndAlso` `OrElse` operatori e non supportano operazioni bit per bit.  
  
> [!NOTE]
> Le operazioni bit per bit possono essere eseguite solo su tipi integrali. È necessario convertire i valori a virgola mobile in tipi integrali prima di procedere con un'operazione bit per bit.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici e bit per bit (Visual Basic)](../../../language-reference/operators/logical-bitwise-operators.md)
- [Espressioni booleane](boolean-expressions.md)
- [Operatori aritmetici in Visual Basic](arithmetic-operators.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Operatori di concatenazione in Visual Basic](concatenation-operators.md)
- [Combinazione efficace di operatori](efficient-combination-of-operators.md)

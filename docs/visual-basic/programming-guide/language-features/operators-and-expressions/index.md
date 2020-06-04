---
title: Operatori ed espressioni
ms.date: 07/20/2015
helpviewer_keywords:
- operators [Visual Basic], operands
- operators [Visual Basic]
- operands [Visual Basic], definition
- Visual Basic code, operators
- Visual Basic code, expressions
- operands
- expressions [Visual Basic]
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
ms.openlocfilehash: dcf52c6200193f81070f323c8037ad82d747942d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403434"
---
# <a name="operators-and-expressions-in-visual-basic"></a>Operatori ed espressioni in Visual Basic
Un *operatore* è un elemento di codice che esegue un'operazione su uno o più elementi di codice che contengono valori. Gli elementi di valore includono variabili, costanti, valori letterali, proprietà, espressioni e valori restituiti da procedure `Function` e `Operator`.  
  
 Un'*espressione* è una serie di elementi di valore combinati con operatori che restituisce un nuovo valore. Gli operatori agiscono sugli elementi di valore mediante l'esecuzione di calcoli, confronti o altre operazioni.  
  
## <a name="types-of-operators"></a>Tipi di operatori  
 Visual Basic fornisce i tipi di operatori seguenti:  
  
- Gli [operatori aritmetici](arithmetic-operators.md) eseguono calcoli comuni su valori numerici, inclusa l'inversione degli schemi di bit.  
  
- Gli [operatori di confronto](comparison-operators.md) confrontano due espressioni e restituiscono un valore `Boolean` che rappresenta il risultato del confronto.  
  
- Gli [operatori di concatenamento](concatenation-operators.md) uniscono più stringhe in un'unica stringa.  
  
- Gli [operatori logici e bit per bit in Visual Basic](logical-and-bitwise-operators.md) combinano valori `Boolean` o numerici e restituiscono un risultato con lo stesso tipo di dati dei valori.  
  
 Gli elementi di valore che vengono combinati con un operatore sono detti *operandi* di tale operatore. Gli operatori combinati con elementi di valore formano espressioni, ad eccezione dell'operatore di assegnazione che forma un'*istruzione*. Per altre informazioni, vedere [Istruzioni](../statements.md).  
  
## <a name="evaluation-of-expressions"></a>Valutazione delle espressioni  
 Il risultato finale di un'espressione rappresenta un valore, in genere espresso con un tipo di dati comune quale `Boolean`, `String` o un tipo numerico.  
  
 Di seguito sono riportati esempi di espressioni.  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 Più operatori possono eseguire azioni in un'unica operazione o istruzione, come illustrato nel seguente esempio.  
  
 [!code-vb[VbVbalrOperators#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#56)]  
  
 Nell'esempio precedente Visual Basic esegue le operazioni nell'espressione sul lato destro dell'operatore di assegnazione ( `=` ), quindi assegna il valore risultante alla variabile a `x` sinistra. Non esistono limiti al numero di operatori combinabili in un'espressione, ma per ottenere i risultati previsti è importante tenere presenti le regole di [Precedenza tra gli operatori in Visual Basic](../../../language-reference/operators/operator-precedence.md).  

## <a name="see-also"></a>Vedere anche

- [Operatori](../../../language-reference/operators/index.md)
- [Combinazione efficace di operatori](efficient-combination-of-operators.md)
- [Istruzioni](../../../language-reference/statements/index.md)

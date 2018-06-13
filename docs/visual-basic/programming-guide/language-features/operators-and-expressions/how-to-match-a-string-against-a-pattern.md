---
title: 'Procedura: confrontare una stringa con un modello (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- pattern matching
- strings [Visual Basic], comparing
- string comparison [Visual Basic], operators
- Visual Basic code, operators
- pattern matching [Visual Basic], string comparison
- string comparison [Visual Basic]
- Like operator [Visual Basic], pattern matching
- pattern matching, empty strings
- operators [Visual Basic], comparison
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
ms.openlocfilehash: aef378bfc32d6deff431a2caac1261a6cd7520c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655212"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>Procedura: confrontare una stringa con un modello (Visual Basic)
Se si desidera determinare se un'espressione del [tipo di dati String](../../../../visual-basic/language-reference/data-types/string-data-type.md) soddisfa un modello, è possibile utilizzare il [operatore Like](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
 `Like` accetta due operandi. L'operando sinistro è un'espressione stringa e l'operando destro è una stringa contenente il modello da utilizzare per la corrispondenza. `Like` Restituisce un `Boolean` valore che indica se l'espressione stringa soddisfa il criterio.  
  
 È possibile associare ogni carattere incluso nell'espressione stringa con un carattere specifico, un carattere jolly, un elenco di caratteri o un intervallo di caratteri. Le posizioni delle specifiche nella stringa modello corrispondono alle posizioni dei caratteri per cui trovare una corrispondenza nell'espressione stringa.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>Per confrontare un carattere incluso nell'espressione stringa con un carattere specifico  
  
-   Inserire il carattere specifico direttamente nella stringa di modello. Alcuni caratteri speciali devono essere racchiusi tra parentesi (`[ ]`). Per ulteriori informazioni, vedere [operatore Like](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
     Nell'esempio seguente viene verificato se `myString` costituito esattamente il singolo carattere `H`.  
  
     [!code-vb[VbVbalrOperators#70](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_1.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>Per confrontare un carattere incluso nell'espressione stringa con un carattere jolly  
  
-   Inserire un punto interrogativo (`?`) nella stringa di modello. Qualsiasi carattere valido in questa posizione determina una corrispondenza corretta.  
  
     Nell'esempio seguente viene verificato se `myString` costituito dal singolo carattere `W` seguita da due caratteri di tutti i valori.  
  
     [!code-vb[VbVbalrOperators#71](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_2.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>Per confrontare un carattere nell'espressione stringa in un elenco di caratteri  
  
-   Inserire le parentesi (`[ ]`) nella stringa di modello e all'interno delle parentesi inserire l'elenco dei caratteri. Non separare i caratteri con virgole o qualsiasi altro separatore. Qualsiasi carattere singolo nell'elenco determina una corrispondenza corretta.  
  
     Nell'esempio seguente viene verificato se `myString` è costituito da qualsiasi carattere valido seguito da esattamente uno dei caratteri `A`, `C`, o `E`.  
  
     [!code-vb[VbVbalrOperators#72](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_3.vb)]  
  
     Si noti che questa corrispondenza tra maiuscole e minuscole.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>Per confrontare un carattere incluso nell'espressione stringa con un intervallo di caratteri  
  
-   Inserire le parentesi (`[ ]`) nella stringa di modello e racchiudere tra parentesi i caratteri minimo e massimo dell'intervallo, separati da un trattino (`–`). Qualsiasi carattere singolo compreso nell'intervallo determina una corrispondenza corretta.  
  
     Nell'esempio seguente viene verificato se `myString` costituito dai caratteri `num` seguiti da un solo i caratteri `i`, `j`, `k`, `l`, `m`, o `n`.  
  
     [!code-vb[VbVbalrOperators#73](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_4.vb)]  
  
     Si noti che questa corrispondenza tra maiuscole e minuscole.  
  
## <a name="matching-empty-strings"></a>Confronto di stringhe vuote  
 `Like` considera la sequenza `[]` come una stringa di lunghezza zero (`""`). È possibile utilizzare `[]` per verificare se l'intera espressione stringa è vuoto, ma non può essere utilizzato per verificare se una determinata posizione nell'espressione stringa è vuota. Se una posizione vuota è una delle opzioni è necessario per il test, è possibile utilizzare `Like` più volte.  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>Per confrontare un carattere nell'espressione stringa in un elenco di caratteri o alcun carattere  
  
1.  Chiamare il `Like` operatore due volte nella stessa espressione di tipo string e connettere le due chiamate con il [operatore o](../../../../visual-basic/language-reference/operators/or-operator.md) o [OrElse (operatore)](../../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
2.  Nella stringa di modello per la prima `Like` clausola, includere l'elenco di caratteri racchiusi tra parentesi quadre (`[ ]`).  
  
3.  Nella stringa di modello per il secondo `Like` clausola, non inserire alcun carattere in corrispondenza della posizione in questione.  
  
     Nell'esempio seguente verifica il numero di telefono di sette cifre `phoneNum` per esattamente tre cifre numeriche, seguita da uno spazio, un trattino (`–`), un periodo (`.`), o nessun carattere, seguita da quattro cifre.  
  
     [!code-vb[VbVbalrOperators#74](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_5.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operatori di confronto](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Operatori ed espressioni](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Operatore Like](../../../../visual-basic/language-reference/operators/like-operator.md)  
 [Tipo di dati String](../../../../visual-basic/language-reference/data-types/string-data-type.md)

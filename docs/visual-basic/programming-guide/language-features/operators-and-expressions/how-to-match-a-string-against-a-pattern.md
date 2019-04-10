---
title: 'Procedura: Confrontare una stringa con un modello (Visual Basic)'
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
ms.openlocfilehash: c14aa35ce15549ad9eccabe2330a7c43b6795140
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316271"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>Procedura: Confrontare una stringa con un modello (Visual Basic)
Se si desidera determinare se un'espressione del [tipo di dati String](../../../../visual-basic/language-reference/data-types/string-data-type.md) soddisfa un modello, è possibile utilizzare il [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
 `Like` accetta due operandi. L'operando sinistro è un'espressione stringa e l'operando destro è una stringa che contiene il modello da utilizzare per la corrispondenza. `Like` Restituisce un `Boolean` valore che indica se l'espressione stringa soddisfa il modello.  
  
 È possibile associare ogni carattere dell'espressione di stringa con un carattere specifico, un carattere jolly, un elenco di caratteri o un intervallo di caratteri. Le posizioni delle specifiche nella stringa di modello corrispondano alle posizioni dei caratteri da cui trovare una corrispondenza nell'espressione stringa.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>Per confrontare un carattere incluso nell'espressione di stringa con un carattere specifico  
  
-   Inserire il carattere specifico direttamente nella stringa di modello. Alcuni caratteri speciali devono essere racchiusi tra parentesi quadre (`[ ]`). Per altre informazioni, vedere [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
     Nell'esempio seguente viene verificato se `myString` è costituito da esattamente il carattere singolo `H`.  
  
     [!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>Per confrontare un carattere incluso nell'espressione di stringa con un carattere jolly  
  
-   Inserire un punto interrogativo (`?`) nella stringa di modello. Qualsiasi carattere valido in questa posizione determina una corrispondenza corretta.  
  
     Nell'esempio seguente viene verificato se `myString` costituita dal carattere singolo `W` seguita da due caratteri di tutti i valori.  
  
     [!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>Per confrontare un carattere nell'espressione stringa rispetto a un elenco di caratteri  
  
-   Inserire le parentesi (`[ ]`) nella stringa di modello e all'interno delle parentesi inserire l'elenco dei caratteri. Non separare i caratteri con virgole o qualsiasi altro separatore. Qualsiasi carattere singolo nell'elenco determina una corrispondenza corretta.  
  
     Nell'esempio seguente viene verificato se `myString` è costituito da qualsiasi carattere valido seguiti da un solo i caratteri `A`, `C`, o `E`.  
  
     [!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]  
  
     Si noti che questa corrispondenza tra maiuscole e minuscole.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>Per confrontare un carattere incluso nell'espressione di stringa con un intervallo di caratteri  
  
-   Inserire le parentesi (`[ ]`) nella stringa di modello e racchiudere tra parentesi i minimo e massimo di caratteri nell'intervallo, separati da un trattino (`–`). Qualsiasi carattere singolo compreso nell'intervallo determina una corrispondenza corretta.  
  
     Nell'esempio seguente viene verificato se `myString` è costituito da caratteri `num` seguita da esattamente uno dei caratteri `i`, `j`, `k`, `l`, `m`, o `n`.  
  
     [!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]  
  
     Si noti che questa corrispondenza tra maiuscole e minuscole.  
  
## <a name="matching-empty-strings"></a>Confronto di stringhe vuote  
 `Like` considera la sequenza `[]` come una stringa di lunghezza zero (`""`). È possibile usare `[]` per verificare se l'espressione intera stringa è vuota, ma non può essere utilizzato per verificare se una determinata posizione nell'espressione stringa è vuota. Se una posizione vuota è una delle opzioni è necessario per il test, è possibile usare `Like` più volte.  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>Per confrontare un carattere nell'espressione stringa rispetto a un elenco di caratteri o nessun carattere  
  
1. Chiamare il `Like` operatore due volte sulla stessa espressione di tipo string e connettere le due chiamate con il [operatore o](../../../../visual-basic/language-reference/operators/or-operator.md) o il [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
2. Nella stringa di modello per i primi `Like` clausola, includere l'elenco di caratteri racchiusi tra parentesi quadre (`[ ]`).  
  
3. Nella stringa di modello per il secondo `Like` clausola, non inserire qualsiasi carattere in corrispondenza della posizione in questione.  
  
     L'esempio seguente verifica il numero di telefono a 7 cifre `phoneNum` per esattamente tre cifre numeriche, seguita da uno spazio, un segno meno (`–`), un periodo (`.`), o nessun carattere affatto, seguita da quattro cifre.  
  
     [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatori di confronto](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Operatori ed espressioni](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Operatore Like](../../../../visual-basic/language-reference/operators/like-operator.md)
- [Tipo di dati String](../../../../visual-basic/language-reference/data-types/string-data-type.md)

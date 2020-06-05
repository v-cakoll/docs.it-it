---
title: 'Procedura: confrontare una stringa con un modello'
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
ms.openlocfilehash: d8a3c363d1a443db4a0b7633e380562af1913aca
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403446"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>Procedura: confrontare una stringa con un modello (Visual Basic)

Se si vuole sapere se un'espressione del [tipo di dati stringa](../../../language-reference/data-types/string-data-type.md) soddisfa un modello, è possibile usare l' [operatore like](../../../language-reference/operators/like-operator.md).

`Like`accetta due operandi. L'operando sinistro è un'espressione stringa e l'operando di destra è una stringa contenente il modello da utilizzare per la corrispondenza. `Like`Restituisce un `Boolean` valore che indica se l'espressione stringa soddisfa il modello.

È possibile trovare la corrispondenza di ogni carattere nell'espressione stringa con un carattere specifico, un carattere jolly, un elenco di caratteri o un intervallo di caratteri. Le posizioni delle specifiche nella stringa di pattern corrispondono alle posizioni dei caratteri per cui trovare una corrispondenza nell'espressione stringa.

## <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>Per trovare la corrispondenza con un carattere nell'espressione stringa con un carattere specifico

Inserire il carattere specifico direttamente nella stringa del modello. Alcuni caratteri speciali devono essere racchiusi tra parentesi quadre ( `[ ]` ). Per ulteriori informazioni, vedere [operatore like](../../../language-reference/operators/like-operator.md).

Nell'esempio seguente viene verificato se `myString` è costituito esattamente da un singolo carattere `H` .

[!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]

## <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>Per trovare la corrispondenza con un carattere nell'espressione stringa con un carattere jolly

Inserire un punto interrogativo ( `?` ) nella stringa del modello. Qualsiasi carattere valido in questa posizione consente di trovare una corrispondenza corretta.

Nell'esempio seguente viene verificato se `myString` è costituito dal carattere singolo `W` seguito da esattamente due caratteri di qualsiasi valore.

[!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]

## <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>Per trovare la corrispondenza con un carattere nell'espressione stringa con un elenco di caratteri

Inserire le parentesi quadre ( `[ ]` ) nella stringa del criterio e inserire l'elenco di caratteri all'interno delle parentesi quadre. Non separare i caratteri con virgole o altri separatori. Qualsiasi carattere singolo nell'elenco esegue una corrispondenza corretta.

Nell'esempio seguente viene verificato se `myString` è costituito da qualsiasi carattere valido seguito da uno dei caratteri `A` , `C` o `E` .

[!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]

Si noti che questa corrispondenza fa distinzione tra maiuscole e minuscole.

## <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>Per trovare la corrispondenza con un carattere nell'espressione stringa con un intervallo di caratteri

Inserire le parentesi quadre ( `[ ]` ) nella stringa del criterio e all'interno delle parentesi inserire i caratteri minimo e massimo nell'intervallo, separati da un trattino ( `–` ). Qualsiasi carattere singolo compreso nell'intervallo consente di trovare una corrispondenza corretta.

Nell'esempio seguente viene verificato se `myString` è costituito `num` da caratteri seguiti esattamente da uno dei caratteri,,,, `i` `j` `k` `l` `m` o `n` .

[!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]

Si noti che questa corrispondenza fa distinzione tra maiuscole e minuscole.

## <a name="matching-empty-strings"></a>Corrispondenza di stringhe vuote

`Like`Considera la sequenza `[]` come una stringa di lunghezza zero ( `""` ). È possibile utilizzare `[]` per verificare se l'intera espressione stringa è vuota, ma non è possibile utilizzarla per verificare se una particolare posizione nell'espressione stringa è vuota. Se una posizione vuota è una delle opzioni di cui è necessario eseguire il test, è possibile usare `Like` più di una volta.

### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>Per trovare la corrispondenza con un carattere nell'espressione stringa con un elenco di caratteri o nessun carattere

1. Chiamare l' `Like` operatore due volte sulla stessa espressione stringa e connettere le due chiamate con l' [operatore OR](../../../language-reference/operators/or-operator.md) o l' [operatore OrElse](../../../language-reference/operators/orelse-operator.md).

2. Nella stringa di modello per la prima `Like` clausola, includere l'elenco di caratteri racchiuso tra parentesi quadre ( `[ ]` ).

3. Nella stringa del criterio per la seconda `Like` clausola, non inserire alcun carattere nella posizione in questione.

    Nell'esempio seguente viene testato il numero di telefono a sette cifre `phoneNum` per esattamente tre cifre numeriche, seguito da uno spazio, un trattino ( `–` ), un punto ( `.` ) o nessun carattere, seguito da esattamente quattro cifre numeriche.

    [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]

## <a name="see-also"></a>Vedere anche

- [Operatori di confronto](../../../language-reference/operators/comparison-operators.md)
- [Operatori ed espressioni](index.md)
- [Operatore Like](../../../language-reference/operators/like-operator.md)
- [Tipo di dati String](../../../language-reference/data-types/string-data-type.md)

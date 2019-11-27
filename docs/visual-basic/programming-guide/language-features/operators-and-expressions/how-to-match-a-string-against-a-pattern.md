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
ms.openlocfilehash: 49328a72c2cff78b8fe13ca73209d224495ad7a1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343630"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>Procedura: confrontare una stringa con un modello (Visual Basic)

Se si vuole sapere se un'espressione del [tipo di dati stringa](../../../../visual-basic/language-reference/data-types/string-data-type.md) soddisfa un modello, è possibile usare l' [operatore like](../../../../visual-basic/language-reference/operators/like-operator.md).

`Like` accetta due operandi. L'operando sinistro è un'espressione stringa e l'operando di destra è una stringa contenente il modello da utilizzare per la corrispondenza. `Like` restituisce un valore `Boolean` che indica se l'espressione stringa soddisfa il modello.

È possibile trovare la corrispondenza di ogni carattere nell'espressione stringa con un carattere specifico, un carattere jolly, un elenco di caratteri o un intervallo di caratteri. Le posizioni delle specifiche nella stringa di pattern corrispondono alle posizioni dei caratteri per cui trovare una corrispondenza nell'espressione stringa.

## <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>Per trovare la corrispondenza con un carattere nell'espressione stringa con un carattere specifico

Inserire il carattere specifico direttamente nella stringa del modello. Alcuni caratteri speciali devono essere racchiusi tra parentesi quadre (`[ ]`). Per ulteriori informazioni, vedere [operatore like](../../../../visual-basic/language-reference/operators/like-operator.md).

Nell'esempio seguente viene verificato se `myString` è costituito esattamente dal carattere singolo `H`.

[!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]

## <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>Per trovare la corrispondenza con un carattere nell'espressione stringa con un carattere jolly

Inserire un punto interrogativo (`?`) nella stringa del modello. Qualsiasi carattere valido in questa posizione consente di trovare una corrispondenza corretta.

Nell'esempio seguente viene verificato se `myString` è costituito dal carattere singolo `W` seguito da esattamente due caratteri di qualsiasi valore.

[!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]

## <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>Per trovare la corrispondenza con un carattere nell'espressione stringa con un elenco di caratteri

Inserire le parentesi quadre (`[ ]`) nella stringa del modello e all'interno delle parentesi inserire l'elenco di caratteri. Non separare i caratteri con virgole o altri separatori. Qualsiasi carattere singolo nell'elenco esegue una corrispondenza corretta.

Nell'esempio seguente viene verificato se `myString` è costituito da qualsiasi carattere valido seguito da uno dei caratteri `A`, `C`o `E`.

[!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]

Si noti che questa corrispondenza fa distinzione tra maiuscole e minuscole.

## <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>Per trovare la corrispondenza con un carattere nell'espressione stringa con un intervallo di caratteri

Inserire le parentesi quadre (`[ ]`) nella stringa del modello e all'interno delle parentesi inserire i caratteri minimo e massimo nell'intervallo, separati da un trattino (`–`). Qualsiasi carattere singolo compreso nell'intervallo consente di trovare una corrispondenza corretta.

Nell'esempio seguente viene verificato se `myString` è costituito dai caratteri `num` seguito da uno dei caratteri `i`, `j`, `k`, `l`, `m`o `n`.

[!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]

Si noti che questa corrispondenza fa distinzione tra maiuscole e minuscole.

## <a name="matching-empty-strings"></a>Corrispondenza di stringhe vuote

`Like` considera la sequenza `[]` come stringa di lunghezza zero (`""`). È possibile utilizzare `[]` per verificare se l'intera espressione stringa è vuota, ma non è possibile utilizzarla per verificare se una particolare posizione nell'espressione stringa è vuota. Se una posizione vuota è una delle opzioni di cui è necessario eseguire il test, è possibile usare `Like` più di una volta.

### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>Per trovare la corrispondenza con un carattere nell'espressione stringa con un elenco di caratteri o nessun carattere

1. Chiamare l'operatore `Like` due volte sulla stessa espressione stringa e connettere le due chiamate con l' [operatore OR](../../../../visual-basic/language-reference/operators/or-operator.md) o l' [operatore OrElse](../../../../visual-basic/language-reference/operators/orelse-operator.md).

2. Nella stringa di modello per la prima clausola `Like`, includere l'elenco di caratteri racchiuso tra parentesi quadre (`[ ]`).

3. Nella stringa del criterio per la seconda clausola `Like`, non inserire alcun carattere nella posizione in questione.

    Nell'esempio seguente viene testato il numero di telefono a sette cifre `phoneNum` per esattamente tre cifre numeriche, seguite da uno spazio, un trattino (`–`), un punto (`.`) o nessun carattere, seguito da esattamente quattro cifre numeriche.

    [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]

## <a name="see-also"></a>Vedere anche

- [Operatori di confronto](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Operatori ed espressioni](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Operatore Like](../../../../visual-basic/language-reference/operators/like-operator.md)
- [Tipo di dati String](../../../../visual-basic/language-reference/data-types/string-data-type.md)

---
title: 'Procedura: creare una nuova variabile'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: 501c8f3aff4c5b204d231bdc26213e13d125a7cf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410529"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Procedura: creare una nuova variabile (Visual Basic)

Si crea una variabile con un' [istruzione Dim](../../../language-reference/statements/dim-statement.md).

### <a name="to-create-a-new-variable"></a>Per creare una nuova variabile

1. Dichiarare la variabile in un' `Dim` istruzione.

    ```vb
    Dim newCustomer
    ```

2. Includere le specifiche per le caratteristiche della variabile, ad esempio [private](../../../language-reference/modifiers/private.md), [static](../../../language-reference/modifiers/static.md), [Shadows](../../../language-reference/modifiers/shadows.md)o [WithEvents](../../../language-reference/modifiers/withevents.md). Per altre informazioni, vedere [caratteristiche degli elementi dichiarati](../declared-elements/declared-element-characteristics.md).

    ```vb
    Public Static newCustomer
    ```

    Non è necessaria la `Dim` parola chiave se si usano altre parole chiave nella dichiarazione.

3. Seguire le specifiche con il nome della variabile, che deve seguire Visual Basic regole e convenzioni. Per ulteriori informazioni, vedere [nomi di elementi dichiarati](../declared-elements/declared-element-names.md).

    ```vb
    Public Static newCustomer
    ```

4. Per specificare il tipo di dati della variabile, seguire il nome con la clausola [As](../../../language-reference/statements/as-clause.md) .

    ```vb
    Public Static newCustomer As Customer
    ```

    Se non si specifica il tipo di dati, verrà utilizzato il valore predefinito: `Object` .

5. Seguire la `As` clausola con un segno di uguale ( `=` ) e seguire il segno di uguale con il valore iniziale della variabile.

    Visual Basic assegna il valore specificato alla variabile ogni volta che viene eseguita l' `Dim` istruzione. Se non si specifica un valore iniziale, Visual Basic assegna il valore iniziale predefinito per il tipo di dati della variabile al momento dell'immissione del codice che contiene l' `Dim` istruzione.

    Se la variabile è un tipo riferimento, è possibile creare un'istanza della relativa classe includendo la parola chiave [new operator](../../../language-reference/operators/new-operator.md) nella `As` clausola. Se non si usa `New` , il valore iniziale della variabile è [Nothing](../../../language-reference/nothing.md).

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a>Vedere anche

- [Variabili](index.md)
- [Dichiarazione di variabile](variable-declaration.md)
- [Declared Element Names](../declared-elements/declared-element-names.md)
- [Caratteristiche di elementi dichiarati](../declared-elements/declared-element-characteristics.md)
- [Value Types and Reference Types](../data-types/value-types-and-reference-types.md)
- [Istruzioni](../../../language-reference/statements/index.md)
- [Inferenza del tipo di variabile locale](local-type-inference.md)
- [Option Infer (istruzione)](../../../language-reference/statements/option-infer-statement.md)

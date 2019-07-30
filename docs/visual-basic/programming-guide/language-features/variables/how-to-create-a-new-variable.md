---
title: 'Procedura: Crea una nuova variabile (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: a6cb7225ea203f0b38b731795684bfb0cfdfd2d1
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630895"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Procedura: Crea una nuova variabile (Visual Basic)

Si crea una variabile con un' [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).

### <a name="to-create-a-new-variable"></a>Per creare una nuova variabile

1. Dichiarare la variabile in un' `Dim` istruzione.

    ```vb
    Dim newCustomer
    ```

2. Includere le specifiche per le caratteristiche della variabile, ad esempio [private](../../../../visual-basic/language-reference/modifiers/private.md), [static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)o [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md). Per altre informazioni, vedere [caratteristiche degli elementi](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)dichiarati.

    ```vb
    Public Static newCustomer
    ```

    Non è necessaria la `Dim` parola chiave se si usano altre parole chiave nella dichiarazione.

3. Seguire le specifiche con il nome della variabile, che deve seguire Visual Basic regole e convenzioni. Per ulteriori informazioni, vedere [nomi di elementi](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)dichiarati.

    ```vb
    Public Static newCustomer
    ```

4. Per specificare il tipo di dati della variabile, seguire il nome con la clausola [As](../../../../visual-basic/language-reference/statements/as-clause.md) .

    ```vb
    Public Static newCustomer As Customer
    ```

    Se non si specifica il tipo di dati, verrà utilizzato il valore predefinito `Object`:.

5. Seguire la `As` clausola con un segno di uguale`=`() e seguire il segno di uguale con il valore iniziale della variabile.

    Visual Basic assegna il valore specificato alla variabile ogni volta che viene eseguita l' `Dim` istruzione. Se non si specifica un valore iniziale, Visual Basic assegna il valore iniziale predefinito per il tipo di dati della variabile al momento dell'immissione del codice che contiene l' `Dim` istruzione.

    Se la variabile è un tipo riferimento, è possibile creare un'istanza della relativa classe includendo la parola chiave [new operator](../../../../visual-basic/language-reference/operators/new-operator.md) nella `As` clausola. Se non si usa `New`, il valore iniziale della variabile è [Nothing](../../../../visual-basic/language-reference/nothing.md).

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a>Vedere anche

- [Variabili](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Istruzioni](../../../../visual-basic/language-reference/statements/index.md)
- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Istruzione Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)

---
title: 'Procedura: Mantieni più di un valore in una variabile (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: 8d07a34a98303f9d220dba0a3c955120b421340e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054190"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a>Procedura: Mantieni più di un valore in una variabile (Visual Basic)

Una variabile include più di un valore se lo si dichiara come *tipo di dati composito*.

[I tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) includono strutture, matrici e classi. Una variabile di un tipo di dati composito può avere una combinazione di tipi di dati elementari e altri tipi compositi. Le strutture e le classi possono conservare il codice e i dati.

## <a name="to-hold-more-than-one-value-in-a-variable"></a>Per conservare più di un valore in una variabile

1. Determinare il tipo di dati composito che si desidera utilizzare per la variabile.

2. Se il tipo di dati composito non è già definito, definirlo in modo che possa essere utilizzato dalla variabile.

    - Definire una struttura con un' [istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md).

    - Definire una matrice con un' [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).

    - Definire una classe con un' [istruzione di classe](../../../../visual-basic/language-reference/statements/class-statement.md).

3. Dichiarare la variabile con un' `Dim` istruzione.

4. Seguire il nome della variabile con `As` una clausola.

5. Seguire la `As` parola chiave con il nome del tipo di dati composito appropriato.

## <a name="see-also"></a>Vedere anche

- [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md)
- [Caratteri tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)

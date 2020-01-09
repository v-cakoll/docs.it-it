---
title: 'Procedura: dichiarare una variabile oggetto e assegnarvi un oggetto'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: eaaeda2a986584e6e1a2e0d2cda3890fb6187598
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344239"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>Procedura: dichiarare una variabile oggetto e assegnarle un oggetto in Visual Basic

Per dichiarare una variabile del [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) , è necessario specificare `As Object` in un' [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md). Per assegnare un oggetto a una variabile di questo tipo, inserire l'oggetto dopo il segno di uguale (`=`) in un'istruzione di assegnazione o in una clausola di inizializzazione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene dichiarata una variabile di `Object` a cui viene assegnata l'istanza corrente.

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

È possibile combinare la dichiarazione e l'assegnazione inizializzando la variabile come parte della relativa dichiarazione. L'esempio seguente è equivalente all'esempio precedente.

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compile-the-code"></a>Compilare il codice

L'esempio presenta i requisiti seguenti:

- Un riferimento allo spazio dei nomi <xref:System>.

- Una classe, una struttura o un modulo in cui inserire l'istruzione `Dim`.

- Routine in cui inserire l'istruzione di assegnazione.

## <a name="see-also"></a>Vedere anche

- [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Dichiarazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)

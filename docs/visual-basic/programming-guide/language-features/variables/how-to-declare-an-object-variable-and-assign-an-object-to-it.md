---
title: 'Procedura: dichiarare una variabile oggetto e assegnarvi un oggetto'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 4cfad1d820b584d4610d24c392b14ac3958471b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352900"
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

## <a name="compiling-the-code"></a>Compilazione del codice

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

---
title: 'Procedura: dichiarare una variabile oggetto e assegnarle un oggetto'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: d9a8c1fb30bfa5988d48202e41202e7ede0f5f27
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410503"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>Procedura: dichiarare una variabile oggetto e assegnarle un oggetto in Visual Basic

Per dichiarare una variabile del [tipo di dati Object](../../../language-reference/data-types/object-data-type.md) , è necessario specificare `As Object` in un' [istruzione Dim](../../../language-reference/statements/dim-statement.md). Per assegnare un oggetto a una variabile di questo tipo, inserire l'oggetto dopo il segno di uguale ( `=` ) in un'istruzione di assegnazione o in una clausola di inizializzazione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene dichiarata una `Object` variabile a cui viene assegnata l'istanza corrente.

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

- Classe, struttura o modulo in cui inserire l' `Dim` istruzione.

- Routine in cui inserire l'istruzione di assegnazione.

## <a name="see-also"></a>Vedere anche

- [Dichiarazione di variabile](variable-declaration.md)
- [Variabili oggetto](object-variables.md)
- [Dichiarazione di variabili oggetto](object-variable-declaration.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Istruzione Dim](../../../language-reference/statements/dim-statement.md)
- [Inferenza del tipo di variabile locale](local-type-inference.md)
- [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)

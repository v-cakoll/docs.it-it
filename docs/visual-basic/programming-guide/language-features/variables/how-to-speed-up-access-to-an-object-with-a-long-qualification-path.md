---
title: "Procedura: velocizzare l'accesso a un oggetto con un percorso di qualificazione lungo"
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: fe93e7bac2a21f1060d1f93765eb35e1ad0c7eb0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410412"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>Procedura: velocizzare l'accesso a un oggetto con un percorso di qualificazione lungo (Visual Basic)

Se si accede di frequente a un oggetto che richiede un percorso di qualificazione di diversi metodi e proprietà, è possibile velocizzare il codice non ripetendo il percorso di qualificazione.

Esistono due modi per evitare di ripetere il percorso di qualificazione. È possibile assegnare l'oggetto a una variabile oppure è possibile usarlo in un `With` blocco... `End With` .

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a>Per velocizzare l'accesso a un oggetto altamente qualificato, assegnarlo a una variabile

1. Dichiarare una variabile del tipo di oggetto a cui si accede di frequente. Specificare il percorso di qualificazione nella parte di inizializzazione della dichiarazione.

    ```vb
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl
    ```

2. Utilizzare la variabile per accedere ai membri dell'oggetto.

    ```vb
    ctrlActv.Text = "Test"
    ctrlActv.Location = New Point(100, 100)
    ctrlActv.Show()
    ```

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a>Per velocizzare l'accesso a un oggetto altamente qualificato usando un con... Termina con blocco

1. Inserire il percorso di qualificazione in un' `With` istruzione.

    ```vb
    With someForm.ActiveForm.ActiveControl
    ```

2. Accedere ai membri dell'oggetto all'interno del `With` blocco, prima dell' `End With` istruzione.

    ```vb
        .Text = "Test"
        .Location = New Point(100, 100)
        .Show()
    End With
    ```

## <a name="see-also"></a>Vedere anche

- [Variabili oggetto](object-variables.md)
- [Istruzione With...End With](../../../language-reference/statements/with-end-with-statement.md)

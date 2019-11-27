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
ms.openlocfilehash: 83670ae6af0904156b08398024658cf504b7663f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346823"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>Procedura: velocizzare l'accesso a un oggetto con un percorso di qualificazione lungo (Visual Basic)

Se si accede di frequente a un oggetto che richiede un percorso di qualificazione di diversi metodi e proprietà, è possibile velocizzare il codice non ripetendo il percorso di qualificazione.

Esistono due modi per evitare di ripetere il percorso di qualificazione. È possibile assegnare l'oggetto a una variabile oppure è possibile usarlo in un blocco `With`...`End With`.

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

1. Inserire il percorso di qualificazione in un'istruzione `With`.

    ```vb
    With someForm.ActiveForm.ActiveControl
    ```

2. Accedere ai membri dell'oggetto all'interno del blocco `With`, prima dell'istruzione `End With`.

    ```vb
        .Text = "Test"
        .Location = New Point(100, 100)
        .Show()
    End With
    ```

## <a name="see-also"></a>Vedere anche

- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Istruzione With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)

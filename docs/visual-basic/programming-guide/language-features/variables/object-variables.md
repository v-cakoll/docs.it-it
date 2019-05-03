---
title: Variabili oggetto in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: cc5be13293a89e73d1790e94a99d7936f1711e12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961234"
---
# <a name="object-variables-in-visual-basic"></a>Variabili oggetto in Visual Basic

Oltre ad archiviare i valori direttamente, una variabile può fare riferimento a un oggetto. Si assegna un oggetto a una variabile per gli stessi motivi che si assegna un valore a una variabile:

- Un nome di variabile è spesso più breve e facile da ricordare rispetto al percorso completo di metodi e proprietà necessarie per accedere all'oggetto stesso.

- Utilizzo di una variabile che fa riferimento a un oggetto è più efficiente ripetutamente l'accesso all'oggetto stesso tramite i metodi necessari o proprietà.

- È possibile modificare una variabile per fare riferimento ad altri oggetti durante l'esecuzione di codice.

## <a name="making-code-shorter"></a>Abbreviazione del codice

È possibile usare le variabili oggetto per abbreviare il codice da digitare. L'esempio seguente usa il percorso completo di proprietà e metodi per accedere a un <xref:System.Windows.Forms.Control> oggetto.

```vb
' Assume Me is a valid Form, or replace Me with a valid Form.
Me.ActiveForm.ActiveControl.Text = "Test"
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)
Me.ActiveForm.ActiveControl.Show()
```

È possibile abbreviare questo codice e aumentare la velocità di esecuzione, se si usa una variabile oggetto per il controllo. È necessario dichiarare la variabile oggetto con la classe specifica che si intende assegnare ad esso (`Control` in questo caso). Una volta che si assegna un oggetto alla variabile, è possibile trattare l'esattamente come si considera l'oggetto a cui viene fatto riferimento. È possibile impostare o recuperare le proprietà dell'oggetto o usare uno qualsiasi dei relativi metodi. Nell'esempio seguente usa una variabile oggetto per semplificare il codice nell'esempio precedente.

```vb
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl
ctrlActv.Text = "Test"
ctrlActv.Location = New Point(100, 100)
ctrlActv.Show()
```

## <a name="see-also"></a>Vedere anche

- [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Procedura: Velocizzare l'accesso a un oggetto con un percorso di qualificazione lungo](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [Dichiarazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Assegnazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Valori di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)

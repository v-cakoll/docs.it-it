---
title: Variabili oggetto
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: a5e61f9308d3484dc228a7d09cc2fd30a2f41b35
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410335"
---
# <a name="object-variables-in-visual-basic"></a>Variabili oggetto in Visual Basic

Oltre a archiviare direttamente i valori, una variabile può fare riferimento a un oggetto. Si assegna un oggetto a una variabile per gli stessi motivi per cui si assegna un valore a una variabile:

- Un nome di variabile è spesso più breve e più facile da ricordare rispetto al percorso completo dei metodi e delle proprietà necessari per accedere all'oggetto stesso.

- L'uso di una variabile che fa riferimento a un oggetto è più efficiente rispetto all'accesso ripetuto ripetutamente all'oggetto tramite le proprietà o i metodi necessari.

- È possibile modificare una variabile in modo che faccia riferimento ad altri oggetti mentre il codice è in esecuzione.

## <a name="making-code-shorter"></a>Creazione di codice più breve

È possibile utilizzare le variabili oggetto per abbreviare il codice che è necessario digitare. Nell'esempio seguente viene usato il percorso completo dei metodi e delle proprietà per accedere a un <xref:System.Windows.Forms.Control> oggetto.

```vb
' Assume Me is a valid Form, or replace Me with a valid Form.
Me.ActiveForm.ActiveControl.Text = "Test"
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)
Me.ActiveForm.ActiveControl.Show()
```

È possibile abbreviare questo codice e velocizzare l'esecuzione, se si usa una variabile oggetto per il controllo. È necessario dichiarare la variabile oggetto con la classe specifica a cui si desidera assegnarla ( `Control` in questo caso). Una volta assegnato un oggetto alla variabile, è possibile considerarlo esattamente come si tratta dell'oggetto a cui fa riferimento. È possibile impostare o recuperare le proprietà dell'oggetto o utilizzare uno dei relativi metodi. Nell'esempio seguente viene usata una variabile oggetto per semplificare il codice nell'esempio precedente.

```vb
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl
ctrlActv.Text = "Test"
ctrlActv.Location = New Point(100, 100)
ctrlActv.Show()
```

## <a name="see-also"></a>Vedere anche

- [Dichiarazione di variabile](variable-declaration.md)
- [Procedura: velocizzare l'accesso a un oggetto con un percorso di qualificazione lungo](how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [Dichiarazione di variabili oggetto](object-variable-declaration.md)
- [Assegnazione di variabili oggetto](object-variable-assignment.md)
- [Valori di variabili oggetto](object-variable-values.md)

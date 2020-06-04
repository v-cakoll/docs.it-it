---
title: L'espressione è un valore, quindi non può essere la destinazione di un'assegnazione
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: 9e4dbaf2f2800454c673cd58ddec4cf0f6e5c6b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409507"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a>L'espressione è un valore, quindi non può essere la destinazione di un'assegnazione

Un'istruzione tenta di assegnare un valore a un'espressione. È possibile assegnare un valore solo a una variabile scrivibile, a una proprietà o a un elemento di matrice in fase di esecuzione. Nell'esempio seguente viene illustrato come può verificarsi l'errore.

```vb
Dim yesterday As Integer
ReadOnly maximum As Integer = 45
yesterday + 1 = DatePart(DateInterval.Day, Now)
' The preceding line is an ERROR because of an expression on the left.
maximum = 50
' The preceding line is an ERROR because maximum is declared ReadOnly.
```

Esempi simili possono essere applicati alle proprietà e agli elementi di matrice.

**Accesso indiretto.** L'accesso indiretto tramite un tipo di valore può anche generare questo errore. Si consideri l'esempio di codice seguente, che tenta di impostare il valore di <xref:System.Drawing.Point> accedendo indirettamente tramite <xref:System.Windows.Forms.Control.Location%2A> .

```vb
' Assume this code runs inside Form1.
Dim exitButton As New System.Windows.Forms.Button()
exitButton.Text = "Exit this form"
exitButton.Location.X = 140
' The preceding line is an ERROR because of no storage for Location.
```

L'ultima istruzione dell'esempio precedente ha esito negativo perché crea solo un'allocazione temporanea per la <xref:System.Drawing.Point> struttura restituita dalla <xref:System.Windows.Forms.Control.Location%2A> Proprietà. Una struttura è un tipo di valore e la struttura temporanea non viene mantenuta dopo l'esecuzione dell'istruzione. Il problema viene risolto dichiarando e utilizzando una variabile per <xref:System.Windows.Forms.Control.Location%2A> , che consente di creare un'allocazione più permanente per la <xref:System.Drawing.Point> struttura. Nell'esempio seguente viene illustrato il codice in grado di sostituire l'ultima istruzione dell'esempio precedente.

```vb
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)
exitButton.Location = exitLocation
```

**ID errore:** BC30068

## <a name="to-correct-this-error"></a>Per correggere l'errore

- Se l'istruzione assegna un valore a un'espressione, sostituire l'espressione con una singola variabile scrivibile, una proprietà o un elemento di matrice.

- Se l'istruzione consente l'accesso indiretto tramite un tipo di valore (in genere una struttura), creare una variabile che contenga il tipo di valore.

- Assegnare la struttura appropriata (o un altro tipo di valore) alla variabile.

- Utilizzare la variabile per accedere alla proprietà per assegnarle un valore.

## <a name="see-also"></a>Vedere anche

- [Operatori ed espressioni](../../programming-guide/language-features/operators-and-expressions/index.md)
- [Istruzioni](../../programming-guide/language-features/statements.md)
- [Risoluzione dei problemi relativi alle routine](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)

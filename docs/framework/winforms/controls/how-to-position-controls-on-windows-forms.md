---
title: 'Procedura: posizionare i controlli in Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: bb57d14397a4626e01c41dd687dfed7331282a10
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458334"
---
# <a name="how-to-position-controls-on-windows-forms"></a>Procedura: posizionare i controlli in Windows Forms

Per posizionare i controlli, usare il Progettazione Windows Form in Visual Studio o specificare la proprietà <xref:System.Windows.Forms.Control.Location%2A>.

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Posizionare un controllo nell'area di progettazione dell'Progettazione Windows Form

In Visual Studio trascinare il controllo nella posizione appropriata con il mouse.

> [!NOTE]
> Selezionare il controllo e spostarlo con i tasti di direzione per posizionarlo più precisamente. Inoltre, le guide di *allineamento* facilitano l'inserimento di controlli con precisione nel form. Per ulteriori informazioni, vedere [procedura dettagliata: disposizione dei controlli su Windows Forms mediante guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).

## <a name="position-a-control-using-the-properties-window"></a>Posizionare un controllo usando il Finestra Proprietà

1. In Visual Studio selezionare il controllo che si vuole posizionare.

2. Nella finestra **Proprietà** immettere i valori per la proprietà <xref:System.Windows.Forms.Control.Location%2A>, separati da una virgola, per posizionare il controllo all'interno del relativo contenitore.

   Il primo numero (X) è la distanza dal bordo sinistro del contenitore; il secondo numero (Y) è la distanza dal bordo superiore dell'area del contenitore, misurata in pixel.

   > [!NOTE]
   > È possibile espandere la proprietà <xref:System.Windows.Forms.Control.Location%2A> per digitare singolarmente i valori **X** e **Y** .

## <a name="position-a-control-programmatically"></a>Posizionare un controllo a livello di codice

1. Impostare la proprietà <xref:System.Windows.Forms.Control.Location%2A> del controllo su una <xref:System.Drawing.Point>.

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. Modificare la coordinata X della posizione del controllo utilizzando la sottoproprietà <xref:System.Windows.Forms.Control.Left%2A>.

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a>Incrementa la posizione di un controllo a livello di codice

Impostare la sottoproprietà <xref:System.Windows.Forms.Control.Left%2A> per incrementare la coordinata X del controllo.

```vb
Button1.Left += 200
```

```csharp
button1.Left += 200;
```

```cpp
button1->Left += 200;
```

> [!NOTE]
> Utilizzare la proprietà <xref:System.Windows.Forms.Control.Location%2A> per impostare contemporaneamente le posizioni X e Y di un controllo. Per impostare una posizione singolarmente, utilizzare la sottoproprietà <xref:System.Windows.Forms.Control.Left%2A> (**X**) o <xref:System.Windows.Forms.Control.Top%2A> (**Y**) del controllo. Non tentare di impostare in modo implicito le coordinate X e Y della struttura <xref:System.Drawing.Point> che rappresenta la posizione del pulsante, perché questa struttura contiene una copia delle coordinate del pulsante.

## <a name="see-also"></a>Vedere anche

- [Controlli Windows Form](index.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: disposizione dei controlli in Windows Form usando FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
- [Procedura: impostare la posizione dello schermo di Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))

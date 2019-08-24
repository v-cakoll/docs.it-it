---
title: 'Procedura: Posizionare i controlli in Windows Forms'
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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1cc2cb4c749b7290a6edf914a8e6a697006ef43c
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987071"
---
# <a name="how-to-position-controls-on-windows-forms"></a>Procedura: Posizionare i controlli su Windows Forms

Per posizionare i controlli, usare il progettazione Windows Form in Visual Studio o specificare <xref:System.Windows.Forms.Control.Location%2A> la proprietà.

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Posizionare un controllo nell'area di progettazione dell'Progettazione Windows Form

In Visual Studio trascinare il controllo nella posizione appropriata con il mouse.

> [!NOTE]
> Selezionare il controllo e spostarlo con i tasti di direzione per posizionarlo più precisamente. Inoltre, le guide di *allineamento* facilitano l'inserimento di controlli con precisione nel form. Per altre informazioni, vedere [Procedura dettagliata: Disposizione di controlli su Windows Forms mediante guide](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)di allineamento.

## <a name="position-a-control-using-the-properties-window"></a>Posizionare un controllo usando il Finestra Proprietà

1. In Visual Studio selezionare il controllo che si vuole posizionare.

2. Nella finestra **Proprietà** immettere i valori per la <xref:System.Windows.Forms.Control.Location%2A> proprietà, separati da una virgola, per posizionare il controllo all'interno del relativo contenitore.

   Il primo numero (X) è la distanza dal bordo sinistro del contenitore; il secondo numero (Y) è la distanza dal bordo superiore dell'area del contenitore, misurata in pixel.

   > [!NOTE]
   > È possibile espandere la <xref:System.Windows.Forms.Control.Location%2A> proprietà per digitare singolarmente i valori **X** e **Y** .

## <a name="position-a-control-programmatically"></a>Posizionare un controllo a livello di codice

1. Impostare la <xref:System.Windows.Forms.Control.Location%2A> proprietà del controllo <xref:System.Drawing.Point>su.

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. Modificare la coordinata X della posizione del controllo utilizzando <xref:System.Windows.Forms.Control.Left%2A> la sottoproprietà.

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

Impostare la <xref:System.Windows.Forms.Control.Left%2A> sottoproprietà per incrementare la coordinata X del controllo.

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
> Utilizzare la <xref:System.Windows.Forms.Control.Location%2A> proprietà per impostare le posizioni X e Y di un controllo simultaneamente. Per impostare una posizione singolarmente, utilizzare la sottoproprietà del controllo <xref:System.Windows.Forms.Control.Left%2A> ( <xref:System.Windows.Forms.Control.Top%2A> **X**) o (**Y**). Non tentare di impostare in modo implicito le coordinate X e Y della <xref:System.Drawing.Point> struttura che rappresenta la posizione del pulsante, perché questa struttura contiene una copia delle coordinate del pulsante.

## <a name="see-also"></a>Vedere anche

- [Controlli Windows Form](index.md)
- [Procedura dettagliata: Disposizione di controlli in Windows Forms mediante guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Procedura dettagliata: Disposizione di controlli in Windows Forms tramite TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: Disposizione di controlli in Windows Forms tramite FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
- [Procedura: Imposta la posizione dello schermo di Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))

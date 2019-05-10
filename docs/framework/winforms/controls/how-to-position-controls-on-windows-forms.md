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
ms.openlocfilehash: 241edbe60c327493c9123c6cf7bdc19b7ba2b724
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211645"
---
# <a name="how-to-position-controls-on-windows-forms"></a>Procedura: Posizionare i controlli in Windows Forms

Per posizionare i controlli, usare la finestra di progettazione Windows Form in Visual Studio o specificare il <xref:System.Windows.Forms.Control.Location%2A> proprietà.

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Posizionare un controllo nell'area di progettazione della finestra di progettazione Windows Form

In Visual Studio, trascinare il controllo nella posizione appropriata con il mouse.

> [!NOTE]
> Selezionare il controllo e spostarsi che con la freccia tasti di direzione per un posizionamento più preciso. È inoltre *guide di allineamento* supporto per il posizionamento preciso dei controlli nel form. Per altre informazioni, vedere [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).

## <a name="position-a-control-using-the-properties-window"></a>Posizionare un controllo usando la finestra proprietà

1. In Visual Studio, fare clic sul controllo che si desidera posizionare.

2. Nel **delle proprietà** finestra, i valori di tipo per il <xref:System.Windows.Forms.Control.Location%2A> proprietà, separati da una virgola, per posizionare il controllo all'interno del contenitore.

     Il primo numero (X) rappresenta la distanza dal bordo sinistro del contenitore; il secondo numero (Y) è la distanza dal bordo superiore dell'area del contenitore, misurato in pixel.

    > [!NOTE]
    > È possibile espandere la <xref:System.Windows.Forms.Control.Location%2A> proprietà digitare il **X** e **Y** valori singolarmente.

## <a name="position-a-control-programmatically"></a>Posizionare un controllo a livello di codice

1. Impostare il <xref:System.Windows.Forms.Control.Location%2A> proprietà del controllo da un <xref:System.Drawing.Point>.

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. Modificare la coordinata X della posizione del controllo utilizzando il <xref:System.Windows.Forms.Control.Left%2A> sottoproprietà.

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

Impostare il <xref:System.Windows.Forms.Control.Left%2A> sottoproprietà per incrementare la coordinata X del controllo.

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
> Usare il <xref:System.Windows.Forms.Control.Location%2A> contemporaneamente le posizioni di proprietà da impostare X e Y di un controllo. Per impostare una posizione individualmente, usare il controllo <xref:System.Windows.Forms.Control.Left%2A> (**X**) oppure <xref:System.Windows.Forms.Control.Top%2A> (**Y**) delle sottoproprietà. Non provare a impostare in modo implicito le coordinate X e Y del <xref:System.Drawing.Point> struttura che rappresenta la posizione del pulsante, perché questa struttura contiene una copia di coordinate del pulsante.

## <a name="see-also"></a>Vedere anche

- [Controlli Windows Form](index.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Disposizione di controlli in Windows Form](arranging-controls-on-windows-forms.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
- [Procedura: Impostare la posizione dello schermo dei Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))

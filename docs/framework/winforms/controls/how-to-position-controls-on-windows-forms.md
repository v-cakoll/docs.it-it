---
title: Posizionare i controlli
description: Informazioni su come usare la Progettazione Windows Form in Visual Studio o la proprietà Location per posizionare i controlli.
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
ms.openlocfilehash: 0aa3faade71e0f7e0a9d5e676327a80747524b8c
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904299"
---
# <a name="how-to-position-controls-on-windows-forms"></a>Procedura: posizionare i controlli in Windows Forms

Per posizionare i controlli, usare il Progettazione Windows Form in Visual Studio o specificare la <xref:System.Windows.Forms.Control.Location%2A> Proprietà.

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Posizionare un controllo nell'area di progettazione dell'Progettazione Windows Form

In Visual Studio trascinare il controllo nella posizione appropriata con il mouse.

> [!NOTE]
> Selezionare il controllo e spostarlo con i tasti di direzione per posizionarlo più precisamente. Inoltre, le guide di *allineamento* facilitano l'inserimento di controlli con precisione nel form. Per ulteriori informazioni, vedere [procedura dettagliata: disposizione dei controlli su Windows Forms mediante guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).

## <a name="position-a-control-using-the-properties-window"></a>Posizionare un controllo usando il Finestra Proprietà

1. In Visual Studio selezionare il controllo che si vuole posizionare.

2. Nella finestra **Proprietà** immettere i valori per la <xref:System.Windows.Forms.Control.Location%2A> proprietà, separati da una virgola, per posizionare il controllo all'interno del relativo contenitore.

   Il primo numero (X) è la distanza dal bordo sinistro del contenitore; il secondo numero (Y) è la distanza dal bordo superiore dell'area del contenitore, misurata in pixel.

   > [!NOTE]
   > È possibile espandere la <xref:System.Windows.Forms.Control.Location%2A> proprietà per digitare singolarmente i valori **X** e **Y** .

## <a name="position-a-control-programmatically"></a>Posizionare un controllo a livello di codice

1. Impostare la <xref:System.Windows.Forms.Control.Location%2A> proprietà del controllo su <xref:System.Drawing.Point> .

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. Modificare la coordinata X della posizione del controllo utilizzando la <xref:System.Windows.Forms.Control.Left%2A> sottoproprietà.

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
> Utilizzare la <xref:System.Windows.Forms.Control.Location%2A> proprietà per impostare le posizioni X e Y di un controllo simultaneamente. Per impostare una posizione singolarmente, utilizzare la <xref:System.Windows.Forms.Control.Left%2A> sottoproprietà del controllo (**X**) o <xref:System.Windows.Forms.Control.Top%2A> (**Y**). Non tentare di impostare in modo implicito le coordinate X e Y della <xref:System.Drawing.Point> struttura che rappresenta la posizione del pulsante, perché questa struttura contiene una copia delle coordinate del pulsante.

## <a name="see-also"></a>Vedere anche

- [Controlli di Windows Forms](index.md)
- [Procedura dettagliata: disposizione dei controlli in Windows Form utilizzando guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: disposizione dei controlli in Windows Form usando FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controlli da utilizzare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
- [Procedura: impostare la posizione dello schermo di Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))

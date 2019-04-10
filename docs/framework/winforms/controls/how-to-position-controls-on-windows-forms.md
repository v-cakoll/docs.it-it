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
ms.openlocfilehash: a0b97073b2f9363a64bfc4a4ede7ffa69e2bce42
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59334003"
---
# <a name="how-to-position-controls-on-windows-forms"></a>Procedura: Posizionare i controlli in Windows Forms
Per posizionare i controlli, usare Progettazione Windows Form o specificare il <xref:System.Windows.Forms.Control.Location%2A> proprietà.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Per posizionare un controllo nell'area di progettazione della finestra di progettazione Windows Form  
  
-   Trascinare il controllo nella posizione appropriata con il mouse.  
  
    > [!NOTE]
    >  Selezionare il controllo e spostarsi che con la freccia tasti di direzione per un posizionamento più preciso. È inoltre *guide di allineamento* supporto per il posizionamento preciso dei controlli nel form. Per altre informazioni, vedere [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
### <a name="to-position-a-control-using-the-properties-window"></a>Per posizionare un controllo usando la finestra proprietà  
  
1. Fare clic sul controllo che si desidera posizionare.  
  
2. Nel **delle proprietà** finestra, i valori di tipo per il <xref:System.Windows.Forms.Control.Location%2A> proprietà, separati da una virgola, per posizionare il controllo all'interno del contenitore.  
  
     Il primo numero (X) rappresenta la distanza dal bordo sinistro del contenitore; il secondo numero (Y) è la distanza dal bordo superiore dell'area del contenitore, misurato in pixel.  
  
    > [!NOTE]
    >  È possibile espandere la <xref:System.Windows.Forms.Control.Location%2A> proprietà digitare il **X** e **Y** valori singolarmente.  
  
### <a name="to-position-a-control-programmatically"></a>Per posizionare un controllo a livello di codice  
  
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
  
### <a name="to-increment-a-controls-location-programmatically"></a>Per incrementare la posizione di un controllo a livello di codice  
  
1. Impostare il <xref:System.Windows.Forms.Control.Left%2A> sottoproprietà per incrementare la coordinata X del controllo.  
  
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
    >  Usare il <xref:System.Windows.Forms.Control.Location%2A> contemporaneamente le posizioni di proprietà da impostare X e Y di un controllo. Per impostare una posizione individualmente, usare il controllo <xref:System.Windows.Forms.Control.Left%2A> (**X**) oppure <xref:System.Windows.Forms.Control.Top%2A> (**Y**) delle sottoproprietà. Non provare a impostare in modo implicito le coordinate X e Y del <xref:System.Drawing.Point> struttura che rappresenta la posizione del pulsante, perché questa struttura contiene una copia di coordinate del pulsante.  
  
## <a name="see-also"></a>Vedere anche

- [Controlli per Windows Form](index.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Forms usando le guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Forms usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Forms usando FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Disposizione di controlli in Windows Form](arranging-controls-on-windows-forms.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
- [Procedura: Impostare la posizione dello schermo dei Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))

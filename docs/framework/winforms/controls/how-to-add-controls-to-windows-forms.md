---
title: Aggiungere controlli
description: Informazioni su come creare un controllo in un Windows Form. Un controllo è un componente di un modulo che è possibile usare per visualizzare informazioni o accettare l'input dell'utente.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: d9ab0d78fa0153cce20fb17d22f6e9e781229ece
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325879"
---
# <a name="how-to-add-controls-to-windows-forms"></a>Procedura: aggiungere controlli a un Windows Form

La maggior parte dei moduli è progettata mediante l'aggiunta di controlli all'area del form per definire un'interfaccia utente (UI). Un *controllo* è un componente di un form usato per visualizzare informazioni o accettare l'input dell'utente. Per ulteriori informazioni sui controlli, vedere [controlli Windows Forms](index.md).

## <a name="to-draw-a-control-on-a-form"></a>Per creare un controllo in un form

1. Aprire il modulo. Per altre informazioni, vedere [procedura: visualizzare Windows Forms nella finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).

2. Nella **casella degli strumenti**fare clic sul controllo che si desidera aggiungere al form.

3. Nel modulo, fare clic su dove si desidera posizionare l'angolo superiore sinistro del controllo e trascinare verso il punto in cui si desidera posizionare l'angolo inferiore destro del controllo.

    Il controllo viene aggiunto al form con la posizione e le dimensioni specificate.

    > [!NOTE]
    > Ogni controllo ha una dimensione predefinita definita. È possibile aggiungere un controllo al form nelle dimensioni predefinite del controllo trascinandoli dalla **casella degli strumenti** nel form.

## <a name="to-drag-a-control-to-a-form"></a>Per trascinare un controllo in un form

1. Aprire il modulo. Per altre informazioni, vedere [procedura: visualizzare Windows Forms nella finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).

2. Nella **casella degli strumenti**fare clic sul controllo desiderato e trascinarlo nel form.

    Il controllo viene aggiunto al form in corrispondenza della posizione specificata nelle dimensioni predefinite.

    > [!NOTE]
    > È possibile fare doppio clic su un controllo nella **casella degli strumenti** per aggiungerlo all'angolo superiore sinistro del form in base alle dimensioni predefinite.

    È anche possibile aggiungere controlli in modo dinamico a un modulo in fase di esecuzione. Nell'esempio di codice seguente viene <xref:System.Windows.Forms.TextBox> aggiunto un controllo al form quando <xref:System.Windows.Forms.Button> si fa clic su un controllo.

    > [!NOTE]
    > La procedura seguente richiede l'esistenza di un form con un controllo **Button** , `Button1` , già inserito.

## <a name="to-add-a-control-to-a-form-programmatically"></a>Per aggiungere un controllo a un modulo a livello di codice

1. Nel metodo che gestisce l'evento del pulsante `Click` all'interno della classe del form, inserire codice simile al seguente per aggiungere un riferimento alla variabile di controllo, impostare l'oggetto del controllo `Location` e aggiungere il controllo.

    ```vb
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
       Dim MyText As New TextBox()
       MyText.Location = New Point(25, 25)
       Me.Controls.Add(MyText)
    End Sub
    ```

    ```csharp
    private void button1_Click(object sender, System.EventArgs e)
    {
       TextBox myText = new TextBox();
       myText.Location = new Point(25,25);
       this.Controls.Add (myText);
    }
    ```

    ```cpp
    private:
      System::Void button1_Click(System::Object ^  sender,
        System::EventArgs ^  e)
      {
        TextBox ^ myText = gcnew TextBox();
        myText->Location = Point(25,25);
        this->Controls->Add(myText);
      }
    ```

    > [!NOTE]
    > È anche possibile aggiungere codice per inizializzare altre proprietà del controllo.

    > [!IMPORTANT]
    > È possibile esporre il computer locale a un rischio di sicurezza attraverso la rete facendo riferimento a un dannoso `UserControl` . Questo potrebbe costituire un problema solo nel caso di un utente malintenzionato che crea un controllo personalizzato dannoso, seguito da un'operazione erroneamente aggiunta al progetto.

## <a name="see-also"></a>Vedi anche

- [Controlli di Windows Forms](index.md)
- [Procedura: ridimensionare i controlli di un Windows Form](how-to-resize-controls-on-windows-forms.md)
- [Procedura: impostare il testo visualizzato da un controllo di Windows Form](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Controlli da utilizzare in Windows Form](controls-to-use-on-windows-forms.md)

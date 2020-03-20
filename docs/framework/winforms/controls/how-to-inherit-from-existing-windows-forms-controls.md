---
title: Ereditare da controlli esistenti
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: b0e0053816efde349c7e4d13d03bef5f8801c667
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849380"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>Procedura: ereditare da controlli di Windows Form esistenti

Se si desidera estendere le funzionalità di un controllo esistente, è possibile creare un controllo derivato da un controllo esistente tramite l'ereditarietà. Quando si eredita da un controllo esistente, si ereditano tutte le funzionalità e le proprietà visive di tale controllo. Ad esempio, se si crea un <xref:System.Windows.Forms.Button>controllo ereditato da , il nuovo <xref:System.Windows.Forms.Button> controllo avrebbe l'aspetto e si comporterebbe esattamente come un controllo standard. È quindi possibile estendere o modificare la funzionalità del nuovo controllo tramite l'implementazione di metodi e proprietà personalizzati. In alcuni controlli è inoltre possibile modificare l'aspetto visivo <xref:System.Windows.Forms.Control.OnPaint%2A> del controllo ereditato eseguendo l'override del relativo metodo.

## <a name="to-create-an-inherited-control"></a>Per creare un controllo ereditato

1. In Visual Studio creare un nuovo progetto **applicazione Windows Form.In Visual** Studio, create a new Windows Forms Application project.

1. Dal menu **Progetto**, scegliere **Aggiungi nuovo elemento**.

    Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento** .

1. Nella finestra di dialogo **Aggiungi nuovo elemento**, fare doppio clic su **Controllo personalizzato**.

    Un nuovo controllo personalizzato viene aggiunto al progetto.

1. Se si utilizza:

    - Visual Basic, nella parte superiore di **Esplora soluzioni**, fare clic su **Mostra tutti i file**. Espandere CustomControl1.vb e quindi aprire Customcontrol1 nell'Editor di codice.
    - aprire CustomControl1.cs nell'editor di codice.

1. Individuare la dichiarazione di <xref:System.Windows.Forms.Control>classe , che eredita da .

1. Modificare la classe di base per il controllo da cui si desidera ereditare.

     Ad esempio, se si <xref:System.Windows.Forms.Button>desidera ereditare da , modificare la dichiarazione di classe nel modo seguente:

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. Se si usa Visual Basic, salvare e chiudere CustomControl1.Designer.vb. Aprire Customcontrol1.vb nell'Editor di codice.

1. Implementare eventuali metodi o proprietà personalizzati da incorporare nel controllo.

1. Se si desidera modificare l'aspetto grafico <xref:System.Windows.Forms.Control.OnPaint%2A> del controllo, eseguire l'override del metodo .

    > [!NOTE]
    > L'override <xref:System.Windows.Forms.Control.OnPaint%2A> non consente di modificare l'aspetto di tutti i controlli. I controlli che hanno tutto il loro disegno <xref:System.Windows.Forms.TextBox>fatto da <xref:System.Windows.Forms.Control.OnPaint%2A> Windows (ad esempio, ) non chiamano mai il loro metodo e pertanto non utilizzeranno mai il codice personalizzato. Fare riferimento alla documentazione della Guida relativa al <xref:System.Windows.Forms.Control.OnPaint%2A> controllo specifico che si desidera modificare per verificare se il metodo è disponibile. Per un elenco di tutti i controlli Windows Forms vedere [Controlli da usare in Windows Forms](controls-to-use-on-windows-forms.md). Se un controllo <xref:System.Windows.Forms.Control.OnPaint%2A> non è elencato come metodo membro, non è possibile modificarne l'aspetto eseguendo l'override di questo metodo. Per altre informazioni sul disegno personalizzato, vedere [Disegno e rendering di controlli personalizzati](custom-control-painting-and-rendering.md).

    ```vb
    Protected Overrides Sub OnPaint(ByVal e As _
       System.Windows.Forms.PaintEventArgs)
       MyBase.OnPaint(e)
       ' Insert code to do custom painting.
       ' If you want to completely change the appearance of your control,
       ' do not call MyBase.OnPaint(e).
    End Sub
    ```

    ```csharp
    protected override void OnPaint(PaintEventArgs pe)
    {
       base.OnPaint(pe);
       // Insert code to do custom painting.
       // If you want to completely change the appearance of your control,
       // do not call base.OnPaint(pe).
    }
    ```

1. Salvare ed eseguire il test del controllo.

## <a name="see-also"></a>Vedere anche

- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
- [Procedura: Ereditare dalla classe Control](how-to-inherit-from-the-control-class.md)
- [Procedura: Ereditare dalla classe UserControl](how-to-inherit-from-the-usercontrol-class.md)
- [Procedura: Creare controlli per Windows Form](how-to-author-controls-for-windows-forms.md)
- [Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Procedura dettagliata: ereditare da un controllo Windows FormWalkthrough: Inheriting from a Windows Forms Control](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)

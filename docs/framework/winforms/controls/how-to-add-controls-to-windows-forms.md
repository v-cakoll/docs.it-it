---
title: 'Procedura: Aggiungere controlli a Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 04597283a8ff2e21a0f227268671d3605eac6356
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343588"
---
# <a name="how-to-add-controls-to-windows-forms"></a>Procedura: Aggiungere controlli a Windows Forms
La maggior parte dei moduli sono progettati con l'aggiunta di controlli alla superficie del form per definire l'interfaccia utente (UI). Oggetto *controllo* è un componente in un formato utilizzato per visualizzare informazioni o accettare l'input dell'utente. Per altre informazioni sui controlli, vedere [Windows Forms Controls](index.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-draw-a-control-on-a-form"></a>Per disegnare un controllo in un form  
  
1. Aprire il form. Per altre informazioni, vedere [Procedura: Visualizzare Windows Form nella finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).  
  
2. Nel **casella degli strumenti**, fare clic sul controllo da aggiungere al form.  
  
3. Nel form, fare clic su cui l'angolo superiore sinistro del controllo da trovare e trascinare in cui si desidera l'angolo inferiore destro del controllo da individuare.  
  
     Il controllo viene aggiunto al form con il percorso specificato e le dimensioni.  
  
    > [!NOTE]
    >  Ogni controllo ha una dimensione predefinita definita. È possibile aggiungere un controllo al form nella dimensione predefinita del controllo trascinandolo dal **casella degli strumenti** al form.  
  
### <a name="to-drag-a-control-to-a-form"></a>Trascinare un controllo a un form  
  
1. Aprire il form. Per altre informazioni, vedere [Procedura: Visualizzare Windows Form nella finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).  
  
2. Nel **casella degli strumenti**, scegliere il controllo desiderato e trascinarlo nel form.  
  
     Il controllo viene aggiunto al form nella posizione specificata nella dimensione predefinita.  
  
    > [!NOTE]
    >  È possibile fare doppio clic su un controllo nel **casella degli strumenti** per aggiungerlo all'angolo superiore sinistro del form nella dimensione predefinita.  
  
     È anche possibile aggiungere dinamicamente controlli a un form in fase di esecuzione. Nell'esempio di codice seguente, un <xref:System.Windows.Forms.TextBox> controllo verrà aggiunto al modulo quando un <xref:System.Windows.Forms.Button> si fa clic sul controllo.  
  
    > [!NOTE]
    >  La procedura seguente presuppone l'esistenza di un form con un **sul pulsante** controllo `Button1`, già posizionato su di esso.  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a>Per aggiungere un controllo a un form a livello di codice  
  
1. Nel metodo che gestisce il pulsante `Click` evento all'interno di classe del modulo, inserire il codice simile al seguente per aggiungere un riferimento alla variabile di controllo, imposta il controllo `Location`e aggiungere il controllo.  
  
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
    >  È anche possibile aggiungere codice per inizializzare le altre proprietà del controllo.  
  
    > [!IMPORTANT]
    >  Si potrebbe esporre il computer locale a un rischio per la sicurezza attraverso la rete facendo riferimento a un malintenzionato `UserControl`. Questa è solo un problema nel caso di un utente con un controllo personalizzato, seguito dall'utente erroneamente aggiungendolo al progetto.  
  
## <a name="see-also"></a>Vedere anche

- [Controlli Windows Form](index.md)
- [Disposizione di controlli in Windows Form](arranging-controls-on-windows-forms.md)
- [Procedura: Ridimensionare i controlli Windows Form](how-to-resize-controls-on-windows-forms.md)
- [Procedura: Impostare il testo visualizzato dal controllo di un Windows Form](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)

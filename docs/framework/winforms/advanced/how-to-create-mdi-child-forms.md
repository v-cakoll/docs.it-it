---
title: 'Procedura: Creare form figlio MDI'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: 73f2004470d5d1da04199af75832cefd6348ce18
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937670"
---
# <a name="how-to-create-mdi-child-forms"></a>Procedura: Creare form figlio MDI
Form figlio MDI sono un elemento essenziale [le applicazioni di interfaccia a documenti multipli (MDI)](multiple-document-interface-mdi-applications.md), come il centro di interazione dell'utente sono elencati i moduli.  
  
 Nella procedura che segue vengono creati form figlio MDI che visualizzano un controllo <xref:System.Windows.Forms.RichTextBox>, analogo alla maggior parte delle applicazioni per l'elaborazione di testi. Sostituendo il controllo <xref:System.Windows.Forms> con altri controlli, ad esempio con <xref:System.Windows.Forms.DataGridView> o con più controlli, è possibile creare finestre figlio MDI e applicazioni MDI con differenti possibilità.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-mdi-child-forms"></a>Per creare form figlio MDI  
  
1. Creare un nuovo progetto Windows Form. Nella **le proprietà di Windows** per il form, impostare relativo <xref:System.Windows.Forms.Form.IsMdiContainer%2A> proprietà `true`e il relativo `WindowsState` proprietà `Maximized`.  
  
     Il form viene così designato come contenitore MDI per le finestre figlio.  
  
2. Dalla `Toolbox` trascinare un controllo <xref:System.Windows.Forms.MenuStrip> nel form. Impostare relativi `Text` proprietà **File**.  
  
3. Fare clic sui puntini di sospensione (...) accanto al **elementi** proprietà e fare clic su **Add** per aggiungere voci di menu ToolStrip figlio strumento due. Impostare il `Text` proprietà per questi elementi per **New** e **finestra**.  
  
4. Nelle **Esplora soluzioni**, fare clic sul progetto, scegliere **Add**, quindi selezionare **Aggiungi nuovo elemento**.  
  
5. Nel **Aggiungi nuovo elemento** finestra di dialogo **Windows Form** (in Visual Basic o Visual c#) o **Windows Forms Application (.NET)** (in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) dal  **I modelli** riquadro. Nel **Name** casella, come nome del form **Form2**. Scegliere il **Open** pulsante per aggiungere il form al progetto.  
  
    > [!NOTE]
    >  Il form figlio MDI creato in questo passaggio è un Windows Form standard. Dispone pertanto di una proprietà <xref:System.Windows.Forms.Form.Opacity%2A> che consente di controllare la trasparenza del form. La proprietà <xref:System.Windows.Forms.Form.Opacity%2A>, tuttavia, è stata progettata per le finestre di primo livello. Per evitare problemi di disegno, non usarla con i form figlio MDI.  
  
     Il form costituirà il modello per i form figlio MDI.  
  
     Il **finestra di progettazione Windows Form** visualizzata **Form2**.  
  
6. Dal **casella degli strumenti**, trascinare un **RichTextBox** controllo al form.  
  
7. Nel **proprietà** impostare nella finestra il `Anchor` proprietà **superiore sinistra** e la `Dock` proprietà **riempire**.  
  
     In questo modo il controllo <xref:System.Windows.Forms.RichTextBox> riempirà completamente l'area del form figlio MDI, anche quando viene ridimensionato.  
  
8. Fare doppio clic il **New** voce di menu per creare un <xref:System.Windows.Forms.Control.Click> relativo gestore eventi.  
  
9. Inserire codice simile al seguente per creare un nuovo form figlio MDI quando l'utente sceglie il **New** voce di menu.  
  
    > [!NOTE]
    >  Nell'esempio che segue il gestore eventi gestisce l'evento <xref:System.Windows.Forms.Control.Click> per `MenuItem2`. Tenere presente che, a seconda delle specifiche di architettura dell'applicazione, il **New** voce di menu non siano `MenuItem2`.  
  
    ```vb  
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click  
       Dim NewMDIChild As New Form2()  
       'Set the Parent Form of the Child window.  
       NewMDIChild.MdiParent = Me  
       'Display the new form.  
       NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    protected void MDIChildNew_Click(object sender, System.EventArgs e){  
       Form2 newMDIChild = new Form2();  
       // Set the Parent Form of the Child window.  
       newMDIChild.MdiParent = this;  
       // Display the new form.  
       newMDIChild.Show();  
    }  
    ```  
  
    ```cpp  
    private:  
       void menuItem2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          Form2^ newMDIChild = gcnew Form2();  
          // Set the Parent Form of the Child window.  
          newMDIChild->MdiParent = this;  
          // Display the new form.  
          newMDIChild->Show();  
       }  
    ```  
  
     In [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)] aggiungere la direttiva `#include` seguente all'inizio di Form1.h:  
  
    ```cpp  
    #include "Form2.h"  
    ```  
  
10. Nell'elenco nella parte superiore dell'elenco a discesa il **delle proprietà** finestra, selezionare il controllo MenuStrip che corrisponde al **File** e impostare il <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà nella finestra di <xref:System.Windows.Forms.ToolStripMenuItem>.  
  
     In questo modo il **finestra** menu per gestire un elenco di finestre figlio MDI aperte con un segno di spunta accanto alla finestra figlio attiva.  
  
11. Premere F5 per eseguire l'applicazione. Selezionando **New** dal **File** dal menu, è possibile creare nuovi form figlio MDI di cui viene tenuta traccia nel **finestra** voce di menu.  
  
    > [!NOTE]
    >  Quando un form figlio MDI con un componente <xref:System.Windows.Forms.MainMenu>, associato in genere a una struttura di voci di menu, viene aperto all'interno di un form padre MDI dotato di un componente <xref:System.Windows.Forms.MainMenu>, solitamente con struttura di voci di menu, le voci di menu vengono unite automaticamente se è stata impostata la proprietà <xref:System.Windows.Forms.MenuItem.MergeType%2A> ed eventualmente la proprietà <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>. Impostare la proprietà <xref:System.Windows.Forms.MenuItem.MergeType%2A> sia per i componenti <xref:System.Windows.Forms.MainMenu> che per tutte le voci di menu del form figlio su <xref:System.Windows.Forms.MenuMerge.MergeItems>. Impostare anche la proprietà <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> in modo che le voci di entrambi i menu appaiano nell'ordine desiderato. Tenere presente inoltre che quando si chiude un form padre MDI, ciascun form figlio MDI genera un evento <xref:System.Windows.Forms.Form.Closing> prima che venga generato l'evento <xref:System.Windows.Forms.Form.Closing> per il padre MDI. L'annullamento di un evento <xref:System.Windows.Forms.Form.Closing> di un figlio MDI non impedisce la generazione dell'evento <xref:System.Windows.Forms.Form.Closing> del padre MDI, ma l'argomento <xref:System.ComponentModel.CancelEventArgs> per l'evento <xref:System.Windows.Forms.Form.Closing> del padre MDI verrà ora impostato su `true`. È possibile imporre la chiusura del form padre MDI e di tutti i form figlio MDI impostando l'argomento <xref:System.ComponentModel.CancelEventArgs> su `false`.  
  
## <a name="see-also"></a>Vedere anche

- [Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)](multiple-document-interface-mdi-applications.md)
- [Procedura: Creare form padre MDI](how-to-create-mdi-parent-forms.md)
- [Procedura: Determinare il figlio MDI attivo](how-to-determine-the-active-mdi-child.md)
- [Procedura: Inviare dati al figlio MDI attivo](how-to-send-data-to-the-active-mdi-child.md)
- [Procedura: Disporre i form figlio MDI](how-to-arrange-mdi-child-forms.md)

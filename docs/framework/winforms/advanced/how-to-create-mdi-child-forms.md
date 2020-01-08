---
title: 'Procedura: creare form figlio MDI'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: b49d43e0e1123921cb3800f0d60193d0ea7b3924
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338589"
---
# <a name="how-to-create-mdi-child-forms"></a>Procedura: creare form figlio MDI

I form figlio MDI sono un elemento essenziale di [applicazioni con interfaccia a documenti multipli (MDI)](multiple-document-interface-mdi-applications.md), in quanto tali forme rappresentano il centro dell'interazione dell'utente.

Nella procedura seguente si userà Visual Studio per creare un form figlio MDI che visualizza un controllo <xref:System.Windows.Forms.RichTextBox>, in modo analogo alla maggior parte delle applicazioni di elaborazione di testi. Sostituendo il controllo <xref:System.Windows.Forms> con altri controlli, ad esempio il controllo <xref:System.Windows.Forms.DataGridView> o una combinazione di controlli, è possibile creare finestre figlio MDI (e, per estensione, applicazioni MDI) con diverse possibilità.

## <a name="create-mdi-child-forms"></a>Creare form figlio MDI

1. Creare un nuovo progetto di Windows Forms Application in Visual Studio. Nella finestra **Proprietà** per il form impostare la relativa proprietà <xref:System.Windows.Forms.Form.IsMdiContainer%2A> su `true` e la relativa proprietà `WindowsState` su `Maximized`.

   Il form viene così designato come contenitore MDI per le finestre figlio.

2. Dalla `Toolbox` trascinare un controllo <xref:System.Windows.Forms.MenuStrip> nel form. Impostare la relativa proprietà `Text` su **file**.

3. Fare clic sui puntini di sospensione (...) accanto alla proprietà **Items** e fare clic su **Aggiungi** per aggiungere due voci di menu della barra degli strumenti figlio. Impostare la proprietà `Text` per questi elementi su **nuovo** e **finestra**.

4. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.

5. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Windows Form** (in Visual Basic o in Visual C#) o **Windows Forms applicazione (.NET)** (in Visual C++) dal riquadro **modelli** . Nella casella **nome** assegnare al modulo il nome **Form2**. Selezionare **Apri** per aggiungere il modulo al progetto.

    > [!NOTE]
    > Il form figlio MDI creato in questo passaggio è un Windows Form standard. Dispone pertanto di una proprietà <xref:System.Windows.Forms.Form.Opacity%2A> che consente di controllare la trasparenza del form. La proprietà <xref:System.Windows.Forms.Form.Opacity%2A>, tuttavia, è stata progettata per le finestre di primo livello. Per evitare problemi di disegno, non usarla con i form figlio MDI.

     Il form costituirà il modello per i form figlio MDI.

     Viene visualizzata la **Progettazione Windows Form** , che visualizza **Form2**.

6. Dalla **casella degli strumenti**trascinare un controllo **RichTextBox** nel form.

7. Nella finestra **Proprietà** impostare la proprietà `Anchor` su **Top, Left** e la proprietà `Dock` su **Fill**.

   In questo modo il controllo <xref:System.Windows.Forms.RichTextBox> riempirà completamente l'area del form figlio MDI, anche quando viene ridimensionato.

8. Fare doppio clic sulla **nuova** voce di menu per creare un gestore dell'evento <xref:System.Windows.Forms.Control.Click>.

9. Inserire codice simile al seguente per creare un nuovo form figlio MDI quando l'utente fa clic sulla **nuova** voce di menu.

   > [!NOTE]
   > Nell'esempio che segue il gestore eventi gestisce l'evento <xref:System.Windows.Forms.Control.Click> per `MenuItem2`. Tenere presente che, a seconda delle specifiche dell'architettura dell'applicazione, la **nuova** voce di menu potrebbe non essere `MenuItem2`.

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

   In C++aggiungere la seguente direttiva di `#include` all'inizio di Form1. h:

   ```cpp
   #include "Form2.h"
   ```

10. Nell'elenco a discesa nella parte superiore della finestra **Proprietà** selezionare la striscia di menu che corrisponde alla striscia di menu **file** e impostare la proprietà <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> sulla finestra <xref:System.Windows.Forms.ToolStripMenuItem>.

    In questo modo il menu **finestra** consente di mantenere un elenco di finestre figlio MDI aperte con un segno di spunta accanto alla finestra figlio attiva.

11. Premere **F5** per eseguire l'applicazione. Selezionando **nuovo** dal menu **file** è possibile creare nuovi form figlio MDI, che vengono mantenuti traccia di nella voce di menu **finestra** .

    > [!NOTE]
    > Quando un form figlio MDI con un componente <xref:System.Windows.Forms.MainMenu>, associato in genere a una struttura di voci di menu, viene aperto all'interno di un form padre MDI dotato di un componente <xref:System.Windows.Forms.MainMenu>, solitamente con struttura di voci di menu, le voci di menu vengono unite automaticamente se è stata impostata la proprietà <xref:System.Windows.Forms.MenuItem.MergeType%2A> ed eventualmente la proprietà <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>. Impostare la proprietà <xref:System.Windows.Forms.MenuItem.MergeType%2A> sia per i componenti <xref:System.Windows.Forms.MainMenu> che per tutte le voci di menu del form figlio su <xref:System.Windows.Forms.MenuMerge.MergeItems>. Impostare anche la proprietà <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> in modo che le voci di entrambi i menu appaiano nell'ordine desiderato. Tenere presente inoltre che quando si chiude un form padre MDI, ciascun form figlio MDI genera un evento <xref:System.Windows.Forms.Form.Closing> prima che venga generato l'evento <xref:System.Windows.Forms.Form.Closing> per il padre MDI. L'annullamento di un evento <xref:System.Windows.Forms.Form.Closing> di un figlio MDI non impedisce la generazione dell'evento <xref:System.Windows.Forms.Form.Closing> del padre MDI, ma l'argomento <xref:System.ComponentModel.CancelEventArgs> per l'evento <xref:System.Windows.Forms.Form.Closing> del padre MDI verrà ora impostato su `true`. È possibile imporre la chiusura del form padre MDI e di tutti i form figlio MDI impostando l'argomento <xref:System.ComponentModel.CancelEventArgs> su `false`.

## <a name="see-also"></a>Vedere anche

- [Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)](multiple-document-interface-mdi-applications.md)
- [Procedura: Creare form padre MDI](how-to-create-mdi-parent-forms.md)
- [Procedura: Determinare il figlio MDI attivo](how-to-determine-the-active-mdi-child.md)
- [Procedura: Inviare dati al figlio MDI attivo](how-to-send-data-to-the-active-mdi-child.md)
- [Procedura: Disporre i form figlio MDI](how-to-arrange-mdi-child-forms.md)

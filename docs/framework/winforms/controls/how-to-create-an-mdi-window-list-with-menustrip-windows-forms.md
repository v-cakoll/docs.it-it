---
title: 'Procedura: Creare un elenco di finestre MDI con MenuStrip (Windows Form)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: ec0d8af81e320bea3d9d69305f91bd56666ba7cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746793"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a>Procedura: Creare un elenco di finestre MDI con MenuStrip (Windows Form)
Usare l'interfaccia a documenti multipli (MDI) per creare applicazioni che possono aprire i documenti diverse alla stessa ora e copia e Incolla il contenuto da un documento a altro.  
  
 Questa procedura illustra come creare un elenco di tutti i form figlio attivo nel menu finestra dell'elemento padre.  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a>Per creare un elenco di finestre MDI con MenuStrip  
  
1. Creare un form e impostarne la proprietà <xref:System.Windows.Forms.Form.IsMdiContainer%2A> su `true`.  
  
2. Aggiungere un tipo <xref:System.Windows.Forms.MenuStrip> al form.  
  
3. Aggiungere due voci di menu di primo livello per il <xref:System.Windows.Forms.MenuStrip> e impostare loro <xref:System.Windows.Forms.Control.Text%2A> delle proprietà per `&File` e `&Window`.  
  
4. Aggiungere una voce del sottomenu alla voce di menu `&File` e impostare la relativa proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su `&Open`.  
  
5. Impostare il <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà del <xref:System.Windows.Forms.MenuStrip> per il `&Window` <xref:System.Windows.Forms.ToolStripMenuItem>.  
  
6. Aggiungere un modulo al progetto e aggiungere il controllo desiderato, ad esempio un'altra <xref:System.Windows.Forms.MenuStrip>.  
  
7. Creare un gestore eventi per l'evento <xref:System.Windows.Forms.Control.Click> di `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
8. All'interno del gestore di evento, inserire codice simile al seguente per creare e visualizzare le nuove istanze di `Form2` come finestre figlio MDI di `Form1`.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. Inserire codice simile al seguente nel `&New` <xref:System.Windows.Forms.ToolStripMenuItem> per registrare il gestore dell'evento.  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Due controlli <xref:System.Windows.Forms.Form> denominati `Form1` e `Form2`.  
  
- Un controllo <xref:System.Windows.Forms.MenuStrip> su `Form1` denominato `menuStrip1` e un controllo <xref:System.Windows.Forms.MenuStrip> su `Form2` denominato `menuStrip2`.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare form padre MDI](../advanced/how-to-create-mdi-parent-forms.md)
- [Procedura: Creare form figlio MDI](../advanced/how-to-create-mdi-child-forms.md)
- [Controllo MenuStrip](menustrip-control-windows-forms.md)

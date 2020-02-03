---
title: 'Procedura: inserire un MenuStrip in un menu a discesa MDI'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip control [Windows Forms], inserting
- MenuStrip control [Windows Forms], merging
- MDI [Windows Forms], merging menu items
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
ms.openlocfilehash: 6e189dd159c48b5779679d0563fab85e9b848992
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736410"
---
# <a name="how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms"></a>Procedura: inserire un MenuStrip in un menu a discesa MDI (Windows Form)
In alcune applicazioni, il tipo di una finestra figlio di interfaccia a documenti multipli (MDI, Multiple Document Interface) può essere diverso dalla finestra padre MDI. Ad esempio, il padre MDI potrebbe essere un foglio di calcolo, mentre il figlio MDI potrebbe essere un grafico. In tal caso, è consigliabile aggiornare il contenuto del menu del padre MDI con il contenuto del menu del figlio MDI in quanto vengono attivate finestre figlio MDI di tipi diversi.  
  
 Nella procedura seguente vengono utilizzate le proprietà <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>e <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> per inserire un gruppo di voci di menu dal menu figlio MDI nella parte a discesa del menu MDI padre. Chiudendo la finestra figlio MDI vengono rimosse le voci di menu inserite dall'elemento padre MDI.  
  
### <a name="to-insert-a-menustrip-into-an-mdi-drop-down-menu"></a>Per inserire un MenuStrip in un menu a discesa MDI  
  
1. Creare un form e impostarne la proprietà <xref:System.Windows.Forms.Form.IsMdiContainer%2A> su `true`.  
  
2. Aggiungere <xref:System.Windows.Forms.MenuStrip> a `Form1` e impostare la proprietà <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> di <xref:System.Windows.Forms.MenuStrip> su `true`.  
  
3. Aggiungere una voce di menu di primo livello a `Form1`<xref:System.Windows.Forms.MenuStrip> e impostare la relativa proprietà <xref:System.Windows.Forms.Control.Text%2A> su `&File`.  
  
4. Aggiungere tre voci di sottomenu alla voce di menu `&File` e impostare le relative proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su `&Open`, `&Import from`e `E&xit`.  
  
5. Aggiungere due voci di sottomenu alla voce di sottomenu `&Import from` e impostare le relative proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su `&Word` e `&Excel`.  
  
6. Aggiungere un form al progetto, aggiungere <xref:System.Windows.Forms.MenuStrip> al form e impostare la proprietà <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> del `Form2`<xref:System.Windows.Forms.MenuStrip> su `true`.  
  
7. Aggiungere una voce di menu di primo livello a `Form2`<xref:System.Windows.Forms.MenuStrip> e impostare la relativa proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su `&File`.  
  
8. Aggiungere voci di sottomenu al menu `&File` di `Form2` nell'ordine seguente: un <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`e un altro <xref:System.Windows.Forms.ToolStripSeparator>.  
  
9. Impostare le proprietà <xref:System.Windows.Forms.MergeAction> e <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> delle voci di menu `Form2` come illustrato nella tabella seguente.  
  
    |Voce di menu Form2|Valore MergeAction|Valore MergeIndex|  
    |---------------------|-----------------------|----------------------|  
    |File|MatchOnly|-1|  
    |Separatore|Inserisci|2|  
    |Salva|Inserisci|3|  
    |Salva e chiudi|Inserisci|4|  
    |Separatore|Inserisci|5|  
  
10. Creare un gestore eventi per l'evento <xref:System.Windows.Forms.Control.Click> di `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. Nel gestore eventi inserire codice simile all'esempio di codice riportato di seguito per creare e visualizzare nuove istanze di `Form2` come finestre figlio MDI di `Form1`.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
12. Inserire codice analogo al seguente esempio di codice nel `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> per registrare il gestore eventi.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Due controlli <xref:System.Windows.Forms.Form> denominati `Form1` e `Form2`.  
  
- Un controllo <xref:System.Windows.Forms.MenuStrip> su `Form1` denominato `menuStrip1` e un controllo <xref:System.Windows.Forms.MenuStrip> su `Form2` denominato `menuStrip2`.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare form padre MDI](../advanced/how-to-create-mdi-parent-forms.md)
- [Procedura: Creare form figlio MDI](../advanced/how-to-create-mdi-child-forms.md)
- [Panoramica sul controllo MenuStrip](menustrip-control-overview-windows-forms.md)

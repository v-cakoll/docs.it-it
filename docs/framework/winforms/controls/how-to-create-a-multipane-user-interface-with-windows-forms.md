---
title: "Procedura: Creare un'interfaccia utente a più riquadri con Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], examples
- ListView control [Windows Forms], examples
- RichTextBox control [Windows Forms], examples
- Panel control [Windows Forms], examples
- TreeView control [Windows Forms], examples
- Splitter control [Windows Forms], examples
ms.assetid: e79f6bcc-3740-4d1e-b46a-c5594d9b7327
ms.openlocfilehash: 4db424b27af09dcb7def0051fba070fe9ccf0491
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721970"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms"></a>Procedura: Creare un'interfaccia utente a più riquadri con Windows Form
Nella procedura seguente, si creerà un'interfaccia utente a più riquadri simile a quello usato in Microsoft Outlook, con un **cartella** elenco, un **messaggi** riquadro e un **anteprima** riquadro. Questa disposizione avviene principalmente tramite l'ancoraggio dei controlli con il modulo.  
  
 Quando si effettua l'ancoraggio di un controllo, determinare il bordo del contenitore padre a cui è bloccato su un controllo. Di conseguenza, se si imposta la <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Right>, il bordo destro del controllo sarà ancorato al bordo destro del controllo padre. Inoltre, il bordo ancorato il controllo viene ridimensionato in modo corrisponde a quello del controllo contenitore. Per altre informazioni sul modo in cui <xref:System.Windows.Forms.SplitContainer.Dock%2A> funzionamento di proprietà, vedere [come: Ancorare i controlli in Windows Form](how-to-dock-controls-on-windows-forms.md).  
  
 Questa procedura illustra la disposizione di <xref:System.Windows.Forms.SplitContainer> e gli altri controlli nel form e non sull'aggiunta di funzionalità che semplificano l'applicazione di simulare Microsoft Outlook.  
  
 Per creare questa interfaccia utente, inserire tutti i controlli all'interno di un <xref:System.Windows.Forms.SplitContainer> controllo, che contiene un <xref:System.Windows.Forms.TreeView> controllo nel Pannello di sinistra. Il pannello destro del <xref:System.Windows.Forms.SplitContainer> controllo contiene un secondo <xref:System.Windows.Forms.SplitContainer> controllare con un <xref:System.Windows.Forms.ListView> controllo sopra un <xref:System.Windows.Forms.RichTextBox> controllo. Questi <xref:System.Windows.Forms.SplitContainer> controlli abilitare il ridimensionamento indipendente degli altri controlli nel form. È possibile adattare le tecniche in questa procedura per le interfacce utente personalizzate di creazione personalizzato.  
  
### <a name="to-create-an-outlook-style-user-interface-programmatically"></a>Per creare un'interfaccia utente lo stile di Outlook a livello di codice  
  
1.  All'interno di un form, dichiarare ogni controllo che è costituito da un'interfaccia utente. Per questo esempio, usare il <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer>, e <xref:System.Windows.Forms.RichTextBox> controlli per simulare l'interfaccia utente di Microsoft Outlook.  
  
    ```vb  
    Private WithEvents treeView1 As System.Windows.Forms.TreeView  
    Private WithEvents listView1 As System.Windows.Forms.ListView  
    Private WithEvents richTextBox1 As System.Windows.Forms.RichTextBox  
    Private WithEvents splitContainer1 As _  
        System.Windows.Forms.SplitContainer  
    Private WithEvents splitContainer2 As _  
        System.Windows.Forms.SplitContainer  
    ```  
  
    ```csharp  
    private System.Windows.Forms.TreeView treeView1;  
    private System.Windows.Forms.ListView listView1;  
    private System.Windows.Forms.RichTextBox richTextBox1;  
    private System.Windows.Forms. SplitContainer splitContainer2;  
    private System.Windows.Forms. SplitContainer splitContainer1;  
    ```  
  
2.  Creare una routine che definisce l'interfaccia utente. Il codice seguente imposta le proprietà in modo che il form sarà simile all'interfaccia utente in Microsoft Outlook. Tuttavia, utilizzando gli altri controlli o ancoraggio loro in modo diverso, è estremamente semplice creare altre interfacce utente che sono altrettanto flessibile.  
  
    ```vb  
    Public Sub CreateOutlookUI()  
        ' Create an instance of each control being used.  
        Me.components = New System.ComponentModel.Container()  
        Me.treeView1 = New System.Windows.Forms.TreeView()  
        Me.listView1 = New System.Windows.Forms.ListView()  
        Me.richTextBox1 = New System.Windows.Forms.RichTextBox()  
        Me.splitContainer1 = New System.Windows.Forms.SplitContainer()  
        Me.splitContainer2= New System.Windows.Forms. SplitContainer()  
  
        ' Should you develop this into a working application,  
        ' use the AddHandler method to hook up event procedures here.  
  
        ' Set properties of TreeView control.  
        ' Use the With statement to avoid repetitive code.  
        With Me.treeView1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 0  
            .Nodes.Add("treeView")  
        End With  
  
    ' Set properties of ListView control.  
       With Me.listView1  
          .Dock = System.Windows.Forms.DockStyle.Top  
          .TabIndex = 2  
          .Items.Add("listView")  
       End With  
  
    ' Set properties of RichTextBox control.  
       With Me.richTextBox1  
          .Dock = System.Windows.Forms.DockStyle.Fill  
          .TabIndex = 3  
          .Text = "richTextBox1"  
       End With  
  
        ' Set properties of the first SplitContainer control.  
        With Me.splitContainer1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 1  
            .SplitterWidth = 4  
            .SplitterDistance = 150  
            .Orientation = Orientation.Horizontal  
            .Panel1.Controls.Add(Me.listView1)  
            .Panel2.Controls.Add(Me.richTextBox1)  
    End With  
  
        ' Set properties of the second SplitContainer control.  
        With Me.splitContainer2  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 4  
            .SplitterWidth = 4  
            .SplitterDistance = 100  
            .Panel1.Controls.Add(Me.treeView1)  
            .Panel2.Controls.Add(Me.SplitContainer1)  
    End With  
  
    ' Add the main SplitContainer control to the form.  
        Me.Controls.Add(Me.splitContainer2)  
        Me.Text = "Intricate UI Example"  
    End Sub  
    ```  
  
    ```csharp  
    public void createOutlookUI()  
    {  
        // Create an instance of each control being used.  
        treeView1 = new System.Windows.Forms.TreeView();  
        listView1 = new System.Windows.Forms.ListView();  
        richTextBox1 = new System.Windows.Forms.RichTextBox();  
        splitContainer2 = new System.Windows.Forms.SplitContainer();  
        splitContainer1 = new System.Windows.Forms.SplitContainer();  
  
        // Insert code here to hook up event methods.  
  
        // Set properties of TreeView control.  
        treeView1.Dock = System.Windows.Forms.DockStyle.Fill;  
        treeView1.TabIndex = 0;  
        treeView1.Nodes.Add("treeView");  
  
        // Set properties of ListView control.  
        listView1.Dock = System.Windows.Forms.DockStyle.Top;  
        listView1.TabIndex = 2;  
        listView1.Items.Add("listView");  
  
        // Set properties of RichTextBox control.  
        richTextBox1.Dock = System.Windows.Forms.DockStyle.Fill;  
        richTextBox1.TabIndex = 3;  
        richTextBox1.Text = "richTextBox1";  
  
        // Set properties of first SplitContainer control.  
        splitContainer1.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 1;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 150;  
        splitContainer2.Orientation = Orientation.Horizontal;  
        splitContainer2.Panel1.Controls.Add(this.listView1);  
        splitContainer2.Panel1.Controls.Add(this.richTextBox1);  
  
        // Set properties of second SplitContainer control.  
        splitContainer2.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 4;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 100;  
        splitContainer2.Panel1.Controls.Add(this.treeView1);  
        splitContainer2.Panel1.Controls.Add(this.splitContainer1);  
  
        // Add the main SplitContainer control to the form.  
        this.Controls.Add(this.splitContainer2);  
        this.Text = "Intricate UI Example";  
    }  
    ```  
  
3.  In Visual Basic, aggiungere una chiamata alla procedura appena creato nella `New()` procedure. Nell'oggetto visivo C#, aggiungere questa riga di codice al costruttore della classe del form.  
  
    ```vb  
    ' Add this to the New procedure.  
    CreateOutlookUI()  
    ```  
  
    ```csharp  
    // Add this to the form class's constructor.  
    createOutlookUI();  
    ```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.SplitContainer>
- [Controllo SplitContainer](splitcontainer-control-windows-forms.md)
- [Procedura: Creare un'interfaccia utente a più riquadri con Windows Form usando la finestra di progettazione](create-a-multipane-user-interface-with-wf-using-the-designer.md)

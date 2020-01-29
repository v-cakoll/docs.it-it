---
title: Creare un'interfaccia utente a più riquadri
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
ms.openlocfilehash: 4b168a6d566e20814d4403f90e157d80efe3bf12
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731331"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms"></a>Procedura: Creare un'interfaccia utente a più riquadri con Windows Form
Nella procedura seguente verrà creata un'interfaccia utente a più riquadri simile a quella usata in Microsoft Outlook, con un elenco di **cartelle** , un riquadro **messaggi** e un riquadro di **Anteprima** . Questa disposizione viene eseguita principalmente tramite l'ancoraggio dei controlli con il modulo.  
  
 Quando si ancora un controllo, si determina il bordo del contenitore padre a cui un controllo viene collegato. Se quindi si imposta la proprietà <xref:System.Windows.Forms.SplitContainer.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Right>, il bordo destro del controllo verrà ancorato al bordo destro del controllo padre. Inoltre, il bordo ancorato del controllo viene ridimensionato in modo che corrisponda a quello del relativo controllo contenitore. Per altre informazioni sul funzionamento della proprietà <xref:System.Windows.Forms.SplitContainer.Dock%2A>, vedere [procedura: ancorare i controlli su Windows Forms](how-to-dock-controls-on-windows-forms.md).  
  
 Questa procedura è incentrata sulla disposizione della <xref:System.Windows.Forms.SplitContainer> e degli altri controlli nel form, non sull'aggiunta di funzionalità per fare in modo che l'applicazione riproduca Microsoft Outlook.  
  
 Per creare questa interfaccia utente, tutti i controlli vengono posizionati all'interno di un controllo <xref:System.Windows.Forms.SplitContainer>, che contiene un controllo <xref:System.Windows.Forms.TreeView> nel pannello a sinistra. Il pannello destro del controllo <xref:System.Windows.Forms.SplitContainer> contiene un secondo controllo <xref:System.Windows.Forms.SplitContainer> con un controllo <xref:System.Windows.Forms.ListView> sopra un controllo <xref:System.Windows.Forms.RichTextBox>. Questi controlli <xref:System.Windows.Forms.SplitContainer> consentono il ridimensionamento indipendente degli altri controlli nel form. È possibile adattare le tecniche di questa procedura per creare interfacce utente personalizzate.  
  
### <a name="to-create-an-outlook-style-user-interface-programmatically"></a>Per creare un'interfaccia utente di tipo Outlook a livello di codice  
  
1. All'interno di un modulo, dichiarare ogni controllo che comprende l'interfaccia utente. Per questo esempio, usare i controlli <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer>e <xref:System.Windows.Forms.RichTextBox> per simulare l'interfaccia utente di Microsoft Outlook.  
  
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
  
2. Creare una procedura che definisce l'interfaccia utente. Il codice seguente imposta le proprietà in modo che il form sarà simile all'interfaccia utente di Microsoft Outlook. Tuttavia, usando altri controlli o ancorarli in modo diverso, è altrettanto semplice creare altre interfacce utente che siano ugualmente flessibili.  
  
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
  
3. In Visual Basic aggiungere una chiamata alla procedura appena creata nella procedura di `New()`. In Visual C#aggiungere questa riga di codice al costruttore per la classe del form.  
  
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

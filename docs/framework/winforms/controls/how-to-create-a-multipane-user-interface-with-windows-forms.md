---
title: "Procedura: creare un'interfaccia utente a più riquadri con Windows Form"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6db621912e76d24b05c8dcdca7f1d3f4e62c2838
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms"></a>Procedura: creare un'interfaccia utente a più riquadri con Windows Form
Nella procedura seguente, si creerà un'interfaccia utente a più riquadri simile a quella utilizzata in Microsoft Outlook, con un **cartella** elenco, un **messaggi** riquadro e un **anteprima** riquadro. Questa disposizione è ottenuta principalmente tramite ancorare i controlli con il modulo.  
  
 Quando si inserisce un controllo, determinare il bordo del contenitore padre a cui è bloccato su un controllo. Pertanto, se si imposta la <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Right>, il bordo destro del controllo viene ancorato al bordo destro del controllo padre. Inoltre, il bordo del controllo ancorato viene ridimensionato per corrispondere a quello del controllo contenitore. Per ulteriori informazioni su come <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà, vedere [procedura: ancorare controlli in Windows Form](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md).  
  
 Questa procedura illustra la disposizione di <xref:System.Windows.Forms.SplitContainer> e altri controlli nel form, non sull'aggiunta di funzionalità per rendere l'applicazione di simulare Microsoft Outlook.  
  
 Per creare questa interfaccia utente, inserire tutti i controlli all'interno di un <xref:System.Windows.Forms.SplitContainer> controllo che contiene un <xref:System.Windows.Forms.TreeView> controllo nel riquadro a sinistra. Il riquadro di destra la <xref:System.Windows.Forms.SplitContainer> controllo contiene un secondo <xref:System.Windows.Forms.SplitContainer> controllare con un <xref:System.Windows.Forms.ListView> controllo precedente un <xref:System.Windows.Forms.RichTextBox> controllo. Questi <xref:System.Windows.Forms.SplitContainer> controlli abilitano il ridimensionamento indipendenti degli altri controlli nel form. È possibile adattare le tecniche in questa procedura per creare interfacce utente personalizzate.  
  
### <a name="to-create-an-outlook-style-user-interface-programmatically"></a>Per creare un'interfaccia utente nello stile di Outlook a livello di codice  
  
1.  All'interno di un form, dichiarare ogni controllo che comprende l'interfaccia utente. Per questo esempio, utilizzare il <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer>, e <xref:System.Windows.Forms.RichTextBox> controlli per simulare l'interfaccia utente di Microsoft Outlook.  
  
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
  
2.  Creare una routine che definisce l'interfaccia utente. Il codice seguente imposta le proprietà in modo che il form sarà simile all'interfaccia utente Microsoft Outlook. Tuttavia, utilizzando altri controlli o un diverso ancoraggio, è facile creare altre interfacce utente altrettanto flessibile.  
  
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
  
3.  In [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], aggiungere una chiamata alla procedura appena creato nel `New()` stored procedure. In [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], aggiungere questa riga di codice al costruttore della classe del form.  
  
    ```vb  
    ' Add this to the New procedure.  
    CreateOutlookUI()  
    ```  
  
    ```csharp  
    // Add this to the form class's constructor.  
    createOutlookUI();  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.SplitContainer>  
 [Controllo SplitContainer](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)  
 [Procedura: Creare un'interfaccia utente a più riquadri con Windows Form usando la finestra di progettazione](../../../../docs/framework/winforms/controls/create-a-multipane-user-interface-with-wf-using-the-designer.md)

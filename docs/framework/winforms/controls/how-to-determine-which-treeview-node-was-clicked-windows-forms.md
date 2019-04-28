---
title: 'Procedura: Individuare il nodo di TreeView scelto (Windows Form)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TreeNode
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- tree nodes in TreeView control [Windows Forms], determining node clicked
- TreeView control [Windows Forms], determining node clicked
ms.assetid: 06a4a191-d918-42af-9f49-956c93eff261
ms.openlocfilehash: 71f13c7b160822c92475d4d03e923b40d4f0454d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771046"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Procedura: Individuare il nodo di TreeView scelto (Windows Form)
Quando si lavora con i moduli di Windows <xref:System.Windows.Forms.TreeView> (controllo), un'attività comune consiste nel determinare quale nodo è stato fatto clic e rispondere in modo appropriato.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>Per determinare quale nodo di TreeView scelto  
  
1. Usare il <xref:System.EventArgs> oggetto per restituire un riferimento all'oggetto del nodo selezionato.  
  
2. Determinare quale nodo è stato scelto controllando il <xref:System.Windows.Forms.TreeViewEventArgs> classe, che contiene i dati relativi all'evento.  
  
    ```vb  
    Private Sub TreeView1_AfterSelect(ByVal sender As System.Object, _  
    ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       ' Determine by checking the Node property of the TreeViewEventArgs.  
       MessageBox.Show(e.Node.Text)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,   
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       // Determine by checking the Text property.  
       MessageBox.Show(e.Node.Text);  
    }  
    ```  
  
    ```cpp  
    private:  
       void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          // Determine by checking the Text property.  
          MessageBox::Show(e->Node->Text);  
       }  
    ```  
  
    > [!NOTE]
    >  In alternativa, è possibile usare la <xref:System.Windows.Forms.MouseEventArgs> del <xref:System.Windows.Forms.Control.MouseDown> o <xref:System.Windows.Forms.Control.MouseUp> evento per ottenere il <xref:System.Drawing.Point.X%2A> e <xref:System.Drawing.Point.Y%2A> coordinare i valori del <xref:System.Drawing.Point> in cui si è verificato il clic. Quindi, usare il <xref:System.Windows.Forms.TreeView> del controllo <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> metodo per determinare quale nodo è stato fatto clic.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo TreeView](treeview-control-windows-forms.md)

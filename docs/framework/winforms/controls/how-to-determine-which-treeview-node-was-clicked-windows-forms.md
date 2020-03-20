---
title: 'Procedura: individuare il nodo di TreeView scelto'
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
ms.openlocfilehash: d960eaae2aa479e0be74e9a5e4fdbfec8ff411c1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182182"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Procedura: individuare il nodo di TreeView scelto (Windows Form)
Quando si utilizza <xref:System.Windows.Forms.TreeView> il controllo Windows Form, un'attività comune consiste nel determinare su quale nodo è stato fatto clic e rispondere in modo appropriato.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>Per determinare su quale nodo TreeView è stato fatto clic  
  
1. Utilizzare <xref:System.EventArgs> l'oggetto per restituire un riferimento all'oggetto nodo su cui è stato fatto clic.  
  
2. Determinare su quale nodo è <xref:System.Windows.Forms.TreeViewEventArgs> stato fatto clic controllando la classe, che contiene i dati correlati all'evento.  
  
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
    > In alternativa, è possibile <xref:System.Windows.Forms.MouseEventArgs> utilizzare <xref:System.Windows.Forms.Control.MouseDown> <xref:System.Windows.Forms.Control.MouseUp> l'evento <xref:System.Drawing.Point.X%2A> o <xref:System.Drawing.Point.Y%2A> per ottenere <xref:System.Drawing.Point> i valori e delle coordinate del punto in cui si è verificato il clic. Quindi, utilizzare <xref:System.Windows.Forms.TreeView> il <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> metodo del controllo per determinare su quale nodo è stato fatto clic.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo TreeView](treeview-control-windows-forms.md)

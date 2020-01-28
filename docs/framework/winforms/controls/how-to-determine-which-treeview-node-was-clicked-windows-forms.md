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
ms.openlocfilehash: 7a0e2b69bbec0eb03d40bee2c8e2d4bc9c3558f9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742007"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Procedura: Individuare il nodo di TreeView scelto (Windows Form)
Quando si lavora con il controllo Windows Forms <xref:System.Windows.Forms.TreeView>, un'attività comune consiste nel determinare quale nodo è stato selezionato e rispondere in modo appropriato.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>Per determinare quale nodo di TreeView è stato selezionato  
  
1. Utilizzare l'oggetto <xref:System.EventArgs> per restituire un riferimento all'oggetto nodo selezionato.  
  
2. Determinare su quale nodo è stato fatto clic controllando la classe <xref:System.Windows.Forms.TreeViewEventArgs>, che contiene i dati relativi all'evento.  
  
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
    > In alternativa, è possibile usare la <xref:System.Windows.Forms.MouseEventArgs> dell'evento <xref:System.Windows.Forms.Control.MouseDown> o <xref:System.Windows.Forms.Control.MouseUp> per ottenere i valori di <xref:System.Drawing.Point.X%2A> e di coordinata <xref:System.Drawing.Point.Y%2A> del <xref:System.Drawing.Point> in cui si è verificato il clic. Usare quindi il metodo di <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> del controllo <xref:System.Windows.Forms.TreeView> per determinare il nodo su cui è stato fatto clic.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo TreeView](treeview-control-windows-forms.md)

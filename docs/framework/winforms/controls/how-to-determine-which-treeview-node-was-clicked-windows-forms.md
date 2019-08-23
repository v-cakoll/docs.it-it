---
title: 'Procedura: Determinare il nodo TreeView selezionato (Windows Forms)'
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
ms.openlocfilehash: ab93158daf987e2f19516b8fb3abf80bfe79a12c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967337"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Procedura: Determinare il nodo TreeView selezionato (Windows Forms)
Quando si utilizza il controllo <xref:System.Windows.Forms.TreeView> Windows Forms, un'attività comune consiste nel determinare il nodo selezionato e rispondere in modo appropriato.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>Per determinare quale nodo di TreeView è stato selezionato  
  
1. Utilizzare l' <xref:System.EventArgs> oggetto per restituire un riferimento all'oggetto nodo selezionato.  
  
2. Determinare su quale nodo è stato fatto clic controllando la <xref:System.Windows.Forms.TreeViewEventArgs> classe, che contiene i dati relativi all'evento.  
  
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
    > In alternativa, è possibile usare l'oggetto <xref:System.Windows.Forms.MouseEventArgs> <xref:System.Windows.Forms.Control.MouseDown> dell'evento o <xref:System.Windows.Forms.Control.MouseUp> per ottenere i <xref:System.Drawing.Point.X%2A> valori della <xref:System.Drawing.Point.Y%2A> coordinata e <xref:System.Drawing.Point> dell'oggetto in cui si è verificato il clic. Usare quindi il <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> metodo <xref:System.Windows.Forms.TreeView> del controllo per determinare su quale nodo è stato fatto clic.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo TreeView](treeview-control-windows-forms.md)

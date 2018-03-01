---
title: 'Procedura: individuare il nodo di TreeView scelto (Windows Form)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2671d2790b3c5e476513cd5932d4684838aeceb6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Procedura: individuare il nodo di TreeView scelto (Windows Form)
Quando si lavora con Windows Form <xref:System.Windows.Forms.TreeView> (controllo), un'attività comune consiste nel determinare quale nodo è stato fatto clic e rispondere in modo appropriato.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>Per determinare il nodo di TreeView scelto  
  
1.  Utilizzare il <xref:System.EventArgs> per restituire un riferimento all'oggetto del nodo selezionato.  
  
2.  Determinare quale nodo è stato scelto controllando il <xref:System.Windows.Forms.TreeViewEventArgs> (classe), che contiene i dati relativi all'evento.  
  
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
    >  In alternativa, è possibile utilizzare il <xref:System.Windows.Forms.MouseEventArgs> del <xref:System.Windows.Forms.Control.MouseDown> o <xref:System.Windows.Forms.Control.MouseUp> evento per ottenere il <xref:System.Drawing.Point.X%2A> e <xref:System.Drawing.Point.Y%2A> coordinare i valori del <xref:System.Drawing.Point> in cui si è verificato il clic. Utilizzare quindi la <xref:System.Windows.Forms.TreeView> del controllo <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> metodo per determinare quale nodo è stato fatto clic.  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)

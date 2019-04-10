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
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296732"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="1ff94-102">Procedura: Individuare il nodo di TreeView scelto (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="1ff94-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="1ff94-103">Quando si lavora con i moduli di Windows <xref:System.Windows.Forms.TreeView> (controllo), un'attività comune consiste nel determinare quale nodo è stato fatto clic e rispondere in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="1ff94-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="1ff94-104">Per determinare quale nodo di TreeView scelto</span><span class="sxs-lookup"><span data-stu-id="1ff94-104">To determine which TreeView node was clicked</span></span>  
  
1. <span data-ttu-id="1ff94-105">Usare il <xref:System.EventArgs> oggetto per restituire un riferimento all'oggetto del nodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="1ff94-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2. <span data-ttu-id="1ff94-106">Determinare quale nodo è stato scelto controllando il <xref:System.Windows.Forms.TreeViewEventArgs> classe, che contiene i dati relativi all'evento.</span><span class="sxs-lookup"><span data-stu-id="1ff94-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
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
    >  <span data-ttu-id="1ff94-107">In alternativa, è possibile usare la <xref:System.Windows.Forms.MouseEventArgs> del <xref:System.Windows.Forms.Control.MouseDown> o <xref:System.Windows.Forms.Control.MouseUp> evento per ottenere il <xref:System.Drawing.Point.X%2A> e <xref:System.Drawing.Point.Y%2A> coordinare i valori del <xref:System.Drawing.Point> in cui si è verificato il clic.</span><span class="sxs-lookup"><span data-stu-id="1ff94-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="1ff94-108">Quindi, usare il <xref:System.Windows.Forms.TreeView> del controllo <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> metodo per determinare quale nodo è stato fatto clic.</span><span class="sxs-lookup"><span data-stu-id="1ff94-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ff94-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ff94-109">See also</span></span>

- [<span data-ttu-id="1ff94-110">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="1ff94-110">TreeView Control</span></span>](treeview-control-windows-forms.md)

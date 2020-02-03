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
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="ccf9c-102">Procedura: Individuare il nodo di TreeView scelto (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="ccf9c-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="ccf9c-103">Quando si lavora con il controllo Windows Forms <xref:System.Windows.Forms.TreeView>, un'attività comune consiste nel determinare quale nodo è stato selezionato e rispondere in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="ccf9c-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="ccf9c-104">Per determinare quale nodo di TreeView è stato selezionato</span><span class="sxs-lookup"><span data-stu-id="ccf9c-104">To determine which TreeView node was clicked</span></span>  
  
1. <span data-ttu-id="ccf9c-105">Utilizzare l'oggetto <xref:System.EventArgs> per restituire un riferimento all'oggetto nodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="ccf9c-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2. <span data-ttu-id="ccf9c-106">Determinare su quale nodo è stato fatto clic controllando la classe <xref:System.Windows.Forms.TreeViewEventArgs>, che contiene i dati relativi all'evento.</span><span class="sxs-lookup"><span data-stu-id="ccf9c-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
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
    > <span data-ttu-id="ccf9c-107">In alternativa, è possibile usare la <xref:System.Windows.Forms.MouseEventArgs> dell'evento <xref:System.Windows.Forms.Control.MouseDown> o <xref:System.Windows.Forms.Control.MouseUp> per ottenere i valori di <xref:System.Drawing.Point.X%2A> e di coordinata <xref:System.Drawing.Point.Y%2A> del <xref:System.Drawing.Point> in cui si è verificato il clic.</span><span class="sxs-lookup"><span data-stu-id="ccf9c-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="ccf9c-108">Usare quindi il metodo di <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> del controllo <xref:System.Windows.Forms.TreeView> per determinare il nodo su cui è stato fatto clic.</span><span class="sxs-lookup"><span data-stu-id="ccf9c-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf9c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccf9c-109">See also</span></span>

- [<span data-ttu-id="ccf9c-110">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="ccf9c-110">TreeView Control</span></span>](treeview-control-windows-forms.md)

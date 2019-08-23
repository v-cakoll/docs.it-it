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
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="d8bdd-102">Procedura: Determinare il nodo TreeView selezionato (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="d8bdd-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="d8bdd-103">Quando si utilizza il controllo <xref:System.Windows.Forms.TreeView> Windows Forms, un'attività comune consiste nel determinare il nodo selezionato e rispondere in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="d8bdd-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="d8bdd-104">Per determinare quale nodo di TreeView è stato selezionato</span><span class="sxs-lookup"><span data-stu-id="d8bdd-104">To determine which TreeView node was clicked</span></span>  
  
1. <span data-ttu-id="d8bdd-105">Utilizzare l' <xref:System.EventArgs> oggetto per restituire un riferimento all'oggetto nodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="d8bdd-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2. <span data-ttu-id="d8bdd-106">Determinare su quale nodo è stato fatto clic controllando la <xref:System.Windows.Forms.TreeViewEventArgs> classe, che contiene i dati relativi all'evento.</span><span class="sxs-lookup"><span data-stu-id="d8bdd-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
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
    > <span data-ttu-id="d8bdd-107">In alternativa, è possibile usare l'oggetto <xref:System.Windows.Forms.MouseEventArgs> <xref:System.Windows.Forms.Control.MouseDown> dell'evento o <xref:System.Windows.Forms.Control.MouseUp> per ottenere i <xref:System.Drawing.Point.X%2A> valori della <xref:System.Drawing.Point.Y%2A> coordinata e <xref:System.Drawing.Point> dell'oggetto in cui si è verificato il clic.</span><span class="sxs-lookup"><span data-stu-id="d8bdd-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="d8bdd-108">Usare quindi il <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> metodo <xref:System.Windows.Forms.TreeView> del controllo per determinare su quale nodo è stato fatto clic.</span><span class="sxs-lookup"><span data-stu-id="d8bdd-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8bdd-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8bdd-109">See also</span></span>

- [<span data-ttu-id="d8bdd-110">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="d8bdd-110">TreeView Control</span></span>](treeview-control-windows-forms.md)

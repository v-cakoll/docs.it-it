---
title: 'Procedura: scorrere tutti i nodi di un controllo TreeView Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], iterating through nodes
- tree nodes in TreeView control [Windows Forms], iterating through
ms.assetid: 427f8928-ebcf-4beb-887f-695b905d5134
ms.openlocfilehash: 89a2c1411ab64b4a20ad291165cfa6d83511c4c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532756"
---
# <a name="how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control"></a><span data-ttu-id="3a5d2-102">Procedura: scorrere tutti i nodi di un controllo TreeView Windows Form</span><span class="sxs-lookup"><span data-stu-id="3a5d2-102">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>
<span data-ttu-id="3a5d2-103">È talvolta utile esaminare tutti i nodi in un Windows Form <xref:System.Windows.Forms.TreeView> controllo per eseguire alcuni calcoli sui valori del nodo.</span><span class="sxs-lookup"><span data-stu-id="3a5d2-103">It is sometimes useful to examine every node in a Windows Forms <xref:System.Windows.Forms.TreeView> control in order to perform some calculation on the node values.</span></span> <span data-ttu-id="3a5d2-104">Questa operazione può essere eseguita usando una routine ricorsiva (metodo ricorsivo in C# e C++) che esegue l'iterazione in ogni nodo in ogni raccolta dell'albero.</span><span class="sxs-lookup"><span data-stu-id="3a5d2-104">This operation can be done using a recursive procedure (recursive method in C# and C++) that iterates through each node in each collection of the tree.</span></span>  
  
 <span data-ttu-id="3a5d2-105">Ogni <xref:System.Windows.Forms.TreeNode> oggetto in una visualizzazione albero include proprietà che è possibile utilizzare per spostarsi nella visualizzazione struttura ad albero: <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A>, e <xref:System.Windows.Forms.TreeNode.Parent%2A>.</span><span class="sxs-lookup"><span data-stu-id="3a5d2-105">Each <xref:System.Windows.Forms.TreeNode> object in a tree view has properties that you can use to navigate the tree view: <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A>, and <xref:System.Windows.Forms.TreeNode.Parent%2A>.</span></span> <span data-ttu-id="3a5d2-106">Il valore di <xref:System.Windows.Forms.TreeNode.Parent%2A> proprietà è il nodo padre del nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="3a5d2-106">The value of the <xref:System.Windows.Forms.TreeNode.Parent%2A> property is the parent node of the current node.</span></span> <span data-ttu-id="3a5d2-107">I nodi figlio del nodo corrente, se sono presenti, vengono elencati nel relativo <xref:System.Windows.Forms.TreeNode.Nodes%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="3a5d2-107">The child nodes of the current node, if there are any, are listed in its <xref:System.Windows.Forms.TreeNode.Nodes%2A> property.</span></span> <span data-ttu-id="3a5d2-108">Il <xref:System.Windows.Forms.TreeView> stesso controllo dispone di <xref:System.Windows.Forms.TreeView.TopNode%2A> proprietà, che è il nodo radice dell'intera visualizzazione struttura.</span><span class="sxs-lookup"><span data-stu-id="3a5d2-108">The <xref:System.Windows.Forms.TreeView> control itself has the <xref:System.Windows.Forms.TreeView.TopNode%2A> property, which is the root node of the entire tree view.</span></span>  
  
### <a name="to-iterate-through-all-nodes-of-the-treeview-control"></a><span data-ttu-id="3a5d2-109">Per eseguire l'iterazione in tutti i nodi di un controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="3a5d2-109">To iterate through all nodes of the TreeView control</span></span>  
  
1.  <span data-ttu-id="3a5d2-110">Creare una routine ricorsiva (metodo ricorsivo in C# e C++) che verifica ogni nodo.</span><span class="sxs-lookup"><span data-stu-id="3a5d2-110">Create a recursive procedure (recursive method in C# and C++) that tests each node.</span></span>  
  
2.  <span data-ttu-id="3a5d2-111">Chiamare la routine.</span><span class="sxs-lookup"><span data-stu-id="3a5d2-111">Call the procedure.</span></span>  
  
     <span data-ttu-id="3a5d2-112">Nell'esempio seguente viene illustrato come stampare ogni <xref:System.Windows.Forms.TreeNode> dell'oggetto <xref:System.Windows.Forms.TreeNode.Text%2A> proprietà:</span><span class="sxs-lookup"><span data-stu-id="3a5d2-112">The following example shows how to print each <xref:System.Windows.Forms.TreeNode> object's <xref:System.Windows.Forms.TreeNode.Text%2A> property:</span></span>  
  
    ```vb  
    Private Sub PrintRecursive(ByVal n As TreeNode)  
       System.Diagnostics.Debug.WriteLine(n.Text)  
       MessageBox.Show(n.Text)  
       Dim aNode As TreeNode  
       For Each aNode In n.Nodes  
          PrintRecursive(aNode)  
       Next  
    End Sub  
  
    ' Call the procedure using the top nodes of the treeview.  
    Private Sub CallRecursive(ByVal aTreeView As TreeView)  
       Dim n As TreeNode  
       For Each n In aTreeView.Nodes  
          PrintRecursive(n)  
       Next  
    End Sub  
    ```  
  
    ```csharp  
    private void PrintRecursive(TreeNode treeNode)  
    {  
       // Print the node.  
       System.Diagnostics.Debug.WriteLine(treeNode.Text);  
       MessageBox.Show(treeNode.Text);  
       // Print each node recursively.  
       foreach (TreeNode tn in treeNode.Nodes)  
       {  
          PrintRecursive(tn);  
       }  
    }  
  
    // Call the procedure using the TreeView.  
    private void CallRecursive(TreeView treeView)  
    {  
       // Print each node recursively.  
       TreeNodeCollection nodes = treeView.Nodes;  
       foreach (TreeNode n in nodes)  
       {  
          PrintRecursive(n);  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void PrintRecursive( TreeNode^ treeNode )  
       {  
          // Print the node.  
          System::Diagnostics::Debug::WriteLine( treeNode->Text );  
          MessageBox::Show( treeNode->Text );  
  
          // Print each node recursively.  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(treeNode->Nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ tn = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( tn );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
  
       // Call the procedure using the TreeView.  
       void CallRecursive( TreeView^ treeView )  
       {  
          // Print each node recursively.  
          TreeNodeCollection^ nodes = treeView->Nodes;  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ n = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( n );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3a5d2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a5d2-113">See Also</span></span>  
 [<span data-ttu-id="3a5d2-114">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="3a5d2-114">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [<span data-ttu-id="3a5d2-115">Routine ricorsive</span><span class="sxs-lookup"><span data-stu-id="3a5d2-115">Recursive Procedures</span></span>](~/docs/visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)

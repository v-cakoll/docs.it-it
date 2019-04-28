---
title: 'Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- ListItem
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- examples [Windows Forms], ListView control
- ListView control [Windows Forms], adding custom information
- TreeView control [Windows Forms], adding custom information
ms.assetid: 68be11de-1d5b-430e-901f-cfbe48d14b19
ms.openlocfilehash: 302eb1b88d4e43b4e2bd6395e27a3a6489320085
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640399"
---
# <a name="how-to-add-custom-information-to-a-treeview-or-listview-control-windows-forms"></a><span data-ttu-id="7ffda-102">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="7ffda-102">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>
<span data-ttu-id="7ffda-103">È possibile creare un nodo derivato in un controllo Windows Form <xref:System.Windows.Forms.TreeView> controllo o un elemento derivato in un <xref:System.Windows.Forms.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="7ffda-103">You can create a derived node in a Windows Forms <xref:System.Windows.Forms.TreeView> control or a derived item in a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="7ffda-104">La derivazione consente di aggiungere eventuali campi necessari, nonché metodi personalizzati e costruttori per gestirli.</span><span class="sxs-lookup"><span data-stu-id="7ffda-104">Derivation allows you to add any fields you require, as well as custom methods and constructors for handling them.</span></span> <span data-ttu-id="7ffda-105">Un utilizzo di questa funzionalità consiste nel collegare un oggetto Customer a ogni nodo di una struttura ad albero o voce di elenco.</span><span class="sxs-lookup"><span data-stu-id="7ffda-105">One use of this feature is to attach a Customer object to each tree node or list item.</span></span> <span data-ttu-id="7ffda-106">Negli esempi seguenti sono per un <xref:System.Windows.Forms.TreeView> controllo, ma lo stesso approccio può essere utilizzato per un <xref:System.Windows.Forms.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="7ffda-106">The examples here are for a <xref:System.Windows.Forms.TreeView> control, but the same approach can be used for a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
### <a name="to-derive-a-tree-node"></a><span data-ttu-id="7ffda-107">Per derivare un nodo della struttura ad albero</span><span class="sxs-lookup"><span data-stu-id="7ffda-107">To derive a tree node</span></span>  
  
- <span data-ttu-id="7ffda-108">Creare una nuova classe nodo, derivata dal <xref:System.Windows.Forms.TreeNode> classe, che ha un campo personalizzato per registrare un percorso di file.</span><span class="sxs-lookup"><span data-stu-id="7ffda-108">Create a new node class, derived from the <xref:System.Windows.Forms.TreeNode> class, which has a custom field to record a file path.</span></span>  
  
    ```vb  
    Class myTreeNode  
       Inherits TreeNode  
  
       Public FilePath As String  
  
       Sub New(ByVal fp As String)  
          MyBase.New()  
          FilePath = fp  
          Me.Text = fp.Substring(fp.LastIndexOf("\"))  
       End Sub  
    End Class  
    ```  
  
    ```csharp  
    class myTreeNode : TreeNode  
    {  
       public string FilePath;  
  
       public myTreeNode(string fp)  
       {  
          FilePath = fp;  
          this.Text = fp.Substring(fp.LastIndexOf("\\"));  
       }  
    }  
    ```  
  
    ```cpp  
    ref class myTreeNode : public TreeNode  
    {  
    public:  
       System::String ^ FilePath;  
  
       myTreeNode(System::String ^ fp)  
       {  
          FilePath = fp;  
          this->Text = fp->Substring(fp->LastIndexOf("\\"));  
       }  
    };  
    ```  
  
### <a name="to-use-a-derived-tree-node"></a><span data-ttu-id="7ffda-109">Per usare un nodo di struttura ad albero derivato</span><span class="sxs-lookup"><span data-stu-id="7ffda-109">To use a derived tree node</span></span>  
  
1. <span data-ttu-id="7ffda-110">È possibile usare il nuovo nodo della struttura ad albero derivato come parametro per le chiamate di funzione.</span><span class="sxs-lookup"><span data-stu-id="7ffda-110">You can use the new derived tree node as a parameter to function calls.</span></span>  
  
     <span data-ttu-id="7ffda-111">Nell'esempio seguente il percorso impostato per la posizione del file di testo è la cartella Documenti.</span><span class="sxs-lookup"><span data-stu-id="7ffda-111">In the example below, the path set for the location of the text file is the My Documents folder.</span></span> <span data-ttu-id="7ffda-112">Si procede in questo modo perché si presume che la maggior parte dei computer con il sistema operativo Windows avrà questa directory.</span><span class="sxs-lookup"><span data-stu-id="7ffda-112">This is done because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="7ffda-113">Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi.</span><span class="sxs-lookup"><span data-stu-id="7ffda-113">This also allows users with minimal system access levels to safely run the application.</span></span>  
  
    ```vb  
    ' You should replace the bold text file   
    ' in the sample below with a text file of your own choosing.  
    TreeView1.Nodes.Add(New myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\ TextFile.txt ") )  
    ```  
  
    ```csharp  
    // You should replace the bold text file   
    // in the sample below with a text file of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    treeView1.Nodes.Add(new myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\TextFile.txt") );  
    ```  
  
    ```cpp  
    // You should replace the bold text file   
    // in the sample below with a text file of your own choosing.  
    treeView1->Nodes->Add(new myTreeNode(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\TextFile.txt")));  
    ```  
  
2. <span data-ttu-id="7ffda-114">Se è stato passato il nodo dell'albero e viene indicato come un <xref:System.Windows.Forms.TreeNode> classe, sarà necessario eseguire il cast alla classe derivata.</span><span class="sxs-lookup"><span data-stu-id="7ffda-114">If you are passed the tree node and it is typed as a <xref:System.Windows.Forms.TreeNode> class, then you will need to cast to your derived class.</span></span> <span data-ttu-id="7ffda-115">Il cast è una conversione esplicita da un tipo di oggetto a un altro.</span><span class="sxs-lookup"><span data-stu-id="7ffda-115">Casting is an explicit conversion from one type of object to another.</span></span> <span data-ttu-id="7ffda-116">Per altre informazioni sul cast, vedere [conversioni implicite ed esplicite](~/docs/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) (Visual Basic), [() operatore](~/docs/csharp/language-reference/operators/invocation-operator.md) (Visual C#), o [operatore Cast: ()](/cpp/cpp/cast-operator-parens) ([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) .</span><span class="sxs-lookup"><span data-stu-id="7ffda-116">For more information on casting, see [Implicit and Explicit Conversions](~/docs/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) (Visual Basic), [() Operator](~/docs/csharp/language-reference/operators/invocation-operator.md) (Visual C#), or [Cast Operator: ()](/cpp/cpp/cast-operator-parens) ([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]).</span></span>  
  
    ```vb  
    Public Sub TreeView1_AfterSelect(ByVal sender As Object, ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       Dim mynode As myTreeNode  
       mynode = CType(e.node, myTreeNode)  
       MessageBox.Show("Node selected is " & mynode.filepath)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,  
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       myTreeNode myNode = (myTreeNode)e.Node;  
       MessageBox.Show("Node selected is " + myNode.FilePath);  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          myTreeNode ^ myNode = safe_cast<myTreeNode^>(e->Node);  
          MessageBox::Show(String::Concat("Node selected is ",   
             myNode->FilePath));  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7ffda-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ffda-117">See also</span></span>

- [<span data-ttu-id="7ffda-118">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="7ffda-118">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="7ffda-119">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="7ffda-119">ListView Control</span></span>](listview-control-windows-forms.md)

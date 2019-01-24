---
title: 'Procedura: Associare un controllo di Windows Form a un oggetto Factory'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], binding
- factory objects [Windows Forms], binding to
- BindingSource component [Windows Forms], binding to a factory object
- BindingSource component [Windows Forms], examples
ms.assetid: 7d59af89-ff82-41d8-a48a-f1fbae788b0d
ms.openlocfilehash: 0173a4ef19765a74df819640f134e782b89395a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730009"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-factory-object"></a><span data-ttu-id="78dce-102">Procedura: Associare un controllo di Windows Form a un oggetto Factory</span><span class="sxs-lookup"><span data-stu-id="78dce-102">How to: Bind a Windows Forms Control to a Factory Object</span></span>
<span data-ttu-id="78dce-103">Quando si compilano controlli che interagiscono con i dati, è a volte necessario associare un controllo a un oggetto o metodo che genera altri oggetti.</span><span class="sxs-lookup"><span data-stu-id="78dce-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to an object or method that generates other objects.</span></span> <span data-ttu-id="78dce-104">Tale oggetto o metodo è definito factory.</span><span class="sxs-lookup"><span data-stu-id="78dce-104">Such an object or method is called a factory.</span></span> <span data-ttu-id="78dce-105">L'origine dati, ad esempio, potrebbe essere il valore restituito da una chiamata al metodo anziché un oggetto in memoria o un tipo.</span><span class="sxs-lookup"><span data-stu-id="78dce-105">Your data source might be, for example, the return value from a method call, instead of an object in memory or a type.</span></span> <span data-ttu-id="78dce-106">È possibile associare un controllo a tale tipo di origine dati purché l'origine restituisca una raccolta.</span><span class="sxs-lookup"><span data-stu-id="78dce-106">You can bind a control to this kind of data source as long as the source returns a collection.</span></span>  
  
 <span data-ttu-id="78dce-107">È possibile associare facilmente un controllo a un oggetto factory usando il controllo <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="78dce-107">You can easily bind a control to a factory object by using the <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78dce-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="78dce-108">Example</span></span>  
 <span data-ttu-id="78dce-109">Nell'esempio seguente viene dimostrato come associare un controllo <xref:System.Windows.Forms.DataGridView> a un metodo factory mediante un controllo <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="78dce-109">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a factory method by using a <xref:System.Windows.Forms.BindingSource> control.</span></span> <span data-ttu-id="78dce-110">Il metodo factory, denominato `GetOrdersByCustomerId`, restituisce tutti gli ordini di un dato cliente nel database Northwind.</span><span class="sxs-lookup"><span data-stu-id="78dce-110">The factory method is named `GetOrdersByCustomerId`, and it returns all the orders for a given customer in the Northwind database.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="78dce-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="78dce-111">Compiling the Code</span></span>  
 <span data-ttu-id="78dce-112">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="78dce-112">This example requires:</span></span>  
  
-   <span data-ttu-id="78dce-113">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="78dce-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="78dce-114">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="78dce-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="78dce-115">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="78dce-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="78dce-116">Vedere anche [come: Compilare ed eseguire un esempio di codice completo di Windows Form con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="78dce-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78dce-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78dce-117">See also</span></span>
- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="78dce-118">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="78dce-118">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [<span data-ttu-id="78dce-119">Procedura: Associare un controllo di Windows Form a un tipo</span><span class="sxs-lookup"><span data-stu-id="78dce-119">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)

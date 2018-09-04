---
title: "Procedura: personalizzare l'aggiunta di elementi con BindingSource Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], creating new items
- BindingSource component [Windows Forms], customizing item addition with
- examples [Windows Forms], BindingSource component
- BindingSource component [Windows Forms], examples
ms.assetid: 1aae11fc-6fb2-4cb9-b3d0-e0638fe77ef0
ms.openlocfilehash: f8956ceb8da2aa14aea8b7e62b9d60ab656a3891
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529428"
---
# <a name="how-to-customize-item-addition-with-the-windows-forms-bindingsource"></a><span data-ttu-id="2c43a-102">Procedura: personalizzare l'aggiunta di elementi con BindingSource Windows Form</span><span class="sxs-lookup"><span data-stu-id="2c43a-102">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>
<span data-ttu-id="2c43a-103">Quando si usa un componente <xref:System.Windows.Forms.BindingSource> per associare un controllo Windows Form a un'origine dati, potrebbe essere necessario personalizzare la creazione di nuovi elementi.</span><span class="sxs-lookup"><span data-stu-id="2c43a-103">When you use a <xref:System.Windows.Forms.BindingSource> component to bind a Windows Forms control to a data source, you may find it necessary to customize the creation of new items.</span></span> <span data-ttu-id="2c43a-104">Il componente <xref:System.Windows.Forms.BindingSource> semplifica questa attività per mezzo dell'evento <xref:System.Windows.Forms.BindingSource.AddingNew> , che di solito viene generato quando il controllo associato deve creare un nuovo elemento.</span><span class="sxs-lookup"><span data-stu-id="2c43a-104">The <xref:System.Windows.Forms.BindingSource> component makes this straightforward by providing the <xref:System.Windows.Forms.BindingSource.AddingNew> event, which is typically raised when the bound control needs to create a new item.</span></span> <span data-ttu-id="2c43a-105">Il gestore eventi può fornire qualsiasi comportamento personalizzato sia necessario (ad esempio, la chiamata a un metodo su un servizio Web o l'acquisizione di un nuovo oggetto da una class factory).</span><span class="sxs-lookup"><span data-stu-id="2c43a-105">Your event handler can provide whatever custom behavior is required (for example, calling a method on a Web service or getting a new object from a class factory).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c43a-106">Quando un elemento viene aggiunto gestendo l'evento <xref:System.Windows.Forms.BindingSource.AddingNew> , l'aggiunta non può essere annullata.</span><span class="sxs-lookup"><span data-stu-id="2c43a-106">When an item is added by handling the <xref:System.Windows.Forms.BindingSource.AddingNew> event, the addition cannot be canceled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c43a-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c43a-107">Example</span></span>  
 <span data-ttu-id="2c43a-108">Il seguente esempio mostra come associare un controllo <xref:System.Windows.Forms.DataGridView> a una class factory usando un componente <xref:System.Windows.Forms.BindingSource> .</span><span class="sxs-lookup"><span data-stu-id="2c43a-108">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a class factory by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="2c43a-109">Quando l'utente fa clic sulla nuova riga del controllo <xref:System.Windows.Forms.DataGridView> , viene generato l'evento <xref:System.Windows.Forms.BindingSource.AddingNew> .</span><span class="sxs-lookup"><span data-stu-id="2c43a-109">When the user clicks the <xref:System.Windows.Forms.DataGridView> control's new row, the <xref:System.Windows.Forms.BindingSource.AddingNew> event is raised.</span></span> <span data-ttu-id="2c43a-110">Il gestore eventi crea un nuovo oggetto `DemoCustomer`, che viene assegnato alla proprietà <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2c43a-110">The event handler creates a new `DemoCustomer` object, which is assigned to the <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="2c43a-111">In questo modo il nuovo oggetto `DemoCustomer` viene aggiunto all'elenco del componente <xref:System.Windows.Forms.BindingSource> e visualizzato nella nuova riga del controllo <xref:System.Windows.Forms.DataGridView> .</span><span class="sxs-lookup"><span data-stu-id="2c43a-111">This causes the new `DemoCustomer` object to be added to the <xref:System.Windows.Forms.BindingSource> component's list and to be displayed in the new row of the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2c43a-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2c43a-112">Compiling the Code</span></span>  
 <span data-ttu-id="2c43a-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c43a-113">This example requires:</span></span>  
  
-   <span data-ttu-id="2c43a-114">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="2c43a-114">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="2c43a-115">Per informazioni sulla compilazione di questo esempio dalla riga di comando per visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="2c43a-115">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="2c43a-116">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="2c43a-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="2c43a-117">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo tramite Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="2c43a-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c43a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c43a-118">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="2c43a-119">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="2c43a-119">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="2c43a-120">Procedura: Associare un controllo di Windows Form a un tipo</span><span class="sxs-lookup"><span data-stu-id="2c43a-120">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)

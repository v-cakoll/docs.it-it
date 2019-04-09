---
title: 'Procedura: Associare un controllo di Windows Forms a un tipo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
ms.openlocfilehash: f47090f5d0765833f7ac17a947691a4693d9923b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162490"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a><span data-ttu-id="eb6fe-102">Procedura: Associare un controllo di Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="eb6fe-102">How to: Bind a Windows Forms Control to a Type</span></span>
<span data-ttu-id="eb6fe-103">Quando si compilano controlli che interagiscono con i dati, a volte è necessario associare un controllo a un tipo, invece che a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="eb6fe-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="eb6fe-104">Questa situazione si verifica soprattutto in fase di progettazione, quando i dati potrebbero non essere disponibili, ma i controlli associati a dati devono visualizzare informazioni provenienti dall'interfaccia pubblica di un tipo.</span><span class="sxs-lookup"><span data-stu-id="eb6fe-104">This situation arises especially at design time, when data may not be available, but your data-bound controls still need to display information from a type's public interface.</span></span> <span data-ttu-id="eb6fe-105">Ad esempio, se si associa un controllo <xref:System.Windows.Forms.DataGridView> a un oggetto esposto da un servizio Web, potrebbe essere necessario che in fase di progettazione il controllo <xref:System.Windows.Forms.DataGridView> assegni alle colonne un'etichetta con i nomi dei membri di un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="eb6fe-105">For example, you may bind a <xref:System.Windows.Forms.DataGridView> control to an object exposed by a Web service and want the <xref:System.Windows.Forms.DataGridView> control to label its columns at design time with the member names of a custom type.</span></span>  
  
 <span data-ttu-id="eb6fe-106">È possibile associare facilmente un controllo a un tipo con il componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="eb6fe-106">You can easily bind a control to a type with the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb6fe-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="eb6fe-107">Example</span></span>  
 <span data-ttu-id="eb6fe-108">Il seguente esempio di codice mostra come associare un controllo <xref:System.Windows.Forms.DataGridView> a un tipo personalizzato usando un componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="eb6fe-108">The following code example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a custom type by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="eb6fe-109">Quando si esegue l'esempio, si noterà che le etichette delle colonne di <xref:System.Windows.Forms.DataGridView> rispecchiano le proprietà di un oggetto `Customer`, prima ancora che il controllo venga popolato con i dati.</span><span class="sxs-lookup"><span data-stu-id="eb6fe-109">When you run the example, you'll notice the <xref:System.Windows.Forms.DataGridView> has labeled columns that reflect the properties of a `Customer` object, before the control is populated with data.</span></span> <span data-ttu-id="eb6fe-110">L'esempio contiene un pulsante Add Customer per aggiungere dati al controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="eb6fe-110">The example has an Add Customer button to add data to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="eb6fe-111">Quando si fa clic sul pulsante, un nuovo oggetto `Customer` viene aggiunto a <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="eb6fe-111">When you click the button, a new `Customer` object is added to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="eb6fe-112">In uno scenario reale, i dati potrebbero essere ottenuti da una chiamata a un servizio Web o da un'altra origine dati.</span><span class="sxs-lookup"><span data-stu-id="eb6fe-112">In a real-world scenario, the data might be obtained by a call to a Web service or other data source.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eb6fe-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="eb6fe-113">Compiling the Code</span></span>  
 <span data-ttu-id="eb6fe-114">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb6fe-114">This example requires:</span></span>  
  
-   <span data-ttu-id="eb6fe-115">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="eb6fe-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="eb6fe-116">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="eb6fe-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="eb6fe-117">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="eb6fe-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb6fe-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb6fe-118">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="eb6fe-119">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="eb6fe-119">BindingSource Component</span></span>](bindingsource-component.md)

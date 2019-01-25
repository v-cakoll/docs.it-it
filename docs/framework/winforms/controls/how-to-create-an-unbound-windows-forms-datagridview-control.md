---
title: 'Procedura: Creare un controllo DataGridView di Windows non associato form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
ms.assetid: b5d4b47d-9a28-4d88-9dba-0a3c90fba71d
ms.openlocfilehash: a1752be8aaac71dff62fe0e4fcd75ab8e386bae5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703103"
---
# <a name="how-to-create-an-unbound-windows-forms-datagridview-control"></a><span data-ttu-id="4f87b-102">Procedura: Creare un controllo DataGridView di Windows non associato form</span><span class="sxs-lookup"><span data-stu-id="4f87b-102">How to: Create an Unbound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4f87b-103">Nell'esempio di codice seguente viene illustrato come compilare un controllo <xref:System.Windows.Forms.DataGridView> a livello di codice senza associarlo a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="4f87b-103">The following code example demonstrates how to populate a <xref:System.Windows.Forms.DataGridView> control programmatically without binding it to a data source.</span></span> <span data-ttu-id="4f87b-104">Ciò è utile quando si dispone di una piccola quantità di dati che si vuole visualizzare in formato tabella.</span><span class="sxs-lookup"><span data-stu-id="4f87b-104">This is useful when you have a small amount of data that you want to display in a table format.</span></span>  
  
 <span data-ttu-id="4f87b-105">Per una spiegazione completa di questo esempio di codice, vedere [procedura dettagliata: Creazione di un Windows non associato di controllo DataGridView form](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="4f87b-105">For a complete explanation of this code example, see [Walkthrough: Creating an Unbound Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f87b-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f87b-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4f87b-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4f87b-107">Compiling the Code</span></span>  
 <span data-ttu-id="4f87b-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f87b-108">This example requires:</span></span>  
  
-   <span data-ttu-id="4f87b-109">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="4f87b-109">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="4f87b-110">Per informazioni sulla compilazione di questo esempio dalla riga di comando per visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4f87b-110">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="4f87b-111">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="4f87b-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="4f87b-112">Vedere anche [come: Compilare ed eseguire un esempio di codice completo di Windows Form con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="4f87b-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f87b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f87b-113">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="4f87b-114">Procedura dettagliata: Creazione di una cornice di Windows Form controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="4f87b-114">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [<span data-ttu-id="4f87b-115">Visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4f87b-115">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="4f87b-116">Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4f87b-116">Data Display Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)

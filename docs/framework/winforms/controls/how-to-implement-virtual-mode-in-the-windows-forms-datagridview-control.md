---
title: 'Procedura: Implementare la modalità virtuale nel controllo DataGridView Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode
- DataGridView control [Windows Forms], large data sets
ms.assetid: 98236267-f08e-4918-bcf9-77acf050a3ca
ms.openlocfilehash: 7ece3dd8c5f0e56c335c85d72030f1b9aa56e33b
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260979"
---
# <a name="how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="1bb58-102">Procedura: Implementare la modalità virtuale nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="1bb58-102">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1bb58-103">Nell'esempio di codice seguente viene illustrato come gestire insiemi di dati di grandi dimensioni mediante un controllo <xref:System.Windows.Forms.DataGridView> con la proprietà <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="1bb58-103">The following code example demonstrates how to manage large sets of data using a <xref:System.Windows.Forms.DataGridView> control with its <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property set to `true`.</span></span>  
  
 <span data-ttu-id="1bb58-104">Per una spiegazione completa di questo esempio di codice, vedere [procedura dettagliata: Implementazione della modalità virtuale in Windows il controllo DataGridView form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="1bb58-104">For a complete explanation of this code example, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bb58-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="1bb58-105">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#000](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#000)]
 [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1bb58-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="1bb58-106">Compiling the Code</span></span>  
 <span data-ttu-id="1bb58-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1bb58-107">This example requires:</span></span>  
  
-   <span data-ttu-id="1bb58-108">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="1bb58-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="1bb58-109">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1bb58-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1bb58-110">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="1bb58-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bb58-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bb58-111">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="1bb58-112">Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="1bb58-112">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)
- [<span data-ttu-id="1bb58-113">Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1bb58-113">Performance Tuning in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1bb58-114">Modo virtuale nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1bb58-114">Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)

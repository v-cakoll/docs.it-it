---
title: 'Procedura: Associare oggetti ai controlli DataGridView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
ms.openlocfilehash: e3ca2ab4be95a77bd2549ae8435d8158434532da
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220244"
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a><span data-ttu-id="06159-102">Procedura: Associare oggetti ai controlli DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="06159-102">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="06159-103">L'esempio di codice seguente illustra come associare un insieme di oggetti a un controllo <xref:System.Windows.Forms.DataGridView> in modo che ogni oggetto venga visualizzato come riga separata.</span><span class="sxs-lookup"><span data-stu-id="06159-103">The following code example demonstrates how to bind a collection of objects to a <xref:System.Windows.Forms.DataGridView> control so that each object displays as a separate row.</span></span> <span data-ttu-id="06159-104">L'esempio descrive anche come visualizzare una proprietà con un tipo di enumerazione in una classe <xref:System.Windows.Forms.DataGridViewComboBoxColumn> in maniera che l'elenco a discesa della casella combinata contenga i valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="06159-104">This example also illustrates how to display a property with an enumeration type in a <xref:System.Windows.Forms.DataGridViewComboBoxColumn> so that the combo box drop-down list contains the enumeration values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06159-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="06159-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="06159-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="06159-106">Compiling the Code</span></span>  
 <span data-ttu-id="06159-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="06159-107">This example requires:</span></span>  
  
-   <span data-ttu-id="06159-108">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="06159-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="06159-109">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="06159-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="06159-110">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="06159-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06159-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06159-111">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="06159-112">Visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="06159-112">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="06159-113">Procedura: Accedere a oggetti associati a un Windows Form righe DataGridView</span><span class="sxs-lookup"><span data-stu-id="06159-113">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](../../../../docs/framework/winforms/controls/how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)

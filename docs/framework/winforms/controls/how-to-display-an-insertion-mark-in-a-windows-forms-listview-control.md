---
title: 'Procedura: visualizzare un segno di inserimento in un controllo ListView per Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ListView control [Windows Forms], drag operations
- graphics [Windows Forms], insertion marks
- drop and drag [Windows Forms], insertion marks
- insertion marks
ms.assetid: 88d0a15b-25fd-4dc3-a685-297351311940
ms.openlocfilehash: b9b6e1911d3e372861ebcdc5a175314d69c89175
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "46000752"
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a><span data-ttu-id="9b937-102">Procedura: visualizzare un segno di inserimento in un controllo ListView per Windows Form</span><span class="sxs-lookup"><span data-stu-id="9b937-102">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>
<span data-ttu-id="9b937-103">Il segno di inserimento nel controllo <xref:System.Windows.Forms.ListView> indica agli utenti il punto in cui verranno inseriti gli elementi trascinati.</span><span class="sxs-lookup"><span data-stu-id="9b937-103">The insertion mark in the <xref:System.Windows.Forms.ListView> control shows users the point where dragged items will be inserted.</span></span> <span data-ttu-id="9b937-104">Quando un utente trascina un elemento in un punto intermedio tra due elementi, il segno di inserimento indica la nuova posizione prevista dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="9b937-104">When a user drags an item to a point between two other items, the insertion mark shows the item's expected new location.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b937-105">La funzionalità del segno di inserimento è disponibile solo in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando l'applicazione chiama il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9b937-105">The insertion mark feature is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9b937-106">Nei sistemi operativi precedenti, qualsiasi codice relativo al segno di inserimento non ha alcun effetto e il segno di inserimento non verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="9b937-106">On earlier operating systems, any code relating to the insertion mark has no effect and the insertion mark will not appear.</span></span> <span data-ttu-id="9b937-107">Per altre informazioni, vedere <xref:System.Windows.Forms.ListViewInsertionMark>.</span><span class="sxs-lookup"><span data-stu-id="9b937-107">For more information, see <xref:System.Windows.Forms.ListViewInsertionMark>.</span></span>  
  
 <span data-ttu-id="9b937-108">L'immagine seguente mostra un segno di inserimento:</span><span class="sxs-lookup"><span data-stu-id="9b937-108">The following image shows an insertion mark:</span></span>  
  
 <span data-ttu-id="9b937-109">![Segno di inserimento di ListView](../../../../docs/framework/winforms/controls/media/listviewinsertion.gif "ListViewInsertion")</span><span class="sxs-lookup"><span data-stu-id="9b937-109">![A ListView Insertion Mark](../../../../docs/framework/winforms/controls/media/listviewinsertion.gif "ListViewInsertion")</span></span>  
  
 <span data-ttu-id="9b937-110">L'esempio di codice seguente illustra l'uso di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9b937-110">The following code example demonstrates how to use this feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b937-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b937-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9b937-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="9b937-112">Compiling the Code</span></span>  
 <span data-ttu-id="9b937-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b937-113">This example requires:</span></span>  
  
-   <span data-ttu-id="9b937-114">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="9b937-114">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="9b937-115">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9b937-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9b937-116">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="9b937-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="9b937-117">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo tramite Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="9b937-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b937-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b937-118">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ListViewInsertionMark>  
 [<span data-ttu-id="9b937-119">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="9b937-119">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="9b937-120">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="9b937-120">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="9b937-121">Funzionalità di Windows XP e controlli di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9b937-121">Windows XP Features and Windows Forms Controls</span></span>](https://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [<span data-ttu-id="9b937-122">Procedura dettagliata: esecuzione di un'operazione di trascinamento in Windows Form</span><span class="sxs-lookup"><span data-stu-id="9b937-122">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)

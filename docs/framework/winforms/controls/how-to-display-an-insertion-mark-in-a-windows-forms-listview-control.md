---
title: 'Procedura: Visualizzare un segno di inserimento in un controllo ListView di Windows Forms'
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
ms.openlocfilehash: f3dff351052eaaf70737c6410c1367ab568f6fd0
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586514"
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a><span data-ttu-id="3c8c7-102">Procedura: Visualizzare un segno di inserimento in un controllo ListView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3c8c7-102">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>
<span data-ttu-id="3c8c7-103">Il segno di inserimento nel controllo <xref:System.Windows.Forms.ListView> indica agli utenti il punto in cui verranno inseriti gli elementi trascinati.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-103">The insertion mark in the <xref:System.Windows.Forms.ListView> control shows users the point where dragged items will be inserted.</span></span> <span data-ttu-id="3c8c7-104">Quando un utente trascina un elemento in un punto intermedio tra due elementi, il segno di inserimento indica la nuova posizione prevista dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-104">When a user drags an item to a point between two other items, the insertion mark shows the item's expected new location.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c8c7-105">La funzionalità del segno di inserimento è disponibile solo in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando l'applicazione chiama il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-105">The insertion mark feature is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="3c8c7-106">Nei sistemi operativi precedenti, qualsiasi codice relativo al segno di inserimento non ha alcun effetto e il segno di inserimento non verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-106">On earlier operating systems, any code relating to the insertion mark has no effect and the insertion mark will not appear.</span></span> <span data-ttu-id="3c8c7-107">Per altre informazioni, vedere <xref:System.Windows.Forms.ListViewInsertionMark>.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-107">For more information, see <xref:System.Windows.Forms.ListViewInsertionMark>.</span></span>  
  
 <span data-ttu-id="3c8c7-108">L'immagine seguente mostra un segno di inserimento:</span><span class="sxs-lookup"><span data-stu-id="3c8c7-108">The following image shows an insertion mark:</span></span>  
  
 <span data-ttu-id="3c8c7-109">![Screenshot che mostra un segno di inserimento di ListView. ](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")</span><span class="sxs-lookup"><span data-stu-id="3c8c7-109">![Screenshot that shows a ListView insertion mark.](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")</span></span>  
  
 <span data-ttu-id="3c8c7-110">L'esempio di codice seguente illustra l'uso di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-110">The following code example demonstrates how to use this feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c8c7-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c8c7-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3c8c7-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3c8c7-112">Compiling the Code</span></span>  
 <span data-ttu-id="3c8c7-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c8c7-113">This example requires:</span></span>  
  
- <span data-ttu-id="3c8c7-114">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-114">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c8c7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c8c7-115">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewInsertionMark>
- [<span data-ttu-id="3c8c7-116">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="3c8c7-116">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="3c8c7-117">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="3c8c7-117">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="3c8c7-118">Procedura dettagliata: Esecuzione di un'operazione di trascinamento e rilascio in Windows Form</span><span class="sxs-lookup"><span data-stu-id="3c8c7-118">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)

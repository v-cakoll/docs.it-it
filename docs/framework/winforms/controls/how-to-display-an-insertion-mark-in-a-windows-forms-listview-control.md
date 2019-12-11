---
title: 'Procedura: Visualizzare un segno di inserimento in un controllo ListView di Windows Form'
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
ms.openlocfilehash: 62d105dc3c0b9aabc3699c12259e1624ac31a3a0
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960436"
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a><span data-ttu-id="c7c10-102">Procedura: Visualizzare un segno di inserimento in un controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c7c10-102">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>
<span data-ttu-id="c7c10-103">Il segno di inserimento nel controllo <xref:System.Windows.Forms.ListView> indica agli utenti il punto in cui verranno inseriti gli elementi trascinati.</span><span class="sxs-lookup"><span data-stu-id="c7c10-103">The insertion mark in the <xref:System.Windows.Forms.ListView> control shows users the point where dragged items will be inserted.</span></span> <span data-ttu-id="c7c10-104">Quando un utente trascina un elemento in un punto intermedio tra due elementi, il segno di inserimento indica la nuova posizione prevista dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="c7c10-104">When a user drags an item to a point between two other items, the insertion mark shows the item's expected new location.</span></span>  
  
 <span data-ttu-id="c7c10-105">L'immagine seguente mostra un segno di inserimento:</span><span class="sxs-lookup"><span data-stu-id="c7c10-105">The following image shows an insertion mark:</span></span>  
  
 <span data-ttu-id="c7c10-106">![Screenshot che mostra un segno di inserimento di ListView.](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")</span><span class="sxs-lookup"><span data-stu-id="c7c10-106">![Screenshot that shows a ListView insertion mark.](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")</span></span>  
  
 <span data-ttu-id="c7c10-107">L'esempio di codice seguente illustra l'uso di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c7c10-107">The following code example demonstrates how to use this feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7c10-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="c7c10-108">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c7c10-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c7c10-109">Compiling the Code</span></span>  
 <span data-ttu-id="c7c10-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7c10-110">This example requires:</span></span>  
  
- <span data-ttu-id="c7c10-111">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="c7c10-111">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7c10-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7c10-112">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewInsertionMark>
- [<span data-ttu-id="c7c10-113">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="c7c10-113">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="c7c10-114">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="c7c10-114">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="c7c10-115">Procedura dettagliata: esecuzione di un'operazione di trascinamento in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c7c10-115">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)

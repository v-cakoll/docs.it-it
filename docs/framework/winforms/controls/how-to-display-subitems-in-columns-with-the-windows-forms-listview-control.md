---
title: Visualizza gli elementi secondari nelle colonne con il controllo ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
ms.openlocfilehash: 5c6d807410ad4ee0198d6334844bd65b148edff4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745552"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a><span data-ttu-id="7e232-102">Procedura: visualizzare elementi secondari nelle colonne con il controllo ListView Windows Form</span><span class="sxs-lookup"><span data-stu-id="7e232-102">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>
<span data-ttu-id="7e232-103">Il controllo Windows Forms <xref:System.Windows.Forms.ListView> può visualizzare testo aggiuntivo, o elementi secondari, per ogni elemento nella visualizzazione dettagli.</span><span class="sxs-lookup"><span data-stu-id="7e232-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display additional text, or subitems, for each item in the Details view.</span></span> <span data-ttu-id="7e232-104">Nella prima colonna viene visualizzato il testo dell'elemento, ad esempio un numero di dipendente.</span><span class="sxs-lookup"><span data-stu-id="7e232-104">The first column displays the item text, for example an employee number.</span></span> <span data-ttu-id="7e232-105">La seconda, la terza e la colonna successiva visualizzano il primo, il secondo e i successivi elementi secondari associati.</span><span class="sxs-lookup"><span data-stu-id="7e232-105">The second, third, and subsequent columns display the first, second, and subsequent associated subitems.</span></span>  
  
### <a name="to-add-subitems-to-a-list-item"></a><span data-ttu-id="7e232-106">Per aggiungere elementi secondari a una voce di elenco</span><span class="sxs-lookup"><span data-stu-id="7e232-106">To add subitems to a list item</span></span>  
  
1. <span data-ttu-id="7e232-107">Aggiungere le colonne necessarie.</span><span class="sxs-lookup"><span data-stu-id="7e232-107">Add any columns needed.</span></span> <span data-ttu-id="7e232-108">Poiché nella prima colonna viene visualizzata la proprietà <xref:System.Windows.Forms.ListView.Text%2A> dell'elemento, è necessaria una colonna maggiore di quella degli elementi secondari.</span><span class="sxs-lookup"><span data-stu-id="7e232-108">Because the first column will display the item's <xref:System.Windows.Forms.ListView.Text%2A> property, you need one more column than there are subitems.</span></span> <span data-ttu-id="7e232-109">Per altre informazioni sull'aggiunta di colonne, vedere [procedura: aggiungere colonne al controllo Windows Forms ListView](how-to-add-columns-to-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="7e232-109">For more information on adding columns, see [How to: Add Columns to the Windows Forms ListView Control](how-to-add-columns-to-the-windows-forms-listview-control.md).</span></span>  
  
2. <span data-ttu-id="7e232-110">Chiamare il metodo <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> della raccolta restituita dalla proprietà <xref:System.Windows.Forms.ListViewItem.SubItems%2A> di un elemento.</span><span class="sxs-lookup"><span data-stu-id="7e232-110">Call the <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.ListViewItem.SubItems%2A> property of an item.</span></span> <span data-ttu-id="7e232-111">L'esempio di codice seguente imposta il nome e il reparto del dipendente per un elemento elenco.</span><span class="sxs-lookup"><span data-stu-id="7e232-111">The code example below sets the employee name and department for a list item.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="7e232-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e232-112">See also</span></span>

- [<span data-ttu-id="7e232-113">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="7e232-113">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="7e232-114">Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="7e232-114">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="7e232-115">Procedura: Aggiungere colonne al controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="7e232-115">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="7e232-116">Procedura: Visualizzare icone per il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="7e232-116">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="7e232-117">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="7e232-117">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)

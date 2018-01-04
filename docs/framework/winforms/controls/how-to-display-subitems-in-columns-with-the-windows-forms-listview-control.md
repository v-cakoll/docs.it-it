---
title: 'Procedura: visualizzare elementi secondari nelle colonne con il controllo ListView Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a9da292b5f65ea9dc44b47a8c3bc13cf43e83b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a><span data-ttu-id="da635-102">Procedura: visualizzare elementi secondari nelle colonne con il controllo ListView Windows Form</span><span class="sxs-lookup"><span data-stu-id="da635-102">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>
<span data-ttu-id="da635-103">Windows Form <xref:System.Windows.Forms.ListView> controllo può visualizzare testo aggiuntivo, o elementi secondari, per ogni elemento nella visualizzazione dettagli.</span><span class="sxs-lookup"><span data-stu-id="da635-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display additional text, or subitems, for each item in the Details view.</span></span> <span data-ttu-id="da635-104">La prima colonna Visualizza il testo dell'elemento, ad esempio il numero di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="da635-104">The first column displays the item text, for example an employee number.</span></span> <span data-ttu-id="da635-105">Il secondo, terzo le colonne successive visualizzano il primo, secondo e successivi elementi secondari associati.</span><span class="sxs-lookup"><span data-stu-id="da635-105">The second, third, and subsequent columns display the first, second, and subsequent associated subitems.</span></span>  
  
### <a name="to-add-subitems-to-a-list-item"></a><span data-ttu-id="da635-106">Per aggiungere elementi secondari a un elemento di elenco</span><span class="sxs-lookup"><span data-stu-id="da635-106">To add subitems to a list item</span></span>  
  
1.  <span data-ttu-id="da635-107">Aggiungere le colonne necessarie.</span><span class="sxs-lookup"><span data-stu-id="da635-107">Add any columns needed.</span></span> <span data-ttu-id="da635-108">Poiché la prima colonna verrà visualizzato l'elemento <xref:System.Windows.Forms.ListView.Text%2A> proprietà, è necessario che una colonna in più del numero di elementi secondari.</span><span class="sxs-lookup"><span data-stu-id="da635-108">Because the first column will display the item's <xref:System.Windows.Forms.ListView.Text%2A> property, you need one more column than there are subitems.</span></span> <span data-ttu-id="da635-109">Per ulteriori informazioni sull'aggiunta di colonne, vedere [procedura: aggiungere colonne al controllo ListView Windows Form](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="da635-109">For more information on adding columns, see [How to: Add Columns to the Windows Forms ListView Control](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).</span></span>  
  
2.  <span data-ttu-id="da635-110">Chiamare il <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> raccolta restituita dal metodo di <xref:System.Windows.Forms.ListViewItem.SubItems%2A> proprietà di un elemento.</span><span class="sxs-lookup"><span data-stu-id="da635-110">Call the <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.ListViewItem.SubItems%2A> property of an item.</span></span> <span data-ttu-id="da635-111">Esempio di codice seguente imposta il nome del dipendente e reparto per un elemento di elenco.</span><span class="sxs-lookup"><span data-stu-id="da635-111">The code example below sets the employee name and department for a list item.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="da635-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da635-112">See Also</span></span>  
 [<span data-ttu-id="da635-113">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="da635-113">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="da635-114">Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="da635-114">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="da635-115">Procedura: Aggiungere colonne al controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="da635-115">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="da635-116">Procedura: Visualizzare icone per il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="da635-116">How to: Display Icons for the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="da635-117">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="da635-117">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)

---
title: 'Procedura: aggiungere e rimuovere elementi tramite il controllo ListView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: 83ef2e108695988bbb0329d9f01e1317d9308f18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525655"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a><span data-ttu-id="23cd1-102">Procedura: aggiungere e rimuovere elementi tramite il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="23cd1-102">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>
<span data-ttu-id="23cd1-103">Il processo di aggiunta di un elemento a un Windows Form <xref:System.Windows.Forms.ListView> controllo consiste principalmente nella definizione dell'elemento e l'assegnazione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="23cd1-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="23cd1-104">Aggiunta o rimozione di elementi dell'elenco può essere eseguita in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="23cd1-104">Adding or removing list items can be done at any time.</span></span>  
  
### <a name="to-add-items-programmatically"></a><span data-ttu-id="23cd1-105">Per aggiungere elementi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="23cd1-105">To add items programmatically</span></span>  
  
1.  <span data-ttu-id="23cd1-106">Utilizzare il <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> metodo il <xref:System.Windows.Forms.ListView.Items%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="23cd1-106">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a><span data-ttu-id="23cd1-107">Per rimuovere gli elementi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="23cd1-107">To remove items programmatically</span></span>  
  
1.  <span data-ttu-id="23cd1-108">Utilizzare il <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> metodo il <xref:System.Windows.Forms.ListView.Items%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="23cd1-108">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span> <span data-ttu-id="23cd1-109">Il <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> metodo rimuove un elemento singolo; <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> metodo rimuove tutti gli elementi dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="23cd1-109">The <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> method removes a single item; the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method removes all items from the list.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="23cd1-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23cd1-110">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 [<span data-ttu-id="23cd1-111">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="23cd1-111">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="23cd1-112">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="23cd1-112">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)

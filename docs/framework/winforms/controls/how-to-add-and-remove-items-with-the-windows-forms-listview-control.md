---
title: 'Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: 8a97d73b9b2c46d02ae0794ad66b20a04db58af6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011125"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a><span data-ttu-id="efaed-102">Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="efaed-102">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>
<span data-ttu-id="efaed-103">Il processo di aggiunta di un elemento a un form Windows <xref:System.Windows.Forms.ListView> controllo consiste principalmente nella definizione dell'elemento e assegnazione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="efaed-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="efaed-104">È possibile aggiungere o rimuovere elementi elenco in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="efaed-104">Adding or removing list items can be done at any time.</span></span>  
  
### <a name="to-add-items-programmatically"></a><span data-ttu-id="efaed-105">Per aggiungere elementi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="efaed-105">To add items programmatically</span></span>  
  
1. <span data-ttu-id="efaed-106">Usare il <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> metodo di <xref:System.Windows.Forms.ListView.Items%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="efaed-106">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a><span data-ttu-id="efaed-107">Per rimuovere gli elementi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="efaed-107">To remove items programmatically</span></span>  
  
1. <span data-ttu-id="efaed-108">Usare il <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> oppure <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> metodo del <xref:System.Windows.Forms.ListView.Items%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="efaed-108">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span> <span data-ttu-id="efaed-109">Il <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> metodo rimuove un singolo elemento; il <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> metodo rimuove tutti gli elementi dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="efaed-109">The <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> method removes a single item; the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method removes all items from the list.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="efaed-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efaed-110">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="efaed-111">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="efaed-111">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="efaed-112">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="efaed-112">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)

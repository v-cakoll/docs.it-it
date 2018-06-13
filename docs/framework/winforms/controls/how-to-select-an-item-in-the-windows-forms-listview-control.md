---
title: 'Procedura: selezionare un elemento nel controllo ListView Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
ms.openlocfilehash: 8256eaeddf98c5a0dd80357bcd562e8f66db85b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532821"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a><span data-ttu-id="e9ff1-102">Procedura: selezionare un elemento nel controllo ListView Windows Form</span><span class="sxs-lookup"><span data-stu-id="e9ff1-102">How to: Select an Item in the Windows Forms ListView Control</span></span>
<span data-ttu-id="e9ff1-103">In questo esempio viene illustrato come selezionare a livello di programmazione un elemento in un Windows Form <xref:System.Windows.Forms.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="e9ff1-103">This example demonstrates how to programmatically select an item in a Windows Forms <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="e9ff1-104">Selezione di un elemento a livello di codice non cambia automaticamente lo stato attivo per il <xref:System.Windows.Forms.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="e9ff1-104">Selecting an item programmatically does not automatically change the focus to the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="e9ff1-105">Per questo motivo, si sarà in genere consigliabile impostare l'elemento, come lo stato attivo quando si seleziona un elemento.</span><span class="sxs-lookup"><span data-stu-id="e9ff1-105">For this reason, you will typically also want to set the item as focused when selecting an item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9ff1-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9ff1-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e9ff1-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e9ff1-107">Compiling the Code</span></span>  
 <span data-ttu-id="e9ff1-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9ff1-108">This example requires:</span></span>  
  
-   <span data-ttu-id="e9ff1-109">Oggetto <xref:System.Windows.Forms.ListView> controllo denominato `listView1` che contiene almeno un elemento.</span><span class="sxs-lookup"><span data-stu-id="e9ff1-109">A <xref:System.Windows.Forms.ListView> control named `listView1` that contains at least one item.</span></span>  
  
-   <span data-ttu-id="e9ff1-110">Riferimenti agli spazi dei nomi <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e9ff1-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9ff1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9ff1-111">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>

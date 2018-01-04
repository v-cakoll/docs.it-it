---
title: 'Procedura: aggiungere colonne al controllo ListView di Windows Form'
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
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4895d9fbd84ac00291a717e47102f3d0e04176f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="5e087-102">Procedura: aggiungere colonne al controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5e087-102">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="5e087-103">Nella visualizzazione dei dettagli, il <xref:System.Windows.Forms.ListView> controllo può visualizzare più colonne per ogni elemento nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5e087-103">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="5e087-104">È possibile utilizzare le colonne da visualizzare all'utente di vari tipi di informazioni su ogni elemento di elenco.</span><span class="sxs-lookup"><span data-stu-id="5e087-104">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="5e087-105">Ad esempio, un elenco di file potrebbe visualizzare il nome del file, il tipo di file, dimensioni e data che dell'ultima modifica il file.</span><span class="sxs-lookup"><span data-stu-id="5e087-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="5e087-106">Per informazioni sulla compilazione delle colonne dopo averli creati, vedere [procedura: visualizzare elementi secondari nelle colonne con il controllo ListView Windows Form](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="5e087-106">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="5e087-107">Per aggiungere colonne a livello di codice</span><span class="sxs-lookup"><span data-stu-id="5e087-107">To add columns programmatically</span></span>  
  
1.  <span data-ttu-id="5e087-108">Impostare il controllo <xref:System.Windows.Forms.ListView.View%2A> proprietà <xref:System.Windows.Forms.View.Details>.</span><span class="sxs-lookup"><span data-stu-id="5e087-108">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2.  <span data-ttu-id="5e087-109">Utilizzare il <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> metodo per la visualizzazione elenco <xref:System.Windows.Forms.ListView.Columns%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="5e087-109">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="5e087-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e087-110">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 [<span data-ttu-id="5e087-111">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="5e087-111">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="5e087-112">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="5e087-112">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)

---
title: "Procedura: impostare la modalità di selezione del controllo DataGridView di Windows Form"
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
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
- data grids [Windows Forms], selection mode
ms.assetid: 2f241643-7f82-4583-8757-03494f63b465
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bb0f9d0cff7be2dd1243916e6505aab9cc63dd0d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="a5857-102">Procedura: impostare la modalità di selezione del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a5857-102">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a5857-103">Esempio di codice riportato di seguito viene illustrato come configurare un <xref:System.Windows.Forms.DataGridView> controllo in modo che facendo clic in un punto qualsiasi all'interno di una riga automaticamente selezionata l'intera riga, e che sia possibile selezionare solo una riga alla volta.</span><span class="sxs-lookup"><span data-stu-id="a5857-103">The following code example demonstrates how to configure a <xref:System.Windows.Forms.DataGridView> control so that clicking anywhere within a row automatically selects the entire row, and so that only one row at a time can be selected.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5857-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5857-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#065](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#065)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#065](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#065)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a5857-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a5857-105">Compiling the Code</span></span>  
 <span data-ttu-id="a5857-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5857-106">This example requires:</span></span>  
  
-   <span data-ttu-id="a5857-107">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="a5857-107">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="a5857-108">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a5857-108">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5857-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5857-109">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
 <xref:System.Windows.Forms.DataGridViewSelectionMode>  
 [<span data-ttu-id="a5857-110">Uso della selezione e degli Appunti con il controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a5857-110">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="a5857-111">Modalità di selezione nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a5857-111">Selection Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)

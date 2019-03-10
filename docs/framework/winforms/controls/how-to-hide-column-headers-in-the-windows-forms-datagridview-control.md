---
title: 'Procedura: Nascondere le intestazioni di colonna nel controllo DataGridView Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], hiding column headers
- column headers [Windows Forms], hiding
- DataGridView control [Windows Forms], column headers
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
ms.openlocfilehash: b9b78020a567d05ea000be97bb116b4f8353d56c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709458"
---
# <a name="how-to-hide-column-headers-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="4e3ae-102">Procedura: Nascondere le intestazioni di colonna nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="4e3ae-102">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4e3ae-103">In alcuni casi si potrebbe essere necessario visualizzare un <xref:System.Windows.Forms.DataGridView> senza intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="4e3ae-103">Sometimes you will want to display a <xref:System.Windows.Forms.DataGridView> without column headers.</span></span> <span data-ttu-id="4e3ae-104">Nel <xref:System.Windows.Forms.DataGridView> (controllo), il <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> valore della proprietà determina se le intestazioni di colonna vengono visualizzate.</span><span class="sxs-lookup"><span data-stu-id="4e3ae-104">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> property value determines whether the column headers are displayed.</span></span>  
  
### <a name="to-hide-the-column-headers"></a><span data-ttu-id="4e3ae-105">Per nascondere le intestazioni di colonna</span><span class="sxs-lookup"><span data-stu-id="4e3ae-105">To hide the column headers</span></span>  
  
-   <span data-ttu-id="4e3ae-106">Impostare la proprietà <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> su `false`.</span><span class="sxs-lookup"><span data-stu-id="4e3ae-106">Set the <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4e3ae-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4e3ae-107">Compiling the Code</span></span>  
 <span data-ttu-id="4e3ae-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e3ae-108">This example requires:</span></span>  
  
-   <span data-ttu-id="4e3ae-109">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="4e3ae-109">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="4e3ae-110">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4e3ae-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e3ae-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e3ae-111">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4e3ae-112">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4e3ae-112">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)

---
title: Blocca le colonne nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], freezing columns
- DataGridView control [Windows Forms], columns always in view
ms.assetid: 2ef8b1de-782e-4867-af8d-58171ab5c106
ms.openlocfilehash: 6d1a98e5c4332078c6012cb7c9ed836108abd86c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736740"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="0b227-102">Procedura: bloccare le colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b227-102">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="0b227-103">Quando gli utenti visualizzano i dati contenuti in un controllo <xref:System.Windows.Forms.DataGridView> Windows Form, a volte devono fare spesso riferimento a una sola colonna o a un set di colonne.</span><span class="sxs-lookup"><span data-stu-id="0b227-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="0b227-104">Ad esempio, quando si visualizza una tabella di informazioni sui clienti che contiene molte colonne, è utile visualizzare il nome del cliente in qualsiasi momento, anche mentre le altre colonne scorrono all'esterno dell'area visibile.</span><span class="sxs-lookup"><span data-stu-id="0b227-104">For example, when displaying a table of customer information that contains many columns, it is useful to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>  
  
 <span data-ttu-id="0b227-105">A tale scopo, è possibile bloccare le colonne nel controllo.</span><span class="sxs-lookup"><span data-stu-id="0b227-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="0b227-106">Quando si blocca una colonna, vengono bloccate anche tutte le colonne alla sua sinistra (o alla sua destra, nelle lingue scritte da destra a sinistra).</span><span class="sxs-lookup"><span data-stu-id="0b227-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="0b227-107">Le colonne bloccate rimangono ferme mentre tutte le altre colonne possono scorrere.</span><span class="sxs-lookup"><span data-stu-id="0b227-107">Frozen columns remain in place while all other columns can scroll.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0b227-108">Se viene abilitato il riordinamento delle colonne, le colonne bloccate vengono considerate come un gruppo distinto dalle colonne non bloccate.</span><span class="sxs-lookup"><span data-stu-id="0b227-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="0b227-109">Gli utenti possono riposizionare le colonne in entrambi i gruppi, ma non possono spostare una colonna da un gruppo all'altro.</span><span class="sxs-lookup"><span data-stu-id="0b227-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>  
  
 <span data-ttu-id="0b227-110">La proprietà <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> di una colonna determina se la colonna è sempre visibile nella griglia.</span><span class="sxs-lookup"><span data-stu-id="0b227-110">The <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property of a column determines whether the column is always visible within the grid.</span></span>  
  
 <span data-ttu-id="0b227-111">Questa attività è supportata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0b227-111">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="0b227-112">Vedere anche [procedura: bloccare le colonne nel controllo DataGridView Windows Forms usando la finestra di progettazione](freeze-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="0b227-112">Also see [How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer](freeze-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-freeze-a-column-programmatically"></a><span data-ttu-id="0b227-113">Per bloccare una colonna a livello di codice</span><span class="sxs-lookup"><span data-stu-id="0b227-113">To freeze a column programmatically</span></span>  
  
- <span data-ttu-id="0b227-114">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> su `true`.</span><span class="sxs-lookup"><span data-stu-id="0b227-114">Set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#061](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#061)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#061](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#061)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0b227-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="0b227-115">Compiling the Code</span></span>  
 <span data-ttu-id="0b227-116">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b227-116">This example requires:</span></span>  
  
- <span data-ttu-id="0b227-117">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` contenente una colonna denominata `AddToCartButton`.</span><span class="sxs-lookup"><span data-stu-id="0b227-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `AddToCartButton`.</span></span>  
  
- <span data-ttu-id="0b227-118">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0b227-118">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b227-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b227-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="0b227-120">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b227-120">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="0b227-121">Procedura: Abilitare il riordinamento delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b227-121">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)

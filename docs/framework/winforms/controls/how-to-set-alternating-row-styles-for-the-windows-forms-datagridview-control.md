---
title: 'Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], row styles
- data grids [Windows Forms], row styles
- rows [Windows Forms], data grids
ms.assetid: 699ef759-458c-426d-ac87-7c7e71b018ae
ms.openlocfilehash: eea77b7601b7dc81b92f7b08806f3f00b494aecd
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2019
ms.locfileid: "56583888"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="efa53-102">Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="efa53-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="efa53-103">I dati tabulari si presentano spesso agli utenti in un formato di tipo registro, in cui le righe alternano colori di sfondo diversi.</span><span class="sxs-lookup"><span data-stu-id="efa53-103">Tabular data is often presented to users in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="efa53-104">Questo formato permette agli utenti di individuare più facilmente le celle di ogni riga, soprattutto nelle tabelle estese in larghezza con molte colonne.</span><span class="sxs-lookup"><span data-stu-id="efa53-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>  
  
 <span data-ttu-id="efa53-105">Con il controllo <xref:System.Windows.Forms.DataGridView>, è possibile specificare informazioni di stile complete per le righe alterne.</span><span class="sxs-lookup"><span data-stu-id="efa53-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="efa53-106">Sarà quindi possibile usare caratteristiche di stile, come il colore primo piano e il tipo di carattere, oltre al colore di sfondo, per differenziare le righe alterne.</span><span class="sxs-lookup"><span data-stu-id="efa53-106">This enables you use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span>  
  
 <span data-ttu-id="efa53-107">Questa attività è supportata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="efa53-107">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="efa53-108">Vedere anche [come: Impostare stili di righe alterne per il Windows Form controllo DataGridView utilizzando la finestra di progettazione](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="efa53-108">Also see [How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-set-alternating-row-styles-programmatically"></a><span data-ttu-id="efa53-109">Per impostare stili di righe alterne a livello di codice</span><span class="sxs-lookup"><span data-stu-id="efa53-109">To set alternating row styles programmatically</span></span>  
  
-   <span data-ttu-id="efa53-110">Impostare le proprietà degli oggetti <xref:System.Windows.Forms.DataGridViewCellStyle> restituiti dalle proprietà <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> e <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> di <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="efa53-110">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> objects returned by the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> properties of the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#068](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#068)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#068](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#068)]  
  
    > [!NOTE]
    >  <span data-ttu-id="efa53-111">Gli stili specificati con le proprietà <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> e <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> eseguono l'override degli stili specificati a livello di colonna e di <xref:System.Windows.Forms.DataGridView>, ma ne viene eseguito l'override dagli stili impostati a livello di singola riga e cella.</span><span class="sxs-lookup"><span data-stu-id="efa53-111">The styles specified using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> properties override the styles specified on the column and <xref:System.Windows.Forms.DataGridView> level, but are overridden by the styles set on the individual row and cell level.</span></span> <span data-ttu-id="efa53-112">Per altre informazioni, vedere [stili della cella nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="efa53-112">For more information, see [Cell Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="efa53-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="efa53-113">Compiling the Code</span></span>  
 <span data-ttu-id="efa53-114">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="efa53-114">This example requires:</span></span>  
  
-   <span data-ttu-id="efa53-115">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="efa53-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="efa53-116">Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="efa53-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="efa53-117">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="efa53-117">Robust Programming</span></span>  
 <span data-ttu-id="efa53-118">Per la massima scalabilità, è opportuno condividere gli oggetti <xref:System.Windows.Forms.DataGridViewCellStyle> su più righe, colonne o celle che usano lo stesso stile anziché impostare separatamente le proprietà di stile per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="efa53-118">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="efa53-119">Per altre informazioni, vedere [procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="efa53-119">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa53-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efa53-120">See also</span></span>
- <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="efa53-121">Formattazione e stile di base nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="efa53-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="efa53-122">Stili delle celle nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="efa53-122">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="efa53-123">Procedure consigliate per ridimensionare il controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="efa53-123">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="efa53-124">Procedura: Impostare gli stili di colore e tipo di carattere nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="efa53-124">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)

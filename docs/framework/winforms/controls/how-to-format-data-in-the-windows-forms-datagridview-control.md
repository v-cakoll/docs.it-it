---
title: Formattare i dati nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
ms.openlocfilehash: 9ee2869cf4085b5acfdf1f8c440151be506dbe3e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736783"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="36a6b-102">Procedura: formattare i dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="36a6b-102">How to: Format Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="36a6b-103">Nelle procedure seguenti viene illustrata la formattazione di base dei valori delle celle utilizzando la proprietà <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> di un controllo <xref:System.Windows.Forms.DataGridView> e di colonne specifiche in un controllo.</span><span class="sxs-lookup"><span data-stu-id="36a6b-103">The following procedures demonstrate basic formatting of cell values using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property of a <xref:System.Windows.Forms.DataGridView> control and of specific columns in a control.</span></span> <span data-ttu-id="36a6b-104">Per informazioni sulla formattazione avanzata dei dati, vedere [procedura: personalizzare la formattazione dei dati nel controllo DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="36a6b-104">For information about advanced data formatting, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-format-currency-and-date-values"></a><span data-ttu-id="36a6b-105">Per formattare i valori di valuta e data</span><span class="sxs-lookup"><span data-stu-id="36a6b-105">To format currency and date values</span></span>  
  
- <span data-ttu-id="36a6b-106">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> di un oggetto <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="36a6b-106">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="36a6b-107">Nell'esempio di codice seguente viene impostato il formato per colonne specifiche utilizzando la proprietà <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> delle colonne.</span><span class="sxs-lookup"><span data-stu-id="36a6b-107">The following code example sets the format for specific columns using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the columns.</span></span> <span data-ttu-id="36a6b-108">I valori nella colonna `UnitPrice` vengono visualizzati nel formato di valuta corrente specifico delle impostazioni cultura, con valori negativi racchiusi tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="36a6b-108">Values in the `UnitPrice` column appear in the current culture-specific currency format, with negative values surrounded by parentheses.</span></span> <span data-ttu-id="36a6b-109">I valori nella colonna `ShipDate` vengono visualizzati nel formato di data breve specifico delle impostazioni cultura corrente.</span><span class="sxs-lookup"><span data-stu-id="36a6b-109">Values in the `ShipDate` column appear in the current culture-specific short date format.</span></span> <span data-ttu-id="36a6b-110">Per ulteriori informazioni sui valori di <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>, vedere [formattazione di tipi](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="36a6b-110">For more information about <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> values, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a><span data-ttu-id="36a6b-111">Per personalizzare la visualizzazione dei valori di database null</span><span class="sxs-lookup"><span data-stu-id="36a6b-111">To customize the display of null database values</span></span>  
  
- <span data-ttu-id="36a6b-112">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> di un oggetto <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="36a6b-112">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="36a6b-113">Nell'esempio di codice seguente viene utilizzata la proprietà <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> per visualizzare "Nessuna voce" in tutte le celle contenenti valori uguali a <xref:System.DBNull.Value?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="36a6b-113">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to display "no entry" in all cells containing values equal to <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a><span data-ttu-id="36a6b-114">Per abilitare WordWrap nelle celle basate su testo</span><span class="sxs-lookup"><span data-stu-id="36a6b-114">To enable wordwrap in text-based cells</span></span>  
  
- <span data-ttu-id="36a6b-115">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> di un <xref:System.Windows.Forms.DataGridViewCellStyle> su uno dei valori di enumerazione di <xref:System.Windows.Forms.DataGridViewTriState>.</span><span class="sxs-lookup"><span data-stu-id="36a6b-115">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewTriState> enumeration values.</span></span> <span data-ttu-id="36a6b-116">Nell'esempio di codice seguente viene utilizzata la proprietà <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> per impostare la modalità a capo automatico per l'intero controllo.</span><span class="sxs-lookup"><span data-stu-id="36a6b-116">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the wrap mode for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a><span data-ttu-id="36a6b-117">Per specificare l'allineamento del testo delle celle DataGridView</span><span class="sxs-lookup"><span data-stu-id="36a6b-117">To specify the text alignment of DataGridView cells</span></span>  
  
- <span data-ttu-id="36a6b-118">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> di un <xref:System.Windows.Forms.DataGridViewCellStyle> su uno dei valori di enumerazione di <xref:System.Windows.Forms.DataGridViewContentAlignment>.</span><span class="sxs-lookup"><span data-stu-id="36a6b-118">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewContentAlignment> enumeration values.</span></span> <span data-ttu-id="36a6b-119">Nell'esempio di codice seguente viene impostato l'allineamento per una colonna specifica utilizzando la proprietà <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> della colonna.</span><span class="sxs-lookup"><span data-stu-id="36a6b-119">The following code example sets the alignment for a specific column using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the column.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a><span data-ttu-id="36a6b-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="36a6b-120">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="36a6b-121">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="36a6b-121">Compiling the Code</span></span>  
 <span data-ttu-id="36a6b-122">Gli esempi presentano i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="36a6b-122">These examples require:</span></span>  
  
- <span data-ttu-id="36a6b-123">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` contenente una colonna denominata `UnitPrice`, una colonna denominata `ShipDate`e una colonna denominata `CustomerName`.</span><span class="sxs-lookup"><span data-stu-id="36a6b-123">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `UnitPrice`, a column named `ShipDate`, and a column named `CustomerName`.</span></span>  
  
- <span data-ttu-id="36a6b-124">Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="36a6b-124">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="36a6b-125">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="36a6b-125">Robust Programming</span></span>  
 <span data-ttu-id="36a6b-126">Per la massima scalabilità, è necessario condividere <xref:System.Windows.Forms.DataGridViewCellStyle> oggetti tra più righe, colonne o celle che usano gli stessi stili anziché impostare separatamente le proprietà di stile per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="36a6b-126">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="36a6b-127">Per ulteriori informazioni, vedere la pagina relativa alle [procedure consigliate per il ridimensionamento del controllo Windows Forms DataGridView](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="36a6b-127">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a6b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36a6b-128">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="36a6b-129">Formattazione e stile di base nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="36a6b-129">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="36a6b-130">Stili delle celle nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="36a6b-130">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="36a6b-131">Formattazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="36a6b-131">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="36a6b-132">Procedura: Formattare dati personalizzati in un controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="36a6b-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="36a6b-133">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="36a6b-133">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)

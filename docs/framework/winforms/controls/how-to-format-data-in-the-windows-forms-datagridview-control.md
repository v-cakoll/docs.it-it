---
title: 'Procedura: Formattare i dati nel controllo DataGridView di Windows Forms'
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
ms.openlocfilehash: 62701edfdb3cf2729cb401ad12a12ee4f524287b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941413"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="58a1a-102">Procedura: Formattare i dati nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="58a1a-102">How to: Format Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="58a1a-103">Le procedure seguenti illustrano la formattazione di base dei valori di cella utilizzando il <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> proprietà di un <xref:System.Windows.Forms.DataGridView> controllo e di colonne specifiche in un controllo.</span><span class="sxs-lookup"><span data-stu-id="58a1a-103">The following procedures demonstrate basic formatting of cell values using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property of a <xref:System.Windows.Forms.DataGridView> control and of specific columns in a control.</span></span> <span data-ttu-id="58a1a-104">Per informazioni sulla formattazione di dati avanzati, vedere [come: Personalizzare la formattazione dei dati nel controllo DataGridView Windows Form](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="58a1a-104">For information about advanced data formatting, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-format-currency-and-date-values"></a><span data-ttu-id="58a1a-105">Per la formattazione della valuta e valori di date</span><span class="sxs-lookup"><span data-stu-id="58a1a-105">To format currency and date values</span></span>  
  
- <span data-ttu-id="58a1a-106">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> di un oggetto <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="58a1a-106">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="58a1a-107">Esempio di codice seguente imposta il formato per determinate colonne utilizzando il <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> proprietà delle colonne.</span><span class="sxs-lookup"><span data-stu-id="58a1a-107">The following code example sets the format for specific columns using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the columns.</span></span> <span data-ttu-id="58a1a-108">I valori di `UnitPrice` colonna vengono visualizzati nel formato di valuta specifico delle impostazioni cultura correnti, con i valori negativi racchiusi tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="58a1a-108">Values in the `UnitPrice` column appear in the current culture-specific currency format, with negative values surrounded by parentheses.</span></span> <span data-ttu-id="58a1a-109">I valori di `ShipDate` colonna vengono visualizzati nel formato data breve specifiche delle impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="58a1a-109">Values in the `ShipDate` column appear in the current culture-specific short date format.</span></span> <span data-ttu-id="58a1a-110">Per altre informazioni sulle <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> valori, vedere [formattazione di tipi](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="58a1a-110">For more information about <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> values, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a><span data-ttu-id="58a1a-111">Per personalizzare la visualizzazione di valori null del database</span><span class="sxs-lookup"><span data-stu-id="58a1a-111">To customize the display of null database values</span></span>  
  
- <span data-ttu-id="58a1a-112">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> di un oggetto <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="58a1a-112">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="58a1a-113">Il codice seguente viene illustrato come utilizzare il <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> proprietà da non visualizzare "alcuna voce" in tutte le celle contenenti valori uguali a <xref:System.DBNull.Value?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="58a1a-113">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to display "no entry" in all cells containing values equal to <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a><span data-ttu-id="58a1a-114">Per abilitare ritorno a capo automatico nelle celle basata su testo</span><span class="sxs-lookup"><span data-stu-id="58a1a-114">To enable wordwrap in text-based cells</span></span>  
  
- <span data-ttu-id="58a1a-115">Impostare il <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> proprietà di un <xref:System.Windows.Forms.DataGridViewCellStyle> a uno del <xref:System.Windows.Forms.DataGridViewTriState> valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="58a1a-115">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewTriState> enumeration values.</span></span> <span data-ttu-id="58a1a-116">Il codice seguente viene illustrato come utilizzare il <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> proprietà da impostare la modalità di disposizione per l'intero controllo.</span><span class="sxs-lookup"><span data-stu-id="58a1a-116">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the wrap mode for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a><span data-ttu-id="58a1a-117">Per specificare l'allineamento del testo delle celle DataGridView</span><span class="sxs-lookup"><span data-stu-id="58a1a-117">To specify the text alignment of DataGridView cells</span></span>  
  
- <span data-ttu-id="58a1a-118">Impostare il <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> proprietà di un <xref:System.Windows.Forms.DataGridViewCellStyle> a uno del <xref:System.Windows.Forms.DataGridViewContentAlignment> valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="58a1a-118">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewContentAlignment> enumeration values.</span></span> <span data-ttu-id="58a1a-119">Esempio di codice seguente imposta l'allineamento di una colonna specifica usando il <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> proprietà della colonna.</span><span class="sxs-lookup"><span data-stu-id="58a1a-119">The following code example sets the alignment for a specific column using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the column.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a><span data-ttu-id="58a1a-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="58a1a-120">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="58a1a-121">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="58a1a-121">Compiling the Code</span></span>  
 <span data-ttu-id="58a1a-122">Gli esempi presentano i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="58a1a-122">These examples require:</span></span>  
  
- <span data-ttu-id="58a1a-123">Oggetto <xref:System.Windows.Forms.DataGridView> controllo denominato `dataGridView1` che contiene una colonna denominata `UnitPrice`, una colonna denominata `ShipDate`e una colonna denominata `CustomerName`.</span><span class="sxs-lookup"><span data-stu-id="58a1a-123">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `UnitPrice`, a column named `ShipDate`, and a column named `CustomerName`.</span></span>  
  
- <span data-ttu-id="58a1a-124">Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="58a1a-124">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="58a1a-125">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="58a1a-125">Robust Programming</span></span>  
 <span data-ttu-id="58a1a-126">Per ottenere la massima scalabilità, è necessario condividere <xref:System.Windows.Forms.DataGridViewCellStyle> oggetti su più righe, colonne o celle che usano lo stesso stile anziché impostare separatamente le proprietà di stile per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="58a1a-126">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="58a1a-127">Per altre informazioni, vedere [procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="58a1a-127">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58a1a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58a1a-128">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="58a1a-129">Formattazione e stile di base nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="58a1a-129">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="58a1a-130">Stili delle celle nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="58a1a-130">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="58a1a-131">Formattazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="58a1a-131">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="58a1a-132">Procedura: Personalizzare la formattazione dei dati nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="58a1a-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="58a1a-133">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="58a1a-133">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)

---
title: 'Procedura: Modificare gli stili dei bordi e delle linee della griglia nel controllo DataGridView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gridlines [Windows Forms], changing styles
- data grids [Windows Forms], changing gridline styles
- DataGridView control [Windows Forms], border styles
- data grids [Windows Forms], changing border styles
- DataGridView control [Windows Forms], gridline styles
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
ms.openlocfilehash: ebeca5f933eac4da2bf3d4f300866fd2ff52b32a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917665"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="55788-102">Procedura: Modificare gli stili dei bordi e delle linee della griglia nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55788-102">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="55788-103">Con il <xref:System.Windows.Forms.DataGridView> controllo è possibile personalizzare l'aspetto del bordo e della griglia del controllo per migliorare l'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="55788-103">With the <xref:System.Windows.Forms.DataGridView> control, you can customize the appearance of the control's border and gridlines to improve the user experience.</span></span> <span data-ttu-id="55788-104">È possibile modificare il colore della griglia e lo stile del bordo del controllo oltre agli stili del bordo per le celle all'interno del controllo.</span><span class="sxs-lookup"><span data-stu-id="55788-104">You can modify the gridline color and the control border style in addition to the border styles for the cells within the control.</span></span> <span data-ttu-id="55788-105">È inoltre possibile applicare stili di bordo delle celle diversi per celle ordinarie, celle di intestazioni di riga e celle di intestazione di colonna.</span><span class="sxs-lookup"><span data-stu-id="55788-105">You can also apply different cell border styles for ordinary cells, row header cells, and column header cells.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55788-106">Il colore della griglia viene utilizzato solo con <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>i <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>valori, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> e <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> dell' <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumerazione e il <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> valore dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="55788-106">The gridline color is used only with the <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, and <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> values of the <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumeration and the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> value of the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> enumeration.</span></span> <span data-ttu-id="55788-107">Gli altri valori di queste enumerazioni utilizzano i colori specificati dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="55788-107">The other values of these enumerations use colors specified by the operating system.</span></span> <span data-ttu-id="55788-108">Inoltre, quando gli stili di visualizzazione sono abilitati in Windows XP e la famiglia di Windows <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> Server 2003 tramite <xref:System.Windows.Forms.DataGridView.GridColor%2A> il metodo, il valore della proprietà non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="55788-108">Additionally, when visual styles are enabled on Windows XP and the Windows Server 2003 family through the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method, the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property value is not used.</span></span>  
  
### <a name="to-change-the-gridline-color-programmatically"></a><span data-ttu-id="55788-109">Per modificare il colore della griglia a livello di codice</span><span class="sxs-lookup"><span data-stu-id="55788-109">To change the gridline color programmatically</span></span>  
  
- <span data-ttu-id="55788-110">Impostare la proprietà <xref:System.Windows.Forms.DataGridView.GridColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="55788-110">Set the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a><span data-ttu-id="55788-111">Per modificare lo stile del bordo dell'intero controllo DataGridView a livello di codice</span><span class="sxs-lookup"><span data-stu-id="55788-111">To change the border style of the entire DataGridView control programmatically</span></span>  
  
- <span data-ttu-id="55788-112">Impostare la proprietà <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> su uno dei valori dell'enumerazione <xref:System.Windows.Forms.BorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="55788-112">Set the <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> property to one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a><span data-ttu-id="55788-113">Per modificare gli stili del bordo per le celle DataGridView a livello di codice</span><span class="sxs-lookup"><span data-stu-id="55788-113">To change the border styles for DataGridView cells programmatically</span></span>  
  
- <span data-ttu-id="55788-114">Impostare le <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>proprietà <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, e <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> .</span><span class="sxs-lookup"><span data-stu-id="55788-114">Set the <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, and <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a><span data-ttu-id="55788-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="55788-115">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="55788-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="55788-116">Compiling the Code</span></span>  
 <span data-ttu-id="55788-117">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="55788-117">This example requires:</span></span>  
  
- <span data-ttu-id="55788-118">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="55788-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="55788-119">Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> e <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="55788-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55788-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55788-120">See also</span></span>

- <xref:System.Windows.Forms.BorderStyle>
- <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellBorderStyle>
- <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>
- [<span data-ttu-id="55788-121">Formattazione e stile di base nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="55788-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)

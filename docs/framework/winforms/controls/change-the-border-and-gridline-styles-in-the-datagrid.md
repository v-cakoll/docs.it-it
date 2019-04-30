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
ms.openlocfilehash: d24adb98c339f911d6bea0312bce4d4b4f198a61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939009"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3081b-102">Procedura: Modificare gli stili dei bordi e delle linee della griglia nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3081b-102">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3081b-103">Con la <xref:System.Windows.Forms.DataGridView> (controllo), è possibile personalizzare l'aspetto del bordo del controllo e le linee della griglia per migliorare l'esperienza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3081b-103">With the <xref:System.Windows.Forms.DataGridView> control, you can customize the appearance of the control's border and gridlines to improve the user experience.</span></span> <span data-ttu-id="3081b-104">È possibile modificare il colore delle linee della griglia e lo stile del bordo del controllo oltre gli stili dei bordi per le celle all'interno del controllo.</span><span class="sxs-lookup"><span data-stu-id="3081b-104">You can modify the gridline color and the control border style in addition to the border styles for the cells within the control.</span></span> <span data-ttu-id="3081b-105">È inoltre possibile applicare gli stili di bordo cella diversa per le celle normali, le celle di intestazione di riga e le celle di intestazione di colonna.</span><span class="sxs-lookup"><span data-stu-id="3081b-105">You can also apply different cell border styles for ordinary cells, row header cells, and column header cells.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3081b-106">Il colore delle linee della griglia viene usato solo con il <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, e <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> valori del <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumerazione e la <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> pari al <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="3081b-106">The gridline color is used only with the <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, and <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> values of the <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumeration and the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> value of the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> enumeration.</span></span> <span data-ttu-id="3081b-107">Gli altri valori di queste enumerazioni usano i colori specificati dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3081b-107">The other values of these enumerations use colors specified by the operating system.</span></span> <span data-ttu-id="3081b-108">Inoltre, quando gli stili di visualizzazione sono abilitati in Windows XP e in Windows Server 2003 tramite il <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> metodo, il <xref:System.Windows.Forms.DataGridView.GridColor%2A> valore proprietà non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="3081b-108">Additionally, when visual styles are enabled on Windows XP and the Windows Server 2003 family through the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method, the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property value is not used.</span></span>  
  
### <a name="to-change-the-gridline-color-programmatically"></a><span data-ttu-id="3081b-109">Per modificare il colore delle linee della griglia a livello di codice</span><span class="sxs-lookup"><span data-stu-id="3081b-109">To change the gridline color programmatically</span></span>  
  
- <span data-ttu-id="3081b-110">Impostare la proprietà <xref:System.Windows.Forms.DataGridView.GridColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="3081b-110">Set the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a><span data-ttu-id="3081b-111">Per modificare lo stile del bordo dell'intero controllo DataGridView a livello di codice</span><span class="sxs-lookup"><span data-stu-id="3081b-111">To change the border style of the entire DataGridView control programmatically</span></span>  
  
- <span data-ttu-id="3081b-112">Impostare la proprietà <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> su uno dei valori dell'enumerazione <xref:System.Windows.Forms.BorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="3081b-112">Set the <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> property to one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a><span data-ttu-id="3081b-113">Per modificare a livello di programmazione gli stili dei bordi per le celle DataGridView</span><span class="sxs-lookup"><span data-stu-id="3081b-113">To change the border styles for DataGridView cells programmatically</span></span>  
  
- <span data-ttu-id="3081b-114">Impostare il <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, e <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="3081b-114">Set the <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, and <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a><span data-ttu-id="3081b-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="3081b-115">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3081b-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3081b-116">Compiling the Code</span></span>  
 <span data-ttu-id="3081b-117">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3081b-117">This example requires:</span></span>  
  
- <span data-ttu-id="3081b-118">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="3081b-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="3081b-119">Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> e <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3081b-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3081b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3081b-120">See also</span></span>

- <xref:System.Windows.Forms.BorderStyle>
- <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellBorderStyle>
- <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>
- [<span data-ttu-id="3081b-121">Formattazione e stile di base nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="3081b-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)

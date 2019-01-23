---
title: "Procedura: Personalizzare l'aspetto delle celle nel controllo DataGridView Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 14667854ce4ebad561aa662fcf7d92632cc43530
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515979"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="eefef-102">Procedura: Personalizzare l'aspetto delle celle nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="eefef-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="eefef-103">È possibile personalizzare l'aspetto di una cella qualsiasi gestendo il <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.CellPainting> evento.</span><span class="sxs-lookup"><span data-stu-id="eefef-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="eefef-104">È possibile estrarre il <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Drawing.Graphics> dal <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> proprietà del <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="eefef-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="eefef-105">Con questo <xref:System.Drawing.Graphics>, è possibile modificare l'aspetto dell'intero <xref:System.Windows.Forms.DataGridView> controllo, ma è di solito si interessano solo l'aspetto della cella attualmente da disegnare.</span><span class="sxs-lookup"><span data-stu-id="eefef-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="eefef-106">Il <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> proprietà del <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> consente di limitare le operazioni di disegno per la cella attualmente da disegnare.</span><span class="sxs-lookup"><span data-stu-id="eefef-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="eefef-107">Nell'esempio di codice seguente, vengono disegnate tutte le celle in una `ContactName` colonna usando il <xref:System.Windows.Forms.DataGridView> combinazione colori del controllo.</span><span class="sxs-lookup"><span data-stu-id="eefef-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="eefef-108">Contenuto di testo di ogni cella viene disegnato nella <xref:System.Drawing.Color.Crimson%2A>, e un rettangolo viene disegnato in sullo stesso colore i <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.GridColor%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="eefef-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eefef-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="eefef-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eefef-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="eefef-110">Compiling the Code</span></span>  
 <span data-ttu-id="eefef-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="eefef-111">This example requires:</span></span>  
  
-   <span data-ttu-id="eefef-112">Oggetto <xref:System.Windows.Forms.DataGridView> controllo denominato `dataGridView1` con un `ContactName` colonna, ad esempio quello nella tabella Customers nel database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="eefef-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
-   <span data-ttu-id="eefef-113">Riferimenti agli assembly System, System.Windows.Forms e System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="eefef-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eefef-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eefef-114">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [<span data-ttu-id="eefef-115">Personalizzazione del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="eefef-115">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)

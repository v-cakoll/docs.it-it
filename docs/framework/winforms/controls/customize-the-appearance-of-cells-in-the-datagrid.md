---
title: Personalizzare l'aspetto delle celle nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 754932427a365a7b032c1ac9627d3237d1f7d0c6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744046"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2a51f-102">Procedura: personalizzare l'aspetto delle celle nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2a51f-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2a51f-103">È possibile personalizzare l'aspetto di una cella gestendo l'evento <xref:System.Windows.Forms.DataGridView.CellPainting> del controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="2a51f-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="2a51f-104">È possibile estrarre la <xref:System.Drawing.Graphics> del controllo <xref:System.Windows.Forms.DataGridView> dalla proprietà <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> della <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="2a51f-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="2a51f-105">Con questa <xref:System.Drawing.Graphics>, è possibile influire sull'aspetto dell'intero controllo <xref:System.Windows.Forms.DataGridView>, ma in genere si desidera influire solo sull'aspetto della cella attualmente disegnata.</span><span class="sxs-lookup"><span data-stu-id="2a51f-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="2a51f-106">La proprietà <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> della <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> consente di limitare le operazioni di disegno alla cella attualmente disegnata.</span><span class="sxs-lookup"><span data-stu-id="2a51f-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="2a51f-107">Nell'esempio di codice seguente, tutte le celle di una colonna di `ContactName` vengono disegnate utilizzando la combinazione di colori del controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="2a51f-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="2a51f-108">Il contenuto di testo di ogni cella viene disegnato in <xref:System.Drawing.Color.Crimson%2A>e un rettangolo di inserimento viene disegnato nello stesso colore della proprietà <xref:System.Windows.Forms.DataGridView.GridColor%2A> del controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="2a51f-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a51f-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="2a51f-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2a51f-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2a51f-110">Compiling the Code</span></span>  
 <span data-ttu-id="2a51f-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a51f-111">This example requires:</span></span>  
  
- <span data-ttu-id="2a51f-112">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` con una colonna `ContactName` come quella nella tabella Customers del database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="2a51f-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
- <span data-ttu-id="2a51f-113">Riferimenti agli assembly System, System.Windows.Forms e System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="2a51f-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a51f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a51f-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [<span data-ttu-id="2a51f-115">Personalizzazione del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2a51f-115">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)

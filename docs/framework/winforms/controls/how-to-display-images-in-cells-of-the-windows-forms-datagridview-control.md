---
title: Visualizzare immagini in celle del controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: e0e125c816877875b80e0f20887d9beee443577a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740281"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="28814-102">Procedura: visualizzare immagini in celle del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="28814-102">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="28814-103">Un'immagine o un elemento grafico è uno dei valori che è possibile visualizzare in una riga di dati.</span><span class="sxs-lookup"><span data-stu-id="28814-103">A picture or graphic is one of the values that you can display in a row of data.</span></span> <span data-ttu-id="28814-104">Spesso, questi elementi grafici hanno il formato di una fotografia di un dipendente o di un logo aziendale.</span><span class="sxs-lookup"><span data-stu-id="28814-104">Frequently, these graphics take the form of an employee's photograph or a company logo.</span></span>  
  
 <span data-ttu-id="28814-105">L'incorporamento di immagini è semplice quando si visualizzano i dati all'interno del controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="28814-105">Incorporating pictures is simple when you display data within the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="28814-106">Il controllo <xref:System.Windows.Forms.DataGridView> gestisce in modo nativo qualsiasi formato di immagine supportato dalla classe <xref:System.Drawing.Image>, nonché il formato immagine OLE utilizzato da alcuni database.</span><span class="sxs-lookup"><span data-stu-id="28814-106">The <xref:System.Windows.Forms.DataGridView> control natively handles any image format supported by the <xref:System.Drawing.Image> class, as well as the OLE picture format used by some databases.</span></span>  
  
 <span data-ttu-id="28814-107">Se l'origine dati del controllo <xref:System.Windows.Forms.DataGridView> dispone di una colonna di immagini, queste verranno visualizzate automaticamente dal controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="28814-107">If the <xref:System.Windows.Forms.DataGridView> control's data source has a column of images, they will be displayed automatically by the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="28814-108">Nell'esempio di codice riportato di seguito viene illustrato come estrarre un'icona da una risorsa incorporata e convertirla in una bitmap per la visualizzazione in ogni cella di una colonna di un'immagine.</span><span class="sxs-lookup"><span data-stu-id="28814-108">The following code example demonstrates how to extract an icon from an embedded resource and convert it to a bitmap for display in every cell of an image column.</span></span> <span data-ttu-id="28814-109">Per un altro esempio che sostituisce i valori di cella testuale con le immagini corrispondenti, vedere [procedura: personalizzare la formattazione dei dati nel controllo DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="28814-109">For another example that replaces textual cell values with corresponding images, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="28814-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="28814-110">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="28814-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="28814-111">Compiling the Code</span></span>  
 <span data-ttu-id="28814-112">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="28814-112">This example requires:</span></span>  
  
- <span data-ttu-id="28814-113">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="28814-113">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="28814-114">Una risorsa icona incorporata denominata `tree.ico`.</span><span class="sxs-lookup"><span data-stu-id="28814-114">An embedded icon resource named `tree.ico`.</span></span>  
  
- <span data-ttu-id="28814-115">Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> e <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="28814-115">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28814-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28814-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="28814-117">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="28814-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="28814-118">Procedura: Formattare dati personalizzati in un controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="28814-118">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)

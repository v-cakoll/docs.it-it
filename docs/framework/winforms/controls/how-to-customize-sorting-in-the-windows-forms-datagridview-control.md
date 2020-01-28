---
title: Personalizzare l'ordinamento in un controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], sorting
- data grids [Windows Forms], customizing sorting
ms.assetid: 92fb5c14-afab-4cf5-a97e-924fd9cb99f5
ms.openlocfilehash: 20f581b2df6fd172a0a1998aed60c56b0306f2eb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743175"
---
# <a name="how-to-customize-sorting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="74681-102">Procedura: personalizzare l'ordinamento nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="74681-102">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="74681-103">Il controllo <xref:System.Windows.Forms.DataGridView> fornisce l'ordinamento automatico, tuttavia le operazioni di ordinamento possono essere personalizzate secondo le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="74681-103">The <xref:System.Windows.Forms.DataGridView> control provides automatic sorting but, depending on your needs, you might need to customize sort operations.</span></span> <span data-ttu-id="74681-104">Ad esempio, è possibile usare l'ordinamento a livello di codice per creare un'interfaccia utente alternativa.</span><span class="sxs-lookup"><span data-stu-id="74681-104">For example, you can use programmatic sorting to create an alternate user interface (UI).</span></span> <span data-ttu-id="74681-105">È anche possibile gestire l'evento <xref:System.Windows.Forms.DataGridView.SortCompare> o chiamare l'overload `Sort(IComparer)` del metodo <xref:System.Windows.Forms.DataGridView.Sort%2A> per una maggiore flessibilità, ad esempio per l'ordinamento di più colonne.</span><span class="sxs-lookup"><span data-stu-id="74681-105">Alternatively, you can handle the <xref:System.Windows.Forms.DataGridView.SortCompare> event or call the `Sort(IComparer)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method for greater sorting flexibility, such as sorting multiple columns.</span></span>  
  
 <span data-ttu-id="74681-106">Gli esempi di codice seguenti illustrano questi tre approcci all'ordinamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="74681-106">The following code examples demonstrate these three approaches to custom sorting.</span></span> <span data-ttu-id="74681-107">Per altre informazioni, vedere [Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form](column-sort-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="74681-107">For more information, see [Column Sort Modes in the Windows Forms DataGridView Control](column-sort-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="programmatic-sorting"></a><span data-ttu-id="74681-108">Ordinamento a livello di codice</span><span class="sxs-lookup"><span data-stu-id="74681-108">Programmatic Sorting</span></span>  
 <span data-ttu-id="74681-109">L'esempio di codice seguente illustra un ordinamento a livello di codice che usa le proprietà <xref:System.Windows.Forms.DataGridView.SortOrder%2A> e <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> per determinare la direzione dell'ordinamento e la proprietà <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> per impostare manualmente il glifo di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="74681-109">The following code example demonstrates a programmatic sort using the <xref:System.Windows.Forms.DataGridView.SortOrder%2A> and <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> properties to determine the direction of the sort, and the <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> property to manually set the sort glyph.</span></span> <span data-ttu-id="74681-110">L'overload `Sort(DataGridViewColumn,ListSortDirection)` del metodo <xref:System.Windows.Forms.DataGridView.Sort%2A> viene usato per ordinare i dati solo in una singola colonna.</span><span class="sxs-lookup"><span data-stu-id="74681-110">The `Sort(DataGridViewColumn,ListSortDirection)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method is used to sort data only in a single column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-sortcompare-event"></a><span data-ttu-id="74681-111">Ordinamento personalizzato tramite l'evento SortCompare</span><span class="sxs-lookup"><span data-stu-id="74681-111">Custom Sorting Using the SortCompare Event</span></span>  
 <span data-ttu-id="74681-112">L'esempio di codice seguente illustra un ordinamento personalizzato tramite un gestore dell'evento <xref:System.Windows.Forms.DataGridView.SortCompare>.</span><span class="sxs-lookup"><span data-stu-id="74681-112">The following code example demonstrates custom sorting using a <xref:System.Windows.Forms.DataGridView.SortCompare> event handler.</span></span> <span data-ttu-id="74681-113">L'oggetto <xref:System.Windows.Forms.DataGridViewColumn> selezionato viene ordinato e, se esistono valori duplicati nella colonna, per determinare l'ordine finale viene usata la colonna ID.</span><span class="sxs-lookup"><span data-stu-id="74681-113">The selected <xref:System.Windows.Forms.DataGridViewColumn> is sorted and, if there are duplicate values in the column, the ID column is used to determine the final order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-icomparer-interface"></a><span data-ttu-id="74681-114">Ordinamento personalizzato tramite l'interfaccia IComparer</span><span class="sxs-lookup"><span data-stu-id="74681-114">Custom Sorting Using the IComparer Interface</span></span>  
 <span data-ttu-id="74681-115">L'esempio di codice seguente illustra  l'ordinamento personalizzato tramite l'overload `Sort(IComparer)` del metodo <xref:System.Windows.Forms.DataGridView.Sort%2A>, che usa un'implementazione dell'interfaccia <xref:System.Collections.IComparer> per eseguire un ordinamento di più colonne.</span><span class="sxs-lookup"><span data-stu-id="74681-115">The following code example demonstrates custom sorting using the `Sort(IComparer)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method, which takes an implementation of the <xref:System.Collections.IComparer> interface to perform a multiple-column sort.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/VB/form1.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="74681-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="74681-116">Compiling the Code</span></span>  
 <span data-ttu-id="74681-117">Gli esempi presentano i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="74681-117">These examples require:</span></span>  
  
- <span data-ttu-id="74681-118">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="74681-118">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74681-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74681-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="74681-120">Ordinamento di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="74681-120">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="74681-121">Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="74681-121">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="74681-122">Procedura: Impostare le modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="74681-122">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)

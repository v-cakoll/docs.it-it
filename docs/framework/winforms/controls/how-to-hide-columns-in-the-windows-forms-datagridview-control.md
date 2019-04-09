---
title: 'Procedura: Nascondere le colonne nel controllo DataGridView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], hiding columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
ms.assetid: 3f94143a-2ef0-49a5-a22a-b2e6f9289642
ms.openlocfilehash: 40fccee551e7840ef474e7775873d4e7178748fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194318"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="ae561-102">Procedura: Nascondere le colonne nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae561-102">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="ae561-103">A volte può essere necessario visualizzare solo alcune colonne tra quelle disponibili in un controllo <xref:System.Windows.Forms.DataGridView> Windows Form.</span><span class="sxs-lookup"><span data-stu-id="ae561-103">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="ae561-104">Ad esempio, può essere necessario mostrare una colonna con gli stipendi dei dipendenti agli utenti con credenziali di gestione e nasconderla invece agli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="ae561-104">For example, you might want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="ae561-105">Oppure potrebbe essere necessario associare il controllo a un'origine dati contenente più colonne, di cui solo alcune devono essere visualizzate.</span><span class="sxs-lookup"><span data-stu-id="ae561-105">Alternately, you might want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="ae561-106">In questo caso, si rimuovono in genere le colonne che non interessa visualizzare, invece di nasconderle.</span><span class="sxs-lookup"><span data-stu-id="ae561-106">In this case, you will typically remove the columns you are not interested in displaying rather than hide them.</span></span>  
  
 <span data-ttu-id="ae561-107">Nel controllo <xref:System.Windows.Forms.DataGridView>, il valore della proprietà <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> di una colonna determina se la colonna viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="ae561-107">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property value of a column determines whether that column is displayed.</span></span>  
  
 <span data-ttu-id="ae561-108">Questa attività è supportata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ae561-108">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="ae561-109">Vedere anche [come: Nascondere le colonne in di Windows Form usando la finestra di progettazione di DataGridView Control](hide-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="ae561-109">Also see [How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer](hide-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-hide-a-column-programmatically"></a><span data-ttu-id="ae561-110">Per nascondere una colonna a livello di codice</span><span class="sxs-lookup"><span data-stu-id="ae561-110">To hide a column programmatically</span></span>  
  
-   <span data-ttu-id="ae561-111">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType> su `false`.</span><span class="sxs-lookup"><span data-stu-id="ae561-111">Set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType> property to `false`.</span></span> <span data-ttu-id="ae561-112">Per nascondere una colonna `CustomerID` generata automaticamente durante il data binding, inserire il seguente esempio di codice in un gestore dell'evento <xref:System.Windows.Forms.DataGridView.DataBindingComplete>.</span><span class="sxs-lookup"><span data-stu-id="ae561-112">To hide a `CustomerID` column that is automatically generated during data binding, place the following code example in a <xref:System.Windows.Forms.DataGridView.DataBindingComplete> event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#063](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#063)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#063](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#063)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ae561-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ae561-113">Compiling the Code</span></span>  
 <span data-ttu-id="ae561-114">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae561-114">This example requires:</span></span>  
  
-   <span data-ttu-id="ae561-115">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` contenente una colonna denominata `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="ae561-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `CustomerID`.</span></span>  
  
-   <span data-ttu-id="ae561-116">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ae561-116">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae561-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae561-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ae561-118">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ae561-118">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="ae561-119">Procedura: Rimuovere le colonne generate automaticamente da un controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae561-119">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)
- [<span data-ttu-id="ae561-120">Procedura: Modificare l'ordine delle colonne nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae561-120">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)

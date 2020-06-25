---
title: Nascondi colonne nel controllo DataGridView
description: Informazioni su come nascondere le colonne a livello nel controllo DataGridView Windows Forms impostando la proprietà DataGridViewColumn. Visible su false.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], hiding columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
ms.assetid: 3f94143a-2ef0-49a5-a22a-b2e6f9289642
ms.openlocfilehash: 46d7faea76098406b8e0a91d22922bf9ca391e28
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325913"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="55c8a-103">Procedura: nascondere le colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="55c8a-103">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="55c8a-104">A volte può essere necessario visualizzare solo alcune colonne tra quelle disponibili in un controllo <xref:System.Windows.Forms.DataGridView> Windows Form.</span><span class="sxs-lookup"><span data-stu-id="55c8a-104">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="55c8a-105">Ad esempio, può essere necessario mostrare una colonna con gli stipendi dei dipendenti agli utenti con credenziali di gestione e nasconderla invece agli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="55c8a-105">For example, you might want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="55c8a-106">Oppure potrebbe essere necessario associare il controllo a un'origine dati contenente più colonne, di cui solo alcune devono essere visualizzate.</span><span class="sxs-lookup"><span data-stu-id="55c8a-106">Alternately, you might want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="55c8a-107">In questo caso, si rimuovono in genere le colonne che non interessa visualizzare, invece di nasconderle.</span><span class="sxs-lookup"><span data-stu-id="55c8a-107">In this case, you will typically remove the columns you are not interested in displaying rather than hide them.</span></span>  
  
 <span data-ttu-id="55c8a-108">Nel controllo <xref:System.Windows.Forms.DataGridView>, il valore della proprietà <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> di una colonna determina se la colonna viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="55c8a-108">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property value of a column determines whether that column is displayed.</span></span>  
  
 <span data-ttu-id="55c8a-109">Questa attività è supportata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="55c8a-109">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="55c8a-110">Vedere anche [procedura: nascondere le colonne nel controllo DataGridView Windows Forms usando la finestra di progettazione](hide-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="55c8a-110">Also see [How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer](hide-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-hide-a-column-programmatically"></a><span data-ttu-id="55c8a-111">Per nascondere una colonna a livello di codice</span><span class="sxs-lookup"><span data-stu-id="55c8a-111">To hide a column programmatically</span></span>  
  
- <span data-ttu-id="55c8a-112">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType> su `false`.</span><span class="sxs-lookup"><span data-stu-id="55c8a-112">Set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType> property to `false`.</span></span> <span data-ttu-id="55c8a-113">Per nascondere una colonna `CustomerID` generata automaticamente durante il data binding, inserire il seguente esempio di codice in un gestore dell'evento <xref:System.Windows.Forms.DataGridView.DataBindingComplete>.</span><span class="sxs-lookup"><span data-stu-id="55c8a-113">To hide a `CustomerID` column that is automatically generated during data binding, place the following code example in a <xref:System.Windows.Forms.DataGridView.DataBindingComplete> event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#063](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#063)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#063](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#063)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="55c8a-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="55c8a-114">Compiling the Code</span></span>  
 <span data-ttu-id="55c8a-115">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="55c8a-115">This example requires:</span></span>  
  
- <span data-ttu-id="55c8a-116">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` contenente una colonna denominata `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="55c8a-116">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `CustomerID`.</span></span>  
  
- <span data-ttu-id="55c8a-117">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="55c8a-117">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c8a-118">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="55c8a-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="55c8a-119">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="55c8a-119">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="55c8a-120">Procedure: rimuovere le colonne generate automaticamente da un controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="55c8a-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)
- [<span data-ttu-id="55c8a-121">Procedura: modificare l'ordine delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="55c8a-121">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)

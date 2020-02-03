---
title: Uso della selezione e degli Appunti con il controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
ms.openlocfilehash: 6993f77e8ce532d8df1bdc7e6b6abc1cc3268e49
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743057"
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="20257-102">Uso della selezione e degli Appunti con il controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="20257-102">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="20257-103">Il controllo `DataGridView` offre un'ampia gamma di opzioni per la configurazione del modo in cui gli utenti possono selezionare celle, righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="20257-103">The `DataGridView` control provides you with a variety of options for configuring how users can select cells, rows, and columns.</span></span> <span data-ttu-id="20257-104">È ad esempio possibile abilitare una selezione singola o multipla, la selezione di intere righe o colonne quando gli utenti fanno clic su celle oppure selezionano intere righe o colonne solo quando gli utenti fanno clic sulle intestazioni, consentendo così la selezione delle celle.</span><span class="sxs-lookup"><span data-stu-id="20257-104">For example, you can enable single or multiple selection, selection of whole rows or columns when users click cells, or selection of whole rows or columns only when users click their headers, which enables cell selection as well.</span></span> <span data-ttu-id="20257-105">Se si desidera fornire un'interfaccia utente personalizzata per la selezione, è possibile disabilitare la selezione ordinaria e gestire tutta la selezione a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="20257-105">If you want to provide your own user interface for selection, you can disable ordinary selection and handle all selection programmatically.</span></span> <span data-ttu-id="20257-106">Inoltre, è possibile consentire agli utenti di copiare i valori selezionati negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="20257-106">Additionally, you can enable users to copy the selected values to the Clipboard.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20257-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="20257-107">In This Section</span></span>  
 [<span data-ttu-id="20257-108">Modalità di selezione nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="20257-108">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="20257-109">Descrive le opzioni per l'utente e la selezione a livello di codice nel controllo.</span><span class="sxs-lookup"><span data-stu-id="20257-109">Describes the options for user and programmatic selection in the control.</span></span>  
  
 [<span data-ttu-id="20257-110">Procedura: Impostare la modalità di selezione del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="20257-110">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="20257-111">Viene descritto come configurare il controllo per la selezione di una singola riga quando un utente fa clic su una cella.</span><span class="sxs-lookup"><span data-stu-id="20257-111">Describes how to configure the control for single-row selection when a user clicks a cell.</span></span>  
  
 [<span data-ttu-id="20257-112">Procedura: Ottenere le celle, righe e colonne selezionate nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="20257-112">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](selected-cells-rows-and-columns-datagridview.md)  
 <span data-ttu-id="20257-113">Viene descritto come utilizzare le raccolte di celle, righe e colonne selezionate.</span><span class="sxs-lookup"><span data-stu-id="20257-113">Describes how to work with the selected cell, row, and column collections.</span></span>  
  
 [<span data-ttu-id="20257-114">Procedura: Consentire agli utenti di copiare più celle negli Appunti dal controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="20257-114">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>](enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 <span data-ttu-id="20257-115">Viene descritto come abilitare il supporto degli Appunti nel controllo.</span><span class="sxs-lookup"><span data-stu-id="20257-115">Describes how to enable Clipboard support in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="20257-116">Riferimento</span><span class="sxs-lookup"><span data-stu-id="20257-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="20257-117">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="20257-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="20257-118">Fornisce la documentazione di riferimento per la proprietà <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="20257-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <span data-ttu-id="20257-119">Fornisce la documentazione di riferimento per la proprietà <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="20257-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <span data-ttu-id="20257-120">Fornisce la documentazione di riferimento per la classe <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>.</span><span class="sxs-lookup"><span data-stu-id="20257-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <span data-ttu-id="20257-121">Fornisce la documentazione di riferimento per la classe <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>.</span><span class="sxs-lookup"><span data-stu-id="20257-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <span data-ttu-id="20257-122">Fornisce la documentazione di riferimento per la classe <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>.</span><span class="sxs-lookup"><span data-stu-id="20257-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20257-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20257-123">See also</span></span>

- [<span data-ttu-id="20257-124">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="20257-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="20257-125">Gestione predefinita di tastiera e mouse nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="20257-125">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)

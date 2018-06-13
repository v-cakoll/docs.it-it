---
title: Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], basic features
- columns [Windows Forms], DataGridView control
- data grids [Windows Forms], examples
- DataGridView control [Windows Forms], examples
ms.assetid: 78085f26-d5d2-4b75-813e-e932b72fd06f
ms.openlocfilehash: 3d6a44dce7dfd59d484d1a3495982a0d7d1f3e46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525494"
---
# <a name="basic-column-row-and-cell-features-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="a6689-102">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a6689-102">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a6689-103">Molti comportamenti di base `DataGridView` celle, righe e colonne possono essere modificate impostando singole proprietà.</span><span class="sxs-lookup"><span data-stu-id="a6689-103">Many basic behaviors of `DataGridView` cells, rows, and columns can be modified by setting single properties.</span></span> <span data-ttu-id="a6689-104">Negli argomenti di questa sezione vengono descritti molti dei più comunemente utilizzate queste funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a6689-104">The topics in this section describe several of the most commonly used of these features.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a6689-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="a6689-105">In This Section</span></span>  
 [<span data-ttu-id="a6689-106">Procedura: Nascondere le colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a6689-106">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a6689-107">Viene descritto come impedire la visualizzazione nel controllo colonne specifiche.</span><span class="sxs-lookup"><span data-stu-id="a6689-107">Describes how to prevent specific columns from appearing in the control.</span></span>  
  
 [<span data-ttu-id="a6689-108">Procedura: Nascondere le intestazioni delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a6689-108">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-column-headers-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a6689-109">Viene descritto come impedire le intestazioni di colonna nel controllo.</span><span class="sxs-lookup"><span data-stu-id="a6689-109">Describes how to prevent the column headers from appearing in the control.</span></span>  
  
 [<span data-ttu-id="a6689-110">Procedura: Abilitare il riordinamento delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a6689-110">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a6689-111">Viene descritto come consentire agli utenti di ridisporre le colonne nel controllo.</span><span class="sxs-lookup"><span data-stu-id="a6689-111">Describes how to enable users to rearrange columns in the control.</span></span>  
  
 [<span data-ttu-id="a6689-112">Procedura: Bloccare le colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a6689-112">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a6689-113">Viene descritto come impedire che una o più colonne adiacenti lo scorrimento.</span><span class="sxs-lookup"><span data-stu-id="a6689-113">Describes how prevent one or more adjacent columns from scrolling.</span></span>  
  
 [<span data-ttu-id="a6689-114">Procedura: Impostare le colonne come in sola lettura nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a6689-114">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a6689-115">Viene descritto come impedire la modifica di colonne specifiche del controllo.</span><span class="sxs-lookup"><span data-stu-id="a6689-115">Describes how to prevent users from editing specific columns in the control.</span></span>  
  
 [<span data-ttu-id="a6689-116">Procedura: Impedire l'aggiunta o l'eliminazione di righe nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a6689-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)  
 <span data-ttu-id="a6689-117">Viene descritto come rimuovere la riga per nuovi record nella parte inferiore del controllo per impedire agli utenti di aggiungere righe.</span><span class="sxs-lookup"><span data-stu-id="a6689-117">Describes how to remove the row for new records at the bottom of the control to prevent users from adding rows.</span></span> <span data-ttu-id="a6689-118">Descrive inoltre come impedire agli utenti di eliminare le righe.</span><span class="sxs-lookup"><span data-stu-id="a6689-118">Also describes how to prevent users from deleting rows.</span></span>  
  
 [<span data-ttu-id="a6689-119">Procedura: Ottenere e impostare la cella corrente nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a6689-119">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/get-and-set-the-current-cell-wf-datagridview-control.md)  
 <span data-ttu-id="a6689-120">Viene descritto come accedere alla cella che ha attualmente lo stato attivo nel controllo.</span><span class="sxs-lookup"><span data-stu-id="a6689-120">Describes how to access the cell that currently has focus in the control.</span></span>  
  
 [<span data-ttu-id="a6689-121">Procedura: visualizzare immagini in celle del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a6689-121">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a6689-122">Viene descritto come creare una colonna di immagine che viene visualizzata un'icona in ogni cella.</span><span class="sxs-lookup"><span data-stu-id="a6689-122">Describes how to create an image column that displays an icon in every cell.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a6689-123">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="a6689-123">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="a6689-124">Fornisce la documentazione di riferimento per il controllo.</span><span class="sxs-lookup"><span data-stu-id="a6689-124">Provides reference documentation for the control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a6689-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a6689-125">Related Sections</span></span>  
 [<span data-ttu-id="a6689-126">Formattazione e stile di base nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a6689-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a6689-127">Fornisce argomenti che descrivono come modificare l'aspetto del controllo e la formattazione di base dei dati delle celle.</span><span class="sxs-lookup"><span data-stu-id="a6689-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="a6689-128">Programmazione con celle, righe e colonne nel controllo DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a6689-128">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="a6689-129">Fornisce argomenti che descrivono come eseguire la programmazione con oggetti cella, riga e colonna.</span><span class="sxs-lookup"><span data-stu-id="a6689-129">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6689-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6689-130">See Also</span></span>  
 [<span data-ttu-id="a6689-131">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="a6689-131">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="a6689-132">Tipi di colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a6689-132">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)

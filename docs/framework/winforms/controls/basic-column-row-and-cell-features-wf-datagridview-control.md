---
title: Funzionalità di base per colonna, riga e cella nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], basic features
- columns [Windows Forms], DataGridView control
- data grids [Windows Forms], examples
- DataGridView control [Windows Forms], examples
ms.assetid: 78085f26-d5d2-4b75-813e-e932b72fd06f
ms.openlocfilehash: 02f8ad7e11a61e9434748a8b3b2f853f98b013d1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746223"
---
# <a name="basic-column-row-and-cell-features-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="24da0-102">Funzionalità di base per colonna, riga e cella nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="24da0-102">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="24da0-103">Molti comportamenti di base di `DataGridView` celle, righe e colonne possono essere modificati impostando singole proprietà.</span><span class="sxs-lookup"><span data-stu-id="24da0-103">Many basic behaviors of `DataGridView` cells, rows, and columns can be modified by setting single properties.</span></span> <span data-ttu-id="24da0-104">Negli argomenti di questa sezione vengono descritte alcune delle funzionalità più comunemente utilizzate.</span><span class="sxs-lookup"><span data-stu-id="24da0-104">The topics in this section describe several of the most commonly used of these features.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="24da0-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="24da0-105">In This Section</span></span>  
 [<span data-ttu-id="24da0-106">Procedura: Nascondere le colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="24da0-106">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>](how-to-hide-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="24da0-107">Viene descritto come impedire che colonne specifiche vengano visualizzate nel controllo.</span><span class="sxs-lookup"><span data-stu-id="24da0-107">Describes how to prevent specific columns from appearing in the control.</span></span>  
  
 [<span data-ttu-id="24da0-108">Procedura: Nascondere le intestazioni delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="24da0-108">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>](how-to-hide-column-headers-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="24da0-109">Viene descritto come impedire che le intestazioni di colonna vengano visualizzate nel controllo.</span><span class="sxs-lookup"><span data-stu-id="24da0-109">Describes how to prevent the column headers from appearing in the control.</span></span>  
  
 [<span data-ttu-id="24da0-110">Procedura: Abilitare il riordinamento delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="24da0-110">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="24da0-111">Viene descritto come consentire agli utenti di ridisporre le colonne nel controllo.</span><span class="sxs-lookup"><span data-stu-id="24da0-111">Describes how to enable users to rearrange columns in the control.</span></span>  
  
 [<span data-ttu-id="24da0-112">Procedura: Bloccare le colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="24da0-112">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="24da0-113">Viene descritto come impedire lo scorrimento di una o più colonne adiacenti.</span><span class="sxs-lookup"><span data-stu-id="24da0-113">Describes how prevent one or more adjacent columns from scrolling.</span></span>  
  
 [<span data-ttu-id="24da0-114">Procedura: Impostare le colonne come in sola lettura nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="24da0-114">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="24da0-115">Viene descritto come impedire agli utenti di modificare colonne specifiche nel controllo.</span><span class="sxs-lookup"><span data-stu-id="24da0-115">Describes how to prevent users from editing specific columns in the control.</span></span>  
  
 [<span data-ttu-id="24da0-116">Procedura: Impedire l'aggiunta o l'eliminazione di righe nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="24da0-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](prevent-row-addition-and-deletion-datagridview.md)  
 <span data-ttu-id="24da0-117">Viene descritto come rimuovere la riga per i nuovi record nella parte inferiore del controllo per impedire agli utenti di aggiungere righe.</span><span class="sxs-lookup"><span data-stu-id="24da0-117">Describes how to remove the row for new records at the bottom of the control to prevent users from adding rows.</span></span> <span data-ttu-id="24da0-118">Viene inoltre descritto come impedire agli utenti di eliminare righe.</span><span class="sxs-lookup"><span data-stu-id="24da0-118">Also describes how to prevent users from deleting rows.</span></span>  
  
 [<span data-ttu-id="24da0-119">Procedura: Ottenere e impostare la cella corrente nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="24da0-119">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>](get-and-set-the-current-cell-wf-datagridview-control.md)  
 <span data-ttu-id="24da0-120">Viene descritto come accedere alla cella che attualmente ha lo stato attivo nel controllo.</span><span class="sxs-lookup"><span data-stu-id="24da0-120">Describes how to access the cell that currently has focus in the control.</span></span>  
  
 [<span data-ttu-id="24da0-121">Procedura: visualizzare immagini in celle del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="24da0-121">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>](how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="24da0-122">Viene descritto come creare una colonna immagine che visualizza un'icona in ogni cella.</span><span class="sxs-lookup"><span data-stu-id="24da0-122">Describes how to create an image column that displays an icon in every cell.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="24da0-123">Riferimento</span><span class="sxs-lookup"><span data-stu-id="24da0-123">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="24da0-124">Fornisce la documentazione di riferimento per il controllo.</span><span class="sxs-lookup"><span data-stu-id="24da0-124">Provides reference documentation for the control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="24da0-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="24da0-125">Related Sections</span></span>  
 [<span data-ttu-id="24da0-126">Formattazione e stile di base nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="24da0-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="24da0-127">Fornisce argomenti che descrivono come modificare l'aspetto del controllo e la formattazione di base dei dati delle celle.</span><span class="sxs-lookup"><span data-stu-id="24da0-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="24da0-128">Programmazione con celle, righe e colonne nel controllo DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24da0-128">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="24da0-129">Fornisce argomenti che descrivono come eseguire la programmazione con oggetti cella, riga e colonna.</span><span class="sxs-lookup"><span data-stu-id="24da0-129">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24da0-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24da0-130">See also</span></span>

- [<span data-ttu-id="24da0-131">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="24da0-131">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="24da0-132">Tipi di colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="24da0-132">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)

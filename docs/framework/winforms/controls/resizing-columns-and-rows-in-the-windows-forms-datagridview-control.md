---
title: Ridimensionamento di colonne e righe nel controllo DataGridView di Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3621b05f1faae671d93106f50dfef1311959e48e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="88d33-102">Ridimensionamento di colonne e righe nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="88d33-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="88d33-103">Il `DataGridView` controllo fornisce numerose opzioni per personalizzare il comportamento di ridimensionamento di colonne e righe.</span><span class="sxs-lookup"><span data-stu-id="88d33-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="88d33-104">In genere, `DataGridView` celle non vengono ridimensionano in base al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="88d33-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="88d33-105">Al contrario, vengono tagliati qualsiasi valore di visualizzazione che è maggiore della cella.</span><span class="sxs-lookup"><span data-stu-id="88d33-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="88d33-106">Se è possibile visualizzare il contenuto come stringa, viene inserito in una descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="88d33-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="88d33-107">Per impostazione predefinita, gli utenti possono trascinare righe, colonne e i separatori di intestazione con il mouse per visualizzare ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="88d33-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="88d33-108">Gli utenti possono anche fare doppio clic su un divisore per ridimensionare automaticamente la banda di riga, colonna o intestazione associata in base al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="88d33-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="88d33-109">Il `DataGridView` controllo fornisce proprietà, metodi ed eventi che consentono la personalizzazione o la disattivazione di tutti i comportamenti gestiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="88d33-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="88d33-110">Inoltre, è possibile ridimensionare a livello di codice le righe, colonne e intestazioni in base al contenuto, oppure è possibile configurare in modo da ridimensionati automaticamente ogni volta che cambia il relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="88d33-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="88d33-111">È inoltre possibile configurare le colonne per dividere automaticamente la larghezza disponibile del controllo in base alle proporzioni specificato.</span><span class="sxs-lookup"><span data-stu-id="88d33-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88d33-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="88d33-112">In This Section</span></span>  
 [<span data-ttu-id="88d33-113">Opzioni di ridimensionamento nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="88d33-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="88d33-114">Vengono descritte le opzioni per intestazioni, colonne e righe di ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="88d33-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="88d33-115">Inoltre fornisce informazioni dettagliate sui metodi e proprietà correlate al ridimensionamento e vengono descritti scenari comuni di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="88d33-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="88d33-116">Modalità di riempimento di colonna nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="88d33-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="88d33-117">Descrive in dettaglio la modalità di riempimento di colonna e viene fornito codice dimostrativo che è possibile utilizzare per sperimentare modalità riempimento delle colonne e gli altri modi.</span><span class="sxs-lookup"><span data-stu-id="88d33-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="88d33-118">Procedura: Impostare le modalità dimensionamento del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="88d33-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="88d33-119">Viene descritto come configurare le modalità di ridimensionamento per attività comuni.</span><span class="sxs-lookup"><span data-stu-id="88d33-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="88d33-120">Procedura: Ridimensionare a livello di codice le celle in base al contenuto nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="88d33-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="88d33-121">Fornisce il codice di esempio che è possibile utilizzare per sperimentare il ridimensionamento a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="88d33-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="88d33-122">Procedura: Ridimensionare automaticamente le celle alla modifica del contenuto del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="88d33-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="88d33-123">Fornisce il codice di esempio che consente di sperimentare le modalità di ridimensionamento automatico.</span><span class="sxs-lookup"><span data-stu-id="88d33-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="88d33-124">Riferimento</span><span class="sxs-lookup"><span data-stu-id="88d33-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="88d33-125">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="88d33-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88d33-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88d33-126">See Also</span></span>  
 [<span data-ttu-id="88d33-127">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="88d33-127">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)

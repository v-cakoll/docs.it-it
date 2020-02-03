---
title: Ridimensionare colonne e righe nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: 8f8394a837ccc11c469f9ad4feeb60464d0014fe
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742408"
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="9deb9-102">Ridimensionamento di colonne e righe nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="9deb9-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="9deb9-103">Il controllo `DataGridView` offre numerose opzioni per la personalizzazione del comportamento di ridimensionamento delle colonne e delle righe.</span><span class="sxs-lookup"><span data-stu-id="9deb9-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="9deb9-104">In genere, `DataGridView` le celle non vengono ridimensionate in base al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="9deb9-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="9deb9-105">Ma ritagliano qualsiasi valore di visualizzazione superiore alla cella.</span><span class="sxs-lookup"><span data-stu-id="9deb9-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="9deb9-106">Se il contenuto può essere visualizzato come stringa, la cella la Visualizza in una descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="9deb9-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="9deb9-107">Per impostazione predefinita, gli utenti possono trascinare i divisori di riga, colonna e intestazione con il mouse per visualizzare altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="9deb9-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="9deb9-108">Gli utenti possono anche fare doppio clic su un divisore per ridimensionare automaticamente la riga, la colonna o la banda di intestazione associata in base al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="9deb9-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="9deb9-109">Il controllo `DataGridView` fornisce proprietà, metodi ed eventi che consentono di personalizzare o disabilitare tutti questi comportamenti indirizzati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="9deb9-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="9deb9-110">Inoltre, è possibile ridimensionare a livello di codice le righe, le colonne e le intestazioni per adattarne il contenuto, oppure è possibile configurarle in modo che vengano ridimensionate automaticamente ogni volta che il contenuto viene modificato.</span><span class="sxs-lookup"><span data-stu-id="9deb9-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="9deb9-111">È inoltre possibile configurare le colonne per dividere automaticamente la larghezza disponibile del controllo in proporzioni specificate.</span><span class="sxs-lookup"><span data-stu-id="9deb9-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9deb9-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9deb9-112">In This Section</span></span>  
 [<span data-ttu-id="9deb9-113">Opzioni di ridimensionamento nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9deb9-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9deb9-114">Descrive le opzioni per il dimensionamento di righe, colonne e intestazioni.</span><span class="sxs-lookup"><span data-stu-id="9deb9-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="9deb9-115">Vengono inoltre fornite informazioni dettagliate sulle proprietà e sui metodi correlati al dimensionamento e vengono descritti gli scenari di utilizzo comuni.</span><span class="sxs-lookup"><span data-stu-id="9deb9-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="9deb9-116">Modalità di riempimento di colonna nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9deb9-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9deb9-117">Viene descritta in dettaglio la modalità di riempimento delle colonne e viene fornito il codice dimostrativo che è possibile utilizzare per sperimentare la modalità di riempimento delle colonne e altre modalità.</span><span class="sxs-lookup"><span data-stu-id="9deb9-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="9deb9-118">Procedura: Impostare le modalità dimensionamento del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9deb9-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9deb9-119">Viene descritto come configurare le modalità di ridimensionamento per scopi comuni.</span><span class="sxs-lookup"><span data-stu-id="9deb9-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="9deb9-120">Procedura: Ridimensionare a livello di codice le celle in base al contenuto nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9deb9-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="9deb9-121">Fornisce il codice dimostrativo che è possibile usare per sperimentare il ridimensionamento a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="9deb9-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="9deb9-122">Procedura: Ridimensionare automaticamente le celle alla modifica del contenuto del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9deb9-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="9deb9-123">Fornisce il codice dimostrativo che è possibile usare per sperimentare le modalità di ridimensionamento automatico.</span><span class="sxs-lookup"><span data-stu-id="9deb9-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9deb9-124">Riferimento</span><span class="sxs-lookup"><span data-stu-id="9deb9-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="9deb9-125">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="9deb9-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9deb9-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9deb9-126">See also</span></span>

- [<span data-ttu-id="9deb9-127">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="9deb9-127">DataGridView Control</span></span>](datagridview-control-windows-forms.md)

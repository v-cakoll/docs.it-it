---
title: Visualizzazione di dati nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: d02362895d75df3735d19554bd44bb8ac443c6c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745875"
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8d83a-102">Visualizzazione di dati nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="8d83a-102">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8d83a-103">Il controllo `DataGridView` viene utilizzato per visualizzare i dati da un'ampia gamma di origini dati esterne.</span><span class="sxs-lookup"><span data-stu-id="8d83a-103">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="8d83a-104">In alternativa, è possibile aggiungere righe e colonne al controllo e popolarle manualmente con i dati.</span><span class="sxs-lookup"><span data-stu-id="8d83a-104">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="8d83a-105">Quando si associa il controllo a un'origine dati, è possibile generare automaticamente le colonne in base allo schema dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="8d83a-105">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="8d83a-106">Se queste colonne non vengono visualizzate esattamente come si desidera, è possibile nasconderle, rimuoverle o riordinarle.</span><span class="sxs-lookup"><span data-stu-id="8d83a-106">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="8d83a-107">È inoltre possibile aggiungere colonne non associate per visualizzare dati supplementari che non provengono dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="8d83a-107">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="8d83a-108">Inoltre, è possibile visualizzare i dati usando formati standard, ad esempio il formato di valuta, oppure personalizzare la formattazione dello schermo per presentare i dati, ma è necessario, ad esempio, modificare il colore di sfondo per i numeri negativi o sostituire i valori stringa con le immagini corrispondenti).</span><span class="sxs-lookup"><span data-stu-id="8d83a-108">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8d83a-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="8d83a-109">In This Section</span></span>  
 [<span data-ttu-id="8d83a-110">Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8d83a-110">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8d83a-111">Descrive le opzioni per popolare il controllo con i dati.</span><span class="sxs-lookup"><span data-stu-id="8d83a-111">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="8d83a-112">Formattazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8d83a-112">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8d83a-113">Descrive le opzioni per la formattazione dei valori di visualizzazione delle celle.</span><span class="sxs-lookup"><span data-stu-id="8d83a-113">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="8d83a-114">Procedura dettagliata: Creazione di un controllo DataGridView di Windows Form non associato</span><span class="sxs-lookup"><span data-stu-id="8d83a-114">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8d83a-115">Viene descritto come popolare manualmente il controllo con i dati.</span><span class="sxs-lookup"><span data-stu-id="8d83a-115">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="8d83a-116">Procedura: Associare dati al controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8d83a-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8d83a-117">Viene descritto come popolare il controllo con i dati mediante l'associazione a una `BindingSource` che contiene informazioni pull da un database.</span><span class="sxs-lookup"><span data-stu-id="8d83a-117">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="8d83a-118">Procedura: Generare automaticamente le colonne in un controllo DataGridView associato ai dati di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8d83a-118">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="8d83a-119">Viene descritto come generare automaticamente colonne basate su un'origine dati associata.</span><span class="sxs-lookup"><span data-stu-id="8d83a-119">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="8d83a-120">Procedura: Rimuovere le colonne generate automaticamente da un controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8d83a-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="8d83a-121">Viene descritto come nascondere o eliminare colonne generate automaticamente da un'origine dati associata.</span><span class="sxs-lookup"><span data-stu-id="8d83a-121">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="8d83a-122">Procedura: Modificare l'ordine delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8d83a-122">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8d83a-123">Viene descritto come ridisporre le colonne generate automaticamente da un'origine dati associata.</span><span class="sxs-lookup"><span data-stu-id="8d83a-123">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="8d83a-124">Procedura: Aggiungere una colonna non associata a un controllo DataGridView di Windows Form associato ai dati</span><span class="sxs-lookup"><span data-stu-id="8d83a-124">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="8d83a-125">Viene descritto come integrare i dati da un'origine dati associata visualizzando colonne aggiuntive non vincolate.</span><span class="sxs-lookup"><span data-stu-id="8d83a-125">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="8d83a-126">Procedura: Associare oggetti ai controlli DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8d83a-126">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="8d83a-127">Viene descritto come associare il controllo a una raccolta di oggetti arbitrari in modo che ogni oggetto venga visualizzato in una riga specifica.</span><span class="sxs-lookup"><span data-stu-id="8d83a-127">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="8d83a-128">Procedura: Accedere a oggetti associati a righe di DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8d83a-128">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="8d83a-129">Viene descritto come recuperare un oggetto associato a una riga specifica del controllo.</span><span class="sxs-lookup"><span data-stu-id="8d83a-129">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="8d83a-130">Procedura dettagliata: Creazione di un form Master-Details con due controlli DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8d83a-130">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="8d83a-131">Viene descritto come visualizzare i dati di due tabelle di database correlate in modo che i valori visualizzati in un `DataGridView` controllo dipendano dalla riga attualmente selezionata in un altro controllo.</span><span class="sxs-lookup"><span data-stu-id="8d83a-131">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="8d83a-132">Procedura: Formattare dati personalizzati in un controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8d83a-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8d83a-133">Viene descritto come gestire l'evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> per modificare l'aspetto delle celle a seconda dei rispettivi valori.</span><span class="sxs-lookup"><span data-stu-id="8d83a-133">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8d83a-134">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="8d83a-134">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="8d83a-135">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="8d83a-135">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="8d83a-136">Fornisce la documentazione di riferimento per la proprietà <xref:System.Windows.Forms.DataGridView.DataSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="8d83a-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="8d83a-137">Fornisce la documentazione di riferimento per il componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="8d83a-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8d83a-138">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="8d83a-138">Related Sections</span></span>  
 [<span data-ttu-id="8d83a-139">Immissione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8d83a-139">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8d83a-140">Fornisce argomenti che spiegano come cambiare la modalità di aggiunta e modifica dei dati nel controllo da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="8d83a-140">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d83a-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d83a-141">See also</span></span>

- [<span data-ttu-id="8d83a-142">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="8d83a-142">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="8d83a-143">Tipi di colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8d83a-143">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)

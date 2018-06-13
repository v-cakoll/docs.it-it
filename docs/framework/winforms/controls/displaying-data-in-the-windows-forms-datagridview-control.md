---
title: Visualizzazione di dati nel controllo DataGridView Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: 06df9bbcb1e8b1b53d061dbd219a25378a311072
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529428"
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="9fd3d-102">Visualizzazione di dati nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="9fd3d-102">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="9fd3d-103">Il `DataGridView` controllo viene utilizzato per visualizzare i dati da un'ampia gamma di origini dati esterne.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-103">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="9fd3d-104">In alternativa, è possibile aggiungere righe e colonne al controllo e popolare manualmente i dati.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-104">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="9fd3d-105">Quando si associa il controllo a un'origine dati, è possibile generare colonne automaticamente in base allo schema dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-105">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="9fd3d-106">Se tali colonne non sono visualizzate come desiderato, nascondere, rimuovere o ridisporre li.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-106">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="9fd3d-107">È anche possibile aggiungere colonne per visualizzare dati supplementari non provenienti dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-107">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="9fd3d-108">Inoltre, è possibile visualizzare i dati utilizzando i formati standard (ad esempio, il formato di valuta) oppure è possibile personalizzare il formato di visualizzazione per presentare i dati, tuttavia è necessario (ad esempio la modifica del colore di sfondo per i numeri negativi o sostituendo i valori stringa con immagini) corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-108">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9fd3d-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="9fd3d-109">In This Section</span></span>  
 [<span data-ttu-id="9fd3d-110">Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9fd3d-110">Data Display Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9fd3d-111">Vengono descritte le opzioni per popolare il controllo con i dati.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-111">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="9fd3d-112">Formattazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9fd3d-112">Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9fd3d-113">Vengono descritte le opzioni per la formattazione di valori visualizzati nelle celle.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-113">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="9fd3d-114">Procedura dettagliata: Creazione di un controllo DataGridView di Windows Form non associato</span><span class="sxs-lookup"><span data-stu-id="9fd3d-114">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9fd3d-115">Viene descritto come popolare manualmente i dati nel controllo.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-115">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="9fd3d-116">Procedura: Associare dati al controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9fd3d-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9fd3d-117">Viene descritto come popolare il controllo con dati associandolo a un `BindingSource` che contiene informazioni estratte da un database.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-117">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="9fd3d-118">Procedura: Generare automaticamente le colonne in un controllo DataGridView associato ai dati di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9fd3d-118">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="9fd3d-119">Viene descritto come generare automaticamente le colonne in base a un'origine dati associata.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-119">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="9fd3d-120">Procedura: Rimuovere le colonne generate automaticamente da un controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9fd3d-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="9fd3d-121">Viene descritto come nascondere o eliminare colonne generate automaticamente da un'origine dati associata.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-121">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="9fd3d-122">Procedura: Modificare l'ordine delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9fd3d-122">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9fd3d-123">Viene descritto come riorganizzare le colonne generate automaticamente da un'origine dati associata.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-123">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="9fd3d-124">Procedura: Aggiungere una colonna non associata a un controllo DataGridView di Windows Form associato ai dati</span><span class="sxs-lookup"><span data-stu-id="9fd3d-124">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="9fd3d-125">Viene descritto come integrare dati da un'origine dati associata visualizzando altre colonne non associate.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-125">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="9fd3d-126">Procedura: Associare oggetti ai controlli DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9fd3d-126">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="9fd3d-127">Viene descritto come associare il controllo a una raccolta di oggetti arbitrari in modo che ogni oggetto viene visualizzato nella propria riga.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-127">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="9fd3d-128">Procedura: Accedere a oggetti associati a righe di DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9fd3d-128">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](../../../../docs/framework/winforms/controls/how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="9fd3d-129">Viene descritto come recuperare un oggetto associato a una particolare riga del controllo.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-129">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="9fd3d-130">Procedura dettagliata: Creazione di un form Master-Details con due controlli DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9fd3d-130">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="9fd3d-131">Viene descritto come visualizzare i dati di due tabelle di database correlati in modo che i valori mostrati in uno `DataGridView` controllo dipendono la riga attualmente selezionata in un altro controllo.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-131">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="9fd3d-132">Procedura: Formattare dati personalizzati in un controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9fd3d-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9fd3d-133">Viene descritto come gestire il <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> evento per modificare l'aspetto delle celle in base ai relativi valori.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-133">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9fd3d-134">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="9fd3d-134">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="9fd3d-135">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-135">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="9fd3d-136">Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="9fd3d-137">Fornisce la documentazione di riferimento per il componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9fd3d-138">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="9fd3d-138">Related Sections</span></span>  
 [<span data-ttu-id="9fd3d-139">Immissione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9fd3d-139">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9fd3d-140">Fornisce argomenti che spiegano come cambiare la modalità di aggiunta e modifica dei dati nel controllo da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="9fd3d-140">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fd3d-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fd3d-141">See Also</span></span>  
 [<span data-ttu-id="9fd3d-142">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="9fd3d-142">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="9fd3d-143">Tipi di colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9fd3d-143">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)

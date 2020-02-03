---
title: Controllo DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- datasets [Windows Forms], user interface
- DataGrid control [Windows Forms]
- datasets [Windows Forms], displaying in DataGrid control
- displaying data [Windows Forms], on forms
- data [Windows Forms], displaying on Windows Forms
ms.assetid: 1d9d5683-43d2-42dd-b6c3-e43f4cf0de99
ms.openlocfilehash: efcc8770232f657c13135cefb4027f814d4d7d19
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742523"
---
# <a name="datagrid-control-windows-forms"></a><span data-ttu-id="0b11e-102">Controllo DataGrid (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="0b11e-102">DataGrid Control (Windows Forms)</span></span>
> [!NOTE]
> <span data-ttu-id="0b11e-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo `DataGrid` aggiungendovi funzionalità, il controllo `DataGrid` viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="0b11e-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the `DataGrid` control; however, the `DataGrid` control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="0b11e-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="0b11e-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="0b11e-105">Il controllo Windows Forms `DataGrid` fornisce un'interfaccia utente per ADO.NET i set di dati, visualizzando i dati tabulari e abilitando gli aggiornamenti all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0b11e-105">The Windows Forms `DataGrid` control provides a user interface to ADO.NET datasets, displaying tabular data and enabling updates to the data source.</span></span>  
  
 <span data-ttu-id="0b11e-106">Quando è impostato su un'origine dati valida, il controllo `DataGrid` viene popolato automaticamente, creando righe e colonne in base alla forma dei dati.</span><span class="sxs-lookup"><span data-stu-id="0b11e-106">When the `DataGrid` control is set to a valid data source, the control is automatically populated, creating columns and rows based on the shape of the data.</span></span> <span data-ttu-id="0b11e-107">Il controllo `DataGrid` può essere usato per visualizzare una singola tabella o le relazioni gerarchiche tra un set di tabelle.</span><span class="sxs-lookup"><span data-stu-id="0b11e-107">The `DataGrid` control can be used to display either a single table or the hierarchical relationships between a set of tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0b11e-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0b11e-108">In This Section</span></span>  
 [<span data-ttu-id="0b11e-109">Cenni preliminari sul controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="0b11e-109">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)  
 <span data-ttu-id="0b11e-110">Descrive le funzionalità di base del controllo `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="0b11e-110">Describes the basic features of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="0b11e-111">Procedura: Aggiungere tabelle e colonne nel controllo DataGrid Windows Form mediante la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="0b11e-111">How to: Add Tables and Columns to the Windows Forms DataGrid Control Using the Designer</span></span>](add-tables-and-columns-to-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="0b11e-112">Descrive come aggiungere tabelle e colonne nel controllo `DataGrid` usando la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="0b11e-112">Describes how to add tables and columns to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="0b11e-113">Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b11e-113">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="0b11e-114">Descrive come aggiungere tabelle e colonne nel controllo `DataGrid` a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="0b11e-114">Describes how to add tables and columns to the `DataGrid` control programmatically.</span></span>  
  
 [<span data-ttu-id="0b11e-115">Procedura: Associare il controllo DataGrid Windows Form a un'origine dati mediante la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="0b11e-115">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)  
 <span data-ttu-id="0b11e-116">Viene descritto come associare un set di dati ADO.NET al controllo `DataGrid` utilizzando la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="0b11e-116">Describes how to bind an ADO.NET dataset to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="0b11e-117">Procedura: Associare il controllo DataGrid Windows Form a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="0b11e-117">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 <span data-ttu-id="0b11e-118">Viene descritto come associare un set di dati ADO.NET al controllo `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="0b11e-118">Describes how to bind an ADO.NET dataset to the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="0b11e-119">Procedura: Modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b11e-119">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)  
 <span data-ttu-id="0b11e-120">Descrive come modificare i dati a livello di codice nel controllo `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="0b11e-120">Describes how to change data programmatically in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="0b11e-121">Procedura: Creare elenchi Master-Details mediante il controllo DataGrid Windows Form nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="0b11e-121">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>](create-master-details-lists-with-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="0b11e-122">Descrive come visualizzare due tabelle unite da una relazione padre/figlio, in due controlli `DataGrid` separati usando la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="0b11e-122">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls using the designer.</span></span>  
  
 <span data-ttu-id="0b11e-123">Procedura: Creare elenchi Master-Details con il controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b11e-123">How to: Create Master-Details Lists with the Windows Forms DataGrid Control</span></span>  
 <span data-ttu-id="0b11e-124">Descrive come visualizzare due tabelle unite da una relazione padre/figlio, in due controlli `DataGrid` separati.</span><span class="sxs-lookup"><span data-stu-id="0b11e-124">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls.</span></span>  
  
 [<span data-ttu-id="0b11e-125">Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b11e-125">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="0b11e-126">Descrivere come rimuovere colonne nel controllo `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="0b11e-126">Describes how to remove columns in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="0b11e-127">Procedura: Formattare il controllo DataGrid Windows Form mediante la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="0b11e-127">How to: Format the Windows Forms DataGrid Control Using the Designer</span></span>](how-to-format-the-windows-forms-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="0b11e-128">Descrive come modificare le proprietà correlate all'aspetto del controllo `DataGrid` usando la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="0b11e-128">Describes how to change the appearance-related properties of the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="0b11e-129">Procedura: Formattare il controllo DataGrid di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b11e-129">How to: Format the Windows Forms DataGrid Control</span></span>](how-to-format-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="0b11e-130">Descrive come modificare le proprietà correlate all'aspetto del controllo `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="0b11e-130">Describes how to change the appearance-related properties of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="0b11e-131">Tasti di scelta rapida per il controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b11e-131">Keyboard Shortcuts for the Windows Forms DataGrid Control</span></span>](keyboard-shortcuts-for-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="0b11e-132">Elenca i tasti di scelta rapida per spostarsi all'interno del controllo `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="0b11e-132">Lists shortcuts for navigating through the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="0b11e-133">Procedura: Rispondere alla selezione nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b11e-133">How to: Respond to Clicks in the Windows Forms DataGrid Control</span></span>](how-to-respond-to-clicks-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="0b11e-134">Descrive come determinare la cella il cui un utente ha fatto clic nel controllo `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="0b11e-134">Describes how to determine which cell a user has clicked in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="0b11e-135">Procedura: Convalidare l'input con il controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b11e-135">How to: Validate Input with the Windows Forms DataGrid Control</span></span>](how-to-validate-input-with-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="0b11e-136">Descrive come convalidare l'input nel set di dati associato al controllo `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="0b11e-136">Describes how to validate input in the dataset bound to the `DataGrid` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0b11e-137">Riferimento</span><span class="sxs-lookup"><span data-stu-id="0b11e-137">Reference</span></span>  
 <xref:System.Windows.Forms.DataGrid>  
 <span data-ttu-id="0b11e-138">Viene fornita una panoramica della classe <xref:System.Windows.Forms.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="0b11e-138">Provides an overview of the <xref:System.Windows.Forms.DataGrid> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGrid.DataSource%2A>  
 <span data-ttu-id="0b11e-139">Vengono fornite informazioni dettagliate sull'utilizzo di questa proprietà per associare il controllo <xref:System.Windows.Forms.DataGrid> ai dati.</span><span class="sxs-lookup"><span data-stu-id="0b11e-139">Provides details about using this property to bind the <xref:System.Windows.Forms.DataGrid> control to data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0b11e-140">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="0b11e-140">Related Sections</span></span>  
 [<span data-ttu-id="0b11e-141">Associazione ai dati di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b11e-141">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="0b11e-142">Collegamenti ad argomenti sul data binding in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="0b11e-142">Provides links to topics on data binding in Windows Forms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b11e-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b11e-143">See also</span></span>

- [<span data-ttu-id="0b11e-144">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="0b11e-144">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="0b11e-145">Differenze tra i controlli DataGridView e DataGrid di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b11e-145">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)

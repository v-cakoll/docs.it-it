---
title: Controllo DataGrid (Windows Form)
ms.date: 03/30/2017
helpviewer_keywords:
- datasets [Windows Forms], user interface
- DataGrid control [Windows Forms]
- datasets [Windows Forms], displaying in DataGrid control
- displaying data [Windows Forms], on forms
- data [Windows Forms], displaying on Windows Forms
ms.assetid: 1d9d5683-43d2-42dd-b6c3-e43f4cf0de99
ms.openlocfilehash: 60978fa952d76c5b64ffd82215eb9cda9013d285
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720839"
---
# <a name="datagrid-control-windows-forms"></a><span data-ttu-id="1e4b6-102">Controllo DataGrid (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="1e4b6-102">DataGrid Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="1e4b6-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo `DataGrid` aggiungendovi funzionalità, il controllo `DataGrid` viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the `DataGrid` control; however, the `DataGrid` control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="1e4b6-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="1e4b6-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="1e4b6-105">Il controllo `DataGrid` di Windows Form fornisce un'interfaccia utente per i set di dati [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], consentendo la visualizzazione dei dati in formato tabulare e abilitando gli aggiornamenti per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-105">The Windows Forms `DataGrid` control provides a user interface to [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] datasets, displaying tabular data and enabling updates to the data source.</span></span>  
  
 <span data-ttu-id="1e4b6-106">Quando è impostato su un'origine dati valida, il controllo `DataGrid` viene popolato automaticamente, creando righe e colonne in base alla forma dei dati.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-106">When the `DataGrid` control is set to a valid data source, the control is automatically populated, creating columns and rows based on the shape of the data.</span></span> <span data-ttu-id="1e4b6-107">Il controllo `DataGrid` può essere usato per visualizzare una singola tabella o le relazioni gerarchiche tra un set di tabelle.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-107">The `DataGrid` control can be used to display either a single table or the hierarchical relationships between a set of tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1e4b6-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="1e4b6-108">In This Section</span></span>  
 [<span data-ttu-id="1e4b6-109">Cenni preliminari sul controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="1e4b6-109">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)  
 <span data-ttu-id="1e4b6-110">Descrive le funzionalità di base del controllo `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-110">Describes the basic features of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="1e4b6-111">Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1e4b6-111">How to: Add Tables and Columns to the Windows Forms DataGrid Control Using the Designer</span></span>](add-tables-and-columns-to-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="1e4b6-112">Descrive come aggiungere tabelle e colonne nel controllo `DataGrid` usando la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-112">Describes how to add tables and columns to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="1e4b6-113">Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e4b6-113">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="1e4b6-114">Descrive come aggiungere tabelle e colonne nel controllo `DataGrid` a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-114">Describes how to add tables and columns to the `DataGrid` control programmatically.</span></span>  
  
 [<span data-ttu-id="1e4b6-115">Procedura: Associare il controllo DataGrid di Windows Form a un'origine dati tramite la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1e4b6-115">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)  
 <span data-ttu-id="1e4b6-116">Descrive come associare un set di dati [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] al controllo `DataGrid` usando la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-116">Describes how to bind an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] dataset to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="1e4b6-117">Procedura: Associare il controllo DataGrid di Windows Form a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="1e4b6-117">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 <span data-ttu-id="1e4b6-118">Descrive come associare un set di dati [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] al controllo `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-118">Describes how to bind an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] dataset to the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="1e4b6-119">Procedura: Modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e4b6-119">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)  
 <span data-ttu-id="1e4b6-120">Descrive come modificare i dati a livello di codice nel controllo `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-120">Describes how to change data programmatically in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="1e4b6-121">Procedura: Creare elenchi Master-Details con il controllo di controllo DataGrid Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1e4b6-121">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>](create-master-details-lists-with-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="1e4b6-122">Descrive come visualizzare due tabelle unite da una relazione padre/figlio, in due controlli `DataGrid` separati usando la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-122">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls using the designer.</span></span>  
  
 <span data-ttu-id="1e4b6-123">Procedura: Creare elenchi Master-Details con il controllo DataGrid di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e4b6-123">How to: Create Master-Details Lists with the Windows Forms DataGrid Control</span></span>  
 <span data-ttu-id="1e4b6-124">Descrive come visualizzare due tabelle unite da una relazione padre/figlio, in due controlli `DataGrid` separati.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-124">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls.</span></span>  
  
 [<span data-ttu-id="1e4b6-125">Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e4b6-125">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="1e4b6-126">Descrivere come rimuovere colonne nel controllo `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-126">Describes how to remove columns in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="1e4b6-127">Procedura: Formattare il controllo di DataGrid Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1e4b6-127">How to: Format the Windows Forms DataGrid Control Using the Designer</span></span>](how-to-format-the-windows-forms-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="1e4b6-128">Descrive come modificare le proprietà correlate all'aspetto del controllo `DataGrid` usando la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-128">Describes how to change the appearance-related properties of the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="1e4b6-129">Procedura: Formattare il controllo DataGrid di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e4b6-129">How to: Format the Windows Forms DataGrid Control</span></span>](how-to-format-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="1e4b6-130">Descrive come modificare le proprietà correlate all'aspetto del controllo `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-130">Describes how to change the appearance-related properties of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="1e4b6-131">Tasti di scelta rapida per il controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e4b6-131">Keyboard Shortcuts for the Windows Forms DataGrid Control</span></span>](keyboard-shortcuts-for-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="1e4b6-132">Elenca i tasti di scelta rapida per spostarsi all'interno del controllo `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-132">Lists shortcuts for navigating through the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="1e4b6-133">Procedura: Rispondere alla selezione nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e4b6-133">How to: Respond to Clicks in the Windows Forms DataGrid Control</span></span>](how-to-respond-to-clicks-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="1e4b6-134">Descrive come determinare la cella il cui un utente ha fatto clic nel controllo `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-134">Describes how to determine which cell a user has clicked in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="1e4b6-135">Procedura: Convalidare l'Input con il controllo DataGrid di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e4b6-135">How to: Validate Input with the Windows Forms DataGrid Control</span></span>](how-to-validate-input-with-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="1e4b6-136">Descrive come convalidare l'input nel set di dati associato al controllo `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-136">Describes how to validate input in the dataset bound to the `DataGrid` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1e4b6-137">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="1e4b6-137">Reference</span></span>  
 <xref:System.Windows.Forms.DataGrid>  
 <span data-ttu-id="1e4b6-138">Viene fornita una panoramica di <xref:System.Windows.Forms.DataGrid> classe.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-138">Provides an overview of the <xref:System.Windows.Forms.DataGrid> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGrid.DataSource%2A>  
 <span data-ttu-id="1e4b6-139">Vengono fornite informazioni dettagliate sull'uso di questa proprietà per associare il <xref:System.Windows.Forms.DataGrid> controllo ai dati.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-139">Provides details about using this property to bind the <xref:System.Windows.Forms.DataGrid> control to data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1e4b6-140">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="1e4b6-140">Related Sections</span></span>  
 [<span data-ttu-id="1e4b6-141">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e4b6-141">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="1e4b6-142">Collegamenti ad argomenti sul data binding in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="1e4b6-142">Provides links to topics on data binding in Windows Forms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e4b6-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e4b6-143">See also</span></span>
- [<span data-ttu-id="1e4b6-144">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="1e4b6-144">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="1e4b6-145">Differenze tra i controlli DataGridView e DataGrid di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e4b6-145">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)

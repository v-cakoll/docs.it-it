---
title: 'Procedura: creare una tabella di ricerca per un controllo ComboBox, ListBox o CheckedListBox Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 93f49a8fbd2cc8ffae94e4dcbbc4babf7c1137cd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="0c8a3-102">Procedura: creare una tabella di ricerca per un controllo ComboBox, ListBox o CheckedListBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="0c8a3-102">How to: Create a Lookup Table for a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="0c8a3-103">Può risultare utile visualizzare i dati all'interno di un Windows Form in un formato facilmente riconoscibile dall'utente, ma memorizzare gli stessi dati in un formato che consenta una migliore gestione da parte del programma.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-103">Sometimes it is useful to display data in a user-friendly format on a Windows Form, but store the data in a format that is more meaningful to your program.</span></span> <span data-ttu-id="0c8a3-104">Ad esempio un form di ordinazione per generi alimentari può visualizzare le voci di menu ordinate in base al nome in una casella di riepilogo,</span><span class="sxs-lookup"><span data-stu-id="0c8a3-104">For example, an order form for food might display the menu items by name in a list box.</span></span> <span data-ttu-id="0c8a3-105">mentre la tabella dati per la registrazione dell'ordine può contenere i numeri univoci di identificazione corrispondenti a ogni piatto.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-105">However, the data table recording the order would contain the unique ID numbers representing the food.</span></span> <span data-ttu-id="0c8a3-106">Nelle tabelle seguenti viene mostrato un esempio di memorizzazione e visualizzazione dei dati contenuti in un form di ordinazione per generi alimentari.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-106">The following tables show an example of how to store and display order-form data for food.</span></span>  
  
### <a name="orderdetailstable"></a><span data-ttu-id="0c8a3-107">OrderDetailsTable</span><span class="sxs-lookup"><span data-stu-id="0c8a3-107">OrderDetailsTable</span></span>  
  
|<span data-ttu-id="0c8a3-108">OrderID</span><span class="sxs-lookup"><span data-stu-id="0c8a3-108">OrderID</span></span>|<span data-ttu-id="0c8a3-109">ItemID</span><span class="sxs-lookup"><span data-stu-id="0c8a3-109">ItemID</span></span>|<span data-ttu-id="0c8a3-110">Quantità</span><span class="sxs-lookup"><span data-stu-id="0c8a3-110">Quantity</span></span>|  
|-------------|------------|--------------|  
|<span data-ttu-id="0c8a3-111">4085</span><span class="sxs-lookup"><span data-stu-id="0c8a3-111">4085</span></span>|<span data-ttu-id="0c8a3-112">12</span><span class="sxs-lookup"><span data-stu-id="0c8a3-112">12</span></span>|<span data-ttu-id="0c8a3-113">1</span><span class="sxs-lookup"><span data-stu-id="0c8a3-113">1</span></span>|  
|<span data-ttu-id="0c8a3-114">4086</span><span class="sxs-lookup"><span data-stu-id="0c8a3-114">4086</span></span>|<span data-ttu-id="0c8a3-115">13</span><span class="sxs-lookup"><span data-stu-id="0c8a3-115">13</span></span>|<span data-ttu-id="0c8a3-116">3</span><span class="sxs-lookup"><span data-stu-id="0c8a3-116">3</span></span>|  
  
### <a name="itemtable"></a><span data-ttu-id="0c8a3-117">ItemTable</span><span class="sxs-lookup"><span data-stu-id="0c8a3-117">ItemTable</span></span>  
  
|<span data-ttu-id="0c8a3-118">Id</span><span class="sxs-lookup"><span data-stu-id="0c8a3-118">ID</span></span>|<span data-ttu-id="0c8a3-119">nome</span><span class="sxs-lookup"><span data-stu-id="0c8a3-119">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="0c8a3-120">12</span><span class="sxs-lookup"><span data-stu-id="0c8a3-120">12</span></span>|<span data-ttu-id="0c8a3-121">Patate</span><span class="sxs-lookup"><span data-stu-id="0c8a3-121">Potato</span></span>|  
|<span data-ttu-id="0c8a3-122">13</span><span class="sxs-lookup"><span data-stu-id="0c8a3-122">13</span></span>|<span data-ttu-id="0c8a3-123">Pollo</span><span class="sxs-lookup"><span data-stu-id="0c8a3-123">Chicken</span></span>|  
  
 <span data-ttu-id="0c8a3-124">In questo scenario, una tabella, **OrderDetailsTable**, archivia le informazioni relative alla visualizzazione e salvataggio.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-124">In this scenario, one table, **OrderDetailsTable**, stores the actual information you are concerned with displaying and saving.</span></span> <span data-ttu-id="0c8a3-125">Per risparmiare spazio, però, la memorizzazione avviene in modo piuttosto criptico.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-125">But to save space, it does so in a fairly cryptic fashion.</span></span> <span data-ttu-id="0c8a3-126">L'altra tabella, **ItemTable**, contiene solo le informazioni correlate all'aspetto ID è equivalente a ogni piatto e niente in merito a ordinazioni numero.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-126">The other table, **ItemTable**, contains only appearance-related information about which ID number is equivalent to which food name, and nothing about the actual food orders.</span></span>  
  
 <span data-ttu-id="0c8a3-127">Il **ItemTable** è connesso il <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, o <xref:System.Windows.Forms.CheckedListBox> attraverso tre proprietà.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-127">The **ItemTable** is connected to the <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control through three properties.</span></span> <span data-ttu-id="0c8a3-128">Il `DataSource` proprietà contiene il nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-128">The `DataSource` property contains the name of this table.</span></span> <span data-ttu-id="0c8a3-129">Il `DisplayMember` proprietà contiene la colonna di dati della tabella che si desidera visualizzare nel controllo (il nome di cibo).</span><span class="sxs-lookup"><span data-stu-id="0c8a3-129">The `DisplayMember` property contains the data column of that table that you want to display in the control (the food name).</span></span> <span data-ttu-id="0c8a3-130">Il `ValueMember` proprietà contiene la colonna di dati della tabella con le informazioni memorizzate (il numero ID).</span><span class="sxs-lookup"><span data-stu-id="0c8a3-130">The `ValueMember` property contains the data column of that table with the stored information (the ID number).</span></span>  
  
 <span data-ttu-id="0c8a3-131">Il **OrderDetailsTable** è collegata al controllo con il suo insieme di associazioni, accessibile tramite la <xref:System.Windows.Forms.Control.DataBindings%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-131">The **OrderDetailsTable** is connected to the control by its bindings collection, accessed through the <xref:System.Windows.Forms.Control.DataBindings%2A> property.</span></span> <span data-ttu-id="0c8a3-132">Quando si aggiunge un oggetto di associazione alla raccolta, connettersi a una proprietà del controllo a un membro dati specifico (la colonna dei numeri ID) in un'origine dati (il **OrderDetailsTable**).</span><span class="sxs-lookup"><span data-stu-id="0c8a3-132">When you add a binding object to the collection, you connect a control property to a specific data member (the column of ID numbers) in a data source (the **OrderDetailsTable**).</span></span> <span data-ttu-id="0c8a3-133">Quando nel controllo viene effettuata una selezione, l'input del form viene salvato in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-133">When a selection is made in the control, this table is where the form input is saved.</span></span>  
  
### <a name="to-create-a-lookup-table"></a><span data-ttu-id="0c8a3-134">Per creare una tabella di ricerca</span><span class="sxs-lookup"><span data-stu-id="0c8a3-134">To create a lookup table</span></span>  
  
1.  <span data-ttu-id="0c8a3-135">Aggiungere un controllo <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> o <xref:System.Windows.Forms.CheckedListBox> al form.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-135">Add a <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control to the form.</span></span>  
  
2.  <span data-ttu-id="0c8a3-136">Effettuare la connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-136">Connect to your data source.</span></span>  
  
3.  <span data-ttu-id="0c8a3-137">Stabilire una relazione dati tra le due tabelle.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-137">Establish a data relation between the two tables.</span></span> <span data-ttu-id="0c8a3-138">Vedere [Introduzione agli oggetti DataRelation](http://msdn.microsoft.com/library/89d8a881-8265-41f2-a88b-61311ab06192).</span><span class="sxs-lookup"><span data-stu-id="0c8a3-138">See [Introduction to DataRelation Objects](http://msdn.microsoft.com/library/89d8a881-8265-41f2-a88b-61311ab06192).</span></span>  
  
4.  <span data-ttu-id="0c8a3-139">Impostare le proprietà seguenti,</span><span class="sxs-lookup"><span data-stu-id="0c8a3-139">Set the following properties.</span></span> <span data-ttu-id="0c8a3-140">nel codice o nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-140">They can be set in code or in the designer.</span></span>  
  
    |<span data-ttu-id="0c8a3-141">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0c8a3-141">Property</span></span>|<span data-ttu-id="0c8a3-142">Impostazione</span><span class="sxs-lookup"><span data-stu-id="0c8a3-142">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|<span data-ttu-id="0c8a3-143">Nella tabella sono contenute le informazioni relative ai numeri ID equivalenti alle diverse voci.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-143">The table that contains information about which ID number is equivalent to which item.</span></span> <span data-ttu-id="0c8a3-144">Nello scenario precedente, si tratta di `ItemTable`.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-144">In the previous scenario, this is `ItemTable`.</span></span>|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|<span data-ttu-id="0c8a3-145">La colonna della tabella dell'origine dati che si vuole visualizzare nel controllo.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-145">The column of the data source table that you want to display in the control.</span></span> <span data-ttu-id="0c8a3-146">Nello scenario precedente, si tratta di `"Name"` (per impostare nel codice, utilizzare le virgolette).</span><span class="sxs-lookup"><span data-stu-id="0c8a3-146">In the previous scenario, this is `"Name"` (to set in code, use quotation marks).</span></span>|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|<span data-ttu-id="0c8a3-147">La colonna della tabella di origine dati che contiene le informazioni memorizzate.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-147">The column of the data source table that contains the stored information.</span></span> <span data-ttu-id="0c8a3-148">Nello scenario precedente, si tratta di `"ID"` (per impostare nel codice, utilizzare le virgolette).</span><span class="sxs-lookup"><span data-stu-id="0c8a3-148">In the previous scenario, this is `"ID"` (to set in code, use quotation marks).</span></span>|  
  
5.  <span data-ttu-id="0c8a3-149">In una routine, chiamare il metodo <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> della classe <xref:System.Windows.Forms.ControlBindingsCollection> per associare la proprietà <xref:System.Windows.Forms.ListControl.SelectedValue%2A> del controllo alla tabella che registra l'input del form.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-149">In a procedure, call the <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> method of the <xref:System.Windows.Forms.ControlBindingsCollection> class to bind the control's <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property to the table recording the form input.</span></span> <span data-ttu-id="0c8a3-150">Per effettuare questa operazione nella finestra di progettazione anziché nel codice, accedendo del controllo <xref:System.Windows.Forms.Control.DataBindings%2A> proprietà il **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-150">You can also do this in the Designer instead of in code, by accessing the control's <xref:System.Windows.Forms.Control.DataBindings%2A> property in the **Properties** window.</span></span> <span data-ttu-id="0c8a3-151">Nello scenario precedente, si tratta di `OrderDetailsTable`, e la colonna è `"ItemID"`.</span><span class="sxs-lookup"><span data-stu-id="0c8a3-151">In the previous scenario, this is `OrderDetailsTable`, and the column is `"ItemID"`.</span></span>  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0c8a3-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c8a3-152">See Also</span></span>  
 [<span data-ttu-id="0c8a3-153">Data binding e Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0c8a3-153">Data Binding and Windows Forms</span></span>](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [<span data-ttu-id="0c8a3-154">Panoramica sul controllo ListBox</span><span class="sxs-lookup"><span data-stu-id="0c8a3-154">ListBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="0c8a3-155">Panoramica sul controllo ComboBox</span><span class="sxs-lookup"><span data-stu-id="0c8a3-155">ComboBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)  
 [<span data-ttu-id="0c8a3-156">Panoramica sul controllo CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="0c8a3-156">CheckedListBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="0c8a3-157">Controlli Windows Form usati per elencare opzioni</span><span class="sxs-lookup"><span data-stu-id="0c8a3-157">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)

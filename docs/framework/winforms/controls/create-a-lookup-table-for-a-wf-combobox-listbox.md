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
ms.openlocfilehash: cb7ffb8a7f20c1e53b24a1db8bda326d73743a93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Procedura: creare una tabella di ricerca per un controllo ComboBox, ListBox o CheckedListBox Windows Form
Può risultare utile visualizzare i dati all'interno di un Windows Form in un formato facilmente riconoscibile dall'utente, ma memorizzare gli stessi dati in un formato che consenta una migliore gestione da parte del programma. Ad esempio un form di ordinazione per generi alimentari può visualizzare le voci di menu ordinate in base al nome in una casella di riepilogo, mentre la tabella dati per la registrazione dell'ordine può contenere i numeri univoci di identificazione corrispondenti a ogni piatto. Nelle tabelle seguenti viene mostrato un esempio di memorizzazione e visualizzazione dei dati contenuti in un form di ordinazione per generi alimentari.  
  
### <a name="orderdetailstable"></a>OrderDetailsTable  
  
|OrderID|ItemID|Quantità|  
|-------------|------------|--------------|  
|4085|12|1|  
|4086|13|3|  
  
### <a name="itemtable"></a>ItemTable  
  
|ID|Nome|  
|--------|----------|  
|12|Patate|  
|13|Pollo|  
  
 In questo scenario, una tabella, **OrderDetailsTable**, archivia le informazioni relative alla visualizzazione e salvataggio. Per risparmiare spazio, però, la memorizzazione avviene in modo piuttosto criptico. L'altra tabella, **ItemTable**, contiene solo le informazioni correlate all'aspetto ID è equivalente a ogni piatto e niente in merito a ordinazioni numero.  
  
 Il **ItemTable** è connesso il <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, o <xref:System.Windows.Forms.CheckedListBox> attraverso tre proprietà. Il `DataSource` proprietà contiene il nome della tabella. Il `DisplayMember` proprietà contiene la colonna di dati della tabella che si desidera visualizzare nel controllo (il nome di cibo). Il `ValueMember` proprietà contiene la colonna di dati della tabella con le informazioni memorizzate (il numero ID).  
  
 Il **OrderDetailsTable** è collegata al controllo con il suo insieme di associazioni, accessibile tramite la <xref:System.Windows.Forms.Control.DataBindings%2A> proprietà. Quando si aggiunge un oggetto di associazione alla raccolta, connettersi a una proprietà del controllo a un membro dati specifico (la colonna dei numeri ID) in un'origine dati (il **OrderDetailsTable**). Quando nel controllo viene effettuata una selezione, l'input del form viene salvato in questa tabella.  
  
### <a name="to-create-a-lookup-table"></a>Per creare una tabella di ricerca  
  
1.  Aggiungere un controllo <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> o <xref:System.Windows.Forms.CheckedListBox> al form.  
  
2.  Effettuare la connessione all'origine dati.  
  
3.  Stabilire una relazione dati tra le due tabelle. Vedere [Introduzione agli oggetti DataRelation](http://msdn.microsoft.com/library/89d8a881-8265-41f2-a88b-61311ab06192).  
  
4.  Impostare le proprietà seguenti, nel codice o nella finestra di progettazione.  
  
    |Proprietà|Impostazione|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|Nella tabella sono contenute le informazioni relative ai numeri ID equivalenti alle diverse voci. Nello scenario precedente, si tratta di `ItemTable`.|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|La colonna della tabella dell'origine dati che si vuole visualizzare nel controllo. Nello scenario precedente, si tratta di `"Name"` (per impostare nel codice, utilizzare le virgolette).|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|La colonna della tabella di origine dati che contiene le informazioni memorizzate. Nello scenario precedente, si tratta di `"ID"` (per impostare nel codice, utilizzare le virgolette).|  
  
5.  In una routine, chiamare il metodo <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> della classe <xref:System.Windows.Forms.ControlBindingsCollection> per associare la proprietà <xref:System.Windows.Forms.ListControl.SelectedValue%2A> del controllo alla tabella che registra l'input del form. Per effettuare questa operazione nella finestra di progettazione anziché nel codice, accedendo del controllo <xref:System.Windows.Forms.Control.DataBindings%2A> proprietà il **proprietà** finestra. Nello scenario precedente, si tratta di `OrderDetailsTable`, e la colonna è `"ItemID"`.  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Data binding e Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Panoramica sul controllo ListBox](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)  
 [Panoramica sul controllo ComboBox](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)  
 [Panoramica sul controllo CheckedListBox](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)  
 [Controlli Windows Form usati per elencare opzioni](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)

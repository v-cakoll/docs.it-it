---
title: 'Procedura: Creare una tabella di ricerca per un Windows Form ComboBox, ListBox o CheckedListBox (controllo)'
ms.date: 03/30/2017
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
ms.openlocfilehash: 5f1a2b220c3fb5d348f8aa45fbf07140844c9adf
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "56441621"
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Procedura: Creare una tabella di ricerca per un Windows Form ComboBox, ListBox o CheckedListBox (controllo)
Può risultare utile visualizzare i dati all'interno di un Windows Form in un formato facilmente riconoscibile dall'utente, ma memorizzare gli stessi dati in un formato che consenta una migliore gestione da parte del programma. Ad esempio un form di ordinazione per generi alimentari può visualizzare le voci di menu ordinate in base al nome in una casella di riepilogo, mentre la tabella dati per la registrazione dell'ordine può contenere i numeri univoci di identificazione corrispondenti a ogni piatto. Nelle tabelle seguenti viene mostrato un esempio di memorizzazione e visualizzazione dei dati contenuti in un form di ordinazione per generi alimentari.  
  
### <a name="orderdetailstable"></a>OrderDetailsTable  
  
|OrderID|ItemID|Quantità|  
|-------------|------------|--------------|  
|4085|12|1|  
|4086|13|3|  
  
### <a name="itemtable"></a>ItemTable  
  
|Id|nome|  
|--------|----------|  
|12|Patate|  
|13|Pollo|  
  
 In questo scenario, una tabella, **OrderDetailsTable**, archivia le informazioni effettive si è preoccupati di visualizzazione e il salvataggio. Per risparmiare spazio, però, la memorizzazione avviene in modo piuttosto criptico. L'altra tabella, **ItemTable**, contiene solo le informazioni correlate all'aspetto su cui ID è equivalente a quale nome di cibo e niente in merito a ordinazioni numero.  
  
 Il **ItemTable** è connessa il <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, o <xref:System.Windows.Forms.CheckedListBox> attraverso tre proprietà. Il `DataSource` proprietà contiene il nome di questa tabella. Il `DisplayMember` proprietà contiene la colonna di dati della tabella che si desidera visualizzare nel controllo (il nome di cibo). Il `ValueMember` proprietà contiene la colonna di dati della tabella con le informazioni archiviate (numero ID).  
  
 Il **OrderDetailsTable** è collegata al controllo tramite il suo insieme di associazioni, accessibile tramite il <xref:System.Windows.Forms.Control.DataBindings%2A> proprietà. Quando si aggiunge un oggetto di associazione alla raccolta, una proprietà del controllo è connettersi a un membro dati specifico (la colonna dei numeri ID) in un'origine dati (il **OrderDetailsTable**). Quando nel controllo viene effettuata una selezione, l'input del form viene salvato in questa tabella.  
  
### <a name="to-create-a-lookup-table"></a>Per creare una tabella di ricerca  
  
1.  Aggiungere un controllo <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> o <xref:System.Windows.Forms.CheckedListBox> al form.  
  
2.  Effettuare la connessione all'origine dati.  
  
3.  Stabilire una relazione dati tra le due tabelle. Visualizzare [Introduzione agli oggetti DataRelation](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).  
  
4.  Impostare le proprietà seguenti, nel codice o nella finestra di progettazione.  
  
    |Proprietà|Impostazione|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|Nella tabella sono contenute le informazioni relative ai numeri ID equivalenti alle diverse voci. Nello scenario precedente, si tratta `ItemTable`.|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|La colonna della tabella dell'origine dati che si vuole visualizzare nel controllo. Nello scenario precedente, si tratta `"Name"` (per impostare nel codice, utilizzare le virgolette).|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|La colonna della tabella di origine dati che contiene le informazioni memorizzate. Nello scenario precedente, si tratta `"ID"` (per impostare nel codice, utilizzare le virgolette).|  
  
5.  In una routine, chiamare il metodo <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> della classe <xref:System.Windows.Forms.ControlBindingsCollection> per associare la proprietà <xref:System.Windows.Forms.ListControl.SelectedValue%2A> del controllo alla tabella che registra l'input del form. È effettuare questa operazione nella finestra di progettazione anziché nel codice, tramite l'accesso del controllo <xref:System.Windows.Forms.Control.DataBindings%2A> nelle proprietà di **proprietà** finestra. Nello scenario precedente, si tratta `OrderDetailsTable`, e la colonna è `"ItemID"`.  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a>Vedere anche
- [Data binding e Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)
- [Panoramica sul controllo ListBox](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)
- [Panoramica sul controllo ComboBox](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)
- [Panoramica sul controllo CheckedListBox](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)
- [Controlli Windows Form usati per elencare opzioni](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)

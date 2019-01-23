---
title: Cenni preliminari sul controllo ComboBox (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- ComboBox
helpviewer_keywords:
- drop-down lists [Windows Forms], Windows Forms
- ComboBox control [Windows Forms], about ComboBox control
- drop-down lists [Windows Forms], ComboBox control
- combo boxes [Windows Forms], about combo boxes
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
ms.openlocfilehash: 1c58249df67efe5e782776d4996adef567f71a15
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492209"
---
# <a name="combobox-control-overview-windows-forms"></a>Cenni preliminari sul controllo ComboBox (Windows Form)
I moduli di Windows <xref:System.Windows.Forms.ComboBox> controllo viene usato per visualizzare i dati in una casella combinata a discesa. Per impostazione predefinita, il <xref:System.Windows.Forms.ComboBox> controllo viene visualizzato in due parti: la parte superiore è una casella di testo che consente all'utente di digitare una voce di elenco. La seconda parte è una casella di riepilogo che visualizza un elenco di elementi da cui l'utente può selezionare uno. Per altre informazioni sugli altri stili di casella combinata, vedere [quando utilizzare un Windows Form casella combinata anziché un controllo ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md).  
  
 Il <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> proprietà restituisce un valore intero che corrisponde all'elemento di elenco selezionato. È possibile modificare l'elemento selezionato a livello di programmazione cambiando le <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valore nel codice; l'elemento corrispondente nell'elenco verrà visualizzati nella casella di testo della casella combinata. Se è selezionato alcun elemento, il <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valore è -1. Se è selezionato il primo elemento nell'elenco, quindi il <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valore è 0. Il <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> proprietà è simile a <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> , ma restituisce l'elemento stesso, in genere un valore di stringa. Il <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> proprietà riflette il numero di elementi nell'elenco e il valore della <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> proprietà è sempre uno, più il più grande possibile <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valore perché <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> è in base zero.  
  
 Per aggiungere o eliminare elementi in un <xref:System.Windows.Forms.ComboBox> controllo, utilizzare il <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> o <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A> (metodo). In alternativa, è possibile aggiungere elementi all'elenco utilizzando il <xref:System.Windows.Forms.ComboBox.Items%2A> proprietà nella finestra di progettazione.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.ComboBox>
- [Panoramica sul controllo ListBox](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)
- [Quando usare un controllo ComboBox Windows Form anziché un controllo ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Procedura: Aggiungere e rimuovere elementi da un Windows Form ComboBox, ListBox o CheckedListBox (controllo)](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)
- [Procedura: Ordinare il contenuto di un Windows Form ComboBox, ListBox o CheckedListBox (controllo)](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Procedura: Accedere a specifici elementi in un Windows Form ComboBox, ListBox o CheckedListBox (controllo)](../../../../docs/framework/winforms/controls/access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)
- [Procedura: Associare un Windows Form controllo ComboBox o ListBox ai dati](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [Controlli Windows Form usati per elencare opzioni](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
- [Procedura: Creare una tabella di ricerca per un Windows Form ComboBox, ListBox o CheckedListBox (controllo)](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)

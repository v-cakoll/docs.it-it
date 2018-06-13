---
title: Cenni preliminari sul controllo ListBox (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
ms.openlocfilehash: d4cb423a6f32778695abeae725da9755b610d209
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537564"
---
# <a name="listbox-control-overview-windows-forms"></a>Cenni preliminari sul controllo ListBox (Windows Form)
Un Windows Form <xref:System.Windows.Forms.ListBox> controllo Visualizza un elenco da cui l'utente può selezionare uno o più elementi. Se il numero totale di elementi supera il numero che può essere visualizzato, una barra di scorrimento viene aggiunta automaticamente per il <xref:System.Windows.Forms.ListBox> controllo. Quando il <xref:System.Windows.Forms.ListBox.MultiColumn%2A> è impostata su `true`, la casella di riepilogo vengono visualizzati elementi in più colonne e viene visualizzata una barra di scorrimento orizzontale. Quando il <xref:System.Windows.Forms.ListBox.MultiColumn%2A> è impostata su `false`, la casella di riepilogo vengono visualizzati elementi in una singola colonna e viene visualizzata una barra di scorrimento verticale. Quando <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> è impostato su `true`, viene visualizzata la barra di scorrimento indipendentemente dal numero di elementi. Il <xref:System.Windows.Forms.ListBox.SelectionMode%2A> proprietà determina il numero di elementi di elenco può essere selezionato contemporaneamente.  
  
## <a name="ways-to-change-the-listbox-control"></a>Modalità di modifica del controllo ListBox  
 Il <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> proprietà restituisce un valore intero che corrisponde al primo elemento selezionato nella casella di riepilogo. A livello di codice, è possibile modificare l'elemento selezionato modificando il <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> valore nel codice; l'elemento corrispondente nell'elenco vengono evidenziato in Windows Form. Se è selezionato alcun elemento, il <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> valore è -1. Se è selezionato il primo elemento nell'elenco, il <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> valore è 0. Quando sono selezionati più elementi, il <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> valore riflette l'elemento selezionato viene visualizzata per prima nell'elenco. Il <xref:System.Windows.Forms.ListBox.SelectedItem%2A> proprietà è simile a <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, ma restituisce l'elemento stesso, in genere un valore di stringa. Il <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> proprietà riflette il numero di elementi nell'elenco e il valore di <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> proprietà supera sempre uno più grande possibile <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> valore perché <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> è in base zero.  
  
 Per aggiungere o eliminare elementi in un <xref:System.Windows.Forms.ListBox> controllo, utilizzare il <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> o <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A> metodo. In alternativa, è possibile aggiungere elementi all'elenco utilizzando il <xref:System.Windows.Forms.ListBox.Items%2A> proprietà in fase di progettazione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ListBox>  
 [Procedura: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox di Windows Form](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [Procedura: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox di Windows Form](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [Procedura: Associare a dati un controllo ComboBox o ListBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 [Panoramica sul controllo ComboBox](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)  
 [Panoramica sul controllo CheckedListBox](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)  
 [Controlli Windows Form usati per elencare opzioni](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)  
 [Procedura: Creare una tabella di ricerca per un controllo ComboBox, ListBox o CheckedListBox di Windows Form](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)

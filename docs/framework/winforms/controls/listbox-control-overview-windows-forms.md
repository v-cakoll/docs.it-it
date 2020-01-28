---
title: Cenni preliminari sul controllo ListBox
ms.date: 03/30/2017
f1_keywords:
- ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
ms.openlocfilehash: 1abf8bea5c786f2ce326631370fa294ada09a92c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745188"
---
# <a name="listbox-control-overview-windows-forms"></a>Cenni preliminari sul controllo ListBox (Windows Form)
Un controllo Windows Forms <xref:System.Windows.Forms.ListBox> Visualizza un elenco da cui l'utente può selezionare uno o più elementi. Se il numero totale di elementi supera il numero che può essere visualizzato, una barra di scorrimento viene aggiunta automaticamente al controllo <xref:System.Windows.Forms.ListBox>. Quando la proprietà <xref:System.Windows.Forms.ListBox.MultiColumn%2A> è impostata su `true`, nella casella di riepilogo vengono visualizzati gli elementi in più colonne e viene visualizzata una barra di scorrimento orizzontale. Quando la proprietà <xref:System.Windows.Forms.ListBox.MultiColumn%2A> è impostata su `false`, nella casella di riepilogo vengono visualizzati gli elementi in una singola colonna e viene visualizzata una barra di scorrimento verticale. Quando <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> è impostato su `true`, la barra di scorrimento viene visualizzata indipendentemente dal numero di elementi. La proprietà <xref:System.Windows.Forms.ListBox.SelectionMode%2A> determina il numero di elementi dell'elenco che è possibile selezionare alla volta.  
  
## <a name="ways-to-change-the-listbox-control"></a>Modalità di modifica del controllo ListBox  
 La proprietà <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> restituisce un valore integer che corrisponde al primo elemento selezionato nella casella di riepilogo. È possibile modificare a livello di codice l'elemento selezionato modificando il valore <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> nel codice; l'elemento corrispondente nell'elenco verrà visualizzato evidenziato nel Windows Form. Se non è selezionato alcun elemento, il valore <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> è-1. Se il primo elemento dell'elenco è selezionato, il valore <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> è 0. Quando vengono selezionati più elementi, il valore <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> riflette l'elemento selezionato visualizzato per primo nell'elenco. La proprietà <xref:System.Windows.Forms.ListBox.SelectedItem%2A> è simile a <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, ma restituisce l'elemento stesso, in genere un valore stringa. La proprietà <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> riflette il numero di elementi nell'elenco e il valore della proprietà <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> è sempre maggiore del valore massimo possibile <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> perché <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> è in base zero.  
  
 Per aggiungere o eliminare elementi in un controllo <xref:System.Windows.Forms.ListBox>, utilizzare il metodo <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> o <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A>. In alternativa, è possibile aggiungere elementi all'elenco utilizzando la proprietà <xref:System.Windows.Forms.ListBox.Items%2A> in fase di progettazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListBox>
- [Procedura: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox di Windows Form](add-and-remove-items-from-a-wf-combobox.md)
- [Procedura: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox di Windows Form](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Procedura: Associare a dati un controllo ComboBox o ListBox di Windows Form](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [Panoramica sul controllo ComboBox](combobox-control-overview-windows-forms.md)
- [Panoramica sul controllo CheckedListBox](checkedlistbox-control-overview-windows-forms.md)
- [Controlli Windows Form usati per elencare opzioni](windows-forms-controls-used-to-list-options.md)
- [Procedura: Creare una tabella di ricerca per un controllo ComboBox, ListBox o CheckedListBox di Windows Form](create-a-lookup-table-for-a-wf-combobox-listbox.md)

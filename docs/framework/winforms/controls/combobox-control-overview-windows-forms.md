---
title: Cenni preliminari sul controllo ComboBox (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ComboBox
helpviewer_keywords:
- drop-down lists [Windows Forms], Windows Forms
- ComboBox control [Windows Forms], about ComboBox control
- drop-down lists [Windows Forms], ComboBox control
- combo boxes [Windows Forms], about combo boxes
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 801ebb97c6ee52ce52bbb8f96a07d55e68ca6f1d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="combobox-control-overview-windows-forms"></a>Cenni preliminari sul controllo ComboBox (Windows Form)
Windows Form <xref:System.Windows.Forms.ComboBox> controllo viene utilizzato per visualizzare i dati in una casella combinata a discesa. Per impostazione predefinita, il <xref:System.Windows.Forms.ComboBox> verrà visualizzato un controllo in due parti: la parte superiore è una casella di testo che consente all'utente di digitare una voce di elenco. La seconda parte è una casella di riepilogo che consente di visualizzare un elenco di elementi da cui l'utente può selezionare uno. Per ulteriori informazioni sugli altri stili casella combinata, vedere [quando utilizzare un Windows Form ComboBox anziché un controllo ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md).  
  
 Il <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> proprietà restituisce un valore intero che corrisponde all'elemento di elenco selezionato. A livello di codice, è possibile modificare l'elemento selezionato modificando il <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valore nel codice; l'elemento corrispondente nell'elenco verrà visualizzati nella casella di testo della casella combinata. Se è selezionato alcun elemento, il <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valore è -1. Se è selezionato il primo elemento nell'elenco, quindi il <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valore è 0. Il <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> proprietà è simile a <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> , ma restituisce l'elemento stesso, in genere un valore di stringa. Il <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> proprietà riflette il numero di elementi nell'elenco e il valore di <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> proprietà supera sempre uno più grande possibile <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valore perché <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> è in base zero.  
  
 Per aggiungere o eliminare elementi in un <xref:System.Windows.Forms.ComboBox> controllo, utilizzare il <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> o <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A> metodo. In alternativa, è possibile aggiungere elementi all'elenco utilizzando il <xref:System.Windows.Forms.ComboBox.Items%2A> proprietà nella finestra di progettazione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ComboBox>  
 [Panoramica sul controllo ListBox](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)  
 [Quando usare un controllo ComboBox Windows Form anziché un controllo ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [Procedura: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox di Windows Form](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [Procedura: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox di Windows Form](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [Procedura: Accedere a elementi specifici di un controllo ComboBox, ListBox o CheckedListBox di Windows Form](../../../../docs/framework/winforms/controls/access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)  
 [Procedura: Associare a dati un controllo ComboBox o ListBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 [Controlli Windows Form usati per elencare opzioni](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)  
 [Procedura: Creare una tabella di ricerca per un controllo ComboBox, ListBox o CheckedListBox di Windows Form](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)

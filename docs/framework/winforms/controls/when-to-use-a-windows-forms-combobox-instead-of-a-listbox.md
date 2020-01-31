---
title: ComboBox e ListBox
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], vs. ComboBox
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- ComboBox control [Windows Forms], compared to ListBox
- combo boxes [Windows Forms], compared to list boxes
- ListBox control [Windows Forms], accessing items
- ListCount property
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
ms.openlocfilehash: 7087760a393bb58d83d899c1741c745fb28585bb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739933"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a>Quando utilizzare un controllo ComboBox Windows Form anziché un controllo ListBox
I controlli <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ListBox> hanno comportamenti simili e in alcuni casi possono essere intercambiabili. In alcuni casi, tuttavia, una o l'altra è più appropriata per un'attività.  
  
 In genere, una casella combinata è appropriata quando è presente un elenco di scelte consigliate e una casella di riepilogo è appropriata quando si desidera limitare l'input a quello presente nell'elenco. Una casella combinata contiene un campo casella di testo, quindi le scelte non presenti nell'elenco possono essere digitate. L'eccezione si verifica quando la proprietà <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> è impostata su <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>. In tal caso, il controllo selezionerà un elemento se si digita la prima lettera.  
  
 Inoltre, le caselle combinate salvano lo spazio in un form. Poiché l'elenco completo non viene visualizzato fino a quando l'utente non fa clic sulla freccia verso il basso, una casella combinata può facilmente rientrare in uno spazio ridotto in cui una casella di riepilogo non è adatta. Si verifica un'eccezione quando la proprietà <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> è impostata su <xref:System.Windows.Forms.ComboBoxStyle.Simple>: viene visualizzato l'elenco completo e la casella combinata occupa più spazio rispetto a una casella di riepilogo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Procedura: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox di Windows Form](add-and-remove-items-from-a-wf-combobox.md)
- [Procedura: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox di Windows Form](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Controlli Windows Form usati per elencare opzioni](windows-forms-controls-used-to-list-options.md)

---
title: ComboBox e ListBox
description: Vengono fornite informazioni sull'utilizzo di Windows Forms ComboBox e Windows Forms ListBox e informazioni su come indicare quando uno o l'altro è più appropriato per un'attività.
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
ms.openlocfilehash: ca6ad6bec2dbc30128ea09808af2806687b17a8c
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174419"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a>Quando utilizzare un controllo ComboBox Windows Form anziché un controllo ListBox
I <xref:System.Windows.Forms.ComboBox> controlli e <xref:System.Windows.Forms.ListBox> hanno comportamenti simili e in alcuni casi possono essere intercambiabili. In alcuni casi, tuttavia, una o l'altra è più appropriata per un'attività.  
  
 In genere, una casella combinata è appropriata quando è presente un elenco di scelte consigliate e una casella di riepilogo è appropriata quando si desidera limitare l'input a quello presente nell'elenco. Una casella combinata contiene un campo casella di testo, quindi le scelte non presenti nell'elenco possono essere digitate. L'eccezione si verifica quando la <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> proprietà è impostata su <xref:System.Windows.Forms.ComboBoxStyle.DropDownList> . In tal caso, il controllo selezionerà un elemento se si digita la prima lettera.  
  
 Inoltre, le caselle combinate salvano lo spazio in un form. Poiché l'elenco completo non viene visualizzato fino a quando l'utente non fa clic sulla freccia verso il basso, una casella combinata può facilmente rientrare in uno spazio ridotto in cui una casella di riepilogo non è adatta. Si verifica un'eccezione quando la <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> proprietà è impostata su <xref:System.Windows.Forms.ComboBoxStyle.Simple> : viene visualizzato l'elenco completo e la casella combinata occupa più spazio rispetto a una casella di riepilogo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Procedura: aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox Windows Form](add-and-remove-items-from-a-wf-combobox.md)
- [Procedura: ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox Windows Form](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Controlli Windows Form usati per elencare opzioni](windows-forms-controls-used-to-list-options.md)

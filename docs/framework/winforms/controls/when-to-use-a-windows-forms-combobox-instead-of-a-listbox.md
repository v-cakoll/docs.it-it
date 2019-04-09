---
title: Quando utilizzare un controllo ComboBox Windows Form anziché un controllo ListBox
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
ms.openlocfilehash: 8a2429049acf1a22edde8d132ece17da4e91f1db
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111423"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a>Quando utilizzare un controllo ComboBox Windows Form anziché un controllo ListBox
Il <xref:System.Windows.Forms.ComboBox> e il <xref:System.Windows.Forms.ListBox> controlli presentano comportamenti simili e in alcuni casi potrebbe essere intercambiabili. Esistono casi, tuttavia, quando uno o l'altro è più appropriato per un'attività.  
  
 In generale, una casella combinata è appropriata quando è disponibile un elenco di opzioni disponibili e una casella di riepilogo è appropriata quando si desidera limitare l'input ai quali è presente nell'elenco. Una casella combinata contiene un campo casella di testo, in modo che le scelte non inclusi nell'elenco possono essere digitate. L'eccezione è quando il <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> è impostata su <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>. In tal caso, il controllo selezionerà un elemento se si digita la prima lettera.  
  
 Inoltre, le caselle combinate di risparmiare spazio in un form. Poiché non viene visualizzato l'elenco completo fino a quando l'utente fa clic sulla freccia in giù, una casella combinata può essere inserita in uno spazio ridotto, in cui non sarebbe sufficienti per una casella di riepilogo. Un'eccezione è quando il <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> è impostata su <xref:System.Windows.Forms.ComboBoxStyle.Simple>: viene visualizzato l'elenco completo e la casella combinata occupa più spazio rispetto a una casella di riepilogo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Procedura: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox di Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Procedura: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox di Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Controlli Windows Form usati per elencare opzioni](windows-forms-controls-used-to-list-options.md)

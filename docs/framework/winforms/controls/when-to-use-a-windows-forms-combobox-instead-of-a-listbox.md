---
title: "Quando utilizzare un controllo ComboBox Windows Form anziché un controllo ListBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b4eb1ce70b1ec4b249eb126b608c9f8578d327c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a>Quando utilizzare un controllo ComboBox Windows Form anziché un controllo ListBox
Il <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ListBox> controlli presentano comportamenti simili e in alcuni casi potrebbe essere intercambiabili. Esistono casi, tuttavia, quando una o l'altra è più appropriata per un'attività.  
  
 In genere, una casella combinata è appropriata quando è disponibile un elenco di opzioni disponibili, e una casella di riepilogo è appropriata quando si desidera limitare l'input ai quali è presente nell'elenco. Una casella combinata contiene un campo di casella di testo, pertanto possono essere digitate opzioni non presenti nell'elenco. L'eccezione si verifica quando il <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> è impostata su <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>. In tal caso, il controllo verrà selezionare un elemento, se si digita la prima lettera.  
  
 Inoltre, le caselle combinate di risparmiare spazio in un form. Poiché non è visualizzato l'elenco completo fino a quando l'utente fa clic sulla freccia rivolta verso il basso, una casella combinata può essere inserita in uno spazio ridotto, in cui non sarebbe sufficienti per una casella di riepilogo. Un'eccezione si verifica quando il <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> è impostata su <xref:System.Windows.Forms.ComboBoxStyle.Simple>: viene visualizzato l'elenco completo e la casella combinata occupa più spazio rispetto a una casella di riepilogo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [Procedura: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox di Windows Form](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [Procedura: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox di Windows Form](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [Controlli Windows Form usati per elencare opzioni](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)

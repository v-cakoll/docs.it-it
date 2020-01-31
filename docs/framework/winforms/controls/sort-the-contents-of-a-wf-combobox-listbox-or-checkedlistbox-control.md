---
title: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: dee969d777edf76434622fe632f7e934987a1dc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742962"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Procedura: ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox Windows Form
I controlli Windows Forms non vengono ordinati quando sono associati a dati. Per visualizzare i dati ordinati, utilizzare un'origine dei dati che supporti l'ordinamento e quindi fare in modo che l'origine dati venga ordinata. Le origini dati che supportano l'ordinamento sono viste dati, gestori visualizzazione dati e matrici ordinate.  
  
 Se il controllo non è associato a dati, è possibile ordinarlo.  
  
### <a name="to-sort-the-list"></a>Per ordinare l'elenco  
  
1. Impostare la proprietà `Sorted` su `true`.  
  
     Questa impostazione riposiziona tutti gli elementi dell'elenco esistenti in base all'ordinamento.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [Data binding in Windows Form](../windows-forms-data-binding.md)
- [Procedura: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox di Windows Form](add-and-remove-items-from-a-wf-combobox.md)
- [Quando usare un controllo ComboBox Windows Form anziché un controllo ListBox](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Controlli Windows Form usati per elencare opzioni](windows-forms-controls-used-to-list-options.md)

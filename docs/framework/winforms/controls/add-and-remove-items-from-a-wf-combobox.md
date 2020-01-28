---
title: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- combo boxes [Windows Forms], adding items
- list boxes [Windows Forms], removing items
- ComboBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], adding and removing items
- list boxes [Windows Forms], adding items
- combo boxes [Windows Forms], removing items
- CheckedListBox control [Windows Forms], adding and removing items
ms.assetid: 7224c8d2-4118-443e-ae1e-d7c17d1e69ee
ms.openlocfilehash: 3a83d98af42386b566b4af7bc11ff383dea8fd6b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746299"
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Procedura: aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox Windows Form
È possibile aggiungere elementi a una casella combinata Windows Forms, una casella di riepilogo o una casella di riepilogo selezionata in diversi modi, perché questi controlli possono essere associati a una varietà di origini dati. Tuttavia, in questo argomento viene illustrato il metodo più semplice e non è necessario alcun data binding. Gli elementi visualizzati sono in genere stringhe; Tuttavia, è possibile usare qualsiasi oggetto. Il testo visualizzato nel controllo corrisponde al valore restituito dal metodo di `ToString` dell'oggetto.  
  
### <a name="to-add-items"></a>Per aggiungere elementi  
  
1. Aggiungere la stringa o l'oggetto all'elenco usando il metodo `Add` della classe `ObjectCollection`. Si fa riferimento alla raccolta usando la proprietà `Items`:  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - oppure -  
  
2. Inserire la stringa o l'oggetto in corrispondenza del punto desiderato nell'elenco con il metodo `Insert`:  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - oppure -  
  
3. Assegnare un'intera matrice alla raccolta di `Items`:  
  
    ```vb  
    Dim ItemObject(9) As System.Object  
    Dim i As Integer  
       For i = 0 To 9  
       ItemObject(i) = "Item" & i  
    Next i  
    ListBox1.Items.AddRange(ItemObject)  
    ```  
  
    ```csharp  
    System.Object[] ItemObject = new System.Object[10];  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = "Item" + i;  
    }  
    listBox1.Items.AddRange(ItemObject);  
    ```  
  
    ```cpp  
    Array<System::Object^>^ ItemObject = gcnew Array<System::Object^>(10);  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = String::Concat("Item", i.ToString());  
    }  
    listBox1->Items->AddRange(ItemObject);  
    ```  
  
### <a name="to-remove-an-item"></a>Per rimuovere un elemento  
  
1. Chiamare il metodo `Remove` o `RemoveAt` per eliminare gli elementi.  
  
     `Remove` dispone di un argomento che specifica l'elemento da rimuovere.`RemoveAt` Rimuove l'elemento con il numero di indice specificato.  
  
    ```vb  
    ' To remove item with index 0:  
    ComboBox1.Items.RemoveAt(0)  
    ' To remove currently selected item:  
    ComboBox1.Items.Remove(ComboBox1.SelectedItem)  
    ' To remove "Tokyo" item:  
    ComboBox1.Items.Remove("Tokyo")  
    ```  
  
    ```csharp  
    // To remove item with index 0:  
    comboBox1.Items.RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1.Items.Remove(comboBox1.SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1.Items.Remove("Tokyo");  
    ```  
  
    ```cpp  
    // To remove item with index 0:  
    comboBox1->Items->RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1->Items->Remove(comboBox1->SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1->Items->Remove("Tokyo");  
    ```  
  
### <a name="to-remove-all-items"></a>Per rimuovere tutti gli elementi  
  
1. Chiamare il metodo `Clear` per rimuovere tutti gli elementi dalla raccolta:  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [Procedura: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox di Windows Form](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Quando usare un controllo ComboBox Windows Form anziché un controllo ListBox](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Controlli Windows Form usati per elencare opzioni](windows-forms-controls-used-to-list-options.md)

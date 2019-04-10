---
title: 'Procedura: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox di Windows Forms'
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
ms.openlocfilehash: bd6614c76c63a44a7367ac7c7113c4db260c9a02
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59322732"
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Procedura: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox di Windows Forms
Gli elementi possono essere aggiunti a una casella combinata Windows Form, casella di riepilogo o casella di riepilogo in svariati modi, poiché questi controlli possono essere associati a una varietà di origini dati. Tuttavia, in questo argomento viene illustrato il metodo più semplice e non richiede supporta l'associazione dati. Gli elementi visualizzati in genere sono stringhe. Tuttavia, può essere usato qualsiasi oggetto. Il testo che viene visualizzato nel controllo è il valore restituito dell'oggetto `ToString` (metodo).  
  
### <a name="to-add-items"></a>Per aggiungere elementi  
  
1. Aggiungere la stringa o l'oggetto all'elenco utilizzando il `Add` metodo di `ObjectCollection` classe. La raccolta viene fatto riferimento tramite il `Items` proprietà:  
  
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
  
2. Inserire la stringa o l'oggetto in corrispondenza del punto desiderato nell'elenco con il `Insert` metodo:  
  
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
  
3. Assegnare un'intera matrice per la `Items` raccolta:  
  
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
  
1. Chiamare il `Remove` o `RemoveAt` metodo per eliminare gli elementi.  
  
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
  
### <a name="to-remove-all-items"></a>Rimuovere tutti gli elementi  
  
1. Chiamare il `Clear` metodo per rimuovere tutti gli elementi dalla raccolta:  
  
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
- [Procedura: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox di Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Quando utilizzare un controllo ComboBox Windows Form anziché un controllo ListBox](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Controlli Windows Form usati per elencare opzioni](windows-forms-controls-used-to-list-options.md)

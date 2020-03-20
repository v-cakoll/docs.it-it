---
title: Determinare gli elementi selezionati nel controllo CheckedListBoxDetermine Checked Items in CheckedListBox Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: 5d93a63e9c1c6aae91ecfe83590c59450a565afe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182198"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>Procedura: rilevare gli elementi selezionati nel controllo CheckedListBox di Windows Form
Quando si presentano dati <xref:System.Windows.Forms.CheckedListBox> in un controllo Windows Form, <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> è possibile scorrere l'insieme <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> archiviato nella proprietà oppure scorrere l'elenco utilizzando il metodo per determinare quali elementi vengono controllati. Il <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> metodo accetta un numero di `true` indice `false`dell'elemento come argomento e restituisce o . Contrariamente a quanto ci <xref:System.Windows.Forms.ListBox.SelectedItems%2A> <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> si potrebbe aspettare, le proprietà e non determinano quali elementi vengono controllati; determinano quali elementi sono evidenziati.  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>Per determinare gli elementi selezionati in un controllo CheckedListBoxTo determine checked items in a CheckedListBox control  
  
1. Scorrere la <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> raccolta, a partire da 0 poiché la raccolta è in base zero. Si noti che questo metodo fornisce il numero di articolo nell'elenco degli elementi selezionati, non l'elenco complessivo. Quindi, se il primo elemento dell'elenco non è selezionato e il secondo elemento è selezionato, il codice seguente visualizzerà testo come "Elemento controllato 1 - MyListItem2".  
  
    ```vb  
    ' Determine if there are any items checked.  
    If CheckedListBox1.CheckedItems.Count <> 0 Then  
       ' If so, loop through all checked items and print results.  
       Dim x As Integer  
       Dim s As String = ""  
       For x = 0 To CheckedListBox1.CheckedItems.Count - 1  
          s = s & "Checked Item " & (x + 1).ToString & " = " & CheckedListBox1.CheckedItems(x).ToString & ControlChars.CrLf  
       Next x  
       MessageBox.Show(s)  
    End If  
    ```  
  
    ```csharp  
    // Determine if there are any items checked.  
    if(checkedListBox1.CheckedItems.Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       string s = "";  
       for(int x = 0; x < checkedListBox1.CheckedItems.Count ; x++)  
       {  
          s = s + "Checked Item " + (x+1).ToString() + " = " + checkedListBox1.CheckedItems[x].ToString() + "\n";  
       }  
       MessageBox.Show(s);  
    }  
    ```  
  
    ```cpp  
    // Determine if there are any items checked.  
    if(checkedListBox1->CheckedItems->Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       String ^ s = "";  
       for(int x = 0; x < checkedListBox1->CheckedItems->Count; x++)  
       {  
          s = String::Concat(s, "Checked Item ", (x+1).ToString(),  
             " = ", checkedListBox1->CheckedItems[x]->ToString(),  
             "\n");  
       }  
       MessageBox::Show(s);  
    }  
    ```  
  
     - - oppure -  
  
2. Eseguire la <xref:System.Windows.Forms.CheckedListBox.Items%2A> raccolta un'istruzione alla volta, a partire <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> da 0 poiché la raccolta è in base zero e chiamare il metodo per ogni elemento. Si noti che questo metodo vi darà il numero di elemento nell'elenco complessivo, quindi se il primo elemento nell'elenco non è selezionato e il secondo elemento è selezionato, verrà visualizzato qualcosa di simile "Elemento 2 - MyListItem2".  
  
    ```vb  
    Dim i As Integer  
    Dim s As String  
    s = "Checked Items:" & ControlChars.CrLf  
    For i = 0 To (CheckedListBox1.Items.Count - 1)  
       If CheckedListBox1.GetItemChecked(i) = True Then  
          s = s & "Item " & (i + 1).ToString & " = " & CheckedListBox1.Items(i).ToString & ControlChars.CrLf  
       End If  
    Next  
    MessageBox.Show(s)  
    ```  
  
    ```csharp  
    int i;  
    string s;
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1.Items.Count-1); i++)  
    {  
       if (checkedListBox1.GetItemChecked(i))  
       {  
          s = s + "Item " + (i+1).ToString() + " = " + checkedListBox1.Items[i].ToString() + "\n";  
       }  
    }  
    MessageBox.Show (s);  
    ```  
  
    ```cpp  
    int i;  
    String ^ s;
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1->Items->Count-1); i++)  
    {  
       if (checkedListBox1->GetItemChecked(i))  
       {  
          s = String::Concat(s, "Item ", (i+1).ToString(), " = ",  
             checkedListBox1->Item[i]->ToString(), "\n");  
       }  
    }  
    MessageBox::Show(s);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Controlli Windows Form usati per elencare opzioni](windows-forms-controls-used-to-list-options.md)

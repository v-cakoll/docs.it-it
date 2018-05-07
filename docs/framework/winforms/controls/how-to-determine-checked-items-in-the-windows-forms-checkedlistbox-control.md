---
title: 'Procedura: rilevare gli elementi selezionati nel controllo CheckedListBox di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: 98b4ef7c4ac73e1560bd5c68f22898e46585d082
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>Procedura: rilevare gli elementi selezionati nel controllo CheckedListBox di Windows Form
Quando la presentazione dei dati in un Windows Form <xref:System.Windows.Forms.CheckedListBox> (controllo), è possibile scorrere la raccolta archiviato nel <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> proprietà o esaminare l'elenco utilizzando il <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> metodo per determinare quali elementi sono selezionati. Il <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> metodo accetta un numero di indice di elemento come argomento e restituisce `true` o `false`. Contrariamente a quanto potrebbe pensare, il <xref:System.Windows.Forms.ListBox.SelectedItems%2A> e <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> proprietà non in grado di determinare quali elementi sono selezionati; è possibile determinare quali elementi vengono evidenziati.  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>Per determinare gli elementi selezionati in un controllo CheckedListBox  
  
1.  Scorrere il <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> insieme, a partire da 0, poiché la raccolta è in base zero. Si noti che questo metodo verrà visualizzato il numero di elementi nell'elenco di elementi controllati, non nell'intero elenco. Pertanto in se il primo elemento nell'elenco non è selezionato e il secondo elemento, il codice seguente viene visualizzato testo, ad esempio "Checked Item 1 = MyListItem2".  
  
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
       for(int x = 0; x <= checkedListBox1.CheckedItems.Count - 1 ; x++)  
       {  
          s = s + "Checked Item " + (x+1).ToString() + " = " + checkedListBox1.CheckedItems[x].ToString() + "\n";  
       }  
    MessageBox.Show (s);  
    }  
    ```  
  
    ```cpp  
    // Determine if there are any items checked.  
    if(checkedListBox1->CheckedItems->Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       String ^ s = "";  
       for(int x = 0; x <= checkedListBox1->CheckedItems->Count - 1; x++)  
       {  
          s = String::Concat(s, "Checked Item ", (x+1).ToString(),  
             " = ", checkedListBox1->CheckedItems[x]->ToString(),  
             "\n");  
       }  
       MessageBox::Show(s);  
    }  
    ```  
  
     - oppure -  
  
2.  Scorrere il <xref:System.Windows.Forms.CheckedListBox.Items%2A> insieme, a partire da 0, poiché la raccolta è in base zero e chiamare il <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> metodo per ogni elemento. Si noti che questo metodo verrà visualizzato il numero di elementi nell'elenco globale, pertanto se il primo elemento nell'elenco non viene verificato e il secondo elemento è selezionato, verrà visualizzato un output simile "elemento 2 = MyListItem2".  
  
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
 [Controlli Windows Form usati per elencare opzioni](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)

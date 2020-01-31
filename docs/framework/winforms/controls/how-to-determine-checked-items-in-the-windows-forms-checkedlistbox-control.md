---
title: Determinare gli elementi selezionati nel controllo CheckedListBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: 5854f7e6be759daeb604458ea8554d3c98ed39c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743245"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>Procedura: rilevare gli elementi selezionati nel controllo CheckedListBox di Windows Form
Quando si presentano dati in un controllo Windows Forms <xref:System.Windows.Forms.CheckedListBox>, è possibile eseguire l'iterazione nella raccolta archiviata nella proprietà <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> o eseguire un'istruzione alla volta nell'elenco usando il metodo <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> per determinare quali elementi sono controllati. Il metodo <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> accetta il numero di indice di un elemento come argomento e restituisce `true` o `false`. Contrariamente a quanto ci si potrebbe aspettare, le proprietà <xref:System.Windows.Forms.ListBox.SelectedItems%2A> e <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> non determinano quali elementi sono controllati; determinano quali elementi sono evidenziati.  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>Per determinare gli elementi selezionati in un controllo CheckedListBox  
  
1. Scorre la raccolta di <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A>, a partire da 0 perché la raccolta è in base zero. Si noti che questo metodo fornirà il numero dell'elemento nell'elenco degli elementi selezionati, non l'elenco generale. Se quindi il primo elemento dell'elenco non è selezionato e il secondo elemento è selezionato, il codice seguente visualizzerà un testo come "checked Item 1 = MyListItem2".  
  
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
  
     - oppure -  
  
2. Scorrere la raccolta di <xref:System.Windows.Forms.CheckedListBox.Items%2A>, a partire da 0 poiché la raccolta è in base zero e chiamare il metodo <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> per ogni elemento. Si noti che questo metodo fornirà il numero dell'elemento nell'elenco generale, pertanto se il primo elemento dell'elenco non è selezionato e il secondo elemento è selezionato, verrà visualizzato un messaggio simile al seguente: "Item 2 = MyListItem2".  
  
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

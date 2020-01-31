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
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a><span data-ttu-id="330cd-102">Procedura: rilevare gli elementi selezionati nel controllo CheckedListBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="330cd-102">How to: Determine Checked Items in the Windows Forms CheckedListBox Control</span></span>
<span data-ttu-id="330cd-103">Quando si presentano dati in un controllo Windows Forms <xref:System.Windows.Forms.CheckedListBox>, è possibile eseguire l'iterazione nella raccolta archiviata nella proprietà <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> o eseguire un'istruzione alla volta nell'elenco usando il metodo <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> per determinare quali elementi sono controllati.</span><span class="sxs-lookup"><span data-stu-id="330cd-103">When presenting data in a Windows Forms <xref:System.Windows.Forms.CheckedListBox> control, you can either iterate through the collection stored in the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> property, or step through the list using the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method to determine which items are checked.</span></span> <span data-ttu-id="330cd-104">Il metodo <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> accetta il numero di indice di un elemento come argomento e restituisce `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="330cd-104">The <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method takes an item index number as its argument and returns `true` or `false`.</span></span> <span data-ttu-id="330cd-105">Contrariamente a quanto ci si potrebbe aspettare, le proprietà <xref:System.Windows.Forms.ListBox.SelectedItems%2A> e <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> non determinano quali elementi sono controllati; determinano quali elementi sono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="330cd-105">Contrary to what you might expect, the <xref:System.Windows.Forms.ListBox.SelectedItems%2A> and <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> properties do not determine which items are checked; they determine which items are highlighted.</span></span>  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a><span data-ttu-id="330cd-106">Per determinare gli elementi selezionati in un controllo CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="330cd-106">To determine checked items in a CheckedListBox control</span></span>  
  
1. <span data-ttu-id="330cd-107">Scorre la raccolta di <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A>, a partire da 0 perché la raccolta è in base zero.</span><span class="sxs-lookup"><span data-stu-id="330cd-107">Iterate through the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> collection, starting at 0 since the collection is zero-based.</span></span> <span data-ttu-id="330cd-108">Si noti che questo metodo fornirà il numero dell'elemento nell'elenco degli elementi selezionati, non l'elenco generale.</span><span class="sxs-lookup"><span data-stu-id="330cd-108">Note that this method will give you the item number in the list of checked items, not the overall list.</span></span> <span data-ttu-id="330cd-109">Se quindi il primo elemento dell'elenco non è selezionato e il secondo elemento è selezionato, il codice seguente visualizzerà un testo come "checked Item 1 = MyListItem2".</span><span class="sxs-lookup"><span data-stu-id="330cd-109">So if the first item in the list is not checked and the second item is checked, the code below will display text like "Checked Item 1 = MyListItem2".</span></span>  
  
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
  
     - <span data-ttu-id="330cd-110">oppure -</span><span class="sxs-lookup"><span data-stu-id="330cd-110">or -</span></span>  
  
2. <span data-ttu-id="330cd-111">Scorrere la raccolta di <xref:System.Windows.Forms.CheckedListBox.Items%2A>, a partire da 0 poiché la raccolta è in base zero e chiamare il metodo <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="330cd-111">Step through the <xref:System.Windows.Forms.CheckedListBox.Items%2A> collection, starting at 0 since the collection is zero-based, and call the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method for each item.</span></span> <span data-ttu-id="330cd-112">Si noti che questo metodo fornirà il numero dell'elemento nell'elenco generale, pertanto se il primo elemento dell'elenco non è selezionato e il secondo elemento è selezionato, verrà visualizzato un messaggio simile al seguente: "Item 2 = MyListItem2".</span><span class="sxs-lookup"><span data-stu-id="330cd-112">Note that this method will give you the item number in the overall list, so if the first item in the list is not checked and the second item is checked, it will display something like "Item 2 = MyListItem2".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="330cd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="330cd-113">See also</span></span>

- [<span data-ttu-id="330cd-114">Controlli Windows Form usati per elencare opzioni</span><span class="sxs-lookup"><span data-stu-id="330cd-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)

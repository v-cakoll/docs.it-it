---
title: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox
ms.date: 03/30/2017
description: Informazioni su come aggiungere e rimuovere un Windows Forms controlli ComboBox, ListBox e CheckedListBox semplicemente e senza data binding.
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
ms.openlocfilehash: f3701257bbe410bf03c4c21700705e87b581bf2e
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904442"
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="8fa72-103">Procedura: aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="8fa72-103">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="8fa72-104">È possibile aggiungere elementi a una casella combinata Windows Forms, una casella di riepilogo o una casella di riepilogo selezionata in diversi modi, perché questi controlli possono essere associati a una varietà di origini dati.</span><span class="sxs-lookup"><span data-stu-id="8fa72-104">Items can be added to a Windows Forms combo box, list box, or checked list box in a variety of ways, because these controls can be bound to a variety of data sources.</span></span> <span data-ttu-id="8fa72-105">Tuttavia, in questo argomento viene illustrato il metodo più semplice e non è necessario alcun data binding.</span><span class="sxs-lookup"><span data-stu-id="8fa72-105">However, this topic demonstrates the simplest method and requires no data binding.</span></span> <span data-ttu-id="8fa72-106">Gli elementi visualizzati sono in genere stringhe; Tuttavia, è possibile usare qualsiasi oggetto.</span><span class="sxs-lookup"><span data-stu-id="8fa72-106">The items displayed are usually strings; however, any object can be used.</span></span> <span data-ttu-id="8fa72-107">Il testo visualizzato nel controllo corrisponde al valore restituito dal metodo dell'oggetto `ToString` .</span><span class="sxs-lookup"><span data-stu-id="8fa72-107">The text that is displayed in the control is the value returned by the object's `ToString` method.</span></span>  
  
### <a name="to-add-items"></a><span data-ttu-id="8fa72-108">Per aggiungere elementi</span><span class="sxs-lookup"><span data-stu-id="8fa72-108">To add items</span></span>  
  
1. <span data-ttu-id="8fa72-109">Aggiungere la stringa o l'oggetto all'elenco usando il `Add` metodo della `ObjectCollection` classe.</span><span class="sxs-lookup"><span data-stu-id="8fa72-109">Add the string or object to the list by using the `Add` method of the `ObjectCollection` class.</span></span> <span data-ttu-id="8fa72-110">Si fa riferimento alla raccolta tramite la `Items` proprietà:</span><span class="sxs-lookup"><span data-stu-id="8fa72-110">The collection is referenced using the `Items` property:</span></span>  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - <span data-ttu-id="8fa72-111">- oppure -</span><span class="sxs-lookup"><span data-stu-id="8fa72-111">or -</span></span>  
  
2. <span data-ttu-id="8fa72-112">Inserire la stringa o l'oggetto in corrispondenza del punto desiderato nell'elenco con il `Insert` Metodo:</span><span class="sxs-lookup"><span data-stu-id="8fa72-112">Insert the string or object at the desired point in the list with the `Insert` method:</span></span>  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - <span data-ttu-id="8fa72-113">- oppure -</span><span class="sxs-lookup"><span data-stu-id="8fa72-113">or -</span></span>  
  
3. <span data-ttu-id="8fa72-114">Assegnare un'intera matrice alla `Items` raccolta:</span><span class="sxs-lookup"><span data-stu-id="8fa72-114">Assign an entire array to the `Items` collection:</span></span>  
  
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
  
### <a name="to-remove-an-item"></a><span data-ttu-id="8fa72-115">Per rimuovere un elemento</span><span class="sxs-lookup"><span data-stu-id="8fa72-115">To remove an item</span></span>  
  
1. <span data-ttu-id="8fa72-116">Chiamare il `Remove` `RemoveAt` metodo o per eliminare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="8fa72-116">Call the `Remove` or `RemoveAt` method to delete items.</span></span>  
  
     <span data-ttu-id="8fa72-117">`Remove`ha un argomento che specifica l'elemento da rimuovere.`RemoveAt`</span><span class="sxs-lookup"><span data-stu-id="8fa72-117">`Remove` has one argument that specifies the item to remove.`RemoveAt`</span></span> <span data-ttu-id="8fa72-118">Rimuove l'elemento con il numero di indice specificato.</span><span class="sxs-lookup"><span data-stu-id="8fa72-118">removes the item with the specified index number.</span></span>  
  
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
  
### <a name="to-remove-all-items"></a><span data-ttu-id="8fa72-119">Per rimuovere tutti gli elementi</span><span class="sxs-lookup"><span data-stu-id="8fa72-119">To remove all items</span></span>  
  
1. <span data-ttu-id="8fa72-120">Chiamare il `Clear` metodo per rimuovere tutti gli elementi dalla raccolta:</span><span class="sxs-lookup"><span data-stu-id="8fa72-120">Call the `Clear` method to remove all items from the collection:</span></span>  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8fa72-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fa72-121">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="8fa72-122">Procedura: ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="8fa72-122">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="8fa72-123">Quando utilizzare un controllo ComboBox Windows Form anziché un controllo ListBox</span><span class="sxs-lookup"><span data-stu-id="8fa72-123">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="8fa72-124">Controlli Windows Form usati per elencare opzioni</span><span class="sxs-lookup"><span data-stu-id="8fa72-124">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)

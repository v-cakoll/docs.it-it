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
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="5b1b2-102">Procedura: aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="5b1b2-102">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="5b1b2-103">È possibile aggiungere elementi a una casella combinata Windows Forms, una casella di riepilogo o una casella di riepilogo selezionata in diversi modi, perché questi controlli possono essere associati a una varietà di origini dati.</span><span class="sxs-lookup"><span data-stu-id="5b1b2-103">Items can be added to a Windows Forms combo box, list box, or checked list box in a variety of ways, because these controls can be bound to a variety of data sources.</span></span> <span data-ttu-id="5b1b2-104">Tuttavia, in questo argomento viene illustrato il metodo più semplice e non è necessario alcun data binding.</span><span class="sxs-lookup"><span data-stu-id="5b1b2-104">However, this topic demonstrates the simplest method and requires no data binding.</span></span> <span data-ttu-id="5b1b2-105">Gli elementi visualizzati sono in genere stringhe; Tuttavia, è possibile usare qualsiasi oggetto.</span><span class="sxs-lookup"><span data-stu-id="5b1b2-105">The items displayed are usually strings; however, any object can be used.</span></span> <span data-ttu-id="5b1b2-106">Il testo visualizzato nel controllo corrisponde al valore restituito dal metodo di `ToString` dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="5b1b2-106">The text that is displayed in the control is the value returned by the object's `ToString` method.</span></span>  
  
### <a name="to-add-items"></a><span data-ttu-id="5b1b2-107">Per aggiungere elementi</span><span class="sxs-lookup"><span data-stu-id="5b1b2-107">To add items</span></span>  
  
1. <span data-ttu-id="5b1b2-108">Aggiungere la stringa o l'oggetto all'elenco usando il metodo `Add` della classe `ObjectCollection`.</span><span class="sxs-lookup"><span data-stu-id="5b1b2-108">Add the string or object to the list by using the `Add` method of the `ObjectCollection` class.</span></span> <span data-ttu-id="5b1b2-109">Si fa riferimento alla raccolta usando la proprietà `Items`:</span><span class="sxs-lookup"><span data-stu-id="5b1b2-109">The collection is referenced using the `Items` property:</span></span>  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - <span data-ttu-id="5b1b2-110">oppure -</span><span class="sxs-lookup"><span data-stu-id="5b1b2-110">or -</span></span>  
  
2. <span data-ttu-id="5b1b2-111">Inserire la stringa o l'oggetto in corrispondenza del punto desiderato nell'elenco con il metodo `Insert`:</span><span class="sxs-lookup"><span data-stu-id="5b1b2-111">Insert the string or object at the desired point in the list with the `Insert` method:</span></span>  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - <span data-ttu-id="5b1b2-112">oppure -</span><span class="sxs-lookup"><span data-stu-id="5b1b2-112">or -</span></span>  
  
3. <span data-ttu-id="5b1b2-113">Assegnare un'intera matrice alla raccolta di `Items`:</span><span class="sxs-lookup"><span data-stu-id="5b1b2-113">Assign an entire array to the `Items` collection:</span></span>  
  
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
  
### <a name="to-remove-an-item"></a><span data-ttu-id="5b1b2-114">Per rimuovere un elemento</span><span class="sxs-lookup"><span data-stu-id="5b1b2-114">To remove an item</span></span>  
  
1. <span data-ttu-id="5b1b2-115">Chiamare il metodo `Remove` o `RemoveAt` per eliminare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="5b1b2-115">Call the `Remove` or `RemoveAt` method to delete items.</span></span>  
  
     <span data-ttu-id="5b1b2-116">`Remove` dispone di un argomento che specifica l'elemento da rimuovere.`RemoveAt`</span><span class="sxs-lookup"><span data-stu-id="5b1b2-116">`Remove` has one argument that specifies the item to remove.`RemoveAt`</span></span> <span data-ttu-id="5b1b2-117">Rimuove l'elemento con il numero di indice specificato.</span><span class="sxs-lookup"><span data-stu-id="5b1b2-117">removes the item with the specified index number.</span></span>  
  
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
  
### <a name="to-remove-all-items"></a><span data-ttu-id="5b1b2-118">Per rimuovere tutti gli elementi</span><span class="sxs-lookup"><span data-stu-id="5b1b2-118">To remove all items</span></span>  
  
1. <span data-ttu-id="5b1b2-119">Chiamare il metodo `Clear` per rimuovere tutti gli elementi dalla raccolta:</span><span class="sxs-lookup"><span data-stu-id="5b1b2-119">Call the `Clear` method to remove all items from the collection:</span></span>  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5b1b2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b1b2-120">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="5b1b2-121">Procedura: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5b1b2-121">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="5b1b2-122">Quando usare un controllo ComboBox Windows Form anziché un controllo ListBox</span><span class="sxs-lookup"><span data-stu-id="5b1b2-122">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="5b1b2-123">Controlli Windows Form usati per elencare opzioni</span><span class="sxs-lookup"><span data-stu-id="5b1b2-123">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)

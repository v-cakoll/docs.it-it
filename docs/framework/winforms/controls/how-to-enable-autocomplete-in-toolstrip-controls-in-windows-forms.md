---
title: 'Procedura: abilitare il completamento automatico nei controlli ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoComplete [Windows Forms], examples
- toolbars [Windows Forms], AutoComplete
- examples [Windows Forms], toolbars
- AutoComplete [Windows Forms], enabling in toolbars
- ToolStripComboBox class [Windows Forms], examples
- ToolStrip control [Windows Forms], AutoComplete
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
ms.openlocfilehash: 18b17aaea9d2354c03bb43f3fdd8d3779697cf58
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142018"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a><span data-ttu-id="ccdda-102">Procedura: abilitare il completamento automatico nei controlli ToolStrip Windows Form</span><span class="sxs-lookup"><span data-stu-id="ccdda-102">How to: Enable AutoComplete in ToolStrip Controls in Windows Forms</span></span>
<span data-ttu-id="ccdda-103">La procedura seguente <xref:System.Windows.Forms.ToolStripLabel> combina <xref:System.Windows.Forms.ToolStripComboBox> un oggetto che può essere rilasciato per visualizzare un elenco di elementi, ad esempio siti Web visitati di recente.</span><span class="sxs-lookup"><span data-stu-id="ccdda-103">The following procedure combines a <xref:System.Windows.Forms.ToolStripLabel> with a <xref:System.Windows.Forms.ToolStripComboBox> that can be dropped down to show a list of items, such as recently visited Web sites.</span></span> <span data-ttu-id="ccdda-104">Se l'utente digita un carattere che corrisponde al primo carattere di uno degli elementi nell'elenco, l'elemento viene immediatamente visualizzato.</span><span class="sxs-lookup"><span data-stu-id="ccdda-104">If the user types a character that matches the first character of one of the items in the list, the item is immediately displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ccdda-105">Il completamento `ToolStrip` automatico funziona con i controlli nello <xref:System.Windows.Forms.ComboBox> stesso <xref:System.Windows.Forms.TextBox>modo in cui funziona con i controlli tradizionali come e .</span><span class="sxs-lookup"><span data-stu-id="ccdda-105">Automatic completion works with `ToolStrip` controls in the same way that it works with traditional controls such as <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.TextBox>.</span></span>  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a><span data-ttu-id="ccdda-106">Per abilitare Completamento automatico in un controllo ToolStripTo enable AutoComplete in a ToolStrip control</span><span class="sxs-lookup"><span data-stu-id="ccdda-106">To enable AutoComplete in a ToolStrip control</span></span>  
  
1. <span data-ttu-id="ccdda-107">Creare <xref:System.Windows.Forms.ToolStrip> un controllo e aggiungervi elementi.</span><span class="sxs-lookup"><span data-stu-id="ccdda-107">Create a <xref:System.Windows.Forms.ToolStrip> control and add items to it.</span></span>  
  
    ```vb  
    ToolStrip1 = New System.Windows.Forms.ToolStrip  
    ToolStrip1.Items.AddRange(New System.Windows.Forms.ToolStripItem()_  
        {ToolStripLabel1, ToolStripComboBox1})  
    ```  
  
    ```csharp  
    toolStrip1 = new System.Windows.Forms.ToolStrip();  
    toolStrip1.Items.AddRange(new System.Windows.Forms.ToolStripItem[]
        {toolStripLabel1, toolStripComboBox1});  
    ```  
  
2. <span data-ttu-id="ccdda-108">Impostare <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> la proprietà dell'etichetta <xref:System.Windows.Forms.ToolStripItemOverflow.Never> e della casella combinata su in modo che l'elenco sia sempre disponibile indipendentemente dalle dimensioni della maschera.</span><span class="sxs-lookup"><span data-stu-id="ccdda-108">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the label and the combo box to <xref:System.Windows.Forms.ToolStripItemOverflow.Never> so that the list is always available regardless of the form's size.</span></span>  
  
    ```vb  
    ToolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ToolStripComboBox1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    toolStripComboBox1.Overflow = System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
3. <span data-ttu-id="ccdda-109">Aggiungere parole alla raccolta <xref:System.Windows.Forms.ToolStripComboBox> Items del controllo.</span><span class="sxs-lookup"><span data-stu-id="ccdda-109">Add words to the Items collection of the <xref:System.Windows.Forms.ToolStripComboBox> control.</span></span>  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4. <span data-ttu-id="ccdda-110">Impostare <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> la proprietà della <xref:System.Windows.Forms.AutoCompleteMode.Append>casella combinata su .</span><span class="sxs-lookup"><span data-stu-id="ccdda-110">Set the <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> property of the combo box to <xref:System.Windows.Forms.AutoCompleteMode.Append>.</span></span>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5. <span data-ttu-id="ccdda-111">Impostare <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> la proprietà della <xref:System.Windows.Forms.AutoCompleteSource.ListItems>casella combinata su .</span><span class="sxs-lookup"><span data-stu-id="ccdda-111">Set the <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> property of the combo box to <xref:System.Windows.Forms.AutoCompleteSource.ListItems>.</span></span>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ccdda-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccdda-112">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [<span data-ttu-id="ccdda-113">Cenni preliminari sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ccdda-113">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="ccdda-114">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ccdda-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="ccdda-115">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ccdda-115">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)

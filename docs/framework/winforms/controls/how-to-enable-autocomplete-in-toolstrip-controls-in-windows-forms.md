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
ms.openlocfilehash: db411023ad624e4c3d60b09bdbd588c85f8e22d1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745512"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a><span data-ttu-id="9e538-102">Procedura: Abilitare il completamento automatico nei controlli ToolStrip di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9e538-102">How to: Enable AutoComplete in ToolStrip Controls in Windows Forms</span></span>
<span data-ttu-id="9e538-103">La procedura seguente combina una <xref:System.Windows.Forms.ToolStripLabel> con un <xref:System.Windows.Forms.ToolStripComboBox> che può essere rilasciata per visualizzare un elenco di elementi, ad esempio siti Web visitati di recente.</span><span class="sxs-lookup"><span data-stu-id="9e538-103">The following procedure combines a <xref:System.Windows.Forms.ToolStripLabel> with a <xref:System.Windows.Forms.ToolStripComboBox> that can be dropped down to show a list of items, such as recently visited Web sites.</span></span> <span data-ttu-id="9e538-104">Se l'utente digita un carattere che corrisponde al primo carattere di uno degli elementi dell'elenco, l'elemento viene immediatamente visualizzato.</span><span class="sxs-lookup"><span data-stu-id="9e538-104">If the user types a character that matches the first character of one of the items in the list, the item is immediately displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e538-105">Il completamento automatico funziona con i controlli `ToolStrip` nello stesso modo in cui funziona con i controlli tradizionali, ad esempio <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="9e538-105">Automatic completion works with `ToolStrip` controls in the same way that it works with traditional controls such as <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.TextBox>.</span></span>  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a><span data-ttu-id="9e538-106">Per abilitare il completamento automatico in un controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9e538-106">To enable AutoComplete in a ToolStrip control</span></span>  
  
1. <span data-ttu-id="9e538-107">Creare un controllo <xref:System.Windows.Forms.ToolStrip> e aggiungervi elementi.</span><span class="sxs-lookup"><span data-stu-id="9e538-107">Create a <xref:System.Windows.Forms.ToolStrip> control and add items to it.</span></span>  
  
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
  
2. <span data-ttu-id="9e538-108">Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> dell'etichetta e della casella combinata su <xref:System.Windows.Forms.ToolStripItemOverflow.Never> in modo che l'elenco sia sempre disponibile indipendentemente dalle dimensioni del form.</span><span class="sxs-lookup"><span data-stu-id="9e538-108">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the label and the combo box to <xref:System.Windows.Forms.ToolStripItemOverflow.Never> so that the list is always available regardless of the form's size.</span></span>  
  
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
  
3. <span data-ttu-id="9e538-109">Aggiungere parole alla raccolta Items del controllo <xref:System.Windows.Forms.ToolStripComboBox>.</span><span class="sxs-lookup"><span data-stu-id="9e538-109">Add words to the Items collection of the <xref:System.Windows.Forms.ToolStripComboBox> control.</span></span>  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4. <span data-ttu-id="9e538-110">Impostare la proprietà <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> della casella combinata su <xref:System.Windows.Forms.AutoCompleteMode.Append>.</span><span class="sxs-lookup"><span data-stu-id="9e538-110">Set the <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> property of the combo box to <xref:System.Windows.Forms.AutoCompleteMode.Append>.</span></span>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5. <span data-ttu-id="9e538-111">Impostare la proprietà <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> della casella combinata su <xref:System.Windows.Forms.AutoCompleteSource.ListItems>.</span><span class="sxs-lookup"><span data-stu-id="9e538-111">Set the <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> property of the combo box to <xref:System.Windows.Forms.AutoCompleteSource.ListItems>.</span></span>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9e538-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e538-112">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [<span data-ttu-id="9e538-113">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9e538-113">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="9e538-114">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9e538-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="9e538-115">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9e538-115">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)

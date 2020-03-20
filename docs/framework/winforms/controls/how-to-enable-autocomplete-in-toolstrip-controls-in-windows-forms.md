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
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a>Procedura: abilitare il completamento automatico nei controlli ToolStrip Windows Form
La procedura seguente <xref:System.Windows.Forms.ToolStripLabel> combina <xref:System.Windows.Forms.ToolStripComboBox> un oggetto che può essere rilasciato per visualizzare un elenco di elementi, ad esempio siti Web visitati di recente. Se l'utente digita un carattere che corrisponde al primo carattere di uno degli elementi nell'elenco, l'elemento viene immediatamente visualizzato.  
  
> [!NOTE]
> Il completamento `ToolStrip` automatico funziona con i controlli nello <xref:System.Windows.Forms.ComboBox> stesso <xref:System.Windows.Forms.TextBox>modo in cui funziona con i controlli tradizionali come e .  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a>Per abilitare Completamento automatico in un controllo ToolStripTo enable AutoComplete in a ToolStrip control  
  
1. Creare <xref:System.Windows.Forms.ToolStrip> un controllo e aggiungervi elementi.  
  
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
  
2. Impostare <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> la proprietà dell'etichetta <xref:System.Windows.Forms.ToolStripItemOverflow.Never> e della casella combinata su in modo che l'elenco sia sempre disponibile indipendentemente dalle dimensioni della maschera.  
  
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
  
3. Aggiungere parole alla raccolta <xref:System.Windows.Forms.ToolStripComboBox> Items del controllo.  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4. Impostare <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> la proprietà della <xref:System.Windows.Forms.AutoCompleteMode.Append>casella combinata su .  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5. Impostare <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> la proprietà della <xref:System.Windows.Forms.AutoCompleteSource.ListItems>casella combinata su .  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [Cenni preliminari sul controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Architettura del controllo ToolStrip](toolstrip-control-architecture.md)
- [Riepilogo della tecnologia ToolStrip](toolstrip-technology-summary.md)

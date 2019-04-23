---
title: "Procedura: Modificare la spaziatura e l'allineamento degli elementi ToolStrip in Windows Forms"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: bed943466348447e30947c170e27027f324342c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59323174"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>Procedura: Modificare la spaziatura e l'allineamento degli elementi ToolStrip in Windows Forms
Il <xref:System.Windows.Forms.ToolStrip> controllo supporta pienamente le funzionalità di layout, ad esempio il ridimensionamento, la spaziatura dei <xref:System.Windows.Forms.ToolStripItem> ai controlli di uno rispetto a altro, la disposizione dei controlli il <xref:System.Windows.Forms.ToolStrip>e la spaziatura dei controlli relativa al <xref:System.Windows.Forms.ToolStrip>.  
  
 Poiché il valore predefinito del <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> proprietà è `true`, i controlli vengono ridimensionati automaticamente, a meno che non si imposta la <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> proprietà `false`.  
  
### <a name="to-manually-size-a-toolstripitem"></a>Per ridimensionare manualmente un ToolStripItem  
  
1. Impostare il <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> proprietà `false` per il controllo associato.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. Impostare il <xref:System.Windows.Forms.ToolStripItem.Size%2A> proprietà nel modo desiderato per la proprietà associata <xref:System.Windows.Forms.ToolStripItem>.  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>Per impostare la spaziatura di un ToolStripItem  
  
1. Inserire i valori desiderati, in pixel, di <xref:System.Windows.Forms.ToolStripItem.Margin%2A> proprietà del controllo associato.  
  
     I valori del <xref:System.Windows.Forms.ToolStripItem.Margin%2A> proprietà specificare la spaziatura tra l'elemento e gli elementi adiacenti nell'ordine indicato: A sinistra, superiore, destro e inferiore.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>Per allineare un oggetto ToolStripItem sul lato destro dell'oggetto ToolStrip  
  
1. Impostare il <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> proprietà <xref:System.Windows.Forms.ToolStripItemAlignment.Right> per il controllo associato. Per impostazione predefinita <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> è impostata su <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, cui controlli sono allineati a sinistra del <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>Per disporre gli elementi di ToolStrip nell'oggetto ToolStrip  
  
-   Impostare il <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> il valore della proprietà <xref:System.Windows.Forms.ToolStripLayoutStyle> desiderato.  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [Panoramica sul controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Architettura del controllo ToolStrip](toolstrip-control-architecture.md)
- [Riepilogo della tecnologia ToolStrip](toolstrip-technology-summary.md)

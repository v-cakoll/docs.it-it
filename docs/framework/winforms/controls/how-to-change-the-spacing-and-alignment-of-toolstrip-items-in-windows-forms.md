---
title: "Procedura: modificare la spaziatura e l'allineamento degli elementi ToolStrip"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 805fbac5fe33071006f29692d503e5c57eacd765
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746554"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>Procedura: Modificare la spaziatura e l'allineamento degli elementi ToolStrip in Windows Form
Il controllo <xref:System.Windows.Forms.ToolStrip> supporta completamente le funzionalità di layout, ad esempio il ridimensionamento, la spaziatura dei controlli <xref:System.Windows.Forms.ToolStripItem> relativi tra loro, la disposizione dei controlli sul <xref:System.Windows.Forms.ToolStrip>e la spaziatura dei controlli relativi alla <xref:System.Windows.Forms.ToolStrip>.  
  
 Poiché il valore predefinito della proprietà <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> è `true`, i controlli vengono ridimensionati automaticamente a meno che non si imposti la proprietà <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> su `false`.  
  
### <a name="to-manually-size-a-toolstripitem"></a>Per ridimensionare manualmente un oggetto ToolStripItem  
  
1. Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> su `false` per il controllo associato.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.Size%2A> nel modo desiderato per il <xref:System.Windows.Forms.ToolStripItem>associato.  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>Per impostare la spaziatura di un oggetto ToolStripItem  
  
1. Inserire i valori desiderati, in pixel, nella proprietà <xref:System.Windows.Forms.ToolStripItem.Margin%2A> del controllo associato.  
  
     I valori della proprietà <xref:System.Windows.Forms.ToolStripItem.Margin%2A> specificano la spaziatura tra l'elemento e gli elementi adiacenti in questo ordine: Left, top, Right e Bottom.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>Per allineare un oggetto ToolStripItem al lato destro di ToolStrip  
  
1. Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> su <xref:System.Windows.Forms.ToolStripItemAlignment.Right> per il controllo associato. Per impostazione predefinita, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> è impostato su <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, che allinea i controlli al lato sinistro della <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>Per disporre gli elementi ToolStrip in ToolStrip  
  
- Impostare la proprietà <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> sul valore di <xref:System.Windows.Forms.ToolStripLayoutStyle> desiderato.  
  
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

---
title: "Procedura: modificare la spaziatura e l'allineamento degli elementi ToolStripHow to: Change the Spacing and Alignment of ToolStrip Items"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 550ac1660a077e8d766a01bfa8d102c07f0fbfeb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182234"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>Procedura: modificare la spaziatura e l'allineamento degli elementi ToolStrip in Windows Form
Il <xref:System.Windows.Forms.ToolStrip> controllo supporta completamente le funzionalità di layout, ad esempio il ridimensionamento, la spaziatura dei <xref:System.Windows.Forms.ToolStripItem> controlli l'uno rispetto all'altro, la disposizione dei controlli in <xref:System.Windows.Forms.ToolStrip>, e la spaziatura dei controlli rispetto a <xref:System.Windows.Forms.ToolStrip>.  
  
 Poiché il valore <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> predefinito `true`della proprietà è , <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> i `false`controlli vengono ridimensionati automaticamente a meno che non si imposti la proprietà su .  
  
### <a name="to-manually-size-a-toolstripitem"></a>Per ridimensionare manualmente un ToolStripItemTo manually size a ToolStripItem  
  
1. Impostare <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> la `false` proprietà su per il controllo associato.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. Impostare <xref:System.Windows.Forms.ToolStripItem.Size%2A> la proprietà nel modo <xref:System.Windows.Forms.ToolStripItem>desiderato per l'oggetto associato.  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>Per impostare la spaziatura di un ToolStripItemTo set the spacing of a ToolStripItem  
  
1. Inserire i valori desiderati, in <xref:System.Windows.Forms.ToolStripItem.Margin%2A> pixel, nella proprietà del controllo associato.  
  
     I valori <xref:System.Windows.Forms.ToolStripItem.Margin%2A> della proprietà specificano la spaziatura tra l'elemento e gli elementi adiacenti nell'ordine seguente: Left, Top, Right e Bottom.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>To align a ToolStripItem to the right side of the ToolStrip  
  
1. Impostare <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> la <xref:System.Windows.Forms.ToolStripItemAlignment.Right> proprietà su per il controllo associato. Per impostazione predefinita, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> è impostato su <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, che <xref:System.Windows.Forms.ToolStrip>allinea i controlli al lato sinistro del file .  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>Per disporre gli elementi ToolStrip in ToolStripTo arrange ToolStrip items on the ToolStrip  
  
- Impostare <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> la proprietà <xref:System.Windows.Forms.ToolStripLayoutStyle> sul valore desiderato.  
  
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
- [Cenni preliminari sul controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Architettura del controllo ToolStrip](toolstrip-control-architecture.md)
- [Riepilogo della tecnologia ToolStrip](toolstrip-technology-summary.md)

---
title: "Procedura: Modificare l'aspetto del testo e delle immagini ToolStrip in Windows Forms"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], appearance
- toolbars [Windows Forms], images
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], appearance
- ToolStrip control [Windows Forms], images
- ToolStrip control [Windows Forms], text
- toolbars [Windows Forms], text
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
ms.openlocfilehash: 5c326c8f6a56c934d317305f85f4c88e95e75f8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781264"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a>Procedura: Modificare l'aspetto del testo e delle immagini ToolStrip in Windows Forms
È possibile controllare se le immagini e testo vengono visualizzate in una <xref:System.Windows.Forms.ToolStripItem> e come siano allineati uno rispetto a altro e <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a>Per definire cosa è visualizzato su un ToolStripItem  
  
- Impostare il <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> proprietà sul valore desiderato. I valori possibili sono `Image`, `ImageAndText`, `None`, e `Text`. Il valore predefinito è `ImageAndText`.  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a>Per allineare il testo su un ToolStripItem  
  
- Impostare il <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> proprietà sul valore desiderato. I valori possibili sono qualsiasi combinazione di alto, medio e basso a sinistra, centro e a destra. Il valore predefinito è `MiddleCenter`.  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a>Per allineare un'immagine in ToolStripItem  
  
- Impostare il <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> proprietà sul valore desiderato. I valori possibili sono qualsiasi combinazione di alto, medio e basso a sinistra, centro e a destra. Il valore predefinito è `MiddleLeft`.  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a>Per definire la modalità di visualizzazione di immagini e testo ToolStripItem mettendone in relazione  
  
- Impostare il <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> proprietà sul valore desiderato. I valori possibili sono `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, e `TextBeforeImage`. Il valore predefinito è `ImageBeforeText`.  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- [Panoramica sul controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Architettura del controllo ToolStrip](toolstrip-control-architecture.md)
- [Riepilogo della tecnologia ToolStrip](toolstrip-technology-summary.md)

---
title: "Procedura: modificare l'aspetto del testo e delle immagini di una descrizione comandi in Windows Form"
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
ms.openlocfilehash: d3f53291e24d6a57e798725b716a7fd56eb661b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a>Procedura: modificare l'aspetto del testo e delle immagini di una descrizione comandi in Windows Form
È possibile controllare se vengono visualizzate testo e immagini in un <xref:System.Windows.Forms.ToolStripItem> e la modalità di allineamento uno rispetto a altro e <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a>Per definire gli elementi visualizzati in un controllo ToolStripItem  
  
-   Impostare il <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> proprietà sul valore desiderato. I valori possibili sono `Image`, `ImageAndText`, `None`, e `Text`. Il valore predefinito è `ImageAndText`.  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a>Per allineare il testo in un controllo ToolStripItem  
  
-   Impostare il <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> proprietà sul valore desiderato. I valori possibili sono qualsiasi combinazione di superiore, centrale e inferiore con left, center e right. Il valore predefinito è `MiddleCenter`.  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a>Per allineare un'immagine in un controllo ToolStripItem  
  
-   Impostare il <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> proprietà sul valore desiderato. I valori possibili sono qualsiasi combinazione di superiore, centrale e inferiore con left, center e right. Il valore predefinito è `MiddleLeft`.  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a>Per definire la modalità di visualizzazione di immagini e testo ToolStripItem reciprocamente  
  
-   Impostare il <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> proprietà sul valore desiderato. I valori possibili sono `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, e `TextBeforeImage`. Il valore predefinito è `ImageBeforeText`.  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ToolStrip>  
 [Panoramica sul controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Architettura del controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [Riepilogo della tecnologia ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)

---
title: "Procedura: modificare l'aspetto del testo e delle immagini di ToolStrip"
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
ms.openlocfilehash: 7816e138e44554683c201895ece1f886ace8bfa6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746603"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a>Procedura: Modificare l'aspetto del testo e delle immagini di una descrizione comandi in Windows Form
È possibile controllare se le immagini e il testo vengono visualizzati in una <xref:System.Windows.Forms.ToolStripItem> e come sono allineati l'uno rispetto all'altro e la <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a>Per definire ciò che viene visualizzato in un oggetto ToolStripItem  
  
- Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> sul valore desiderato. Le possibilità sono `Image`, `ImageAndText`, `None`e `Text`. Il valore predefinito è `ImageAndText`.  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a>Per allineare il testo in un oggetto ToolStripItem  
  
- Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> sul valore desiderato. Le possibilità sono qualsiasi combinazione di Top, Middle e Bottom con Left, Center e Right. Il valore predefinito è `MiddleCenter`.  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a>Per allineare un'immagine in un oggetto ToolStripItem  
  
- Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> sul valore desiderato. Le possibilità sono qualsiasi combinazione di Top, Middle e Bottom con Left, Center e Right. Il valore predefinito è `MiddleLeft`.  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a>Per definire la modalità di visualizzazione delle immagini e del testo di ToolStripItem  
  
- Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> sul valore desiderato. Le possibilità sono `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`e `TextBeforeImage`. Il valore predefinito è `ImageBeforeText`.  
  
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

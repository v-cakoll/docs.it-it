---
title: 'Procedura: creare pulsanti interruttore nei controlli ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: a04d531433273328c2d8eb0c5ef614f08c33952a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a>Procedura: creare pulsanti interruttore nei controlli ToolStrip
Quando un utente fa clic su un interruttore, appaiono incassato e mantiene tale aspetto fino a quando l'utente fa clic sul pulsante nuovo.  
  
### <a name="to-create-a-toggling-toolstripbutton"></a>Per creare un ToolStripButton  
  
-   Usare codice simile all'esempio di codice seguente. Questo codice presuppone che il modulo contiene un <xref:System.Windows.Forms.ToolStrip> controllo e che il relativo <xref:System.Windows.Forms.ToolStrip.Items%2A> raccolta contiene un <xref:System.Windows.Forms.ToolStripButton> chiamato `toolStripButton1`. Inoltre, presuppone che si dispone di un gestore eventi denominato `toolStripButton1_CheckedChanged`.  
  
    ```vb  
    toolStripButton1.CheckOnClick = True  
    toolStripButton1.CheckedChanged AddressOf _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
    ```csharp  
    toolStripButton1.CheckOnClick = true;  
    toolStripButton1.CheckedChanged += new _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ToolStripButton>  
 [Panoramica sul controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)

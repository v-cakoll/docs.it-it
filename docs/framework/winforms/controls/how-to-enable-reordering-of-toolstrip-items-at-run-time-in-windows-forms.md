---
title: 'Procedura: abilitare il riordino degli elementi di ToolStrip in fase di esecuzione in Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 73ea6d3615780c8def31b7dbdcf870020a106e80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a>Procedura: abilitare il riordino degli elementi di ToolStrip in fase di esecuzione in Windows Form
È possibile consentire all'utente di ridisporre <xref:System.Windows.Forms.ToolStripItem> ai controlli di <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a>Per abilitare il riordino di ToolStripItem in fase di esecuzione  
  
-   Impostare la proprietà <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> su `true`. Per impostazione predefinita, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> è `false`.  
  
     In fase di esecuzione, l'utente tiene premuto il tasto ALT e il pulsante sinistro del mouse per trascinare un <xref:System.Windows.Forms.ToolStripItem> a una posizione diversa sul <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>  
 [Panoramica sul controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Architettura del controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [Riepilogo della tecnologia ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)

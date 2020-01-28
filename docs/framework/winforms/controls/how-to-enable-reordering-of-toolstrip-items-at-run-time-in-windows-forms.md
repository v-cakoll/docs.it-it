---
title: 'Procedura: abilitare il riordino di elementi ToolStrip in fase di esecuzione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
ms.openlocfilehash: 44b52bf997819f090569d08eb395d8af18f61370
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745481"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a>Procedura: Abilitare il riordino degli elementi di ToolStrip in fase di esecuzione in Windows Form
È possibile consentire all'utente di ridisporre i controlli <xref:System.Windows.Forms.ToolStripItem> nel <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a>Per abilitare la riorganizzazione di ToolStripItem in fase di esecuzione  
  
- Impostare la proprietà <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> su `true`. Per impostazione predefinita, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> è `false`.  
  
     In fase di esecuzione, l'utente deve tenere premuto il tasto ALT e il pulsante sinistro del mouse per trascinare un <xref:System.Windows.Forms.ToolStripItem> in un percorso diverso nel <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [Panoramica sul controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Architettura del controllo ToolStrip](toolstrip-control-architecture.md)
- [Riepilogo della tecnologia ToolStrip](toolstrip-technology-summary.md)

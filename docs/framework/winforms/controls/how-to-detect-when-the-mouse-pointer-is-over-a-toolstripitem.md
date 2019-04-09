---
title: 'Procedura: Rilevare quando il puntatore del mouse si trova sopra un ToolStripItem'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 09fd9f2f9b8cc44b6c04b829bf2854bea4aa8cf7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220046"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a>Procedura: Rilevare quando il puntatore del mouse si trova sopra un ToolStripItem
Usare la procedura seguente per rilevare quando il puntatore del mouse è posizionato sopra un <xref:System.Windows.Forms.ToolStripItem>.  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a>Per rilevare quando il puntatore si trova sopra un ToolStripItem  
  
-   Usare la <xref:System.Windows.Forms.ToolStripItem.Selected%2A> proprietà per gli elementi in cui <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> è `true`.  
  
     Ciò impedirà è la necessità di sincronizzare le <xref:System.Windows.Forms.ToolStripItem.MouseEnter> e <xref:System.Windows.Forms.ToolStripItem.MouseLeave> eventi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [Panoramica del controllo ToolStrip](toolstrip-control-overview-windows-forms.md)

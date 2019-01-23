---
title: 'Procedura: Rilevare quando il puntatore del Mouse si trova sopra un ToolStripItem'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 20fbc91773f431fc68f606f8aa9f24f4c0cc06bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539597"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a>Procedura: Rilevare quando il puntatore del Mouse si trova sopra un ToolStripItem
Usare la procedura seguente per rilevare quando il puntatore del mouse è posizionato sopra un <xref:System.Windows.Forms.ToolStripItem>.  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a>Per rilevare quando il puntatore si trova sopra un ToolStripItem  
  
-   Usare la <xref:System.Windows.Forms.ToolStripItem.Selected%2A> proprietà per gli elementi in cui <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> è `true`.  
  
     Ciò impedirà è la necessità di sincronizzare le <xref:System.Windows.Forms.ToolStripItem.MouseEnter> e <xref:System.Windows.Forms.ToolStripItem.MouseLeave> eventi.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [Panoramica sul controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)

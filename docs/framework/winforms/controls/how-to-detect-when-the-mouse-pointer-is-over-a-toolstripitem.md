---
title: 'Procedura: Rilevare quando il puntatore del mouse si trova sopra un ToolStripItem'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: f01a9acb3a566be40d65fb075c8487d4e9cb6e73
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623646"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a>Procedura: Rilevare quando il puntatore del mouse si trova sopra un ToolStripItem
Usare la procedura seguente per rilevare quando il puntatore del mouse è posizionato sopra un <xref:System.Windows.Forms.ToolStripItem>.  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a>Per rilevare quando il puntatore si trova sopra un ToolStripItem  
  
- Usare la <xref:System.Windows.Forms.ToolStripItem.Selected%2A> proprietà per gli elementi in cui <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> è `true`.  
  
     Ciò impedirà è la necessità di sincronizzare le <xref:System.Windows.Forms.ToolStripItem.MouseEnter> e <xref:System.Windows.Forms.ToolStripItem.MouseLeave> eventi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [Panoramica sul controllo ToolStrip](toolstrip-control-overview-windows-forms.md)

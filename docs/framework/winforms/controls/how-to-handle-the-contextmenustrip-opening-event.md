---
title: "Procedura: gestire l'evento di apertura ContextMenuStrip"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- context menus [Windows Forms], event handling
- ToolStrip control [Windows Forms]
- event handling [Windows Forms], context menus
- shortcut menus [Windows Forms], event handling
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
ms.openlocfilehash: c5af03f4726063754f81ec9226b4b161599b4121
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531862"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a>Procedura: gestire l'evento di apertura ContextMenuStrip
È possibile personalizzare il comportamento del <xref:System.Windows.Forms.ContextMenuStrip> controllo gestendo il <xref:System.Windows.Forms.ToolStripDropDown.Opening> evento.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come gestire il <xref:System.Windows.Forms.ToolStripDropDown.Opening> evento. Il gestore eventi aggiunge gli elementi in modo dinamico a un <xref:System.Windows.Forms.ContextMenuStrip> controllo. Per l'esempio di codice completo, vedere [procedura: aggiungere dinamicamente elementi ToolStrip](../../../../docs/framework/winforms/controls/how-to-add-toolstrip-items-dynamically.md).  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 Impostare il <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> proprietà `true` per impedire l'apertura del menu.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>  
 <xref:System.Windows.Forms.ToolStripDropDown>  
 [Controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)

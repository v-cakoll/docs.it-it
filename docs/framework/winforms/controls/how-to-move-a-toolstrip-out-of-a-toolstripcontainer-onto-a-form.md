---
title: 'Procedura: Spostare ToolStrip da ToolStripContainer a un Form'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: 4e5c621b9738ce6b5f259425e63a2369556c4ded
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597715"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Procedura: Spostare ToolStrip da ToolStripContainer a un Form
Usare la procedura seguente per spostare un <xref:System.Windows.Forms.ToolStrip> fuori un <xref:System.Windows.Forms.ToolStripContainer> in un form.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Per spostare un controllo ToolStrip da ToolStripContainer a un form  
  
1.  Selezionare <xref:System.Windows.Forms.ToolStrip>.  
  
2.  Taglia il <xref:System.Windows.Forms.ToolStrip> premendo CTRL + X o fare doppio clic il <xref:System.Windows.Forms.ToolStrip> e scegliere **Taglia** dal menu di scelta rapida.  
  
3.  Selezionare il form.  
  
4.  Incollare il <xref:System.Windows.Forms.ToolStrip> premendo CTRL + V oppure scegliere **incollare** dal **modifica** menu.  
  
5.  Impostare il <xref:System.Windows.Forms.ToolStrip.Dock%2A> proprietà del <xref:System.Windows.Forms.ToolStrip> al **Top**.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripContainer>
- [Panoramica sul controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)

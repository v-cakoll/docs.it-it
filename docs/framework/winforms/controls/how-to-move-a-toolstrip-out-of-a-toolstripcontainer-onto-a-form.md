---
title: 'Procedura: Spostare ToolStrip da ToolStripContainer a un modulo'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: 9106a69ea9f28442da6e3270f7cf5abb9374b62d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913657"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Procedura: Spostare ToolStrip da ToolStripContainer a un modulo
Usare la procedura seguente per spostare un <xref:System.Windows.Forms.ToolStrip> fuori un <xref:System.Windows.Forms.ToolStripContainer> in un form.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Per spostare un controllo ToolStrip da ToolStripContainer a un form  
  
1. Selezionare <xref:System.Windows.Forms.ToolStrip>.  
  
2. Taglia il <xref:System.Windows.Forms.ToolStrip> premendo CTRL + X o fare doppio clic il <xref:System.Windows.Forms.ToolStrip> e scegliere **Taglia** dal menu di scelta rapida.  
  
3. Selezionare il form.  
  
4. Incollare il <xref:System.Windows.Forms.ToolStrip> premendo CTRL + V oppure scegliere **incollare** dal **modifica** menu.  
  
5. Impostare il <xref:System.Windows.Forms.ToolStrip.Dock%2A> proprietà del <xref:System.Windows.Forms.ToolStrip> al **Top**.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripContainer>
- [Panoramica sul controllo ToolStrip](toolstrip-control-overview-windows-forms.md)

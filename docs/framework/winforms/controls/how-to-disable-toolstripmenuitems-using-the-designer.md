---
title: 'Procedura: Disabilitare ToolStripMenuItems usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: 9965825458afcd50b29699c3b89ed506078e04d9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59338059"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a>Procedura: Disabilitare ToolStripMenuItems usando la finestra di progettazione
È possibile limitare o estendere i comandi di che un utente può eseguire l'abilitazione e disabilitazione di voci di menu in risposta alle attività dell'utente. Voci di menu sono abilitate per impostazione predefinita quando vengono creati, ma ciò può essere modificato tramite la <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà. È possibile modificare questa proprietà in fase di progettazione nel **proprietà** finestra o a livello di codice mediante l'impostazione nel codice. Per altre informazioni, vedere [Procedura: Disabilitare i ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-disable-a-menu-item-at-design-time"></a>Per disabilitare una voce di menu in fase di progettazione  
  
1. Con la voce di menu selezionata nel form, impostare il <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà `false`.  
  
    > [!TIP]
    >  La voce di menu di primo livello o prima in un menu di disabilitazione disabilita tutte le voci di menu contenute all'interno del menu. La disabilitazione di una voce di menu che contiene voci di sottomenu disabilita in modo analogo, le voci di sottomenu. Se tutti i comandi in un determinato menu non sono disponibili all'utente, viene considerata buona norma di programmazione per nascondere e disabilitare l'intero menu, come questa operazione presenta un'interfaccia utente pulita. Si deve nascondere e disabilitare il menu di scelta, come nascondere da solo non impedisce l'accesso a un comando di menu tramite un tasto di scelta rapida. Impostare il <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà di una voce di menu di primo livello a `false` per nascondere l'intero menu.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Procedura: Nascondere ToolStripMenuItems](how-to-hide-toolstripmenuitems.md)
- [Panoramica sul controllo MenuStrip](menustrip-control-overview-windows-forms.md)

---
title: 'Procedura: nascondere ToolStripMenuItems utilizzando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 37371269ef9db929573efff0a8e62c86a51b2c35
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43423874"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>Procedura: nascondere ToolStripMenuItems utilizzando la finestra di progettazione
Se si nasconde le voci di menu è un modo per controllare l'interfaccia utente (UI) dell'applicazione e limitare i comandi dell'utente. Spesso, è consigliabile nascondere un intero menu quando tutte le voci di menu su di esso non sono disponibili. Evitare distrazioni per l'utente. Inoltre, si potrebbe voler nascondere e disabilitare il menu o la voce di menu, come nascondere da solo non impedisce all'utente di accesso a un comando di menu tramite un tasto di scelta rapida. Per altre informazioni sulla disabilitazione delle voci di menu, vedere [procedura: disabilitare ToolStripMenuItems usando la finestra di progettazione](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>Per nascondere un menu di primo livello e le voci di sottomenu  
  
1.  Selezionare la voce di menu di primo livello e impostata relativi <xref:System.Windows.Forms.ToolStripItem.Visible%2A> oppure <xref:System.Windows.Forms.ToolStripItem.Available%2A> proprietà `false`.  
  
     Quando si nasconde la voce di menu di primo livello, sono nascoste anche tutte le voci di menu all'interno di tale menu. Se si fa clic in una posizione diversa sul <xref:System.Windows.Forms.MenuStrip> dopo l'impostazione <xref:System.Windows.Forms.ToolStripItem.Visible%2A> a `false`, la voce di menu di primo livello intera e voci dei relativi sottomenu scompaiono dal form, così che mostra l'effetto in fase di esecuzione dell'azione. Per visualizzare la voce di menu di primo livello in fase di progettazione, fare clic sui <xref:System.Windows.Forms.MenuStrip> nella **sulla barra dei componenti**, in **struttura documento**, o nella parte superiore della griglia delle proprietà.  
  
> [!NOTE]
>  Raramente sarà necessario nascondere un menu di tutto ad eccezione di menu figlio documenti (MDI) interfaccia multipli in uno scenario di unione.  
  
### <a name="to-hide-a-submenu-item"></a>Per nascondere una voce di sottomenu  
  
1.  Selezionare la voce di sottomenu e impostare relativi <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà `false`.  
  
     Quando si nasconde una voce di sottomenu, rimane visibile sul form in fase di progettazione in modo che è possibile selezionare facilmente per la successiva elaborazione. Tale riga verrà effettivamente nascosta in fase di esecuzione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [Panoramica sul controllo MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [Procedura: Disabilitare i ToolStripMenuItems con la finestra di progettazione](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)

---
title: 'Procedura: Nascondere ToolStripMenuItems usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 0e1cd7d1868adabd4d3eec9510f6ee567ba3867d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966621"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>Procedura: Nascondere ToolStripMenuItems usando la finestra di progettazione
Nascondere le voci di menu consente di controllare l'interfaccia utente dell'applicazione e limitare i comandi dell'utente. Spesso è necessario nascondere un intero menu quando tutte le voci di menu non sono disponibili. Questa operazione presenta un minor numero di distrazioni per l'utente. Inoltre, potrebbe essere necessario nascondere e disabilitare il menu o la voce di menu, perché nascondersi da solo non impedisce all'utente di accedere a un comando di menu utilizzando un tasto di scelta rapida. Per ulteriori informazioni sulla disabilitazione delle voci di menu [, vedere Procedura: Disabilitare ToolStripMenuItems usando la finestra](how-to-disable-toolstripmenuitems-using-the-designer.md)di progettazione.

## <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>Per nascondere un menu di primo livello e le relative voci di sottomenu

1. Selezionare la voce di menu di primo livello e impostare <xref:System.Windows.Forms.ToolStripItem.Visible%2A> la <xref:System.Windows.Forms.ToolStripItem.Available%2A> relativa proprietà `false`o su.

     Quando si nasconde la voce di menu di primo livello, vengono nascoste anche tutte le voci di menu all'interno di tale menu. Se si fa clic in un punto diverso <xref:System.Windows.Forms.MenuStrip> da dopo <xref:System.Windows.Forms.ToolStripItem.Visible%2A> l' `false`impostazione di su, l'intera voce di menu di primo livello e le relative voci di sottomenu scompariranno dal form, in modo da visualizzare l'effetto della fase di esecuzione dell'azione. Per visualizzare la voce di menu di primo livello nascosta in fase di progettazione, fare <xref:System.Windows.Forms.MenuStrip> clic su nella **barra dei componenti**, nella struttura del **documento**o nella parte superiore della griglia delle proprietà.

> [!NOTE]
> Si nasconderà raramente un intero menu eccetto i menu figlio dell'interfaccia a documenti multipli (MDI) in uno scenario di Unione.

## <a name="to-hide-a-submenu-item"></a>Per nascondere una voce di sottomenu

1. Selezionare la voce di sottomenu e impostare <xref:System.Windows.Forms.ToolStripItem.Visible%2A> la relativa `false`proprietà su.

     Quando si nasconde una voce di sottomenu, rimane visibile nel form in fase di progettazione in modo che sia possibile selezionarla facilmente per un ulteriore lavoro. Che verrà nascosta in fase di esecuzione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [Panoramica sul controllo MenuStrip](menustrip-control-overview-windows-forms.md)
- [Procedura: Disabilitare ToolStripMenuItems usando la finestra di progettazione](how-to-disable-toolstripmenuitems-using-the-designer.md)

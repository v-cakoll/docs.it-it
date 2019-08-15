---
title: 'Procedura: Disabilitare ToolStripMenuItems usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: fd80a6543c83ae957cd9c51b068d0702559f0925
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040263"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a>Procedura: Disabilitare ToolStripMenuItems usando la finestra di progettazione
È possibile limitare o ampliare i comandi che un utente può eseguire abilitando e disabilitando le voci di menu in risposta alle attività dell'utente. Le voci di menu sono abilitate per impostazione predefinita al momento della creazione, ma possono essere <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> modificate tramite la proprietà. È possibile modificare questa proprietà in fase di progettazione nella finestra **Proprietà** o a livello di codice impostando tale proprietà nel codice. Per altre informazioni, vedere [Procedura: Disabilitare ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).

## <a name="to-disable-a-menu-item-at-design-time"></a>Per disabilitare una voce di menu in fase di progettazione

1. Con la voce di <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> `false`menu selezionata nel form, impostare la proprietà su.

    > [!TIP]
    >  La disabilitazione della prima o della voce di menu di primo livello in un menu Disattiva tutte le voci di menu contenute nel menu. Analogamente, la disabilitazione di una voce di menu con voci di sottomenu Disabilita le voci di sottomenu. Se tutti i comandi di un determinato menu non sono disponibili per l'utente, viene considerata una procedura di programmazione efficace per nascondere e disabilitare l'intero menu, in quanto presenta un'interfaccia utente pulita. È necessario nascondere e disabilitare il menu, perché nascondersi da solo non impedisce l'accesso a un comando di menu tramite un tasto di scelta rapida. Impostare la <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà di una voce di menu di primo livello `false` su per nascondere l'intero menu.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Procedura: Nascondi ToolStripMenuItems](how-to-hide-toolstripmenuitems.md)
- [Panoramica sul controllo MenuStrip](menustrip-control-overview-windows-forms.md)

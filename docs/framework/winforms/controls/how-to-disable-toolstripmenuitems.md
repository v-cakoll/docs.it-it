---
title: 'Procedura: Disabilitare ToolStripMenuItems'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
ms.openlocfilehash: f86a2934e799e4604693491dacbecc517d44d810
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046218"
---
# <a name="how-to-disable-toolstripmenuitems"></a>Procedura: Disabilitare ToolStripMenuItems
È possibile limitare o ampliare i comandi che un utente può eseguire abilitando e disabilitando le voci di menu in risposta alle attività dell'utente. Le voci di menu sono abilitate per impostazione predefinita al momento della creazione, ma possono essere <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> modificate tramite la proprietà. È possibile modificare questa proprietà in fase di progettazione nella finestra **Proprietà** o a livello di codice impostando tale proprietà nel codice.  
  
### <a name="to-disable-a-menu-item-programmatically"></a>Per disabilitare una voce di menu a livello di codice  
  
- All'interno del metodo in cui si impostano le proprietà della voce di menu, aggiungere <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> il codice `false`su cui impostare la proprietà.  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    > La disabilitazione della prima o della voce di menu di primo livello in un menu nasconde tutte le voci di menu contenute nel menu, ma non le Disabilita. Analogamente, la disabilitazione di una voce di menu con voci di sottomenu nasconde le voci di sottomenu, ma non le Disabilita. Se tutti i comandi di un determinato menu non sono disponibili per l'utente, viene considerata una procedura di programmazione efficace per nascondere e disabilitare l'intero menu, in quanto presenta un'interfaccia utente pulita. È necessario nascondere e disabilitare il menu e disabilitare tutti gli elementi e le voci di sottomenu nel menu, perché la sola maschera non impedisce l'accesso a un comando di menu tramite un tasto di scelta rapida. Impostare la <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà di una voce di menu di primo livello `false` su per nascondere l'intero menu.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Procedura: Nascondi ToolStripMenuItems](how-to-hide-toolstripmenuitems.md)
- [Panoramica sul controllo MenuStrip](menustrip-control-overview-windows-forms.md)

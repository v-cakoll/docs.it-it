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
ms.openlocfilehash: a480cd29eef1a79a69f702eed7cd02c28d7ea3de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59082724"
---
# <a name="how-to-disable-toolstripmenuitems"></a>Procedura: Disabilitare ToolStripMenuItems
È possibile limitare o estendere i comandi di che un utente può eseguire l'abilitazione e disabilitazione di voci di menu in risposta alle attività dell'utente. Voci di menu sono abilitate per impostazione predefinita quando vengono creati, ma ciò può essere modificato tramite la <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà. È possibile modificare questa proprietà in fase di progettazione nel **proprietà** finestra o a livello di codice mediante l'impostazione nel codice.  
  
### <a name="to-disable-a-menu-item-programmatically"></a>Per disabilitare una voce di menu a livello di codice  
  
-   All'interno del metodo in cui si impostano le proprietà della voce di menu, aggiungere il codice per impostare il <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà `false`.  
  
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
    >  Disabilitare la voce di menu di primo livello o prima in un menu nasconde tutte le voci di menu contenute all'interno del menu, ma non li disabilita. Analogamente, la disabilitazione di una voce di menu che contiene voci di sottomenu nasconde le voci di sottomenu, ma non li disabilita. Se tutti i comandi in un determinato menu non sono disponibili all'utente, viene considerata buona norma di programmazione per nascondere e disabilitare l'intero menu, come questa operazione presenta un'interfaccia utente pulita. Si deve nascondere e disabilitare il menu di scelta e disabilitare ogni elemento e una voce di sottomenu del menu, perché nascondere da solo non impedisce l'accesso a un comando di menu tramite un tasto di scelta rapida. Impostare il <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà di una voce di menu di primo livello a `false` per nascondere l'intero menu.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Procedura: Nascondere ToolStripMenuItems](how-to-hide-toolstripmenuitems.md)
- [Panoramica del controllo MenuStrip](menustrip-control-overview-windows-forms.md)

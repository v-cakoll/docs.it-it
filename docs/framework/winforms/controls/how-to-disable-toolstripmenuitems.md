---
title: 'Procedura: disabilitare ToolStripMenuItems'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0432c59979f8f595b481154f5b339e448ee66b06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-disable-toolstripmenuitems"></a>Procedura: disabilitare ToolStripMenuItems
È possibile limitare o ampliare i comandi di che un utente può eseguire mediante l'abilitazione e disabilitazione di voci di menu in risposta alle attività dell'utente. Voci di menu sono attivate per impostazione predefinita quando vengono creati, ma ciò può essere modificata tramite il <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà. È possibile modificare questa proprietà in fase di progettazione nel **proprietà** finestra o a livello di codice mediante l'impostazione nel codice.  
  
### <a name="to-disable-a-menu-item-programmatically"></a>Per disabilitare una voce di menu a livello di codice  
  
-   All'interno del metodo in cui si impostano le proprietà della voce di menu, aggiungere codice per impostare il <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà `false`.  
  
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
    >  La voce di menu prima di primo livello in un menu di disabilitazione nasconde tutte le voci di menu contenute all'interno del menu, ma non li disabilita. Analogamente, la disabilitazione di una voce di menu che contiene voci di sottomenu nasconde le voci di sottomenu, ma non li disabilita. Se non sono disponibili all'utente tutti i comandi di un menu, buona norma di programmazione per nascondere e disabilitare l'intero menu, viene considerato come l'interfaccia utente pulita. Nascondere e disabilitare il menu e disattivare ogni elemento e la voce di sottomenu nel menu, in quanto nasconderlo solamente non impedisce l'accesso a un comando di menu tramite un tasto di scelta rapida. Impostare il <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà di una voce di menu di primo livello per `false` per nascondere l'intero menu.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Procedura: Nascondere ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [Panoramica sul controllo MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)

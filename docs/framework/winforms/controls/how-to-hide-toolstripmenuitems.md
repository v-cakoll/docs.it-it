---
title: 'Procedura: nascondere ToolStripMenuItems'
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
- ToolStripMenuItems [Windows Forms], hiding
- MenuStrip control [Windows Forms], hiding menu items
- menus [Windows Forms], hiding menu items
- menu items [Windows Forms], hiding
- hiding menu items
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7cb24fd36bdee76fa80a87d48f41b72f01c8f263
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-toolstripmenuitems"></a>Procedura: nascondere ToolStripMenuItems
Nascondere le voci di menu è un modo per controllare l'interfaccia utente dell'applicazione e limitare i comandi dell'utente. Spesso, è possibile nascondere un intero menu quando tutte le voci di menu su di esso non sono disponibili. Distrazioni per l'utente. Inoltre, potrebbe essere da nascondere e disabilitare il menu o una voce di menu come nasconderlo solamente non impedire all'utente l'accesso a un comando di menu con un tasto di scelta rapida.  
  
### <a name="to-hide-any-menu-item-programmatically"></a>Per nascondere un elemento a livello di codice  
  
-   All'interno del metodo in cui si impostano le proprietà della voce di menu, aggiungere codice per impostare il <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà `false`.  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 [Panoramica sul controllo MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [Procedura: Disabilitare ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)

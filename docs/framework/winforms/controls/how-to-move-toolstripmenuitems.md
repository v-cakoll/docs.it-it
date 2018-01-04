---
title: 'Procedura: spostare i ToolStripMenuItems'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfc1cb718b3738ac93b284b0b438b08d1e721349
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-move-toolstripmenuitems"></a>Procedura: spostare i ToolStripMenuItems
In fase di progettazione, è possibile spostare menu di primo livello e i relativi elementi in un'altra posizione <xref:System.Windows.Forms.MenuStrip>. È inoltre possibile spostare singole voci di menu tra menu di primo livello o modificare la posizione delle voci di menu all'interno di un menu.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a>Per spostare un menu di primo livello e le voci di menu in un'altra posizione di primo livello  
  
1.  Fare clic e tenere premuto il pulsante sinistro del mouse sul menu che si desidera spostare.  
  
2.  Trascinare il punto di inserimento per il menu di primo livello che precede la nuova posizione e rilasciare il pulsante sinistro del mouse.  
  
     Il menu selezionato viene spostato a destra del punto di inserimento.  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a>Per spostare un menu di primo livello e i relativi elementi in un percorso di elenco a discesa  
  
1.  Fare clic sul menu che si desidera spostare e premere CTRL + X, o il menu di scelta rapida e selezionare **Taglia** dal menu di scelta rapida.  
  
2.  Nel menu di primo livello di destinazione, fare clic sulla voce di menu sopra la nuova posizione individuata e premere CTRL + V, o la voce di menu sopra la nuova posizione di mouse e scegliere **Incolla** dal menu di scelta rapida.  
  
     Il menu che si taglia viene inserito dopo la voce di menu selezionata.  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a>Per spostare una voce di menu all'interno di un menu utilizzando l'Editor della raccolta Items  
  
1.  Menu di scelta rapida che contiene la voce di menu che si desidera spostare.  
  
2.  Nel menu di scelta rapida, scegliere **Modifica DropDownItems**.  
  
3.  Nel **Editor della raccolta Items**, fare clic sulla voce di menu che si desidera spostare.  
  
4.  Fare clic sui tasti freccia su e giù per spostare la voce di menu all'interno del menu.  
  
5.  Fare clic su **OK**.  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a>Per spostare una voce di menu all'interno di un menu utilizzando la tastiera  
  
1.  Premere e tenere premuto il tasto ALT.  
  
2.  Fare clic e tenere premuto il pulsante sinistro del mouse sulla voce di menu che si desidera spostare.  
  
3.  Trascinare la voce di menu nella nuova posizione e rilasciare il pulsante sinistro del mouse.  
  
### <a name="to-move-a-menu-item-to-another-menu"></a>Per spostare una voce di menu in un altro menu  
  
1.  Fare clic sulla voce di menu che si desidera spostare e premere CTRL + X, o la voce di menu e scegliere **Taglia** dal menu di scelta rapida.  
  
2.  Fare clic sul menu che conterrà la voce di menu che si taglia.  
  
3.  Fare clic sulla voce di menu che precede la nuova posizione individuata e premere CTRL + V oppure fare clic sulla voce di menu che precede la nuova posizione e selezionare **Incolla** dal menu di scelta rapida.  
  
     La voce di menu che si taglia viene inserita dopo la voce di menu selezionata.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Panoramica sul controllo MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)

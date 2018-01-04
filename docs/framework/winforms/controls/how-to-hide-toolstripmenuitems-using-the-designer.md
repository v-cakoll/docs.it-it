---
title: 'Procedura: nascondere ToolStripMenuItems utilizzando la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5ac840953e34ac6726bb1c240c062d0f17b8cb71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>Procedura: nascondere ToolStripMenuItems utilizzando la finestra di progettazione
Nascondere le voci di menu è un modo per controllare l'interfaccia utente (UI) dell'applicazione e limitare i comandi dell'utente. Spesso, è possibile nascondere un intero menu quando tutte le voci di menu su di esso non sono disponibili. Distrazioni per l'utente. Inoltre, potrebbe essere da nascondere e disabilitare il menu o una voce di menu come nasconderlo solamente non impedire all'utente l'accesso a un comando di menu con un tasto di scelta rapida. Per ulteriori informazioni sulla disabilitazione di voci di menu, vedere [procedura: disabilitare ToolStripMenuItems usando la finestra di progettazione](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>Per nascondere un menu di primo livello e delle relative voci di sottomenu  
  
1.  Selezionare la voce di menu di primo livello e impostare il relativo <xref:System.Windows.Forms.ToolStripItem.Visible%2A> o <xref:System.Windows.Forms.ToolStripItem.Available%2A> proprietà `false`.  
  
     Quando si nasconde la voce di menu di primo livello, sono nascoste anche tutte le voci di menu all'interno di tale menu. Se si fa clic in una posizione diversa sul <xref:System.Windows.Forms.MenuStrip> dopo l'impostazione <xref:System.Windows.Forms.ToolStripItem.Visible%2A> a `false`, la voce di menu di primo livello intero e relative voci di sottomenu vengono rimosse dal form, così che mostra l'effetto in fase di esecuzione dell'azione. Per visualizzare la voce di menu di primo livello in fase di progettazione, fare clic su di <xref:System.Windows.Forms.MenuStrip> nel **sulla barra dei componenti**nella **struttura documento**, o nella parte superiore della griglia delle proprietà.  
  
> [!NOTE]
>  Raramente sarà necessario nascondere un intero menu ad eccezione di più i menu figlio MDI (interfaccia) documento in uno scenario di unione.  
  
### <a name="to-hide-a-submenu-item"></a>Per nascondere una voce di sottomenu  
  
1.  Selezionare la voce di sottomenu e impostare il relativo <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà `false`.  
  
     Quando si nasconde una voce di sottomenu, rimane visibile sul form in fase di progettazione in modo che è possibile selezionare con facilità per ulteriore lavoro. Verranno effettivamente nascoste in fase di esecuzione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [Panoramica sul controllo MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [Procedura: Disabilitare i ToolStripMenuItems con la finestra di progettazione](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)

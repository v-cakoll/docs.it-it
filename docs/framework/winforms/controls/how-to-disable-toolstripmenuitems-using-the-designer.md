---
title: 'Procedura: disabilitare i ToolStripMenuItems con la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f704e99622900d8c37c8ddd5054a3c5ad920bc6b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a>Procedura: disabilitare i ToolStripMenuItems con la finestra di progettazione
È possibile limitare o ampliare i comandi di che un utente può eseguire mediante l'abilitazione e disabilitazione di voci di menu in risposta alle attività dell'utente. Voci di menu sono attivate per impostazione predefinita quando vengono creati, ma ciò può essere modificata tramite il <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà. È possibile modificare questa proprietà in fase di progettazione nel **proprietà** finestra o a livello di codice mediante l'impostazione nel codice. Per ulteriori informazioni, vedere [procedura: disabilitare ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-disable-a-menu-item-at-design-time"></a>Per disabilitare una voce di menu in fase di progettazione  
  
1.  La voce di menu selezionata sul form, impostare il <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà `false`.  
  
    > [!TIP]
    >  La voce di menu prima di primo livello in un menu di disabilitazione disabilita tutte le voci di menu contenute all'interno del menu. La disabilitazione di una voce di menu che contiene voci di sottomenu disabilita in modo analogo, le voci di sottomenu. Se non sono disponibili all'utente tutti i comandi di un menu, buona norma di programmazione per nascondere e disabilitare l'intero menu, viene considerato come l'interfaccia utente pulita. È necessario nascondere e disabilitare il menu, come nasconderlo solamente non impedisce l'accesso a un comando di menu tramite un tasto di scelta rapida. Impostare il <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà di una voce di menu di primo livello per `false` per nascondere l'intero menu.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Procedura: Nascondere ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [Panoramica sul controllo MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)

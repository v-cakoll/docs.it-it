---
title: 'Procedura: Associare un menu di scelta rapida a un TreeNode usando la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3acc1a731fa584a17c8a96f8a02986a504cd302d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a>Procedura: Associare un menu di scelta rapida a un TreeNode usando la finestra di progettazione
Windows Form <xref:System.Windows.Forms.TreeView> controllo Visualizza una gerarchia di nodi, simile ai file e cartelle vengono visualizzati nel riquadro sinistro della funzionalità Esplora risorse nei sistemi operativi Windows. Impostando il <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> proprietà, è possibile fornire operazioni sensibili al contesto per l'utente quando sono destro la <xref:System.Windows.Forms.TreeView> controllo. Associando un <xref:System.Windows.Forms.ContextMenuStrip> componente con singoli <xref:System.Windows.Forms.TreeNode> elementi, è possibile aggiungere un livello di funzionalità del menu di scelta rapida per personalizzato il <xref:System.Windows.Forms.TreeView> controlli.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a>Per associare un menu di scelta rapida a un TreeNode in fase di progettazione  
  
1.  Aggiungere un <xref:System.Windows.Forms.TreeView> il controllo al form e quindi aggiungere i nodi per il <xref:System.Windows.Forms.TreeView> in base alle esigenze. Per ulteriori informazioni, vedere [procedura: aggiungere e rimuovere nodi con il controllo TreeView Windows Form](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).  
  
2.  Aggiungere un <xref:System.Windows.Forms.ContextMenuStrip> componente al form, quindi aggiungere le voci di menu al menu di scelta rapida che rappresentano le operazioni a livello di nodo che si desidera rendere disponibili in fase di esecuzione. Per ulteriori informazioni, vedere [procedura: aggiungere voci di Menu a un ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md).  
  
3.  Riaprire il **Editor TreeNode** la finestra di dialogo per la <xref:System.Windows.Forms.TreeView> di controllo, selezionare il nodo da modificare e impostare il relativo <xref:System.Windows.Forms.ContextMenuStrip> proprietà per il menu di scelta rapida che è stato aggiunto.  
  
4.  Quando questa proprietà è impostata, verrà visualizzato il menu di scelta rapida si fa clic con il pulsante destro del nodo.  
  
     Inoltre, è possibile scrivere codice per gestire il <xref:System.Windows.Forms.ToolStripItem.Click> gli eventi per queste voci di menu.  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [Panoramica sul controllo TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [Controllo ContextMenuStrip](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)

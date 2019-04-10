---
title: 'Procedura: Associare un menu di scelta rapida a un TreeNode usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: 9be633d14429bc2ceda1f0db2ff09252d55d5dd5
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337448"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a>Procedura: Associare un menu di scelta rapida a un TreeNode usando la finestra di progettazione
I moduli di Windows <xref:System.Windows.Forms.TreeView> controllo Visualizza una gerarchia di nodi, simile ai file e cartelle vengono visualizzati nel riquadro a sinistra della funzionalità di Windows Explorer in sistemi operativi Windows. Impostando il <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> proprietà, è possibile fornire operazioni sensibili al contesto per l'utente quando sono fare doppio clic il <xref:System.Windows.Forms.TreeView> controllo. Associando un <xref:System.Windows.Forms.ContextMenuStrip> componenti con singolo <xref:System.Windows.Forms.TreeNode> gli elementi, è possibile aggiungere un livello di funzionalità dal menu di scelta rapida per personalizzato di <xref:System.Windows.Forms.TreeView> controlli.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a>Per associare un menu di scelta rapida a un TreeNode in fase di progettazione  
  
1. Aggiungere un <xref:System.Windows.Forms.TreeView> controllo al form e quindi aggiungere nodi di <xref:System.Windows.Forms.TreeView> in base alle esigenze. Per altre informazioni, vedere [Procedura: Aggiungere e rimuovere nodi tramite il Windows Form controllo TreeView](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).  
  
2. Aggiungere un <xref:System.Windows.Forms.ContextMenuStrip> al form, quindi aggiungere le voci di menu al menu di scelta rapida che rappresentano operazioni a livello di nodo che si desidera rendere disponibili in fase di esecuzione. Per altre informazioni, vedere [Procedura: Aggiungere le voci di Menu a un ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md).  
  
3. Riaprire il **Editor TreeNode** finestra di dialogo per il <xref:System.Windows.Forms.TreeView> controllare, selezionare il nodo da modificare e impostare relativo <xref:System.Windows.Forms.ContextMenuStrip> proprietà per il menu di scelta rapida che è stato aggiunto.  
  
4. Quando questa proprietà è impostata, verrà visualizzato il menu di scelta rapida si fa clic con il pulsante destro del nodo.  
  
     Inoltre, è opportuno scrivere codice per gestire il <xref:System.Windows.Forms.ToolStripItem.Click> gli eventi per queste voci di menu.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo TreeView](treeview-control-windows-forms.md)
- [Panoramica del controllo TreeView](treeview-control-overview-windows-forms.md)
- [Controllo ContextMenuStrip](contextmenustrip-control.md)

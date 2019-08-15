---
title: 'Procedura: Associare un menu di scelta rapida a un TreeNode usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: eb3240d35309e03aa8ce949b9c5000f8581d2c2f
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040452"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a>Procedura: Associare un menu di scelta rapida a un TreeNode usando la finestra di progettazione
Il controllo <xref:System.Windows.Forms.TreeView> Windows Forms Visualizza una gerarchia di nodi, in modo analogo ai file e alle cartelle visualizzati nel riquadro sinistro della funzionalità Esplora risorse nei sistemi operativi Windows. Impostando la <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> proprietà, è possibile fornire all'utente operazioni sensibili al contesto facendo clic con il pulsante destro del <xref:System.Windows.Forms.TreeView> mouse sul controllo. Associando un <xref:System.Windows.Forms.ContextMenuStrip> componente a singoli <xref:System.Windows.Forms.TreeNode> elementi, è possibile aggiungere un livello personalizzato di funzionalità del menu di <xref:System.Windows.Forms.TreeView> scelta rapida ai controlli.

## <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a>Per associare un menu di scelta rapida a un oggetto TreeNode in fase di progettazione

1. Aggiungere un <xref:System.Windows.Forms.TreeView> controllo al form e quindi aggiungere nodi <xref:System.Windows.Forms.TreeView> a in base alle esigenze. Per altre informazioni, vedere [Procedura: Aggiungere e rimuovere nodi con il controllo](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)TreeView Windows Forms.

2. Aggiungere un <xref:System.Windows.Forms.ContextMenuStrip> componente al form, quindi aggiungere voci di menu al menu di scelta rapida che rappresentano le operazioni a livello di nodo che si desidera rendere disponibili in fase di esecuzione. Per altre informazioni, vedere [Procedura: Aggiungere voci di menu a un](how-to-add-menu-items-to-a-contextmenustrip.md)ContextMenuStrip.

3. Riaprire la finestra di dialogo **Editor TreeNode** per <xref:System.Windows.Forms.TreeView> il controllo, selezionare il nodo da modificare e impostare la <xref:System.Windows.Forms.ContextMenuStrip> relativa proprietà sul menu di scelta rapida aggiunto.

4. Quando questa proprietà è impostata, il menu di scelta rapida viene visualizzato quando si fa clic con il pulsante destro del mouse sul nodo.

     Inoltre, sarà necessario scrivere il codice per gestire gli <xref:System.Windows.Forms.ToolStripItem.Click> eventi per queste voci di menu.

## <a name="see-also"></a>Vedere anche

- [Controllo TreeView](treeview-control-windows-forms.md)
- [Panoramica sul controllo TreeView](treeview-control-overview-windows-forms.md)
- [Controllo ContextMenuStrip](contextmenustrip-control.md)

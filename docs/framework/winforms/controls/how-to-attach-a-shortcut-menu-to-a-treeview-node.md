---
title: 'Procedura: associare un menu di scelta rapida a un nodo di TreeView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
ms.openlocfilehash: 737e74184b0763ed84b4e585f2508d69944d0e77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a>Procedura: associare un menu di scelta rapida a un nodo di TreeView
Windows Form <xref:System.Windows.Forms.TreeView> controllo Visualizza una gerarchia di nodi, simile ai file e cartelle vengono visualizzati nel riquadro sinistro della finestra di Esplora risorse. Impostando il <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> proprietà, è possibile fornire operazioni sensibili al contesto per l'utente quando sono destro la <xref:System.Windows.Forms.TreeView> controllo. Associando un <xref:System.Windows.Forms.ContextMenuStrip> componente con singoli <xref:System.Windows.Forms.TreeNode> elementi, è possibile aggiungere un livello di funzionalità del menu di scelta rapida per personalizzato il <xref:System.Windows.Forms.TreeView> controlli.  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a>Per associare un menu di scelta rapida a un TreeNode a livello di codice  
  
1.  Creare un'istanza di un <xref:System.Windows.Forms.TreeView> di controllo con le impostazioni delle proprietà appropriata, creare una radice <xref:System.Windows.Forms.TreeNode>, quindi aggiungere i sottonodi.  
  
2.  Creare un'istanza di un <xref:System.Windows.Forms.ContextMenuStrip> componente, quindi aggiungere un <xref:System.Windows.Forms.ToolStripMenuItem> per ogni operazione che si desidera rendere disponibili in fase di esecuzione.  
  
3.  Impostare il <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> proprietà del appropriato <xref:System.Windows.Forms.TreeNode> al menu di scelta rapida creato.  
  
4.  Quando questa proprietà è impostata, verrà visualizzato il menu di scelta rapida si fa clic con il pulsante destro del nodo.  
  
 L'esempio di codice seguente viene creato un basic <xref:System.Windows.Forms.TreeView> e <xref:System.Windows.Forms.ContextMenuStrip> associato alla radice <xref:System.Windows.Forms.TreeNode> del <xref:System.Windows.Forms.TreeView>. È necessario personalizzare le opzioni di menu in base a quelle di <xref:System.Windows.Forms.TreeView> si sta sviluppando. Inoltre, è possibile scrivere codice per gestire il <xref:System.Windows.Forms.ToolStripItem.Click> gli eventi per queste voci di menu.  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [Controllo TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)

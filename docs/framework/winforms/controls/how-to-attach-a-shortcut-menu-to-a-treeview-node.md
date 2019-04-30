---
title: 'Procedura: Associare un menu di scelta rapida a un nodo di TreeView'
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
ms.openlocfilehash: f818cccb3103866af993f1aff527a9c1a7c82109
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053015"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a>Procedura: Associare un menu di scelta rapida a un nodo di TreeView
I moduli di Windows <xref:System.Windows.Forms.TreeView> controllo Visualizza una gerarchia di nodi, simile ai file e cartelle vengono visualizzati nel riquadro a sinistra di Windows Explorer. Impostando il <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> proprietà, è possibile fornire operazioni sensibili al contesto per l'utente quando sono fare doppio clic il <xref:System.Windows.Forms.TreeView> controllo. Associando un <xref:System.Windows.Forms.ContextMenuStrip> componenti con singolo <xref:System.Windows.Forms.TreeNode> gli elementi, è possibile aggiungere un livello di funzionalità dal menu di scelta rapida per personalizzato di <xref:System.Windows.Forms.TreeView> controlli.  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a>Per associare un menu di scelta rapida a un TreeNode a livello di codice  
  
1. Creare un'istanza di un <xref:System.Windows.Forms.TreeView> controllo con le impostazioni delle proprietà appropriata, creare una radice <xref:System.Windows.Forms.TreeNode>e quindi aggiungere i sottonodi.  
  
2. Creare un'istanza di un <xref:System.Windows.Forms.ContextMenuStrip> componente, quindi aggiungere un <xref:System.Windows.Forms.ToolStripMenuItem> per ogni operazione che si desidera rendere disponibili in fase di esecuzione.  
  
3. Impostare il <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> proprietà del appropriato <xref:System.Windows.Forms.TreeNode> al menu di scelta rapida si crea.  
  
4. Quando questa proprietà è impostata, verrà visualizzato il menu di scelta rapida si fa clic con il pulsante destro del nodo.  
  
 L'esempio di codice seguente viene creata una semplice <xref:System.Windows.Forms.TreeView> e <xref:System.Windows.Forms.ContextMenuStrip> associato alla radice <xref:System.Windows.Forms.TreeNode> del <xref:System.Windows.Forms.TreeView>. È necessario personalizzare le opzioni di menu in base a quelle di <xref:System.Windows.Forms.TreeView> si sta sviluppando. Inoltre, è opportuno scrivere codice per gestire il <xref:System.Windows.Forms.ToolStripItem.Click> gli eventi per queste voci di menu.  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ContextMenuStrip>
- [Controllo TreeView](treeview-control-windows-forms.md)

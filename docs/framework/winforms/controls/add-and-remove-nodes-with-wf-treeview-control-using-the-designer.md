---
title: Aggiungere e rimuovere nodi con il controllo TreeView usando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 7edf09539719ec76fa3f650254c5c84ff0bc3af7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732245"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>Procedura: aggiungere e rimuovere nodi nel controllo TreeView Windows Form mediante la finestra di progettazione

Poiché il controllo Windows Forms <xref:System.Windows.Forms.TreeView> Visualizza i nodi in modo gerarchico, quando si aggiunge un nodo è necessario prestare attenzione a ciò che è il nodo padre.

Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.TreeView>. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-add-or-remove-nodes-in-the-designer"></a>Per aggiungere o rimuovere nodi nella finestra di progettazione

1. Selezionare il controllo <xref:System.Windows.Forms.TreeView>.

2. Nella finestra **Proprietà** fare clic sui **puntini** di sospensione (![pulsante con i puntini di sospensione (...) nel pulsante finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà <xref:System.Windows.Forms.TreeView.Nodes%2A>.

     Viene visualizzato l' **Editor TreeNode** .

3. Per aggiungere nodi, è necessario che esista un nodo radice. Se non è presente, è necessario innanzitutto aggiungere una radice facendo clic sul pulsante **Aggiungi radice** . È quindi possibile aggiungere nodi figlio selezionando la radice o qualsiasi altro nodo e facendo clic sul pulsante **Aggiungi figlio** .

4. Per eliminare i nodi, selezionare il nodo da eliminare, quindi fare clic sul pulsante **Elimina** .

## <a name="see-also"></a>Vedere anche

- [Controllo TreeView](treeview-control-windows-forms.md)
- [Panoramica sul controllo TreeView](treeview-control-overview-windows-forms.md)
- [Procedura: Impostare icone per il controllo TreeView di Windows Form](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Form](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Procedura: Individuare il nodo di TreeView scelto](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)](add-custom-information-to-a-treeview-or-listview-control-wf.md)

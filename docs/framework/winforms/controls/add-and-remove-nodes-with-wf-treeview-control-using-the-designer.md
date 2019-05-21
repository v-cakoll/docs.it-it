---
title: 'Procedura: Aggiungere e rimuovere nodi tramite il controllo TreeView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 71ada3235343aa7e014e12ebf5b367ec744b00d3
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959668"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>Procedura: Aggiungere e rimuovere nodi tramite il controllo TreeView di Windows Forms usando la finestra di progettazione

Poiché il Windows Form <xref:System.Windows.Forms.TreeView> controllo consente di visualizzare i nodi in modo gerarchico, quando si aggiunge un nodo è necessario prestare attenzione a ciò che è il relativo nodo padre.

La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.TreeView> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).

> [!NOTE]
> Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).

### <a name="to-add-or-remove-nodes-in-the-designer"></a>Per aggiungere o rimuovere nodi nella finestra di progettazione

1. Selezionare il controllo <xref:System.Windows.Forms.TreeView>.

2. Nel **delle proprietà** finestra, fare clic sul **puntini di sospensione** (![The puntini di sospensione nella finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto al <xref:System.Windows.Forms.TreeView.Nodes%2A> proprietà .

     Il **Editor objektu TreeNode** viene visualizzata.

3. Per aggiungere nodi, deve esistere un nodo radice; Se non ne esiste, è necessario aggiungere innanzitutto una radice facendo il **radice aggiungere** pulsante. È quindi possibile aggiungere i nodi figlio, selezionando la radice o qualsiasi altro nodo e scegliendo il **Aggiungi figlio** pulsante.

4. Per eliminare i nodi, selezionare il nodo da eliminare e quindi scegliere il **eliminare** pulsante.

## <a name="see-also"></a>Vedere anche

- [Controllo TreeView](treeview-control-windows-forms.md)
- [Panoramica sul controllo TreeView](treeview-control-overview-windows-forms.md)
- [Procedura: Impostare icone per il controllo TreeView di Windows Form](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Form](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Procedura: Individuare il nodo di TreeView scelto](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)](add-custom-information-to-a-treeview-or-listview-control-wf.md)

---
title: Cenni preliminari sul controllo TreeView
ms.date: 03/30/2017
f1_keywords:
- TreeView
helpviewer_keywords:
- TreeView control [Windows Forms], about TreeView control
ms.assetid: 0ece823a-9508-478a-bbdb-7d7c3bae51d5
ms.openlocfilehash: 44b5e27273d122f38ea00e009302d427305977a3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743214"
---
# <a name="treeview-control-overview-windows-forms"></a>Cenni preliminari sul controllo TreeView (Windows Form)

Il controllo <xref:System.Windows.Forms.TreeView> di Windows Form consente di visualizzare una gerarchia di nodi, nello stesso modo in cui file e cartelle vengono visualizzati nel riquadro sinistro della funzionalità Esplora risorse in un sistema operativo Windows. Ogni nodo nella visualizzazione albero potrebbe contenere altri nodi, denominati *nodi figlio*. I nodi padre, o i nodi che contengono i nodi figlio, possono essere visualizzati in forma espansa o compressa. Nella visualizzazione albero, accanto ai nodi possono essere presenti anche caselle di controllo se la proprietà <xref:System.Windows.Forms.TreeView.CheckBoxes%2A> della visualizzazione albero viene impostata su `true`. È quindi possibile selezionare o cancellare i nodi a livello di codice impostando la proprietà <xref:System.Windows.Forms.TreeNode.Checked%2A> del nodo su `true` o `false`.

## <a name="key-properties"></a>Proprietà chiave

Le proprietà chiave del controllo <xref:System.Windows.Forms.TreeView> sono <xref:System.Windows.Forms.TreeView.Nodes%2A> e <xref:System.Windows.Forms.TreeView.SelectedNode%2A>. La proprietà <xref:System.Windows.Forms.TreeView.Nodes%2A> contiene l'elenco dei nodi di primo livello nella visualizzazione albero. La proprietà <xref:System.Windows.Forms.TreeView.SelectedNode%2A> consente di impostare il nodo attualmente selezionato. Accanto ai nodi è possibile visualizzare icone. Il controllo usa le immagini della classe <xref:System.Windows.Forms.ImageList> indicate nella proprietà <xref:System.Windows.Forms.TreeView.ImageList%2A> della visualizzazione struttura ad albero. La proprietà <xref:System.Windows.Forms.TreeView.ImageIndex%2A> consente di impostare l'immagine predefinita per i nodi nella visualizzazione albero. Per altre informazioni sulla visualizzazione delle immagini, vedere [procedura: impostare icone per il controllo TreeView Windows Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md). Se si usa Visual Studio 2005, è possibile accedere a un'ampia libreria di immagini standard che è possibile usare con il controllo <xref:System.Windows.Forms.TreeView>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TreeView>
- [Controllo TreeView](treeview-control-windows-forms.md)
- [Procedura: Impostare icone per il controllo TreeView di Windows Form](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Procedura: Aggiungere e rimuovere nodi tramite il controllo TreeView di Windows Form](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Form](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Procedura: Individuare il nodo di TreeView scelto](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)](add-custom-information-to-a-treeview-or-listview-control-wf.md)

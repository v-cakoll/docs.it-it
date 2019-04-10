---
title: 'Procedura: Impostare icone per il controllo TreeView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: 1a857aade86d2366bb68ce14d716b3ce532ecb05
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59328413"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>Procedura: Impostare icone per il controllo TreeView di Windows Forms
I moduli di Windows <xref:System.Windows.Forms.TreeView> controllo può visualizzare le icone accanto a ogni nodo. Le icone vengono posizionate a sinistra del testo del nodo. Per visualizzare queste icone, è necessario associare la visualizzazione struttura ad albero con un <xref:System.Windows.Forms.ImageList> controllo. Per altre informazioni sugli elenchi di immagini, vedere [componente ImageList](imagelist-component-windows-forms.md) e [come: Aggiungere o rimuovere immagini tramite il Windows Form componente ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
> [!NOTE]
>  Un bug in Microsoft .NET Framework versione 1.1 impedisce le immagini nei <xref:System.Windows.Forms.TreeView> nodi quando l'applicazione chiama <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. Per risolvere questo errore, chiamare <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> nella `Main` metodo immediatamente dopo la chiamata <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>. Questo bug è stato risolto in [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
### <a name="to-display-images-in-a-tree-view"></a>Per visualizzare le immagini in una visualizzazione albero  
  
1. Impostare il <xref:System.Windows.Forms.TreeView> del controllo <xref:System.Windows.Forms.TreeView.ImageList%2A> proprietà esistente <xref:System.Windows.Forms.ImageList> controllo da usare.  
  
     Queste proprietà possono essere impostate nella finestra di progettazione con la finestra proprietà o nel codice.  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. Impostare il nodo <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> e <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> proprietà. Il <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> proprietà determina l'immagine visualizzata per gli stati di normale ed espanso del nodo e il <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> proprietà determina l'immagine visualizzata per lo stato del nodo selezionato.  
  
     Queste proprietà possono essere impostate nel codice o tramite l'Editor TreeNode. Per aprire l'Editor objektu TreeNode, fare clic sui puntini di sospensione ( ![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.TreeView.Nodes%2A> proprietà nella finestra Proprietà.  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica del controllo TreeView](treeview-control-overview-windows-forms.md)
- [Procedura: Aggiungere e rimuovere nodi tramite il controllo TreeView di Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Procedura: Individuare il nodo di TreeView scelto](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)

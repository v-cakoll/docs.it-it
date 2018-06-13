---
title: 'Procedura: impostare icone per il controllo TreeView Windows Form'
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
ms.openlocfilehash: b732aa510be22f3cbdc5197574f1e2a825c35df4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536485"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>Procedura: impostare icone per il controllo TreeView Windows Form
Windows Form <xref:System.Windows.Forms.TreeView> controllo può visualizzare icone accanto a ogni nodo. Le icone vengono posizionate immediatamente a sinistra del testo del nodo. Per visualizzare queste icone, è necessario associare la visualizzazione albero con un <xref:System.Windows.Forms.ImageList> controllo. Per ulteriori informazioni sugli elenchi di immagini, vedere [componente ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) e [procedura: aggiungere o rimuovere immagini con il componente ImageList di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
> [!NOTE]
>  Un bug in Microsoft .NET Framework versione 1.1 impedisce immagini nei <xref:System.Windows.Forms.TreeView> nodi quando l'applicazione chiama <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. Per risolvere questo errore, chiamare <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> nel `Main` metodo immediatamente dopo la chiamata <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>. Questo bug è stato risolto in [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
### <a name="to-display-images-in-a-tree-view"></a>Per visualizzare le immagini in una visualizzazione albero  
  
1.  Impostare il <xref:System.Windows.Forms.TreeView> del controllo <xref:System.Windows.Forms.TreeView.ImageList%2A> proprietà esistente <xref:System.Windows.Forms.ImageList> controllo che si desidera utilizzare.  
  
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
  
2.  Impostare il nodo <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> e <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> proprietà. Il <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> proprietà determina l'immagine visualizzata per gli stati del nodo normale ed espanso e <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> proprietà determina l'immagine visualizzata per lo stato del nodo selezionato.  
  
     Queste proprietà possono essere impostate nel codice o tramite l'Editor TreeNode. Per aprire l'Editor TreeNode, fare clic sul pulsante con puntini di sospensione ( ![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.TreeView.Nodes%2A> proprietà nella finestra Proprietà.  
  
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
 [Panoramica sul controllo TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [Procedura: Aggiungere e rimuovere nodi tramite il controllo TreeView di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Form](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [Procedura: Individuare il nodo di TreeView scelto](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)

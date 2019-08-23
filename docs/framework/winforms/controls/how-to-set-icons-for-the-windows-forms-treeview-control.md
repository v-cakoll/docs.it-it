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
ms.openlocfilehash: 451f9ab2b35ad1fbbe9401dacbc8aab44e302701
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909802"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>Procedura: Impostare icone per il controllo TreeView di Windows Forms
Il controllo <xref:System.Windows.Forms.TreeView> Windows Forms può visualizzare le icone accanto a ogni nodo. Le icone vengono posizionate all'estrema sinistra del testo del nodo. Per visualizzare queste icone, è necessario associare la visualizzazione ad albero a <xref:System.Windows.Forms.ImageList> un controllo. Per ulteriori informazioni sugli elenchi di immagini, vedere [componente ImageList](imagelist-component-windows-forms.md) e [procedura: Aggiungere o rimuovere immagini con il componente](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)Windows Forms ImageList.  
  
> [!NOTE]
> Un bug in Microsoft .NET Framework versione 1,1 impedisce che le immagini vengano visualizzate <xref:System.Windows.Forms.TreeView> nei nodi quando l'applicazione <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>chiama. Per ovviare a questo bug, <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> chiamare nel `Main` metodo immediatamente dopo la <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>chiamata a. Questo bug è stato risolto in .NET Framework 2,0.  
  
### <a name="to-display-images-in-a-tree-view"></a>Per visualizzare le immagini in una visualizzazione albero  
  
1. Impostare la <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.TreeView.ImageList%2A> proprietà del controllo sul controllo esistente <xref:System.Windows.Forms.ImageList> che si desidera utilizzare.  
  
     È possibile impostare queste proprietà nella finestra di progettazione con il Finestra Proprietà o nel codice.  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. Impostare le proprietà <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> e <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> del nodo. La <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> proprietà determina l'immagine visualizzata per gli stati normali e espansi del nodo e la <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> proprietà determina l'immagine visualizzata per lo stato selezionato del nodo.  
  
     Queste proprietà possono essere impostate nel codice o nell'editor di TreeNode. Per aprire l'editor di TreeNode, fare clic sul pulsante ![con i puntini di sospensione (il pulsante con i puntini di sospensione](./media/visual-studio-ellipsis-button.png)(... <xref:System.Windows.Forms.TreeView.Nodes%2A> ) nella finestra proprietà di Visual Studio.) accanto alla proprietà nell'finestra Proprietà.  
  
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

- [Panoramica sul controllo TreeView](treeview-control-overview-windows-forms.md)
- [Procedura: Aggiungere e rimuovere nodi con il controllo TreeView Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Procedura: Scorre tutti i nodi di un controllo TreeView Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Procedura: Determinare il nodo TreeView selezionato](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)

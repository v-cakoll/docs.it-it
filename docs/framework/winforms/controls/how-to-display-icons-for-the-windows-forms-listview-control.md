---
title: 'Procedura: visualizzare icone per il controllo ListView Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 0e597ed182739947014b4f405ee2dc3149b62849
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533604"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a>Procedura: visualizzare icone per il controllo ListView Windows Form
Windows Form <xref:System.Windows.Forms.ListView> controllo può visualizzare le icone da tre elenchi di immagini. Le visualizzazioni elenco e dettagli SmallIcon visualizzano immagini dall'elenco di immagini specificato nella <xref:System.Windows.Forms.ListView.SmallImageList%2A> proprietà. La visualizzazione LargeIcon visualizza immagini dall'elenco di immagini specificato nella <xref:System.Windows.Forms.ListView.LargeImageList%2A> proprietà. Una visualizzazione elenco può anche visualizzare un altro set di icone, impostato nella <xref:System.Windows.Forms.ListView.StateImageList%2A> proprietà, accanto alle icone grandi o piccole. Per ulteriori informazioni sugli elenchi di immagini, vedere [componente ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) e [procedura: aggiungere o rimuovere immagini con il componente ImageList di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
### <a name="to-display-images-in-a-list-view"></a>Per visualizzare le immagini in una visualizzazione elenco  
  
1.  Impostare la proprietà appropriata, ovvero<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, o <xref:System.Windows.Forms.ListView.StateImageList%2A>: esistente <xref:System.Windows.Forms.ImageList> componente che si desidera utilizzare.  
  
     Queste proprietà possono essere impostate nella finestra di progettazione con la finestra proprietà o nel codice.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2.  Impostare il <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> o <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> proprietà per ogni elemento di elenco che è associata un'icona.  
  
     Queste proprietà possono essere impostate nel codice o all'interno di **Editor della raccolta ListViewItem**. Per aprire la **Editor della raccolta ListViewItem**, fare clic sul pulsante con i puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto il <xref:System.Windows.Forms.ListView.Items%2A>proprietà il **proprietà** finestra.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica del controllo ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [Procedura: Aggiungere colonne al controllo ListView di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [Componente ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)

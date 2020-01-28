---
title: Visualizza icone per il controllo ListView
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
ms.openlocfilehash: 5fc54c448dae95cab50cdafa8403769fb421dffa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744511"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a>Procedura: Visualizzare icone per il controllo ListView di Windows Form
Il controllo Windows Forms <xref:System.Windows.Forms.ListView> può visualizzare icone da tre elenchi di immagini. Le visualizzazioni List, Details e SmallIcon visualizzano immagini dall'elenco di immagini specificato nella proprietà <xref:System.Windows.Forms.ListView.SmallImageList%2A>. La vista LargeIcon visualizza le immagini dall'elenco di immagini specificato nella proprietà <xref:System.Windows.Forms.ListView.LargeImageList%2A>. In una visualizzazione elenco è inoltre possibile visualizzare un set di icone aggiuntivo, impostato nella proprietà <xref:System.Windows.Forms.ListView.StateImageList%2A>, accanto alle icone grandi o piccole. Per altre informazioni sugli elenchi di immagini, vedere [componente ImageList](imagelist-component-windows-forms.md) e [procedura: aggiungere o rimuovere immagini con il componente Windows Forms ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
### <a name="to-display-images-in-a-list-view"></a>Per visualizzare le immagini in una visualizzazione elenco  
  
1. Impostare la proprietà appropriata, ovvero<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>o <xref:System.Windows.Forms.ListView.StateImageList%2A>, sul componente di <xref:System.Windows.Forms.ImageList> esistente che si desidera utilizzare.  
  
     È possibile impostare queste proprietà nella finestra di progettazione con il Finestra Proprietà o nel codice.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. Impostare la proprietà <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> o <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> per ogni elemento elenco a cui è associata un'icona.  
  
     Queste proprietà possono essere impostate nel codice o nell'editor della **raccolta ListViewItem**. Per aprire l' **Editor della raccolta ListViewItem**, fare clic sul pulsante con i puntini di sospensione (![pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà <xref:System.Windows.Forms.ListView.Items%2A> nella finestra **Proprietà** .  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
- [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Procedura: Aggiungere colonne al controllo ListView di Windows Form](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Componente ImageList](imagelist-component-windows-forms.md)

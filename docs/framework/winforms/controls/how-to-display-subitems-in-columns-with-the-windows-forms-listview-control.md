---
title: 'Procedura: visualizzare elementi secondari nelle colonne con il controllo ListView Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
ms.openlocfilehash: efee926301bc358bb7645ba67826f412c0d0dbbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a>Procedura: visualizzare elementi secondari nelle colonne con il controllo ListView Windows Form
Windows Form <xref:System.Windows.Forms.ListView> controllo può visualizzare testo aggiuntivo, o elementi secondari, per ogni elemento nella visualizzazione dettagli. La prima colonna Visualizza il testo dell'elemento, ad esempio il numero di un dipendente. Il secondo, terzo le colonne successive visualizzano il primo, secondo e successivi elementi secondari associati.  
  
### <a name="to-add-subitems-to-a-list-item"></a>Per aggiungere elementi secondari a un elemento di elenco  
  
1.  Aggiungere le colonne necessarie. Poiché la prima colonna verrà visualizzato l'elemento <xref:System.Windows.Forms.ListView.Text%2A> proprietà, è necessario che una colonna in più del numero di elementi secondari. Per ulteriori informazioni sull'aggiunta di colonne, vedere [procedura: aggiungere colonne al controllo ListView Windows Form](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).  
  
2.  Chiamare il <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> raccolta restituita dal metodo di <xref:System.Windows.Forms.ListViewItem.SubItems%2A> proprietà di un elemento. Esempio di codice seguente imposta il nome del dipendente e reparto per un elemento di elenco.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica del controllo ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [Procedura: Aggiungere colonne al controllo ListView di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [Procedura: Visualizzare icone per il controllo ListView di Windows Form](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)

---
title: 'Procedura: Visualizzare elementi secondari nelle colonne con il controllo ListView di Windows Forms'
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
ms.openlocfilehash: 318521cc1377be89ef54706d80c8b2990a6ba1b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650466"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a>Procedura: Visualizzare elementi secondari nelle colonne con il controllo ListView di Windows Forms
I moduli di Windows <xref:System.Windows.Forms.ListView> controllo può visualizzare testo aggiuntivi o secondari, per ogni elemento nella visualizzazione dettagli. La prima colonna consente di visualizzare il testo dell'elemento, ad esempio un numero di dipendenti. La seconda, terza le colonne successive visualizzano il primo, secondo e successivi elementi secondari associati.  
  
### <a name="to-add-subitems-to-a-list-item"></a>Per aggiungere gli elementi secondari a un elemento di elenco  
  
1. Aggiungere tutte le colonne necessite. Poiché la prima colonna visualizzerà l'elemento <xref:System.Windows.Forms.ListView.Text%2A> proprietà, è necessario una colonna in più di quanti sono gli elementi secondari. Per altre informazioni sull'aggiunta di colonne, vedere [come: Aggiungere colonne per i Windows Form controllo ListView](how-to-add-columns-to-the-windows-forms-listview-control.md).  
  
2. Chiamare il <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> della raccolta restituita dal metodo di <xref:System.Windows.Forms.ListViewItem.SubItems%2A> proprietà di un elemento. L'esempio di codice seguente imposta il nome del dipendente e reparto per un elemento dell'elenco.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
- [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Procedura: Aggiungere colonne al controllo ListView Windows Form](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Procedura: Visualizzare le icone per il controllo ListView di Windows Form](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)](add-custom-information-to-a-treeview-or-listview-control-wf.md)

---
title: Raggruppare elementi nel controllo ListViewGroup Items in ListView Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
ms.openlocfilehash: a1754d10de2bbb5895ae861cd17f4af1f18810e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141991"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>Procedura: raggruppare elementi in un controllo ListView Windows Form
Con la funzionalità <xref:System.Windows.Forms.ListView> di raggruppamento del controllo, è possibile visualizzare in gruppi set correlati di elementi. Questi gruppi sono separati sullo schermo da intestazioni di gruppo orizzontali che contengono i titoli dei gruppi. È possibile <xref:System.Windows.Forms.ListView> utilizzare i gruppi per semplificare l'esplorazione di elenchi di grandi dimensioni raggruppando gli elementi in ordine alfabetico, per data o in base a qualsiasi altro raggruppamento logico. L'immagine seguente mostra alcuni elementi raggruppati.  
  
 ![Screenshot di gruppi ListView pari e dispari.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  

 Per abilitare il raggruppamento, è innanzitutto necessario creare uno o più gruppi nella finestra di progettazione o a livello di codice. Dopo aver definito un gruppo, <xref:System.Windows.Forms.ListView> è possibile assegnare gli articoli ai gruppi. È inoltre possibile spostare elementi da un gruppo a un altro a livello di codice.  
  
### <a name="to-add-groups"></a>Per aggiungere gruppi  
  
1. Usare il metodo <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> della raccolta <xref:System.Windows.Forms.ListView.Groups%2A> .  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>Per rimuovere gruppi  
  
1. Utilizzare <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> il <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> metodo <xref:System.Windows.Forms.ListView.Groups%2A> o della raccolta.  
  
     Il <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> metodo rimuove un singolo gruppo; il <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> metodo rimuove tutti i gruppi dall'elenco.  
  
    > [!NOTE]
    > La rimozione di un gruppo non comporta la rimozione degli elementi all'interno di tale gruppo.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>Per assegnare elementi a gruppi o spostare elementi tra gruppi  
  
1. Impostare <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> la proprietà dei singoli elementi.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [Controllo ListView](listview-control-windows-forms.md)
- [Cenni preliminari sul controllo ListView](listview-control-overview-windows-forms.md)
- [Procedura: aggiungere e rimuovere elementi tramite il controllo ListView di Windows Form](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)

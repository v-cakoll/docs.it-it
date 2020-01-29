---
title: Raggruppa elementi nel controllo ListView
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
ms.openlocfilehash: 45846751780f433c29b186fe8b9a908f5d295ab3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736634"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>Procedura: Raggruppare elementi in un controllo ListView di Windows Form
Con la funzionalità di raggruppamento del controllo <xref:System.Windows.Forms.ListView> è possibile visualizzare set correlati di elementi in gruppi. Questi gruppi sono separati sullo schermo da intestazioni di gruppo orizzontali che contengono i titoli del gruppo. È possibile utilizzare i gruppi di <xref:System.Windows.Forms.ListView> per semplificare l'esplorazione degli elenchi di grandi dimensioni raggruppando gli elementi in ordine alfabetico, per data o per qualsiasi altro raggruppamento logico. Nell'immagine seguente vengono illustrati alcuni elementi raggruppati.  
  
 ![Screenshot dei gruppi dispari e persino di ListView.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  
   
 Per abilitare il raggruppamento, è innanzitutto necessario creare uno o più gruppi nella finestra di progettazione o a livello di codice. Dopo aver definito un gruppo, è possibile assegnare elementi <xref:System.Windows.Forms.ListView> ai gruppi. È anche possibile spostare elementi da un gruppo a un altro a livello di codice.  
  
### <a name="to-add-groups"></a>Per aggiungere gruppi  
  
1. Usare il metodo <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> della raccolta <xref:System.Windows.Forms.ListView.Groups%2A> .  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>Per rimuovere i gruppi  
  
1. Usare il metodo <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> della raccolta di <xref:System.Windows.Forms.ListView.Groups%2A>.  
  
     Il metodo <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> rimuove un singolo gruppo. il metodo <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> rimuove tutti i gruppi dall'elenco.  
  
    > [!NOTE]
    > La rimozione di un gruppo non comporta la rimozione degli elementi all'interno di tale gruppo.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>Per assegnare elementi a gruppi o spostare elementi tra gruppi  
  
1. Imposta la proprietà <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> dei singoli elementi.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [Controllo ListView](listview-control-windows-forms.md)
- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
- [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)

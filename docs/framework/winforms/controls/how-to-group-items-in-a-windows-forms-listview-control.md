---
title: 'Procedura: raggruppare elementi in un controllo ListView Windows Form'
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
ms.openlocfilehash: 2847b95694eefec524bee9c95b5de91fa5a03f5d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43661502"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>Procedura: raggruppare elementi in un controllo ListView Windows Form
Con la caratteristica di raggruppamento del <xref:System.Windows.Forms.ListView> (controllo), è possibile visualizzare insiemi di elementi correlati nei gruppi. Questi gruppi vengono separati nella schermata dalle intestazioni del gruppo orizzontali che contengono i titoli di gruppo. È possibile usare <xref:System.Windows.Forms.ListView> gruppi per semplificare lo spostamento di elenchi di grandi dimensioni più facili raggruppando gli elementi in ordine alfabetico, per data o da qualsiasi altra forma di raggruppamento logico. L'immagine seguente mostra alcuni elementi raggruppati.  
  
 ![Gruppi ListView](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
Gli elementi raggruppati in ListView  
  
 Per abilitare il raggruppamento, è innanzitutto necessario creare uno o più gruppi a livello di codice o nella finestra di progettazione. Dopo aver definito un gruppo, è possibile assegnare <xref:System.Windows.Forms.ListView> elementi ai gruppi. È possibile anche spostare gli elementi da un gruppo a un'altra a livello di codice.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView> i gruppi sono disponibili solo nei [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando l'applicazione chiama il <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> (metodo). Nei sistemi operativi precedenti, qualsiasi codice relativo ai gruppi non ha alcun effetto e non verranno visualizzati i gruppi. Per altre informazioni, vedere <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.  
  
### <a name="to-add-groups"></a>Per aggiungere gruppi  
  
1.  Usare il metodo <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> della raccolta <xref:System.Windows.Forms.ListView.Groups%2A>.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>Per rimuovere i gruppi  
  
1.  Usare la <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> metodo il <xref:System.Windows.Forms.ListView.Groups%2A> raccolta.  
  
     Il <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> metodo rimuove un singolo gruppo; il <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> metodo rimuove tutti i gruppi dall'elenco.  
  
    > [!NOTE]
    >  Rimozione di un gruppo non rimuove gli elementi all'interno di tale gruppo.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>Assegnare elementi ai gruppi o spostare gli elementi tra i gruppi  
  
1.  Impostare il <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> proprietà dei singoli elementi.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [Controllo ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Panoramica del controllo ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Funzionalità di Windows XP e controlli di Windows Forms](https://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)

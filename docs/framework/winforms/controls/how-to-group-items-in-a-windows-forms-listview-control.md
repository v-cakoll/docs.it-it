---
title: 'Procedura: raggruppare elementi in un controllo ListView Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b12b7126e03f6a6c8363c69a607f4961f13120ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>Procedura: raggruppare elementi in un controllo ListView Windows Form
La funzionalità di raggruppamento del <xref:System.Windows.Forms.ListView> (controllo), è possibile visualizzare i relativi set di elementi in gruppi. Questi gruppi sono separati sullo schermo dalle intestazioni del gruppo orizzontale che contengono i titoli di gruppo. È possibile utilizzare <xref:System.Windows.Forms.ListView> gruppi per semplificare lo spostamento negli elenchi di grandi dimensioni raggruppando gli elementi in ordine alfabetico, in base alla data o da qualsiasi altro raggruppamento logico. La figura seguente mostra alcuni elementi raggruppati.  
  
 ![Gruppi ListView](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
Elementi raggruppati ListView  
  
 Per abilitare il raggruppamento, è innanzitutto necessario creare uno o più gruppi a livello di codice o nella finestra di progettazione. Dopo aver definito un gruppo, è possibile assegnare <xref:System.Windows.Forms.ListView> elementi ai gruppi. È possibile inoltre spostare elementi da un gruppo a un altro livello di codice.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView>i gruppi sono disponibili solo in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando l'applicazione chiama il <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> metodo. Nei sistemi operativi precedenti, qualsiasi codice relativo ai gruppi non ha alcun effetto e non verranno visualizzati i gruppi. Per altre informazioni, vedere <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.  
  
### <a name="to-add-groups"></a>Per aggiungere gruppi  
  
1.  Usare il metodo <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> della raccolta <xref:System.Windows.Forms.ListView.Groups%2A>.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>Per rimuovere i gruppi  
  
1.  Utilizzare il <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> metodo il <xref:System.Windows.Forms.ListView.Groups%2A> insieme.  
  
     Il <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> metodo rimuove un singolo gruppo; <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> metodo rimuove tutti i gruppi dall'elenco.  
  
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
 [Funzionalità di Windows XP e controlli di Windows Forms](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)

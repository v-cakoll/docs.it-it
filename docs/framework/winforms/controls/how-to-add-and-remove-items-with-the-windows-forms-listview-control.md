---
title: 'Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: 8a97d73b9b2c46d02ae0794ad66b20a04db58af6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59327659"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a>Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Forms
Il processo di aggiunta di un elemento a un form Windows <xref:System.Windows.Forms.ListView> controllo consiste principalmente nella definizione dell'elemento e assegnazione di proprietà. È possibile aggiungere o rimuovere elementi elenco in qualsiasi momento.  
  
### <a name="to-add-items-programmatically"></a>Per aggiungere elementi a livello di codice  
  
1. Usare il <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> metodo di <xref:System.Windows.Forms.ListView.Items%2A> proprietà.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a>Per rimuovere gli elementi a livello di codice  
  
1. Usare il <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> oppure <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> metodo del <xref:System.Windows.Forms.ListView.Items%2A> proprietà. Il <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> metodo rimuove un singolo elemento; il <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> metodo rimuove tutti gli elementi dall'elenco.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView>
- [Controllo ListView](listview-control-windows-forms.md)
- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)

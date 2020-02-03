---
title: Aggiungere e rimuovere elementi con il controllo ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: bbfe99db857ebe3a80bf99926f3ce0bec38a1f3f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743147"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a>Procedura: aggiungere e rimuovere elementi tramite il controllo ListView di Windows Form
Il processo di aggiunta di un elemento a un Windows Forms <xref:System.Windows.Forms.ListView> controllo è costituito principalmente dalla specifica dell'elemento e dall'assegnazione di proprietà. L'aggiunta o la rimozione di elementi elenco può essere eseguita in qualsiasi momento.  
  
### <a name="to-add-items-programmatically"></a>Per aggiungere elementi a livello di codice  
  
1. Usare il metodo <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> della proprietà <xref:System.Windows.Forms.ListView.Items%2A>.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a>Per rimuovere elementi a livello di codice  
  
1. Usare il metodo <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> della proprietà <xref:System.Windows.Forms.ListView.Items%2A>. Il metodo <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> rimuove un singolo elemento. il metodo <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> rimuove tutti gli elementi dall'elenco.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView>
- [Controllo ListView](listview-control-windows-forms.md)
- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)

---
title: 'Procedura: accedere a raccolte con chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: 717ba9cc8605da08701de1bd13d6bc6da1c9b758
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739621"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a>Procedura: accedere a raccolte con chiavi in Windows Form

- È possibile accedere a singoli elementi della raccolta in base alla chiave. Questa funzionalità è stata aggiunta a numerose classi di raccolta che in genere vengono utilizzate dalle applicazioni Windows Forms. Nell'elenco seguente vengono illustrate alcune delle classi di raccolta con le raccolte con chiave accessibili:  
  
- <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
- <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
- <xref:System.Windows.Forms.Control.ControlCollection>  
  
- <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
- <xref:System.Windows.Forms.TreeNodeCollection>  
  
 La chiave associata a un elemento in una raccolta è in genere il nome dell'elemento. Nelle procedure riportate di seguito viene illustrato come utilizzare le classi di raccolta per eseguire attività comuni.  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a>Per individuare e assegnare lo stato attivo a un controllo annidato in una raccolta di controlli  
  
- Usare i metodi <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> e <xref:System.Windows.Forms.Control.Focus%2A> per specificare il nome del controllo da trovare e fornire lo stato attivo a.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a>Per accedere a un'immagine in una raccolta di immagini  
  
- Usare la proprietà <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> per specificare il nome dell'immagine a cui si vuole accedere.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a>Per impostare una scheda come scheda selezionata  
  
- Utilizzare la proprietà <xref:System.Windows.Forms.TabControl.SelectedTab%2A> insieme alla proprietà <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> per specificare il nome della scheda da impostare come scheda selezionata.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida introduttiva a Windows Form](getting-started-with-windows-forms.md)
- [Procedura: Aggiungere o rimuovere immagini con il componente ImageList di Windows Form](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)

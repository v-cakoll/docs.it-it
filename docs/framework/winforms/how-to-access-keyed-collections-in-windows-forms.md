---
title: 'Procedura: accedere a raccolte con chiavi in Windows Form'
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
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 852e82aff12dc39adeba6ea2dada5934ae55f951
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a>Procedura: accedere a raccolte con chiavi in Windows Form
-   È possibile accedere a singoli elementi dell'insieme dalla chiave. Questa funzionalità è stata aggiunta a molte classi di raccolta che vengono in genere utilizzate dalle applicazioni Windows Form. Nell'elenco seguente sono illustrate alcune delle classi di raccolte che sono accessibili raccolte con chiave:  
  
-   <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
-   <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
-   <xref:System.Windows.Forms.Control.ControlCollection>  
  
-   <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
-   <xref:System.Windows.Forms.TreeNodeCollection>  
  
 La chiave associata a un elemento in una raccolta è in genere il nome dell'elemento. Le procedure seguenti viene illustrato come utilizzare le classi di raccolta per eseguire attività comuni.  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a>Per trovare e fornire lo stato attivo a un controllo in una raccolta di controllo annidate  
  
-   Utilizzare il <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> e <xref:System.Windows.Forms.Control.Focus%2A> metodi per specificare il nome del controllo da trovare e portare lo stato attivo.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a>Per accedere a un'immagine in una raccolta di immagini  
  
-   Utilizzare il <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> proprietà per specificare il nome dell'immagine di cui si desidera accedere.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a>Per impostare una pagina della scheda come scheda selezionata  
  
-   Utilizzare il <xref:System.Windows.Forms.TabControl.SelectedTab%2A> proprietà con il <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> proprietà per specificare il nome della scheda per impostare come scheda selezionata.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida introduttiva a Windows Form](../../../docs/framework/winforms/getting-started-with-windows-forms.md)  
 [Procedura: Aggiungere o rimuovere immagini con il componente ImageList di Windows Form](../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)

---
title: "Procedura: aggiungere funzionalità di ricerca a un controllo ListView"
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
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 111fc6e4945998c99e63560afab6104f4daf89e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a>Procedura: aggiungere funzionalità di ricerca a un controllo ListView
Spesso quando si lavora con un lungo elenco di elementi in un <xref:System.Windows.Forms.ListView> (controllo), a cui si desidera offrire funzionalità di ricerca per l'utente. Il <xref:System.Windows.Forms.ListView> controllo offre questa funzionalità in due modi diversi: percorso di ricerca e i criteri di testo.  
  
 Il <xref:System.Windows.Forms.ListView.FindItemWithText%2A> metodo consente di eseguire una ricerca di testo in un <xref:System.Windows.Forms.ListView> nella visualizzazione elenco o dettagli, assegnato a una stringa di ricerca e un inizio e fine facoltativi dell'indice. Al contrario, il <xref:System.Windows.Forms.ListView.FindNearestItem%2A> metodo consente di trovare un elemento in un <xref:System.Windows.Forms.ListView> nella visualizzazione di icone o affiancata, dato un set di coordinate x e y e una direzione di ricerca.  
  
### <a name="to-find-an-item-using-text"></a>Per trovare un elemento di testo  
  
1.  Creare un <xref:System.Windows.Forms.ListView> con il <xref:System.Windows.Forms.ListView.View%2A> proprietà impostata su <xref:System.Windows.Forms.View.Details> o <xref:System.Windows.Forms.View.List>, quindi compilare il <xref:System.Windows.Forms.ListView> con gli elementi.  
  
2.  Chiamare il <xref:System.Windows.Forms.ListView.FindItemWithText%2A> , passando il testo dell'elemento di cui si desidera trovare.  
  
3.  Esempio di codice riportato di seguito viene illustrato come creare un tipo di base <xref:System.Windows.Forms.ListView>viene popolato con gli elementi e utilizzare testo immesso dall'utente per trovare un elemento nell'elenco.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a>Per trovare un elemento utilizzando le coordinate x e y  
  
1.  Creare un <xref:System.Windows.Forms.ListView> con il <xref:System.Windows.Forms.View> proprietà impostata su <xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>, quindi compilare il <xref:System.Windows.Forms.ListView> con gli elementi.  
  
2.  Chiamare il <xref:System.Windows.Forms.ListView.FindNearestItem%2A> , passando le coordinate x e y desiderata e la direzione in cui si desidera eseguire la ricerca.  
  
3.  Esempio di codice riportato di seguito viene illustrato come creare un'icona di base <xref:System.Windows.Forms.ListView>, viene popolato con elementi e acquisire il <xref:System.Windows.Forms.Control.MouseDown> eventi per trovare l'elemento più vicino in alto.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.FindItemWithText%2A>  
 <xref:System.Windows.Forms.ListView.FindNearestItem%2A>  
 [Controllo ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Panoramica del controllo ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)

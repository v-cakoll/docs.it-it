---
title: 'Procedura: Visualizzare un segno di inserimento in un controllo ListView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ListView control [Windows Forms], drag operations
- graphics [Windows Forms], insertion marks
- drop and drag [Windows Forms], insertion marks
- insertion marks
ms.assetid: 88d0a15b-25fd-4dc3-a685-297351311940
ms.openlocfilehash: f5de00fd41b24fc1a7f1ff4484c3a126e98952a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967826"
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a>Procedura: Visualizzare un segno di inserimento in un controllo ListView di Windows Forms
Il segno di inserimento nel controllo <xref:System.Windows.Forms.ListView> indica agli utenti il punto in cui verranno inseriti gli elementi trascinati. Quando un utente trascina un elemento in un punto intermedio tra due elementi, il segno di inserimento indica la nuova posizione prevista dell'elemento.  
  
> [!NOTE]
> La funzionalità del segno di inserimento è disponibile solo in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando l'applicazione chiama il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. Nei sistemi operativi precedenti, qualsiasi codice relativo al segno di inserimento non ha alcun effetto e il segno di inserimento non verrà visualizzato. Per altre informazioni, vedere <xref:System.Windows.Forms.ListViewInsertionMark>.  
  
 L'immagine seguente mostra un segno di inserimento:  
  
 ![Screenshot che mostra un segno di inserimento di ListView.](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")  
  
 L'esempio di codice seguente illustra l'uso di questa funzionalità.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewInsertionMark>
- [Controllo ListView](listview-control-windows-forms.md)
- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
- [Procedura dettagliata: Esecuzione di un'operazione di trascinamento della selezione in Windows Forms](../advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)

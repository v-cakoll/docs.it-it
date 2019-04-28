---
title: "Procedura: Gestire l'evento ScrollChanged"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], raising ScrollChanged events
- ScrollChanged events [WPF]
ms.assetid: 42c695d8-ee28-49d4-80fd-fc71e9be7f29
ms.openlocfilehash: 54f20a4b8c6e6fcc190257fcf5de4374415d68b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771059"
---
# <a name="how-to-handle-the-scrollchanged-event"></a>Procedura: Gestire l'evento ScrollChanged
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato come gestire le <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> eventi di un <xref:System.Windows.Controls.ScrollViewer>.  
  
 Oggetto <xref:System.Windows.Documents.FlowDocument> elemento con <xref:System.Windows.Documents.Paragraph> parti è definito in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Quando la <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> evento si verifica a causa dell'interazione dell'utente, viene richiamato un gestore e il testo viene scritto un <xref:System.Windows.Controls.TextBlock> che indica che si è verificato l'evento.  
  
 [!code-xaml[scrollchangedeventargsLayout#1](~/samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#1)]  
[!code-xaml[scrollchangedeventargsLayout#2](~/samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[scrollchangedeventargsLayout#3](~/samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml.cs#3)]
 [!code-vb[scrollchangedeventargsLayout#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/scrollchangedeventargsLayout/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>
- <xref:System.Windows.Controls.ScrollChangedEventHandler>
- <xref:System.Windows.Controls.ScrollChangedEventArgs>

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
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59974162"
---
# <a name="how-to-handle-the-scrollchanged-event"></a><span data-ttu-id="85bc1-102">Procedura: Gestire l'evento ScrollChanged</span><span class="sxs-lookup"><span data-stu-id="85bc1-102">How to: Handle the ScrollChanged Event</span></span>
## <a name="example"></a><span data-ttu-id="85bc1-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="85bc1-103">Example</span></span>  
 <span data-ttu-id="85bc1-104">In questo esempio viene illustrato come gestire le <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> eventi di un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="85bc1-104">This example shows how to handle the <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> event of a <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
 <span data-ttu-id="85bc1-105">Oggetto <xref:System.Windows.Documents.FlowDocument> elemento con <xref:System.Windows.Documents.Paragraph> parti è definito in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85bc1-105">A <xref:System.Windows.Documents.FlowDocument> element with <xref:System.Windows.Documents.Paragraph> parts is defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="85bc1-106">Quando la <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> evento si verifica a causa dell'interazione dell'utente, viene richiamato un gestore e il testo viene scritto un <xref:System.Windows.Controls.TextBlock> che indica che si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="85bc1-106">When the <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> event occurs due to user interaction, a handler is invoked, and text is written to a <xref:System.Windows.Controls.TextBlock> indicating that the event has occurred.</span></span>  
  
 [!code-xaml[scrollchangedeventargsLayout#1](~/samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#1)]  
[!code-xaml[scrollchangedeventargsLayout#2](~/samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[scrollchangedeventargsLayout#3](~/samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml.cs#3)]
 [!code-vb[scrollchangedeventargsLayout#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/scrollchangedeventargsLayout/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="85bc1-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85bc1-107">See also</span></span>

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>
- <xref:System.Windows.Controls.ScrollChangedEventHandler>
- <xref:System.Windows.Controls.ScrollChangedEventArgs>

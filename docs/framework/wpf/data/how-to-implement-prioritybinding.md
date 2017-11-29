---
title: 'Procedura: implementare un oggetto PriorityBinding'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9753462908928eaf177e100a16186826bf4828ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-prioritybinding"></a>Procedura: implementare un oggetto PriorityBinding
<xref:System.Windows.Data.PriorityBinding>in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funziona specificando un elenco di associazioni. L'elenco di associazioni è ordinato dalla priorità più alta alla priorità più bassa. Se l'associazione con la priorità più alta restituisce un valore correttamente quando viene elaborato è mai necessario elaborare altre associazioni nell'elenco. È possibile che l'associazione con la priorità più alta richiede molto tempo per essere valutata, verrà utilizzata la priorità più elevata successiva che restituisce un valore correttamente finché un'associazione di una priorità più alta restituisce un valore correttamente.  
  
## <a name="example"></a>Esempio  
 Per illustrare come <xref:System.Windows.Data.PriorityBinding> funziona, il `AsyncDataSource` oggetto è stato creato con le seguenti tre proprietà: `FastDP`, `SlowerDP`, e `SlowestDP`.  
  
 La funzione di accesso get di `FastDP` restituisce il valore della `_fastDP` (membro dati).  
  
 La funzione di accesso get di `SlowerDP` attende 3 secondi prima di restituire il valore della `_slowerDP` (membro dati).  
  
 La funzione di accesso get di `SlowestDP` attende 5 secondi prima di restituire il valore di `_slowestDP` (membro dati).  
  
> [!NOTE]
>  Questo esempio è solo per scopi dimostrativi. Il [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] linee guida si consiglia di non definire le proprietà che gli ordini di grandezza più lente rispetto a un set di campi. Per ulteriori informazioni, vedere [NIB: scelta tra proprietà e metodi](http://msdn.microsoft.com/en-us/55825e8f-7e2e-448a-9505-7217cc91b1af).  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 Il <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà associa a quanto sopra `AsyncDS` utilizzando <xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Quando il motore di associazione elabora il <xref:System.Windows.Data.Binding> oggetti, inizia con il primo <xref:System.Windows.Data.Binding>, che è associato il `SlowestDP` proprietà. Quando questo <xref:System.Windows.Data.Binding> viene elaborato, non restituisce un valore correttamente perché rimane inattivo per 5 secondi, pertanto alla successiva <xref:System.Windows.Data.Binding> elemento viene elaborato. Alla successiva <xref:System.Windows.Data.Binding> non restituisce un valore correttamente perché rimane inattivo per 3 secondi. Il motore di associazione passa quindi alla successiva <xref:System.Windows.Data.Binding> elemento che è associato il `FastDP` proprietà. Questo <xref:System.Windows.Data.Binding> restituisce il valore "Fast Value". Il <xref:System.Windows.Controls.TextBlock> verrà visualizzato il valore "Fast Value".  
  
 Dopo la scadenza di 3 secondi, il `SlowerDP` proprietà restituisce il valore "Slower Value". Il <xref:System.Windows.Controls.TextBlock> quindi Visualizza il valore "Slower Value".  
  
 Dopo questo intervallo di 5 secondi, il `SlowestDP` proprietà restituisce il valore "lento". Tale associazione ha la priorità più alta poiché è elencato prima. Il <xref:System.Windows.Controls.TextBlock> ora consente di visualizzare il valore "lento".  
  
 Vedere <xref:System.Windows.Data.PriorityBinding> per informazioni sulla definizione di un valore restituito correttamente da un'associazione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [Cenni preliminari sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

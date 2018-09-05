---
title: 'Procedura: implementare un oggetto PriorityBinding'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: a7729ec3d06ec701cf2194bed5d90b5bed76573a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43671696"
---
# <a name="how-to-implement-prioritybinding"></a>Procedura: implementare un oggetto PriorityBinding
<xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funziona specificando un elenco di associazioni. L'elenco di associazioni viene ordinata dalla priorità più alta alla priorità più bassa. Se l'associazione con la priorità più alto restituisce un valore correttamente quando viene elaborato quindi non è mai necessario per elaborare le altre associazioni nell'elenco. Potrebbe essere il caso che l'associazione con la priorità più alta richiede molto tempo per essere valutata, verrà utilizzata la priorità più elevata successiva che restituisce un valore correttamente fino a quando un'associazione di una priorità più alta restituisce un valore correttamente.  
  
## <a name="example"></a>Esempio  
 Per illustrare la modalità <xref:System.Windows.Data.PriorityBinding> funziona, il `AsyncDataSource` oggetto è stato creato con le seguenti tre proprietà: `FastDP`, `SlowerDP`, e `SlowestDP`.  
  
 Funzione di accesso get della `FastDP` restituisce il valore della `_fastDP` (membro dati).  
  
 Funzione di accesso get della `SlowerDP` attende 3 secondi prima di restituire il valore della `_slowerDP` (membro dati).  
  
 Funzione di accesso get della `SlowestDP` attende 5 secondi prima di restituire il valore della `_slowestDP` (membro dati).  
  
> [!NOTE]
>  L'esempio ha solo scopo dimostrativo. Il [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] linee guida consigliabile evitare di definire le proprietà che sono più lenti rispetto a un set di campi di ordini di grandezza. Per altre informazioni, vedere [NIB: scelta tra proprietà e metodi](https://msdn.microsoft.com/library/55825e8f-7e2e-448a-9505-7217cc91b1af).  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 Il <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà viene associata a quello precedente `AsyncDS` usando <xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Quando il motore di binding elabora i <xref:System.Windows.Data.Binding> oggetti, inizia con il primo <xref:System.Windows.Data.Binding>, che è associato ai `SlowestDP` proprietà. Quando ciò <xref:System.Windows.Data.Binding> viene elaborato, non restituisce un valore correttamente perché rimane inattivo per 5 secondi, quindi, alla successiva <xref:System.Windows.Data.Binding> elemento viene elaborato. Alla successiva <xref:System.Windows.Data.Binding> non restituisce un valore correttamente in quanto rimane inattivo per 3 secondi. Il motore di binding viene quindi ripetuto sul successivo <xref:System.Windows.Data.Binding> elemento, che è associato il `FastDP` proprietà. Ciò <xref:System.Windows.Data.Binding> restituisce il valore "veloce". Il <xref:System.Windows.Controls.TextBlock> Visualizza ora il valore "veloce".  
  
 Trascorsi 3 secondi, il `SlowerDP` proprietà restituisce il valore "Value più lento". Il <xref:System.Windows.Controls.TextBlock> quindi Visualizza il valore "Value più lento".  
  
 Dopo la scadenza di 5 secondi, il `SlowestDP` proprietà restituisce il valore "lento". Tale associazione ha la priorità più alta in quanto lo sia elencato per prima. Il <xref:System.Windows.Controls.TextBlock> Visualizza ora il valore "lento".  
  
 Vedere <xref:System.Windows.Data.PriorityBinding> per informazioni su ciò che viene considerato un valore restituito correttamente da un'associazione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

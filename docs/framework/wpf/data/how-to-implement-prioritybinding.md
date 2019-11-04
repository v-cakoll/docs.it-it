---
title: 'Procedura: implementare un oggetto PriorityBinding'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: 343b0aca4736905f3a0cbff5a0f76b170da0c920
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459790"
---
# <a name="how-to-implement-prioritybinding"></a>Procedura: implementare un oggetto PriorityBinding
<xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funziona specificando un elenco di associazioni. L'elenco delle associazioni viene ordinato dalla priorità più alta alla priorità più bassa. Se l'associazione con la priorità più alta restituisce un valore correttamente quando viene elaborato, non è mai necessario elaborare le altre associazioni nell'elenco. Il caso in cui il binding con priorità più elevata impiega molto tempo per la valutazione, la successiva priorità più alta che restituisce un valore verrà utilizzata correttamente finché un'associazione di una priorità più alta non restituirà correttamente un valore.  
  
## <a name="example"></a>Esempio  
 Per illustrare il funzionamento di <xref:System.Windows.Data.PriorityBinding>, è stato creato l'oggetto `AsyncDataSource` con le tre proprietà seguenti: `FastDP`, `SlowerDP`e `SlowestDP`.  
  
 La funzione di accesso get di `FastDP` restituisce il valore del membro dati `_fastDP`.  
  
 La funzione di accesso get di `SlowerDP` attende 3 secondi prima di restituire il valore del membro dati `_slowerDP`.  
  
 La funzione di accesso get di `SlowestDP` attende 5 secondi prima di restituire il valore del membro dati `_slowestDP`.  
  
> [!NOTE]
> L'esempio ha solo scopo dimostrativo. Le linee guida di .NET sconsigliano di definire proprietà che sono più lente rispetto a un set di campi. Per ulteriori informazioni, vedere [scelta tra proprietà e metodi](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 La proprietà <xref:System.Windows.Controls.TextBlock.Text%2A> viene associata al `AsyncDS` precedente utilizzando <xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Quando il motore di binding elabora gli oggetti <xref:System.Windows.Data.Binding>, inizia con il primo <xref:System.Windows.Data.Binding>, associato alla proprietà `SlowestDP`. Quando questa <xref:System.Windows.Data.Binding> viene elaborata, non restituisce un valore correttamente perché è in sospensione per 5 secondi, quindi viene elaborato l'elemento <xref:System.Windows.Data.Binding> successivo. Il <xref:System.Windows.Data.Binding> successivo non restituisce correttamente un valore perché è in sospensione per 3 secondi. Il motore di associazione viene quindi spostato sull'elemento <xref:System.Windows.Data.Binding> successivo, associato alla proprietà `FastDP`. Questo <xref:System.Windows.Data.Binding> restituisce il valore "Fast Value". Il <xref:System.Windows.Controls.TextBlock> ora Visualizza il valore "valore rapido".  
  
 Dopo 3 secondi trascorsi, la proprietà `SlowerDP` restituisce il valore "valore più lento". Il <xref:System.Windows.Controls.TextBlock> Visualizza quindi il valore "valore più lento".  
  
 Dopo 5 secondi trascorsi, la proprietà `SlowestDP` restituisce il valore "valore più lento". Tale associazione ha la priorità più alta perché è elencata per prima. Il <xref:System.Windows.Controls.TextBlock> ora Visualizza il valore "valore più lento".  
  
 Per informazioni su ciò che viene considerato un valore restituito correttamente da un'associazione, vedere <xref:System.Windows.Data.PriorityBinding>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)

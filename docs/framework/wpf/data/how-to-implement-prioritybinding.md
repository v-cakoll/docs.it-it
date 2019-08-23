---
title: 'Procedura: Implementare un oggetto PriorityBinding'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: ad19db9d686469e3ade1ff188553fceb8d525674
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937439"
---
# <a name="how-to-implement-prioritybinding"></a>Procedura: Implementare un oggetto PriorityBinding
<xref:System.Windows.Data.PriorityBinding>in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Works specificando un elenco di associazioni. L'elenco delle associazioni viene ordinato dalla priorità più alta alla priorità più bassa. Se l'associazione con la priorità più alta restituisce un valore correttamente quando viene elaborato, non è mai necessario elaborare le altre associazioni nell'elenco. Il caso in cui il binding con priorità più elevata impiega molto tempo per la valutazione, la successiva priorità più alta che restituisce un valore verrà utilizzata correttamente finché un'associazione di una priorità più alta non restituirà correttamente un valore.  
  
## <a name="example"></a>Esempio  
 Per illustrare <xref:System.Windows.Data.PriorityBinding> il funzionamento di `AsyncDataSource` , l'oggetto è stato creato con le tre proprietà `FastDP`seguenti `SlowerDP`:, `SlowestDP`e.  
  
 La funzione di accesso `FastDP` Get di restituisce il valore `_fastDP` del membro dati.  
  
 La funzione di accesso `SlowerDP` Get di attende 3 secondi prima di restituire il valore `_slowerDP` del membro dati.  
  
 La funzione di accesso `SlowestDP` Get di attende 5 secondi prima di restituire il valore `_slowestDP` del membro dati.  
  
> [!NOTE]
> L'esempio ha solo scopo dimostrativo. Le [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] linee guida consigliano di non definire proprietà di ordine di grandezza più lente rispetto a un set di campi. Per ulteriori informazioni, vedere [scelta tra proprietà e metodi](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 La <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà viene associata all'oggetto precedente `AsyncDS` utilizzando <xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Quando il motore di binding elabora <xref:System.Windows.Data.Binding> gli oggetti, inizia con il primo <xref:System.Windows.Data.Binding>, associato alla `SlowestDP` proprietà. Quando viene elaborato, il valore non viene restituito correttamente perché è in sospensione per 5 secondi, quindi l'elemento successivo <xref:System.Windows.Data.Binding> viene elaborato. <xref:System.Windows.Data.Binding> Il successivo <xref:System.Windows.Data.Binding> non restituisce correttamente un valore perché è in sospensione per 3 secondi. Il motore di associazione viene quindi spostato sull' <xref:System.Windows.Data.Binding> elemento successivo, associato `FastDP` alla proprietà. Viene <xref:System.Windows.Data.Binding> restituito il valore "Fast Value". <xref:System.Windows.Controls.TextBlock> Ora viene visualizzato il valore "valore rapido".  
  
 Dopo 3 secondi trascorsi, la `SlowerDP` proprietà restituisce il valore "valore più lento". Viene <xref:System.Windows.Controls.TextBlock> quindi visualizzato il valore "valore più lento".  
  
 Dopo 5 secondi trascorsi, la `SlowestDP` proprietà restituisce il valore "valore più lento". Tale associazione ha la priorità più alta perché è elencata per prima. Viene <xref:System.Windows.Controls.TextBlock> ora visualizzato il valore "valore più lento".  
  
 Per <xref:System.Windows.Data.PriorityBinding> informazioni su ciò che viene considerato un valore restituito correttamente da un'associazione, vedere.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [Panoramica sul data binding](data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)

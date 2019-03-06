---
title: 'Procedura: Gestire un evento indirizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], handling
- bubbling events [WPF]
ms.assetid: 157787b4-f469-4047-8777-5b034145f32e
ms.openlocfilehash: 42f5f247e775fbf0bd323fc693a74d6149c87bb3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368194"
---
# <a name="how-to-handle-a-routed-event"></a>Procedura: Gestire un evento indirizzato
Questo esempio illustra il funzionamento degli eventi di bubbling e spiega come scrivere un gestore in grado di elaborare i dati dell'evento indirizzato.  
  
## <a name="example"></a>Esempio  
 In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] gli elementi sono disposti in una struttura ad albero degli elementi. L'elemento padre può partecipare alla gestione di eventi inizialmente generati dagli elementi figlio nell'albero degli elementi. Questo è possibile grazie al routing di eventi.  
  
 Per gli eventi indirizzati si usa in genere una delle due strategie di routing seguenti: bubbling o tunneling. Questo esempio illustra l'evento di bubbling e Usa il <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType> evento per visualizzarne il funzionamento del routing.  
  
 L'esempio seguente crea due <xref:System.Windows.Controls.Button> consente di controllare e viene utilizzato [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] la sintassi per associare un gestore eventi a un elemento padre comune, ovvero in questo esempio di attributo <xref:System.Windows.Controls.StackPanel>. Anziché associare singoli gestori eventi per ognuno <xref:System.Windows.Controls.Button> elemento figlio, l'esempio Usa la sintassi degli attributi per associare il gestore eventi per il <xref:System.Windows.Controls.StackPanel> elemento padre. Questo criterio di gestione degli eventi illustra in che modo usare il routing di eventi come tecnica per ridurre il numero di elementi a cui è associato un gestore. Tutti gli eventi di bubbling per ogni <xref:System.Windows.Controls.Button> viene instradato attraverso l'elemento padre.  
  
 Si noti che nell'elemento padre <xref:System.Windows.Controls.StackPanel> elemento, il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> nome dell'evento specificato, come l'attributo è parzialmente qualificato mediante la denominazione di <xref:System.Windows.Controls.Button> classe. Il <xref:System.Windows.Controls.Button> classe è una <xref:System.Windows.Controls.Primitives.ButtonBase> classe derivata che ha il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento nel relativo elenco dei membri. La tecnica della qualifica parziale per l'associazione di un gestore eventi è necessaria se l'evento che viene gestito non esiste nell'elenco dei membri dell'elemento a cui è associato il gestore dell'evento indirizzato.  
  
 [!code-xaml[RoutedEventHandle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml#xaml)]  
  
 L'esempio seguente viene gestito il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento.  L'esempio stabilisce quale elemento gestisce l'evento e quale elemento genera l'evento. Il gestore eventi viene eseguito quando l'utente fa clic su uno dei pulsanti.  
  
 [!code-csharp[RoutedEventHandle#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventHandle#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventHandle/VisualBasic/MainWindow.xaml.vb#handler)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.RoutedEvent>
- [Cenni preliminari sull'input](input-overview.md)
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
- [Procedure relative alle proprietà](events-how-to-topics.md)
- [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md)

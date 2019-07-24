---
title: 'Procedura: Creare un evento indirizzato personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
ms.openlocfilehash: cbfb88af4e35e3f090248982bb14d6b7a3a03cef
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401463"
---
# <a name="how-to-create-a-custom-routed-event"></a>Procedura: Creare un evento indirizzato personalizzato
Affinché l'evento personalizzato supporti il routing degli eventi, è necessario registrare un <xref:System.Windows.RoutedEvent> usando il <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> metodo. Questo esempio illustra le nozioni di base per la creazione di un evento indirizzato personalizzato.  
  
## <a name="example"></a>Esempio  
 Come illustrato nell'esempio seguente, è necessario innanzitutto registrare un <xref:System.Windows.RoutedEvent> oggetto usando <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> il metodo. Per convenzione, il <xref:System.Windows.RoutedEvent> nome del campo statico deve terminare con l' ***evento***suffisso. In questo esempio, il nome dell'evento è `Tap` e la strategia di routing dell'evento è. <xref:System.Windows.RoutingStrategy.Bubble> Dopo la chiamata di registrazione, è possibile fornire funzioni di accesso agli eventi Common Language Runtime (CLR) Add-and-Remove per l'evento.  
  
 Si noti che anche se l'evento viene generato tramite il metodo virtuale `OnTap` in questo particolare esempio, la modalità di generazione dell'evento o la relativa risposta alle modifiche varierà in base alle esigenze.  
  
 Si noti inoltre che in questo esempio viene implementata essenzialmente <xref:System.Windows.Controls.Button>un'intera sottoclasse di. tale sottoclasse viene compilata come assembly separato e quindi creata come [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] classe personalizzata in una pagina separata. Ciò dimostra che i controlli sottoclassati possono essere inseriti in alberi composti da altri controlli e che, in una situazione del genere, gli eventi personalizzati in questi controlli dispongono delle stesse funzionalità di routing di qualsiasi elemento [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] nativo.  
  
 [!code-csharp[RoutedEventCustom#CustomClass](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 Gli eventi di tunneling vengono creati nello stesso modo, <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> ma con <xref:System.Windows.RoutingStrategy.Tunnel> impostato su nella chiamata di registrazione. Per convenzione, gli eventi di tunneling in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vengono denominati con il prefisso "Preview".  
  
 Per un esempio di funzionamento degli eventi di bubbling, vedere [Gestire un evento indirizzato](how-to-handle-a-routed-event.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
- [Cenni preliminari sull'input](input-overview.md)
- [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md)

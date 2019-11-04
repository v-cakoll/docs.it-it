---
title: 'Procedura: applicare un oggetto FocusVisualStyle a un controllo'
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: b44330ee7554f953389556bd62ff49db120b5db9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459814"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a>Procedura: applicare un oggetto FocusVisualStyle a un controllo
Questo esempio illustra come creare uno stile di visualizzazione dello stato attivo nelle risorse e applicare lo stile a un controllo usando la proprietà <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definito uno stile che consente di creare la composizione di controlli aggiuntivi che si applica solo quando il controllo è focalizzato sulla tastiera nel [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Questa operazione viene eseguita definendo uno stile con una <xref:System.Windows.Controls.ControlTemplate>, quindi facendo riferimento a tale stile come risorsa quando si imposta la proprietà <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.  
  
 Un rettangolo esterno simile a un bordo viene inserito all'esterno dell'area rettangolare. Se non diversamente modificato, il dimensionamento dello stile usa il <xref:System.Windows.FrameworkElement.ActualHeight%2A> e <xref:System.Windows.FrameworkElement.ActualWidth%2A> del controllo rettangolare in cui viene applicato lo stile di visualizzazione dello stato attivo. In questo esempio vengono impostati i valori negativi per il <xref:System.Windows.FrameworkElement.Margin%2A> per far apparire il bordo leggermente al di fuori del controllo attivo.  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 Un <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> è additivo per qualsiasi stile di modello di controllo che deriva da uno stile esplicito o da uno stile del tema; lo stile principale di un controllo può comunque essere creato utilizzando un <xref:System.Windows.Controls.ControlTemplate> e impostando tale stile sulla proprietà <xref:System.Windows.FrameworkElement.Style%2A>.  
  
 Gli stili di visualizzazione dello stato attivo devono essere usati in modo coerente in un tema o in un'interfaccia utente, anziché usare uno diverso per ogni elemento attivabile. Per informazioni dettagliate, vedere applicazione di [stili per lo stato attivo nei controlli e FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Applicazione di stili per lo stato attivo nei controlli e FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md)

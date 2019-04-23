---
title: 'Procedura: Applicare un oggetto FocusVisualStyle a un controllo'
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: 53d4984946143c15c4a2b71095529fb5ee7de4b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133549"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a>Procedura: Applicare un oggetto FocusVisualStyle a un controllo
In questo esempio illustra come creare uno stile di visualizzazione dello stato attivo in risorse e applicare lo stile a un controllo, usando il <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce uno stile che consente di creare la composizione di controlli aggiuntivi che si applica solo quando il controllo è attivo nel [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Questa operazione viene eseguita mediante la definizione di uno stile con un <xref:System.Windows.Controls.ControlTemplate>, quindi fare riferimento a tale stile come risorsa quando si impostano le <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> proprietà.  
  
 Un rettangolo esterno che assomiglia a un bordo viene posizionato all'esterno dell'area rettangolare. A meno che non viene modificato in caso contrario, il ridimensionamento dello stile utilizza il <xref:System.Windows.FrameworkElement.ActualHeight%2A> e <xref:System.Windows.FrameworkElement.ActualWidth%2A> del controllo rettangolare in cui viene applicato lo stile di visualizzazione dello stato attivo. In questo esempio imposta i valori negativi per le <xref:System.Windows.FrameworkElement.Margin%2A> per rendere il bordo apparire leggermente di fuori del controllo con lo stato attivo.  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 Oggetto <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> è additivo per qualsiasi stile di modello di controllo che deriva da uno stile esplicito o uno stile del tema; lo stile di un controllo primario può comunque creato utilizzando una <xref:System.Windows.Controls.ControlTemplate> e impostando lo stile sul <xref:System.Windows.FrameworkElement.Style%2A> proprietà.  
  
 Lo stato attivo gli stili di visualizzazione deve essere usate in modo coerente un tema o un'interfaccia utente, invece di usare una diversa per ogni elemento attivabile. Per informazioni dettagliate, vedere [applicazione di stili per lo stato attivo nei controlli e FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [Applicazione di stili e modelli](../controls/styling-and-templating.md)
- [Applicazione di stili per lo stato attivo nei controlli e FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md)

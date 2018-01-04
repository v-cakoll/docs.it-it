---
title: 'Procedura: applicare un oggetto FocusVisualStyle a un controllo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 41895974b7e6c128d979e362f2dcef1c68e0a5c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a>Procedura: applicare un oggetto FocusVisualStyle a un controllo
In questo esempio viene illustrato come creare uno stile di visualizzazione dello stato attivo in risorse e applicare lo stile a un controllo, utilizzando il <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definito uno stile che crea la composizione del controllo aggiuntivo che si applica solo quando il controllo è attivo nel [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Questa operazione viene eseguita mediante la definizione di uno stile con un <xref:System.Windows.Controls.ControlTemplate>, quindi creare riferimenti a tale stile come una risorsa durante l'impostazione di <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> proprietà.  
  
 Un rettangolo esterno simili a un bordo viene inserito all'esterno dell'area rettangolare. A meno che non viene modificato in caso contrario, il ridimensionamento dello stile utilizza il <xref:System.Windows.FrameworkElement.ActualHeight%2A> e <xref:System.Windows.FrameworkElement.ActualWidth%2A> del controllo rettangolare in cui viene applicato lo stile di visualizzazione dello stato attivo. In questo esempio imposta i valori negativi per le <xref:System.Windows.FrameworkElement.Margin%2A> per rendere il bordo leggermente di fuori del controllo con stato attivo.  
  
 [!code-xaml[FEFocusVisualStyle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> è additivo per qualsiasi stile di modello di controllo che deriva da uno stile esplicito o uno stile del tema; lo stile primario per un controllo può comunque essere creato utilizzando un <xref:System.Windows.Controls.ControlTemplate> e l'impostazione dello stile il <xref:System.Windows.FrameworkElement.Style%2A> proprietà.  
  
 Lo stato attivo per gli stili di visualizzazione deve essere usate in modo coerente un tema o un'interfaccia utente, anziché utilizzare una diversa per ogni elemento con stato attivabile. Per informazioni dettagliate, vedere [stile per lo stato attivo nei controlli e FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>  
 [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Applicazione di stili per lo stato attivo nei controlli e FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)

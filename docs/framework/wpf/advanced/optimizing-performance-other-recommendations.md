---
title: 'Ottimizzazione delle prestazioni: Altri suggerimenti'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Terminal Services rendering [WPF]
- opacity [WPF]
- hit-test objects [WPF]
- ScrollBarVisibility enumeration [WPF]
- brushes [WPF], performance
ms.assetid: d028cc65-7e97-4a4f-9859-929734eaf40d
ms.openlocfilehash: fecb16592f3b3af78e329e095684b9c726f056f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703679"
---
# <a name="optimizing-performance-other-recommendations"></a>Ottimizzazione delle prestazioni: Altri suggerimenti
<a name="introduction"></a> Questo argomento offre suggerimenti sulle prestazioni aggiuntivi rispetto a quelli descritti negli argomenti della sezione [Ottimizzazione delle prestazioni di applicazioni WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md).  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
-   [Pennelli opachi ed elementi opachi](#Opacity)  
  
-   [Navigazione a un oggetto](#Navigation_Objects)  
  
-   [Hit testing su superfici 3D ampie](#Hit_Testing)  
  
-   [Evento CompositionTarget.Rendering](#CompositionTarget_Rendering_Event)  
  
-   [Evitare l'uso di ScrollBarVisibility=Auto](#Avoid_Using_ScrollBarVisibility)  
  
-   [Configurare il servizio Cache tipi di carattere per ridurre i tempi di avvio](#FontCache)  
  
<a name="Opacity"></a>   
## <a name="opacity-on-brushes-versus-opacity-on-elements"></a>Pennelli opachi ed elementi opachi  
 Quando si usa un' <xref:System.Windows.Media.Brush> per impostare il <xref:System.Windows.Shapes.Shape.Fill%2A> o <xref:System.Windows.Shapes.Shape.Stroke%2A> di un elemento, è consigliabile impostare il <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> valore anziché l'impostazione dell'elemento <xref:System.Windows.UIElement.Opacity%2A> proprietà. Modifica di un elemento <xref:System.Windows.UIElement.Opacity%2A> può causare proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per creare un'area temporanea.  
  
<a name="Navigation_Objects"></a>   
## <a name="navigation-to-object"></a>Navigazione a un oggetto  
 Il <xref:System.Windows.Navigation.NavigationWindow> oggetto deriva da <xref:System.Windows.Window> e lo estende con il supporto di esplorazione dei contenuti, principalmente tramite l'aggregazione <xref:System.Windows.Navigation.NavigationService> e il journal. È possibile aggiornare l'area client di <xref:System.Windows.Navigation.NavigationWindow> specificando una [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] o un oggetto. L'esempio seguente illustra entrambi i metodi:  
  
 [!code-csharp[Performance#PerformanceSnippet14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 Ogni <xref:System.Windows.Navigation.NavigationWindow> oggetto ha un journal che registra la cronologia di navigazione dell'utente in tale finestra. Uno degli scopi del journal è quello di consentire agli utenti di rintracciare i passaggi eseguiti.  
  
 Con la navigazione tramite un [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], il journal archivia solo il riferimento all'[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]. Ogni volta che viene rivisitata, la pagina viene ricostruita in modo dinamico; questa operazione può richiedere molto tempo, a seconda della complessità della pagina. In questo caso, il costo di archiviazione nel journal è basso, ma il tempo necessario per la ricostruzione della pagina è potenzialmente lungo.  
  
 Con la navigazione tramite un oggetto, nel journal viene archiviata l'intera struttura ad albero visiva dell'oggetto. Ogni volta che la pagina viene rivisitata, quindi, ne viene immediatamente eseguito il rendering, senza che debba essere ricostruita. In questo caso, il costo di archiviazione nel journal è alto, ma il tempo necessario per la ricostruzione della pagina è ridotto.  
  
 Quando si usa il <xref:System.Windows.Navigation.NavigationWindow> dell'oggetto, è necessario tenere presente come il supporto di inserimento nel journal influisce sulle prestazioni dell'applicazione. Per altre informazioni, vedere [Cenni preliminari sulla navigazione](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
<a name="Hit_Testing"></a>   
## <a name="hit-testing-on-large-3d-surfaces"></a>Hit testing su superfici 3D ampie  
 L'hit testing su superfici 3D ampie presenta requisiti particolarmente elevati in termini di consumo della CPU, soprattutto se alla superficie 3D viene aggiunta un'animazione. Se l'hit testing su queste superfici non è necessario, quindi, è opportuno disabilitarlo. Gli oggetti che derivano da <xref:System.Windows.UIElement> possa disabilitare l'hit testing impostando la <xref:System.Windows.UIElement.IsHitTestVisible%2A> proprietà `false`.  
  
<a name="CompositionTarget_Rendering_Event"></a>   
## <a name="compositiontargetrendering-event"></a>Evento CompositionTarget.Rendering  
 Il <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> evento causa [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] continua di animazioni a. Se si usa questo evento, disconnetterlo ogni volta che è possibile.  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>   
## <a name="avoid-using-scrollbarvisibilityauto"></a>Evitare l'uso di ScrollBarVisibility=Auto  
 Quando possibile, evitare di usare la <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> valore per il `HorizontalScrollBarVisibility` e `VerticalScrollBarVisibility` proprietà. Queste proprietà sono definite per <xref:System.Windows.Controls.RichTextBox>, <xref:System.Windows.Controls.ScrollViewer>, e <xref:System.Windows.Controls.TextBox> oggetti e come proprietà associata per il <xref:System.Windows.Controls.ListBox> oggetto. Al contrario, impostare <xref:System.Windows.Controls.ScrollBarVisibility> al <xref:System.Windows.Controls.ScrollBarVisibility.Disabled>, <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>, o <xref:System.Windows.Controls.ScrollBarVisibility.Visible>.  
  
 Il <xref:System.Windows.Controls.ScrollBarVisibility.Auto> valore è destinato ai casi quando lo spazio è limitato e le barre di scorrimento devono essere visualizzate solo quando necessario. Ad esempio, può essere utile usare questa <xref:System.Windows.Controls.ScrollBarVisibility> valore con un <xref:System.Windows.Controls.ListBox> di 30 elementi in contrapposizione a un <xref:System.Windows.Controls.TextBox> con centinaia di righe di testo.  
  
<a name="FontCache"></a>   
## <a name="configure-font-cache-service-to-reduce-start-up-time"></a>Configurare il servizio Cache tipi di carattere per ridurre il tempo di avvio  
 Con il servizio Cache tipi di carattere di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], i dati relativi ai tipi di carattere vengono condivisi tra le applicazioni [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Il servizio viene avviato insieme alla prima applicazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eseguita, a meno che non sia già in esecuzione. Se si usa [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)], è possibile impostare il servizio "Windows Presentation Foundation (WPF) del tipo di carattere Cache 3.0.0.0" da "Manuale" (predefinito) su "Automatico (avvio ritardato)" per ridurre il tempo di avvio di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazioni.  
  
## <a name="see-also"></a>Vedere anche
- [Pianificazione delle prestazioni dell'applicazione](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)
- [Sfruttare appieno l'hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)
- [Ottimizzazione delle prestazioni: layout e progettazione](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
- [Grafica bidimensionale e creazione di immagini](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamento dell'oggetto](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)
- [Risorse di applicazioni](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)
- [per](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)
- [Data binding](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)
- [Suggerimenti sulle animazioni](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)

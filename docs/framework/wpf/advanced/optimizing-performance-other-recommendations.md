---
title: 'Ottimizzazione delle prestazioni: altri suggerimenti'
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
ms.openlocfilehash: b6d99d90a3da232e1873ebe8433e01ceb2977de6
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636432"
---
# <a name="optimizing-performance-other-recommendations"></a>Ottimizzazione delle prestazioni: altri suggerimenti
<a name="introduction"></a> Questo argomento offre suggerimenti sulle prestazioni aggiuntivi rispetto a quelli descritti negli argomenti della sezione [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md).  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
- [Pennelli opachi ed elementi opachi](#Opacity)  
  
- [Navigazione a un oggetto](#Navigation_Objects)  
  
- [Hit testing su superfici 3D ampie](#Hit_Testing)  
  
- [Evento CompositionTarget.Rendering](#CompositionTarget_Rendering_Event)  
  
- [Evitare l'uso di ScrollBarVisibility=Auto](#Avoid_Using_ScrollBarVisibility)  
  
- [Configurare il servizio Cache tipi di carattere per ridurre i tempi di avvio](#FontCache)  
  
<a name="Opacity"></a>   
## <a name="opacity-on-brushes-versus-opacity-on-elements"></a>Pennelli opachi ed elementi opachi  
 Quando si usa un <xref:System.Windows.Media.Brush> per impostare la <xref:System.Windows.Shapes.Shape.Fill%2A> o <xref:System.Windows.Shapes.Shape.Stroke%2A> di un elemento, è preferibile impostare il valore di <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> anziché l'impostazione della proprietà <xref:System.Windows.UIElement.Opacity%2A> dell'elemento. La modifica della proprietà <xref:System.Windows.UIElement.Opacity%2A> di un elemento può provocare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la creazione di una superficie temporanea.  
  
<a name="Navigation_Objects"></a>   
## <a name="navigation-to-object"></a>Navigazione a un oggetto  
 L'oggetto <xref:System.Windows.Navigation.NavigationWindow> deriva da <xref:System.Windows.Window> e lo estende con il supporto per la navigazione del contenuto, principalmente aggregando <xref:System.Windows.Navigation.NavigationService> e Journal. È possibile aggiornare l'area client di <xref:System.Windows.Navigation.NavigationWindow> specificando un URI (Uniform Resource Identifier) o un oggetto. L'esempio seguente illustra entrambi i metodi:  
  
 [!code-csharp[Performance#PerformanceSnippet14](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 Ogni oggetto <xref:System.Windows.Navigation.NavigationWindow> dispone di un journal che registra la cronologia di navigazione dell'utente in tale finestra. Uno degli scopi del journal è quello di consentire agli utenti di rintracciare i passaggi eseguiti.  
  
 Quando si esegue la navigazione utilizzando un URI (Uniform Resource Identifier), nel journal viene archiviato solo il riferimento URI (Uniform Resource Identifier). Ogni volta che viene rivisitata, la pagina viene ricostruita in modo dinamico; questa operazione può richiedere molto tempo, a seconda della complessità della pagina. In questo caso, il costo di archiviazione nel journal è basso, ma il tempo necessario per la ricostruzione della pagina è potenzialmente lungo.  
  
 Con la navigazione tramite un oggetto, nel journal viene archiviata l'intera struttura ad albero visiva dell'oggetto. Ogni volta che la pagina viene rivisitata, quindi, ne viene immediatamente eseguito il rendering, senza che debba essere ricostruita. In questo caso, il costo di archiviazione nel journal è alto, ma il tempo necessario per la ricostruzione della pagina è ridotto.  
  
 Quando si utilizza l'oggetto <xref:System.Windows.Navigation.NavigationWindow>, è necessario tenere presente il modo in cui il supporto per il Journal influisca sulle prestazioni dell'applicazione. Per altre informazioni, vedere [Cenni preliminari sulla navigazione](../app-development/navigation-overview.md).  
  
<a name="Hit_Testing"></a>   
## <a name="hit-testing-on-large-3d-surfaces"></a>Hit testing su superfici 3D ampie  
 L'hit testing su superfici 3D ampie presenta requisiti particolarmente elevati in termini di consumo della CPU, soprattutto se alla superficie 3D viene aggiunta un'animazione. Se l'hit testing su queste superfici non è necessario, quindi, è opportuno disabilitarlo. Gli oggetti derivati da <xref:System.Windows.UIElement> possono disabilitare l'hit testing impostando la proprietà <xref:System.Windows.UIElement.IsHitTestVisible%2A> su `false`.  
  
<a name="CompositionTarget_Rendering_Event"></a>   
## <a name="compositiontargetrendering-event"></a>Evento CompositionTarget.Rendering  
 L'evento <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> causa l'animazione continua di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Se si usa questo evento, disconnetterlo ogni volta che è possibile.  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>   
## <a name="avoid-using-scrollbarvisibilityauto"></a>Evitare l'uso di ScrollBarVisibility=Auto  
 Quando possibile, evitare di utilizzare il valore <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> per le proprietà `HorizontalScrollBarVisibility` e `VerticalScrollBarVisibility`. Queste proprietà sono definite per gli oggetti <xref:System.Windows.Controls.RichTextBox>, <xref:System.Windows.Controls.ScrollViewer>e <xref:System.Windows.Controls.TextBox> e come proprietà associata per l'oggetto <xref:System.Windows.Controls.ListBox>. Impostare invece <xref:System.Windows.Controls.ScrollBarVisibility> su <xref:System.Windows.Controls.ScrollBarVisibility.Disabled>, <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>o <xref:System.Windows.Controls.ScrollBarVisibility.Visible>.  
  
 Il valore <xref:System.Windows.Controls.ScrollBarVisibility.Auto> è destinato ai casi in cui lo spazio è limitato e le barre di scorrimento devono essere visualizzate solo quando necessario. Ad esempio, può essere utile usare questo valore <xref:System.Windows.Controls.ScrollBarVisibility> con una <xref:System.Windows.Controls.ListBox> di 30 elementi, anziché un <xref:System.Windows.Controls.TextBox> con centinaia di righe di testo.  
  
<a name="FontCache"></a>   
## <a name="configure-font-cache-service-to-reduce-start-up-time"></a>Configurare il servizio Cache tipi di carattere per ridurre il tempo di avvio  
 Il servizio cache dei tipi di carattere WPF condivide i dati di tipo carattere tra le applicazioni WPF. La prima applicazione WPF eseguita avvia il servizio se il servizio non è già in esecuzione. Se si utilizza Windows Vista, è possibile impostare il servizio "Windows Presentation Foundation (WPF) font cache 3.0.0.0" da "Manual" (impostazione predefinita) a "Automatic (avvio ritardato)" per ridurre il tempo di avvio iniziale delle applicazioni WPF.  
  
## <a name="see-also"></a>Vedere anche

- [Pianificazione delle prestazioni dell'applicazione](planning-for-application-performance.md)
- [Sfruttare appieno l'hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Ottimizzazione delle prestazioni: layout e progettazione](optimizing-performance-layout-and-design.md)
- [Grafica bidimensionale e creazione di immagini](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamento dell'oggetto](optimizing-performance-object-behavior.md)
- [Risorse di applicazioni](optimizing-performance-application-resources.md)
- [per](optimizing-performance-text.md)
- [Data binding](optimizing-performance-data-binding.md)
- [Suggerimenti sulle animazioni](../graphics-multimedia/animation-tips-and-tricks.md)

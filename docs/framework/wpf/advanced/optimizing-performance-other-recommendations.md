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
ms.openlocfilehash: 727331adb41251460209f157d1804ff455bcf473
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186308"
---
# <a name="optimizing-performance-other-recommendations"></a>Ottimizzazione delle prestazioni: altri suggerimenti
<a name="introduction"></a> Questo argomento offre suggerimenti sulle prestazioni aggiuntivi rispetto a quelli descritti negli argomenti della sezione [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md).  
  
 In questo argomento sono incluse le sezioni seguenti:  
  
- [Pennelli opachi ed elementi opachi](#Opacity)  
  
- [Navigazione a un oggetto](#Navigation_Objects)  
  
- [Hit testing su superfici 3D ampie](#Hit_Testing)  
  
- [Evento CompositionTarget.Rendering](#CompositionTarget_Rendering_Event)  
  
- [Evitare l'uso di ScrollBarVisibility=Auto](#Avoid_Using_ScrollBarVisibility)  
  
- [Configurare il servizio Cache tipi di carattere per ridurre il tempo di avvio](#FontCache)  
  
<a name="Opacity"></a>
## <a name="opacity-on-brushes-versus-opacity-on-elements"></a>Pennelli opachi ed elementi opachi  
 Quando si <xref:System.Windows.Media.Brush> utilizza un <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Shape.Stroke%2A> per impostare l'oggetto o <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> di un elemento, è <xref:System.Windows.UIElement.Opacity%2A> preferibile impostare il valore anziché l'impostazione della proprietà dell'elemento. La modifica della <xref:System.Windows.UIElement.Opacity%2A> proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di un elemento può causare la creazione di una superficie temporanea.  
  
<a name="Navigation_Objects"></a>
## <a name="navigation-to-object"></a>Navigazione a un oggetto  
 L'oggetto <xref:System.Windows.Navigation.NavigationWindow> deriva <xref:System.Windows.Window> da e lo estende con il <xref:System.Windows.Navigation.NavigationService> supporto per l'esplorazione del contenuto, principalmente mediante l'aggregazione e il journal. È possibile aggiornare <xref:System.Windows.Navigation.NavigationWindow> l'area client di specificando un URI (Uniform Resource Identifier) o un oggetto. L'esempio seguente illustra entrambi i metodi:  
  
 [!code-csharp[Performance#PerformanceSnippet14](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 Ogni <xref:System.Windows.Navigation.NavigationWindow> oggetto dispone di un giornale di registrazione che registra la cronologia di spostamento dell'utente in tale finestra. Uno degli scopi del journal è quello di consentire agli utenti di rintracciare i passaggi eseguiti.  
  
 Quando ci si sposta utilizzando un URI (Uniform Resource Identifier), il giornale di registrazione archivia solo il riferimento URI (Uniform Resource Identifier). Ogni volta che viene rivisitata, la pagina viene ricostruita in modo dinamico; questa operazione può richiedere molto tempo, a seconda della complessità della pagina. In questo caso, il costo di archiviazione nel journal è basso, ma il tempo necessario per la ricostruzione della pagina è potenzialmente lungo.  
  
 Con la navigazione tramite un oggetto, nel journal viene archiviata l'intera struttura ad albero visiva dell'oggetto. Ogni volta che la pagina viene rivisitata, quindi, ne viene immediatamente eseguito il rendering, senza che debba essere ricostruita. In questo caso, il costo di archiviazione nel journal è alto, ma il tempo necessario per la ricostruzione della pagina è ridotto.  
  
 Quando si <xref:System.Windows.Navigation.NavigationWindow> utilizza l'oggetto, è necessario tenere presente in che modo il supporto per l'inserimento nel journal influisce sulle prestazioni dell'applicazione. Per ulteriori informazioni, consultate [Cenni preliminari sulla navigazione.](../app-development/navigation-overview.md)  
  
<a name="Hit_Testing"></a>
## <a name="hit-testing-on-large-3d-surfaces"></a>Hit testing su superfici 3D ampie  
 L'hit testing su superfici 3D ampie presenta requisiti particolarmente elevati in termini di consumo della CPU, soprattutto se alla superficie 3D viene aggiunta un'animazione. Se l'hit testing su queste superfici non è necessario, quindi, è opportuno disabilitarlo. Gli oggetti derivati da <xref:System.Windows.UIElement> possono disabilitare l'hit testing impostando la proprietà su <xref:System.Windows.UIElement.IsHitTestVisible%2A> `false`.  
  
<a name="CompositionTarget_Rendering_Event"></a>
## <a name="compositiontargetrendering-event"></a>Evento CompositionTarget.Rendering  
 <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> L'evento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] causa l'animazione continua. Se si usa questo evento, disconnetterlo ogni volta che è possibile.  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>
## <a name="avoid-using-scrollbarvisibilityauto"></a>Evitare l'uso di ScrollBarVisibility=Auto  
 Quando possibile, evitare di utilizzare il <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> valore delle proprietà `HorizontalScrollBarVisibility` e `VerticalScrollBarVisibility` . Queste proprietà vengono <xref:System.Windows.Controls.RichTextBox> <xref:System.Windows.Controls.ScrollViewer>definite <xref:System.Windows.Controls.TextBox> per gli oggetti , e <xref:System.Windows.Controls.ListBox> e come proprietà associata per l'oggetto. Impostare <xref:System.Windows.Controls.ScrollBarVisibility> invece <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>su <xref:System.Windows.Controls.ScrollBarVisibility.Visible> <xref:System.Windows.Controls.ScrollBarVisibility.Disabled>, , o .  
  
 Il <xref:System.Windows.Controls.ScrollBarVisibility.Auto> valore è destinato ai casi in cui lo spazio è limitato e le barre di scorrimento devono essere visualizzate solo quando necessario. Ad esempio, può essere utile <xref:System.Windows.Controls.ScrollBarVisibility> utilizzare <xref:System.Windows.Controls.ListBox> questo valore con un massimo <xref:System.Windows.Controls.TextBox> di 30 elementi anziché con centinaia di righe di testo.  
  
<a name="FontCache"></a>
## <a name="configure-font-cache-service-to-reduce-start-up-time"></a>Configurare il servizio Cache tipi di carattere per ridurre il tempo di avvio  
 Il servizio Cache tipi di carattere WPF condivide i dati dei tipi di carattere tra le applicazioni WPFWPF. La prima applicazione WPFWPF eseguita avvia questo servizio se il servizio non è già in esecuzione. Se si utilizza Windows Vista, è possibile impostare il servizio "Windows Presentation Foundation (WPF) Font Cache 3.0.0.0" da "Manuale" (impostazione predefinita) a "Automatico (avvio ritardato)" per ridurre il tempo di avvio iniziale delle applicazioni WPFWPF.  
  
## <a name="see-also"></a>Vedere anche

- [Pianificazione delle prestazioni dell'applicazione](planning-for-application-performance.md)
- [Sfruttare appieno l'hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout e progettazione](optimizing-performance-layout-and-design.md)
- [Grafica 2D e creazione di immagini](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamento degli oggetti](optimizing-performance-object-behavior.md)
- [Risorse dell'applicazione](optimizing-performance-application-resources.md)
- [Testo](optimizing-performance-text.md)
- [Associazione dati](optimizing-performance-data-binding.md)
- [Suggerimenti sulle animazioni](../graphics-multimedia/animation-tips-and-tricks.md)

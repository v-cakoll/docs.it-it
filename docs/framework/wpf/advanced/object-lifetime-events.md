---
title: Eventi di durata degli oggetti
ms.date: 03/30/2017
helpviewer_keywords:
- events [WPF], ContentRendered
- events [WPF], Deactivated
- events [WPF], Unloaded
- Activated events [WPF]
- events [WPF], Loaded
- Application objects [WPF], lifetime events
- events [WPF], Activated
- ContentRendered events [WPF]
- Deactivated events [WPF]
- events [WPF], Initialized
- events [WPF], Closing
- Unloaded events [WPF]
- exit events [WPF]
- objects' lifetime events [WPF]
- Loaded events [WPF]
- Closing events [WPF]
- events [WPF], Closed
- Initialized events [WPF]
- Closed events [WPF]
- startup events [WPF]
- lifetime events of objects [WPF]
ms.assetid: face6fc7-465b-4502-bfe5-e88d2e729a78
ms.openlocfilehash: 3b761674bd2464ee87e07d9299c805431f8fdeb7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141107"
---
# <a name="object-lifetime-events"></a>Eventi di durata degli oggetti
In questo argomento vengono descritti gli eventi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] specifici che denotano le fasi della durata di un oggetto in termini di creazione, uso e distruzione.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Prerequisites  
 In questo argomento si presuppongono la conoscenza delle proprietà di dipendenza dal punto di vista di un consumer di proprietà di dipendenza esistenti nelle classi [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], nonché la lettura dell'argomento [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md). Per seguire gli esempi illustrati in questo argomento, è anche necessario conoscere [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] (vedere [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)) e saper scrivere applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="intro"></a>
## <a name="object-lifetime-events"></a>Eventi di durata degli oggetti  
 Tutti gli oggetti nel codice gestito di Microsoft .NET Framework passano attraverso un insieme simile di fasi di vita, creazione, utilizzo e distruzione. Per molti oggetti la fase di finalizzazione della vita si verifica nell'ambito della fase di distruzione. Gli oggetti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] più specificamente gli oggetti visivi che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] identifica come elementi, hanno una serie comune di fasi di vita dell'oggetto. I modelli di programmazione e applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] espongono queste fasi come una serie di eventi. Esistono quattro tipi principali di oggetti in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in relazione agli eventi di durata: gli elementi in generale, gli elementi finestra, gli host di navigazione e gli oggetti applicazione. Le finestre e gli host di navigazione fanno parte anche del più ampio raggruppamento di oggetti visivi (elementi). In questo argomento vengono descritti gli eventi di durata che sono comuni a tutti gli elementi; vengono quindi introdotti quelli più specifici che si applicano alle definizioni dell'applicazione, alle finestre o agli host di navigazione.  
  
<a name="common_events"></a>
## <a name="common-lifetime-events-for-elements"></a>Eventi di durata comuni degli elementi  
 Qualsiasi elemento a livello di framework WPF <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>(quegli oggetti che <xref:System.Windows.FrameworkElement.Initialized> <xref:System.Windows.FrameworkElement.Loaded>derivano <xref:System.Windows.FrameworkElement.Unloaded>da uno o più ) dispone di tre eventi di durata comuni: , e .  
  
### <a name="initialized"></a>Inizializzato  
 <xref:System.Windows.FrameworkElement.Initialized>viene generato per primo e corrisponde approssimativamente all'inizializzazione dell'oggetto dalla chiamata al relativo costruttore. Poiché l'evento si verifica in seguito all'inizializzazione, tutte le proprietà dell'oggetto sono sicuramente impostate. (Un'eccezione è l'utilizzo di espressioni, ad esempio le risorse dinamiche o l'associazione; queste saranno espressioni non valutate.) Come conseguenza del requisito che tutte le <xref:System.Windows.FrameworkElement.Initialized> proprietà sono impostate, la sequenza di essere generato da elementi annidati definiti nel markup sembra verificarsi in ordine di elementi più profondi nella struttura ad albero dell'elemento prima, quindi gli elementi padre verso la radice. Questo ordine è determinato dal fatto che le relazioni padre-figlio e il contenimento sono proprietà e pertanto l'elemento padre non può segnalare l'inizializzazione finché tutti gli elementi figlio che riempiono la proprietà non sono stati completamente inizializzati.  
  
 Quando si scrivono gestori <xref:System.Windows.FrameworkElement.Initialized> in risposta all'evento, è necessario considerare che non vi è alcuna garanzia che tutti gli altri elementi nella struttura ad albero dell'elemento (albero logico o struttura ad albero visuale) intorno al punto in cui è associato il gestore, in particolare gli elementi padre. Le variabili membro potrebbero essere Null oppure le origini dati potrebbero non essere ancora popolate dall'associazione sottostante (anche a livello di espressione).  
  
### <a name="loaded"></a>Loaded  
 <xref:System.Windows.FrameworkElement.Loaded>viene sollevato successivamente. L'evento <xref:System.Windows.FrameworkElement.Loaded> viene generato prima del rendering finale, ma dopo che il sistema di layout ha calcolato tutti i valori necessari per il rendering. <xref:System.Windows.FrameworkElement.Loaded>comporta che l'albero logico in cui è contenuto un elemento sia completo e si connette a un'origine di presentazione che fornisce HWND e la superficie di rendering. L'associazione dati standard (associazione a origini locali, ad esempio <xref:System.Windows.FrameworkElement.Loaded>altre proprietà o origini dati definite direttamente) avrà avuto esista prima di . È possibile che il data binding asincrono (a origini esterne o dinamiche) si sia verificato, ma a causa della sua natura asincrona non è possibile averne la certezza.  
  
 Il meccanismo <xref:System.Windows.FrameworkElement.Loaded> in base al <xref:System.Windows.FrameworkElement.Initialized>quale viene generato l'evento è diverso da . L'evento <xref:System.Windows.FrameworkElement.Initialized> viene generato elemento per elemento, senza un coordinamento diretto da parte di una struttura ad albero dell'elemento completata. Al contrario, l'evento <xref:System.Windows.FrameworkElement.Loaded> viene generato come uno sforzo coordinato in tutto l'albero dell'elemento (in particolare, l'albero logico). Quando tutti gli elementi nella struttura ad albero si <xref:System.Windows.FrameworkElement.Loaded> trovano in uno stato in cui sono considerati caricati, l'evento viene generato innanzitutto sull'elemento radice. L'evento <xref:System.Windows.FrameworkElement.Loaded> viene quindi generato successivamente su ogni elemento figlio.  
  
> [!NOTE]
> Questo comportamento potrebbe sembrare a prima vista analogo al tunneling per un evento indirizzato. Tuttavia, le informazioni non vengono passate da evento a evento. Ogni elemento ha sempre la <xref:System.Windows.FrameworkElement.Loaded> possibilità di gestire il proprio evento e contrassegnare i dati dell'evento come gestiti non ha alcun effetto oltre tale elemento.  
  
### <a name="unloaded"></a>Unloaded  
 <xref:System.Windows.FrameworkElement.Unloaded>viene generato per ultimo e viene avviato dall'origine della presentazione o dal padre visivo da rimuovere. Quando <xref:System.Windows.FrameworkElement.Unloaded> viene generato e gestito, l'elemento che è <xref:System.Windows.FrameworkElement.Parent%2A> l'elemento padre dell'origine eventi (come determinato dalla proprietà) o qualsiasi elemento specificato verso l'alto nelle strutture ad albero logiche o visive potrebbe essere già stato annullato, il che significa che l'associazione dati, i riferimenti alle risorse e gli stili non possono essere impostati sul valore normale o per l'ultimo periodo di esecuzione noto.  
  
<a name="application_model_elements"></a>
## <a name="lifetime-events-application-model-elements"></a>Elementi del modello di applicazione di eventi di durata  
 La compilazione degli eventi di durata comuni <xref:System.Windows.Application>per <xref:System.Windows.Window> <xref:System.Windows.Controls.Page>gli <xref:System.Windows.Navigation.NavigationWindow>elementi sono i seguenti elementi del modello di applicazione: , , , e <xref:System.Windows.Controls.Frame>. Questi estendono gli eventi di durata comuni con eventi aggiuntivi, pertinenti al relativo scopo specifico e vengono descritti in dettaglio nelle sezioni seguenti:  
  
- <xref:System.Windows.Application>: [Panoramica della gestione delle applicazioni](../app-development/application-management-overview.md).  
  
- <xref:System.Windows.Window>: [Cenni preliminari su Windows WPF](../app-development/wpf-windows-overview.md).  
  
- <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, e : [Panoramica della navigazione](../app-development/navigation-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Precedenza del valore della proprietà di dipendenzaDependency Property Value Precedence](dependency-property-value-precedence.md)
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)

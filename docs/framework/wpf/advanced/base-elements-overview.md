---
title: Cenni preliminari sugli elementi di base
ms.date: 03/30/2017
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: f6519675ebf3624152e1077e7582f04e38b1dce9
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644045"
---
# <a name="base-elements-overview"></a>Cenni preliminari sugli elementi di base
Un'alta percentuale [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] di classi in sono derivate da quattro classi che sono comunemente indicate nella documentazione SDK come le classi dell'elemento di base. Queste classi <xref:System.Windows.UIElement> <xref:System.Windows.FrameworkElement>sono <xref:System.Windows.ContentElement>, <xref:System.Windows.FrameworkContentElement>, e . La <xref:System.Windows.DependencyObject> classe è anche correlata, perché è <xref:System.Windows.UIElement> una classe base comune di entrambi e<xref:System.Windows.ContentElement>  

<a name="base_apis"></a>
## <a name="base-element-apis-in-wpf-classes"></a>API degli elementi di base nelle classi WPF  
 Entrambi <xref:System.Windows.UIElement> <xref:System.Windows.ContentElement> e sono <xref:System.Windows.DependencyObject>derivati da , attraverso percorsi un po 'diversi. La divisione a questo <xref:System.Windows.UIElement> livello <xref:System.Windows.ContentElement> riguarda il modo in cui un o viene utilizzato in un'interfaccia utente e lo scopo che servono in un'applicazione. <xref:System.Windows.UIElement>ha <xref:System.Windows.Media.Visual> anche nella gerarchia di classi, che è una classe [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]che espone il supporto grafico di livello inferiore sottostante il . <xref:System.Windows.Media.Visual>fornisce un framework di rendering definendo aree dello schermo rettangolari indipendenti. In pratica, <xref:System.Windows.UIElement> è per gli elementi che supporteranno un modello a oggetti più grande, sono destinati a eseguire il rendering e il layout in aree che possono essere descritte come aree dello schermo rettangolari e in cui il modello di contenuto è deliberatamente più aperto, per consentire diverse combinazioni di elementi. <xref:System.Windows.ContentElement>non deriva <xref:System.Windows.Media.Visual>da ; il suo modello <xref:System.Windows.ContentElement> è che un sarebbe stato utilizzato da qualcos'altro, ad esempio <xref:System.Windows.Media.Visual> un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] lettore o un visualizzatore che sarebbe quindi interpretare gli elementi e produrre il completo per consumare. Alcune <xref:System.Windows.UIElement> classi devono essere host di contenuto: forniscono l'hosting e il rendering per una o più <xref:System.Windows.ContentElement> classi (è<xref:System.Windows.Controls.DocumentViewer> un esempio di tale classe). <xref:System.Windows.ContentElement>viene utilizzato come classe base per gli elementi con modelli a oggetti leggermente più piccoli e <xref:System.Windows.UIElement>che più indirizzano il testo, le informazioni o il contenuto del documento che potrebbe essere ospitato all'interno di un oggetto .  
  
### <a name="framework-level-and-core-level"></a>Livello di framework e livello principale  
 <xref:System.Windows.UIElement>funge da classe <xref:System.Windows.FrameworkElement>base <xref:System.Windows.ContentElement> per , e <xref:System.Windows.FrameworkContentElement>funge da classe base per . Il motivo di questo livello successivo di classi consiste nel supportare un livello di base WPF che è separato da un livello di framework WPF, con questa divisione esistente anche nel modo in cui le API vengono suddivise tra gli assembly PresentationCore e PresentationFramework. Il livello di framework WPF offre una soluzione più completa per le necessità di base delle applicazioni, inclusa l'implementazione del gestore di layout per le presentazioni. Il livello principale WPF offre una modalità per usare in modo esteso [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] senza l'overhead di assembly aggiuntivo. La distinzione tra questi livelli molto raramente è importante per la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] maggior parte degli scenari di sviluppo di applicazioni tipici e in generale è necessario considerare le API nel suo complesso e non preoccuparsi della differenza tra il livello del framework WPF e il livello di core WPFWPF. Può essere necessario conoscere le distinzioni tra i livelli se in un progetto di applicazione si decide di sostituire quantità significative di funzionalità del livello di framework WPF, ad esempio se la soluzione complessiva dispone già di implementazioni personalizzate per la composizione e il layout dell'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
<a name="subclassing_elements"></a>
## <a name="choosing-which-element-to-derive-from"></a>Scelta dell'elemento da cui derivare  
 Il modo ottimale per creare una classe personalizzata che estende [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consiste nel derivare da una delle classi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante cui si ottiene la massima funzionalità desiderata tramite la gerarchia di classi esistente. Questa sezione elenca le funzionalità fornite da tre delle più importanti classi di elementi che consentono di decidere da quale classe ereditare.  
  
 Se si implementa un controllo, che in realtà è uno [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dei motivi più comuni per la derivazione da una classe, è probabile che <xref:System.Windows.Controls.Control> si desideri derivare da una classe che è un controllo pratico, una classe base di famiglia di controlli o almeno dalla classe base. Per istruzioni ed esempi pratici, vedere [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md).  
  
 Se non si crea un controllo ed è necessario derivare da una classe più elevata nella gerarchia, nelle sezioni seguenti vengono fornite informazioni sulle caratteristiche definite in ogni classe degli elementi di base.  
  
 Se si crea una classe <xref:System.Windows.DependencyObject>che deriva da , si ereditano le seguenti funzionalità:  
  
- <xref:System.Windows.DependencyObject.GetValue%2A>e <xref:System.Windows.DependencyObject.SetValue%2A> supporto, e il supporto generale del sistema di proprietà.  
  
- Possibilità di utilizzare le proprietà di dipendenza e le proprietà associate implementate come proprietà di dipendenza.  
  
 Se si crea una classe <xref:System.Windows.UIElement>che deriva da , si ereditano le seguenti funzionalità oltre a quella fornita da <xref:System.Windows.DependencyObject>:  
  
- Supporto di base per i valori delle proprietà animate. Per ulteriori informazioni, consultate [Cenni preliminari sull'animazione.](../graphics-multimedia/animation-overview.md)  
  
- Supporto di eventi di input di base e supporto dei comandi. Per altre informazioni, vedere [Cenni preliminari sull’input](input-overview.md) e [Cenni preliminari sull'esecuzione di comandi](commanding-overview.md).  
  
- Metodi virtuali di cui è possibile eseguire l'override per fornire informazioni a un sistema di layout.  
  
 Se si crea una classe <xref:System.Windows.FrameworkElement>che deriva da , si ereditano le seguenti funzionalità oltre a quella fornita da <xref:System.Windows.UIElement>:  
  
- Supporto per l'uso di stili e storyboard. Per ulteriori informazioni, vedere <xref:System.Windows.Style> [Cenni preliminari](../graphics-multimedia/storyboards-overview.md)sugli storyboard .  
  
- Supporto del data binding. Per ulteriori informazioni, vedere [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md).  
  
- Supporto per i riferimenti di risorse dinamiche. Per altre informazioni, vedere [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Supporto dell'ereditarietà dei valori di proprietà e altri flag nei metadati che agevolano la segnalazione di condizioni relative alle proprietà ai servizi del framework, ad esempio data binding, stili o implementazione del layout del framework. Per altre informazioni, vedere [Metadati delle proprietà del framework](framework-property-metadata.md).  
  
- Concetto di albero logico. Per altre informazioni, vedere [Strutture ad albero in WPF](trees-in-wpf.md).  
  
- Supporto per l'implementazione pratica a livello di <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> framework WPF del sistema di layout, incluso un override in grado di rilevare le modifiche alle proprietà che influenzano il layout.  
  
 Se si crea una classe <xref:System.Windows.ContentElement>che deriva da , si ereditano le seguenti funzionalità oltre a quella fornita da <xref:System.Windows.DependencyObject>:  
  
- Supporto per le animazioni. Per ulteriori informazioni, consultate [Cenni preliminari sull'animazione.](../graphics-multimedia/animation-overview.md)  
  
- Supporto di eventi di input di base e supporto dei comandi. Per altre informazioni, vedere [Cenni preliminari sull’input](input-overview.md) e [Cenni preliminari sull'esecuzione di comandi](commanding-overview.md).  
  
 Se si crea una classe <xref:System.Windows.FrameworkContentElement>che deriva da , si ottengono le seguenti funzionalità oltre a quella fornita da <xref:System.Windows.ContentElement>:  
  
- Supporto per l'uso di stili e storyboard. Per ulteriori informazioni, vedere <xref:System.Windows.Style> e [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md).  
  
- Supporto del data binding. Per ulteriori informazioni, vedere [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md).  
  
- Supporto per i riferimenti di risorse dinamiche. Per altre informazioni, vedere [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Supporto dell'ereditarietà dei valori di proprietà e altri flag nei metadati che agevolano la segnalazione di condizioni relative alle proprietà ai servizi del framework, ad esempio data binding, stili o implementazione del layout del framework. Per altre informazioni, vedere [Metadati delle proprietà del framework](framework-property-metadata.md).  
  
- Non si eredita l'accesso alle modifiche <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>del sistema di layout (ad esempio ). Le implementazioni del sistema <xref:System.Windows.FrameworkElement>di layout sono disponibili solo su . Tuttavia, si <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> eredita una sostituzione in grado di rilevare le modifiche alle proprietà che influenzano il layout e segnalarle a qualsiasi host di contenuto.  
  
 I modelli di contenuto sono documentati per una varietà di classi. Il modello di contenuto per una classe è un fattore possibile da considerare per trovare una classe adatta da cui derivare. Per altre informazioni, vedere [Modello di contenuto WPF](../controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>
## <a name="other-base-classes"></a>Altre classi di base  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject>fornisce supporto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per il modello di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] threading e consente <xref:System.Windows.Threading.Dispatcher>a tutti gli oggetti creati per le applicazioni di essere associati a un oggetto . Anche se non si <xref:System.Windows.UIElement> <xref:System.Windows.DependencyObject>deriva <xref:System.Windows.Media.Visual>da , , o <xref:System.Windows.Threading.DispatcherObject> , è consigliabile derivare da per ottenere il supporto del modello di threading. Per altre informazioni, vedere [Modello di threading](threading-model.md).  
  
### <a name="visual"></a>Visual  
 <xref:System.Windows.Media.Visual>implementa il concetto di un oggetto 2D che generalmente richiede la presentazione visiva in un'area approssimativamente rettangolare. Il rendering effettivo <xref:System.Windows.Media.Visual> di un avviene in altre classi <xref:System.Windows.Media.Visual> (non è indipendente), ma la classe fornisce un tipo noto che viene utilizzato dai processi di rendering a vari livelli. <xref:System.Windows.Media.Visual>implementa l'hit testing, ma non espone eventi che segnalano <xref:System.Windows.UIElement>positivi di hit testing (questi sono in ). Per altre informazioni, vedere [Programmazione a livello visivo](../graphics-multimedia/visual-layer-programming.md).  
  
### <a name="freezable"></a>Freezable  
 <xref:System.Windows.Freezable>simula l'immutabilità in un oggetto modificabile fornendo i mezzi per generare copie dell'oggetto quando un oggetto non modificabile è richiesto o desiderato per motivi di prestazioni. Il <xref:System.Windows.Freezable> tipo fornisce una base comune per alcuni elementi grafici, ad esempio geometrie e pennelli, nonché per le animazioni. In particolare, <xref:System.Windows.Freezable> a <xref:System.Windows.Media.Visual>non è un ; può contenere proprietà che diventano sottoproprietà quando l'oggetto <xref:System.Windows.Freezable> viene applicato per riempire un valore di proprietà di un altro oggetto e tali sottoproprietà potrebbero influire sul rendering. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable>è <xref:System.Windows.Freezable> una classe derivata che aggiunge in modo specifico il livello di controllo dell'animazione e alcuni membri dell'utilità in modo che le proprietà attualmente animate possano essere distinte dalle proprietà non animate.  
  
### <a name="control"></a>Controllo  
 <xref:System.Windows.Controls.Control>è la classe base desiderata per il tipo di oggetto che viene definito in modo varia un controllo o un componente, a seconda della tecnologia. In genere, le classi di controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono classi che rappresentano direttamente un controllo dell'interfaccia utente o partecipano alla composizione di tale controllo. La funzionalità <xref:System.Windows.Controls.Control> principale che consente è il modello di controllo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Control>
- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Panoramica della creazione di controlli](../controls/control-authoring-overview.md)
- [Architettura WPF](wpf-architecture.md)

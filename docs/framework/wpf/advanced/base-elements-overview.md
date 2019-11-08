---
title: Cenni preliminari sugli elementi di base
ms.date: 03/30/2017
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: 823c81bf6b21b88d719503387a68ce6e7d643d61
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740920"
---
# <a name="base-elements-overview"></a>Cenni preliminari sugli elementi di base
Una percentuale elevata di classi in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] deriva da quattro classi, comunemente definite nella documentazione dell'SDK come classi di elementi di base. Queste classi sono <xref:System.Windows.UIElement>, <xref:System.Windows.FrameworkElement>, <xref:System.Windows.ContentElement>e <xref:System.Windows.FrameworkContentElement>. Anche la classe <xref:System.Windows.DependencyObject> è correlata, perché è una classe di base comune sia <xref:System.Windows.UIElement> che <xref:System.Windows.ContentElement>  

<a name="base_apis"></a>   
## <a name="base-element-apis-in-wpf-classes"></a>API degli elementi di base nelle classi WPF  
 Sia <xref:System.Windows.UIElement> che <xref:System.Windows.ContentElement> derivano da <xref:System.Windows.DependencyObject>, tramite percorsi leggermente diversi. La suddivisione a questo livello riguarda il modo in cui un <xref:System.Windows.UIElement> o un <xref:System.Windows.ContentElement> vengono usati in un'interfaccia utente e lo scopo che svolgono in un'applicazione. <xref:System.Windows.UIElement> dispone anche di <xref:System.Windows.Media.Visual> nella relativa gerarchia di classi, ovvero una classe che espone il supporto della grafica di livello inferiore sottostante al [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. <xref:System.Windows.Media.Visual> fornisce un Framework di rendering definendo aree della schermata rettangolari indipendenti. In pratica, <xref:System.Windows.UIElement> è per gli elementi che supporteranno un modello a oggetti più grande, sono progettati per il rendering e il layout in aree che possono essere descritte come aree della schermata rettangolare e in cui il modello di contenuto è intenzionalmente più aperto, per consentire combinazioni diverse di elementi. <xref:System.Windows.ContentElement> non deriva da <xref:System.Windows.Media.Visual>; il modello è che un <xref:System.Windows.ContentElement> verrebbe utilizzato da un altro elemento, ad esempio un Reader o un visualizzatore che interpreterà quindi gli elementi e produrrà la <xref:System.Windows.Media.Visual> completa per l'utilizzo da parte di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Alcune classi di <xref:System.Windows.UIElement> sono destinate a essere host di contenuto: forniscono l'hosting e il rendering per una o più classi <xref:System.Windows.ContentElement> (<xref:System.Windows.Controls.DocumentViewer> è un esempio di tale classe). <xref:System.Windows.ContentElement> viene utilizzata come classe di base per gli elementi con modelli a oggetti più piccoli e che più indirizzano il contenuto del testo, delle informazioni o del documento che potrebbe essere ospitato all'interno di un <xref:System.Windows.UIElement>.  
  
### <a name="framework-level-and-core-level"></a>Livello di framework e livello principale  
 <xref:System.Windows.UIElement> funge da classe base per <xref:System.Windows.FrameworkElement>e <xref:System.Windows.ContentElement> funge da classe di base per <xref:System.Windows.FrameworkContentElement>. Il motivo di questo livello di classi successivo è quello di supportare un livello di core WPF separato da un livello di Framework WPF, con questa divisione anche nel modo in cui le API sono divise tra gli assembly PresentationCore e PresentationFramework. Il livello di framework WPF offre una soluzione più completa per le necessità di base delle applicazioni, inclusa l'implementazione del gestore di layout per le presentazioni. Il livello principale WPF offre una modalità per usare in modo esteso [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] senza l'overhead di assembly aggiuntivo. La distinzione tra questi livelli è molto raramente importante per gli scenari di sviluppo di applicazioni più comuni e in generale è opportuno considerare le API [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nel suo complesso e non preoccuparsi della differenza tra il livello di Framework WPF e il livello di core WPF. Può essere necessario conoscere le distinzioni tra i livelli se in un progetto di applicazione si decide di sostituire quantità significative di funzionalità del livello di framework WPF, ad esempio se la soluzione complessiva dispone già di implementazioni personalizzate per la composizione e il layout dell'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
<a name="subclassing_elements"></a>   
## <a name="choosing-which-element-to-derive-from"></a>Scelta dell'elemento da cui derivare  
 Il modo ottimale per creare una classe personalizzata che estende [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consiste nel derivare da una delle classi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante cui si ottiene la massima funzionalità desiderata tramite la gerarchia di classi esistente. Questa sezione elenca le funzionalità fornite da tre delle più importanti classi di elementi che consentono di decidere da quale classe ereditare.  
  
 Se si implementa un controllo, che è in realtà uno dei motivi più comuni per derivare da una classe di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è probabile che si desideri derivare da una classe che sia un controllo pratico, una classe di base della famiglia di controlli o almeno dalla classe di base <xref:System.Windows.Controls.Control>. Per istruzioni ed esempi pratici, vedere [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md).  
  
 Se non si crea un controllo ed è necessario derivare da una classe più elevata nella gerarchia, nelle sezioni seguenti vengono fornite informazioni sulle caratteristiche definite in ogni classe degli elementi di base.  
  
 Se si crea una classe che deriva da <xref:System.Windows.DependencyObject>, si ereditano le funzionalità seguenti:  
  
- supporto di <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A> e supporto del sistema di proprietà generale.  
  
- Possibilità di utilizzare le proprietà di dipendenza e le proprietà associate implementate come proprietà di dipendenza.  
  
 Se si crea una classe che deriva da <xref:System.Windows.UIElement>, si ereditano le funzionalità seguenti oltre a quelle fornite da <xref:System.Windows.DependencyObject>:  
  
- Supporto di base per i valori delle proprietà animate. Per altre informazioni, vedere [Panoramica dell'animazione](../graphics-multimedia/animation-overview.md).  
  
- Supporto di eventi di input di base e supporto dei comandi. Per altre informazioni, vedere [Cenni preliminari sull’input](input-overview.md) e [Cenni preliminari sull'esecuzione di comandi](commanding-overview.md).  
  
- Metodi virtuali di cui è possibile eseguire l'override per fornire informazioni a un sistema di layout.  
  
 Se si crea una classe che deriva da <xref:System.Windows.FrameworkElement>, si ereditano le funzionalità seguenti oltre a quelle fornite da <xref:System.Windows.UIElement>:  
  
- Supporto per l'uso di stili e storyboard. Per ulteriori informazioni, vedere [Cenni preliminari sugli storyboard](../graphics-multimedia/storyboards-overview.md)e <xref:System.Windows.Style>.  
  
- Supporto del data binding. Per altre informazioni, vedere la [panoramica del data binding](../data/data-binding-overview.md).  
  
- Supporto per i riferimenti di risorse dinamiche. Per altre informazioni, vedere [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Supporto dell'ereditarietà dei valori di proprietà e altri flag nei metadati che agevolano la segnalazione di condizioni relative alle proprietà ai servizi del framework, ad esempio data binding, stili o implementazione del layout del framework. Per altre informazioni, vedere [Metadati delle proprietà del framework](framework-property-metadata.md).  
  
- Concetto di albero logico. Per altre informazioni, vedere [Strutture ad albero in WPF](trees-in-wpf.md).  
  
- Supporto per l'implementazione pratica a livello di Framework WPF del sistema di layout, incluso un override <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> in grado di rilevare le modifiche apportate alle proprietà che influenzano il layout.  
  
 Se si crea una classe che deriva da <xref:System.Windows.ContentElement>, si ereditano le funzionalità seguenti oltre a quelle fornite da <xref:System.Windows.DependencyObject>:  
  
- Supporto per le animazioni. Per altre informazioni, vedere [Panoramica dell'animazione](../graphics-multimedia/animation-overview.md).  
  
- Supporto di eventi di input di base e supporto dei comandi. Per altre informazioni, vedere [Cenni preliminari sull’input](input-overview.md) e [Cenni preliminari sull'esecuzione di comandi](commanding-overview.md).  
  
 Se si crea una classe che deriva da <xref:System.Windows.FrameworkContentElement>, si ottengono le funzionalità seguenti, oltre a quelle fornite da <xref:System.Windows.ContentElement>:  
  
- Supporto per l'uso di stili e storyboard. Per ulteriori informazioni, vedere <xref:System.Windows.Style> e [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md).  
  
- Supporto del data binding. Per altre informazioni, vedere la [panoramica del data binding](../data/data-binding-overview.md).  
  
- Supporto per i riferimenti di risorse dinamiche. Per altre informazioni, vedere [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Supporto dell'ereditarietà dei valori di proprietà e altri flag nei metadati che agevolano la segnalazione di condizioni relative alle proprietà ai servizi del framework, ad esempio data binding, stili o implementazione del layout del framework. Per altre informazioni, vedere [Metadati delle proprietà del framework](framework-property-metadata.md).  
  
- L'accesso alle modifiche apportate al sistema di layout, ad esempio <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>, non viene ereditato. Le implementazioni del sistema di layout sono disponibili solo in <xref:System.Windows.FrameworkElement>. Tuttavia, è possibile ereditare un override <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> in grado di rilevare le modifiche apportate alle proprietà che influenzano il layout e segnalarle a tutti gli host di contenuto.  
  
 I modelli di contenuto sono documentati per una varietà di classi. Il modello di contenuto per una classe è un fattore possibile da considerare per trovare una classe adatta da cui derivare. Per altre informazioni, vedere [Modello di contenuto WPF](../controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>   
## <a name="other-base-classes"></a>Altre classi di base  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject> fornisce il supporto per il modello di threading [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e consente a tutti gli oggetti creati per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni di essere associati a una <xref:System.Windows.Threading.Dispatcher>. Anche se non si esegue la derivazione da <xref:System.Windows.UIElement>, <xref:System.Windows.DependencyObject>o <xref:System.Windows.Media.Visual>, è necessario considerare la derivazione da <xref:System.Windows.Threading.DispatcherObject> per ottenere il supporto del modello di Threading. Per altre informazioni, vedere [Modello di threading](threading-model.md).  
  
### <a name="visual"></a>Visual  
 <xref:System.Windows.Media.Visual> implementa il concetto di oggetto 2D che in genere richiede la presentazione visiva in un'area approssimativamente rettangolare. Il rendering effettivo di un <xref:System.Windows.Media.Visual> si verifica in altre classi (non è indipendente), ma la classe <xref:System.Windows.Media.Visual> fornisce un tipo noto che viene usato dai processi di rendering a vari livelli. <xref:System.Windows.Media.Visual> implementa l'hit testing, ma non espone eventi che segnalano positivi di hit testing (si trovano in <xref:System.Windows.UIElement>). Per altre informazioni, vedere [Programmazione a livello visivo](../graphics-multimedia/visual-layer-programming.md).  
  
### <a name="freezable"></a>Freezable  
 <xref:System.Windows.Freezable> simula l'immutabilità in un oggetto modificabile fornendo i mezzi per generare copie dell'oggetto quando un oggetto non modificabile è obbligatorio o desiderato per motivi di prestazioni. Il tipo di <xref:System.Windows.Freezable> fornisce una base comune per determinati elementi grafici, ad esempio le geometrie e i pennelli, nonché le animazioni. In particolare, un <xref:System.Windows.Freezable> non è un <xref:System.Windows.Media.Visual>; può ospitare proprietà che diventano sottoproprietà quando l'<xref:System.Windows.Freezable> viene applicato per riempire un valore di proprietà di un altro oggetto e tali proprietà possono influire sul rendering. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable> è una classe <xref:System.Windows.Freezable> derivata che aggiunge in modo specifico il livello di controllo dell'animazione e alcuni membri dell'utilità in modo che le proprietà attualmente animate possano essere distinte dalle proprietà non animate.  
  
### <a name="control"></a>Control  
 <xref:System.Windows.Controls.Control> è la classe base prevista per il tipo di oggetto che viene definito da un controllo o un componente, a seconda della tecnologia. In genere, le classi di controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono classi che rappresentano direttamente un controllo dell'interfaccia utente o partecipano alla composizione di tale controllo. La funzionalità principale che <xref:System.Windows.Controls.Control> Abilita è il modello di controllo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Control>
- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md)
- [Architettura WPF](wpf-architecture.md)

---
title: Cenni preliminari sugli elementi di base
ms.date: 03/30/2017
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: bcfcb87d0ddf5181a47d459e821bacd9b9f6b61c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="base-elements-overview"></a>Cenni preliminari sugli elementi di base
Una percentuale elevata di classi in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] deriva da quattro classi alle quali viene comunemente fatto riferimento nella documentazione [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] come classi degli elementi di base. Queste classi sono <xref:System.Windows.UIElement>, <xref:System.Windows.FrameworkElement>, <xref:System.Windows.ContentElement>, e <xref:System.Windows.FrameworkContentElement>. Il <xref:System.Windows.DependencyObject> classe è correlata, perché è una classe di base comune di entrambi <xref:System.Windows.UIElement> e <xref:System.Windows.ContentElement>  
 
  
<a name="base_apis"></a>   
## <a name="base-element-apis-in-wpf-classes"></a>API degli elementi di base nelle classi WPF  
 Entrambi <xref:System.Windows.UIElement> e <xref:System.Windows.ContentElement> derivati da <xref:System.Windows.DependencyObject>, attraverso percorsi diversi. La divisione a questo livello viene descritto un <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement> vengono utilizzati in un'interfaccia utente e allo scopo che vengono usati in un'applicazione. <xref:System.Windows.UIElement> dispone inoltre <xref:System.Windows.Media.Visual> nella propria gerarchia di classi, che rappresenta una classe che espone il supporto grafica di basso livello sottostante il [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. <xref:System.Windows.Media.Visual> fornisce un framework per il rendering tramite la definizione di aree rettangolari indipendenti sullo schermo. In pratica, <xref:System.Windows.UIElement> è per gli elementi che supportano un modello a oggetti più grande, sono destinati a eseguire il rendering e il layout in aree che può essere descritta come aree rettangolari dello schermo e in cui il modello di contenuto è più aperto, per consentire diversi combinazioni di elementi. <xref:System.Windows.ContentElement> non deriva da <xref:System.Windows.Media.Visual>; il modello è che una <xref:System.Windows.ContentElement> potrebbe essere utilizzati da un titolo, ad esempio un visualizzatore che quindi interpretare gli elementi e produrre l'intero o un reader <xref:System.Windows.Media.Visual> per [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] utilizzare. Determinati <xref:System.Windows.UIElement> classi sono destinate a essere host del contenuto: forniscono l'hosting e il rendering per uno o più <xref:System.Windows.ContentElement> classi (<xref:System.Windows.Controls.DocumentViewer> è riportato un esempio di tale classe). <xref:System.Windows.ContentElement> viene utilizzata come classe base per gli elementi con modelli a oggetti più piccoli e che ulteriori degli indirizzi di testo, informazioni o documento di contenuto che potrebbe essere ospitati all'interno di un <xref:System.Windows.UIElement>.  
  
### <a name="framework-level-and-core-level"></a>Livello di framework e livello principale  
 <xref:System.Windows.UIElement> funge da classe basa per <xref:System.Windows.FrameworkElement>, e <xref:System.Windows.ContentElement> funge da classe basa per <xref:System.Windows.FrameworkContentElement>. Il motivo per questo livello successivo di classi è il supporto di un livello principale WPF separato da un livello di framework WPF, una divisione che esiste anche nella modalità in cui vengono suddivise le [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] tra gli assembly PresentationCore e PresentationFramework. Il livello di framework WPF offre una soluzione più completa per le necessità di base delle applicazioni, inclusa l'implementazione del gestore di layout per le presentazioni. Il livello principale WPF offre una modalità per usare in modo esteso [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] senza l'overhead di assembly aggiuntivo. La distinzione tra questi livelli raramente è importante nella maggior parte degli scenari di sviluppo delle applicazioni tipici e, in genere, occorre considerare le [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] come un tutto, senza preoccuparsi della differenza tra livello di framework WPF e livello principale WPF. Può essere necessario conoscere le distinzioni tra i livelli se in un progetto di applicazione si decide di sostituire quantità significative di funzionalità del livello di framework WPF, ad esempio se la soluzione complessiva dispone già di implementazioni personalizzate per la composizione e il layout dell'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
<a name="subclassing_elements"></a>   
## <a name="choosing-which-element-to-derive-from"></a>Scelta dell'elemento da cui derivare  
 Il modo ottimale per creare una classe personalizzata che estende [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consiste nel derivare da una delle classi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante cui si ottiene la massima funzionalità desiderata tramite la gerarchia di classi esistente. Questa sezione elenca le funzionalità fornite da tre delle più importanti classi di elementi che consentono di decidere da quale classe ereditare.  
  
 Se si implementa un controllo, uno dei motivi più comuni per la derivazione da una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (classe), è consigliabile derivare da una classe che è un controllo pratico, una classe di base controllo famiglia, o almeno dalla <xref:System.Windows.Controls.Control> classe di base. Per istruzioni ed esempi pratici, vedere [Cenni preliminari sulla modifica di controlli](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Se non si crea un controllo ed è necessario derivare da una classe più elevata nella gerarchia, nelle sezioni seguenti vengono fornite informazioni sulle caratteristiche definite in ogni classe degli elementi di base.  
  
 Se si crea una classe che deriva da <xref:System.Windows.DependencyObject>, si ereditano le funzionalità seguenti:  
  
-   <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A> supporto e il supporto di sistema di proprietà generale.  
  
-   Possibilità di utilizzare le proprietà di dipendenza e le proprietà associate implementate come proprietà di dipendenza.  
  
 Se si crea una classe che deriva da <xref:System.Windows.UIElement>, si ereditano le funzionalità seguenti, oltre a quelle fornite da <xref:System.Windows.DependencyObject>:  
  
-   Supporto di base per i valori delle proprietà animate. Per altre informazioni, vedere [Panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Supporto di eventi di input di base e supporto dei comandi. Per altre informazioni, vedere [Cenni preliminari sull’input](../../../../docs/framework/wpf/advanced/input-overview.md) e [Cenni preliminari sull'esecuzione di comandi](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
-   Metodi virtuali di cui è possibile eseguire l'override per fornire informazioni a un sistema di layout.  
  
 Se si crea una classe che deriva da <xref:System.Windows.FrameworkElement>, si ereditano le funzionalità seguenti, oltre a quelle fornite da <xref:System.Windows.UIElement>:  
  
-   Supporto per l'uso di stili e storyboard. Per ulteriori informazioni, vedere <xref:System.Windows.Style> e [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
-   Supporto del data binding. Per altre informazioni, vedere la [panoramica del data binding](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Supporto per i riferimenti di risorse dinamiche. Per altre informazioni, vedere [Risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Supporto dell'ereditarietà dei valori di proprietà e altri flag nei metadati che agevolano la segnalazione di condizioni relative alle proprietà ai servizi del framework, ad esempio data binding, stili o implementazione del layout del framework. Per altre informazioni, vedere [Metadati delle proprietà del framework](../../../../docs/framework/wpf/advanced/framework-property-metadata.md).  
  
-   Concetto di albero logico. Per altre informazioni, vedere [Strutture ad albero in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
-   Supporto per l'implementazione pratica di livello di framework WPF di sistema di layout, inclusi un <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> sostituzione in grado di rilevare le modifiche alle proprietà che hanno effetto sul layout.  
  
 Se si crea una classe che deriva da <xref:System.Windows.ContentElement>, si ereditano le funzionalità seguenti, oltre a quelle fornite da <xref:System.Windows.DependencyObject>:  
  
-   Supporto per le animazioni. Per altre informazioni, vedere [Panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Supporto di eventi di input di base e supporto dei comandi. Per altre informazioni, vedere [Cenni preliminari sull’input](../../../../docs/framework/wpf/advanced/input-overview.md) e [Cenni preliminari sull'esecuzione di comandi](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
 Se si crea una classe che deriva da <xref:System.Windows.FrameworkContentElement>, si ottengono le funzionalità seguenti, oltre a quelle fornite da <xref:System.Windows.ContentElement>:  
  
-   Supporto per l'uso di stili e storyboard. Per ulteriori informazioni, vedere <xref:System.Windows.Style> e [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Supporto del data binding. Per altre informazioni, vedere la [panoramica del data binding](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Supporto per i riferimenti di risorse dinamiche. Per altre informazioni, vedere [Risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Supporto dell'ereditarietà dei valori di proprietà e altri flag nei metadati che agevolano la segnalazione di condizioni relative alle proprietà ai servizi del framework, ad esempio data binding, stili o implementazione del layout del framework. Per altre informazioni, vedere [Metadati delle proprietà del framework](../../../../docs/framework/wpf/advanced/framework-property-metadata.md).  
  
-   Non si eredita l'accesso alle modifiche di sistema di layout (ad esempio <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>). Le implementazioni del sistema di layout sono disponibili solo in <xref:System.Windows.FrameworkElement>. Tuttavia, si eredita un <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> override per rilevare le modifiche alle proprietà che hanno effetto sul layout e segnalarle a qualsiasi host del contenuto.  
  
 I modelli di contenuto sono documentati per una varietà di classi. Il modello di contenuto per una classe è un fattore possibile da considerare per trovare una classe adatta da cui derivare. Per altre informazioni, vedere [Modello di contenuto WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>   
## <a name="other-base-classes"></a>Altre classi di base  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject> fornisce il supporto per la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modello di threading e Abilita tutti gli oggetti creati per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le applicazioni da associare a un <xref:System.Windows.Threading.Dispatcher>. Anche se non si deriva da <xref:System.Windows.UIElement>, <xref:System.Windows.DependencyObject>, o <xref:System.Windows.Media.Visual>, è necessario considerare la derivazione da <xref:System.Windows.Threading.DispatcherObject> per ottenere il supporto del modello di threading. Per altre informazioni, vedere [Modello di threading](../../../../docs/framework/wpf/advanced/threading-model.md).  
  
### <a name="visual"></a>Visual  
 <xref:System.Windows.Media.Visual> implementa il concetto di un oggetto 2D che in genere richiede la presentazione visiva in un'area approssimativamente rettangolare. Il rendering effettivo di un <xref:System.Windows.Media.Visual> avviene in altre classi (non è indipendente), ma la <xref:System.Windows.Media.Visual> classe fornisce un tipo conosciuto utilizzato dai processi di rendering a vari livelli. <xref:System.Windows.Media.Visual> implementa l'hit test, ma non espone gli eventi che indicano positivi ed eseguire hit testing (si tratta <xref:System.Windows.UIElement>). Per altre informazioni, vedere [Programmazione a livello visivo](../../../../docs/framework/wpf/graphics-multimedia/visual-layer-programming.md).  
  
### <a name="freezable"></a>Freezable  
 <xref:System.Windows.Freezable> Simula immutabilità in un oggetto modificabile, fornendo i mezzi per la creazione di copie dell'oggetto quando un oggetto non modificabile è necessaria o desiderato per motivi di prestazioni. Il <xref:System.Windows.Freezable> tipo fornisce una base comune per alcuni elementi grafici, quali le geometrie pennelli, nonché le animazioni. In particolare, un <xref:System.Windows.Freezable> non è un <xref:System.Windows.Media.Visual>; può contenere proprietà che diventano sottoproprietà quando la <xref:System.Windows.Freezable> viene applicato per riempire un valore della proprietà di un altro oggetto, e tali sottoproprietà possono influire sul rendering. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable> è un <xref:System.Windows.Freezable> classe derivata che specificamente aggiunge il livello di controllo di animazione e alcuni membri dell'utilità in modo che sia possibile distinguere proprietà attualmente animate da animate.  
  
### <a name="control"></a>Control  
 <xref:System.Windows.Controls.Control> è la classe base desiderata per il tipo di oggetto noto come un controllo o un componente, a seconda della tecnologia. In genere, le classi di controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono classi che rappresentano direttamente un controllo dell'interfaccia utente o partecipano alla composizione di tale controllo. La funzionalità principale che <xref:System.Windows.Controls.Control> attiva è il modello di controllo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Control>  
 [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Cenni preliminari sulla modifica di controlli](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
 [Architettura WPF](../../../../docs/framework/wpf/advanced/wpf-architecture.md)

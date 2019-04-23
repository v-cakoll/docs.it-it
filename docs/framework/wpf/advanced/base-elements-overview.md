---
title: Cenni preliminari sugli elementi di base
ms.date: 03/30/2017
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: 0cd69a4d2d6087c1ebf93bb5931511f32a4c9c5f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110058"
---
# <a name="base-elements-overview"></a>Cenni preliminari sugli elementi di base
Una percentuale elevata di classi in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] deriva da quattro classi alle quali viene comunemente fatto riferimento nella documentazione [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] come classi degli elementi di base. Queste classi sono <xref:System.Windows.UIElement>, <xref:System.Windows.FrameworkElement>, <xref:System.Windows.ContentElement>, e <xref:System.Windows.FrameworkContentElement>. Il <xref:System.Windows.DependencyObject> classe è correlata, perché è una classe di base comune di entrambi <xref:System.Windows.UIElement> e <xref:System.Windows.ContentElement>  

<a name="base_apis"></a>   
## <a name="base-element-apis-in-wpf-classes"></a>API degli elementi di base nelle classi WPF  
 Entrambe <xref:System.Windows.UIElement> e <xref:System.Windows.ContentElement> derivano dalla <xref:System.Windows.DependencyObject>, attraverso percorsi diversi. La divisione a questo livello gestisce come una <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement> vengono usati in un'interfaccia utente e allo scopo di tali oggetti assolvono in un'applicazione. <xref:System.Windows.UIElement> dispone inoltre <xref:System.Windows.Media.Visual> nella propria gerarchia di classe, ovvero una classe che espone il supporto grafica di basso livello sottostante il [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. <xref:System.Windows.Media.Visual> fornisce un framework per il rendering con la definizione di aree rettangolari indipendenti sullo schermo. In pratica, <xref:System.Windows.UIElement> sia per gli elementi che supporteranno un modello a oggetti più grande, sono previsti per il rendering e layout in aree che è possibile descrivere come aree dello schermo rettangolari e in cui il modello di contenuto è più aperto, per consentire diversi combinazioni di elementi. <xref:System.Windows.ContentElement> non deriva da <xref:System.Windows.Media.Visual>; il modello è che un <xref:System.Windows.ContentElement> verrebbe utilizzata da altre operazioni, ad esempio un visualizzatore che sarebbe quindi interpretare gli elementi e produrre l'intero o un reader <xref:System.Windows.Media.Visual> per [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] utilizzare. Determinati <xref:System.Windows.UIElement> classi sono destinate a essere host di contenuto: forniscono l'hosting e rendering per una o più <xref:System.Windows.ContentElement> classi (<xref:System.Windows.Controls.DocumentViewer> è riportato un esempio di tale classe). <xref:System.Windows.ContentElement> viene usata come classe di base per gli elementi con modelli a oggetti più piccoli e più indirizzati il testo, informazioni o documento di contenuto che potrebbe essere ospitati all'interno di un <xref:System.Windows.UIElement>.  
  
### <a name="framework-level-and-core-level"></a>Livello di framework e livello principale  
 <xref:System.Windows.UIElement> funge da classe base per <xref:System.Windows.FrameworkElement>, e <xref:System.Windows.ContentElement> funge da classe base per <xref:System.Windows.FrameworkContentElement>. Il motivo per questo livello successivo di classi è il supporto di un livello principale WPF separato da un livello di framework WPF, una divisione che esiste anche nella modalità in cui vengono suddivise le [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] tra gli assembly PresentationCore e PresentationFramework. Il livello di framework WPF offre una soluzione più completa per le necessità di base delle applicazioni, inclusa l'implementazione del gestore di layout per le presentazioni. Il livello principale WPF offre una modalità per usare in modo esteso [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] senza l'overhead di assembly aggiuntivo. La distinzione tra questi livelli raramente è importante nella maggior parte degli scenari di sviluppo delle applicazioni tipici e, in genere, occorre considerare le [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] come un tutto, senza preoccuparsi della differenza tra livello di framework WPF e livello principale WPF. Può essere necessario conoscere le distinzioni tra i livelli se in un progetto di applicazione si decide di sostituire quantità significative di funzionalità del livello di framework WPF, ad esempio se la soluzione complessiva dispone già di implementazioni personalizzate per la composizione e il layout dell'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
<a name="subclassing_elements"></a>   
## <a name="choosing-which-element-to-derive-from"></a>Scelta dell'elemento da cui derivare  
 Il modo ottimale per creare una classe personalizzata che estende [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consiste nel derivare da una delle classi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante cui si ottiene la massima funzionalità desiderata tramite la gerarchia di classi esistente. Questa sezione elenca le funzionalità fornite da tre delle più importanti classi di elementi che consentono di decidere da quale classe ereditare.  
  
 Se si implementa un controllo, ovvero uno dei motivi più comuni per la derivazione da una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (classe), è possibile derivare da una classe che rappresenta un controllo pratico, una classe di base della famiglia controlli o almeno dal <xref:System.Windows.Controls.Control> classe di base. Per istruzioni ed esempi pratici, vedere [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md).  
  
 Se non si crea un controllo ed è necessario derivare da una classe più elevata nella gerarchia, nelle sezioni seguenti vengono fornite informazioni sulle caratteristiche definite in ogni classe degli elementi di base.  
  
 Se si crea una classe che deriva da <xref:System.Windows.DependencyObject>, si ereditano le funzionalità seguenti:  
  
-   <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A> supporto e il supporto di sistema di proprietà generale.  
  
-   Possibilità di utilizzare le proprietà di dipendenza e le proprietà associate implementate come proprietà di dipendenza.  
  
 Se si crea una classe che deriva da <xref:System.Windows.UIElement>, si ereditano le funzionalità seguenti oltre a quelle fornite da <xref:System.Windows.DependencyObject>:  
  
-   Supporto di base per i valori delle proprietà animate. Per altre informazioni, vedere [Panoramica dell'animazione](../graphics-multimedia/animation-overview.md).  
  
-   Supporto di eventi di input di base e supporto dei comandi. Per altre informazioni, vedere [Cenni preliminari sull’input](input-overview.md) e [Cenni preliminari sull'esecuzione di comandi](commanding-overview.md).  
  
-   Metodi virtuali di cui è possibile eseguire l'override per fornire informazioni a un sistema di layout.  
  
 Se si crea una classe che deriva da <xref:System.Windows.FrameworkElement>, si ereditano le funzionalità seguenti oltre a quelle fornite da <xref:System.Windows.UIElement>:  
  
-   Supporto per l'uso di stili e storyboard. Per altre informazioni, vedere <xref:System.Windows.Style> e [Cenni preliminari sugli storyboard](../graphics-multimedia/storyboards-overview.md).  
  
-   Supporto del data binding. Per altre informazioni, vedere la [panoramica del data binding](../data/data-binding-overview.md).  
  
-   Supporto per i riferimenti di risorse dinamiche. Per altre informazioni, vedere [Risorse XAML](xaml-resources.md).  
  
-   Supporto dell'ereditarietà dei valori di proprietà e altri flag nei metadati che agevolano la segnalazione di condizioni relative alle proprietà ai servizi del framework, ad esempio data binding, stili o implementazione del layout del framework. Per altre informazioni, vedere [Metadati delle proprietà del framework](framework-property-metadata.md).  
  
-   Concetto di albero logico. Per altre informazioni, vedere [Strutture ad albero in WPF](trees-in-wpf.md).  
  
-   Supporto per l'implementazione pratica a livello di framework WPF del sistema di layout, inclusi un <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> override che consentono di rilevare le modifiche alle proprietà che hanno effetto sul layout.  
  
 Se si crea una classe che deriva da <xref:System.Windows.ContentElement>, si ereditano le funzionalità seguenti oltre a quelle fornite da <xref:System.Windows.DependencyObject>:  
  
-   Supporto per le animazioni. Per altre informazioni, vedere [Panoramica dell'animazione](../graphics-multimedia/animation-overview.md).  
  
-   Supporto di eventi di input di base e supporto dei comandi. Per altre informazioni, vedere [Cenni preliminari sull’input](input-overview.md) e [Cenni preliminari sull'esecuzione di comandi](commanding-overview.md).  
  
 Se si crea una classe che deriva da <xref:System.Windows.FrameworkContentElement>, si ottengono le funzionalità seguenti oltre a quelle fornite da <xref:System.Windows.ContentElement>:  
  
-   Supporto per l'uso di stili e storyboard. Per altre informazioni, vedere <xref:System.Windows.Style> e [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md).  
  
-   Supporto del data binding. Per altre informazioni, vedere la [panoramica del data binding](../data/data-binding-overview.md).  
  
-   Supporto per i riferimenti di risorse dinamiche. Per altre informazioni, vedere [Risorse XAML](xaml-resources.md).  
  
-   Supporto dell'ereditarietà dei valori di proprietà e altri flag nei metadati che agevolano la segnalazione di condizioni relative alle proprietà ai servizi del framework, ad esempio data binding, stili o implementazione del layout del framework. Per altre informazioni, vedere [Metadati delle proprietà del framework](framework-property-metadata.md).  
  
-   Non si eredita l'accesso alle modifiche del sistema di layout (ad esempio <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>). Le implementazioni del sistema di layout sono disponibili solo in <xref:System.Windows.FrameworkElement>. Tuttavia, ereditano un' <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> override per rilevare le modifiche alle proprietà che hanno effetto sul layout e segnalarle a qualsiasi host del contenuto.  
  
 I modelli di contenuto sono documentati per una varietà di classi. Il modello di contenuto per una classe è un fattore possibile da considerare per trovare una classe adatta da cui derivare. Per altre informazioni, vedere [Modello di contenuto WPF](../controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>   
## <a name="other-base-classes"></a>Altre classi di base  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject> fornisce il supporto per la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modello di threading e Abilita tutti gli oggetti creati per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] alle applicazioni di essere associato un <xref:System.Windows.Threading.Dispatcher>. Anche se non si deriva da <xref:System.Windows.UIElement>, <xref:System.Windows.DependencyObject>, o <xref:System.Windows.Media.Visual>, è necessario considerare che deriva da <xref:System.Windows.Threading.DispatcherObject> per ottenere il supporto del modello di threading. Per altre informazioni, vedere [Modello di threading](threading-model.md).  
  
### <a name="visual"></a>Visual  
 <xref:System.Windows.Media.Visual> implementa il concetto di un oggetto 2D che generalmente richiede la presentazione visiva in un'area approssimativamente rettangolare. Il rendering effettivo di una <xref:System.Windows.Media.Visual> avviene in altre classi (non indipendente), ma il <xref:System.Windows.Media.Visual> classe fornisce un tipo noto usato dai processi di rendering a vari livelli. <xref:System.Windows.Media.Visual> implementa l'hit testing, ma non espone eventi che segnalano valori positivi di hit testing (questi siano <xref:System.Windows.UIElement>). Per altre informazioni, vedere [Programmazione a livello visivo](../graphics-multimedia/visual-layer-programming.md).  
  
### <a name="freezable"></a>Freezable  
 <xref:System.Windows.Freezable> Simula la non modificabilità in un oggetto modificabile fornendo i mezzi per generare copie dell'oggetto quando un oggetto non modificabile è necessario o utile per motivi di prestazioni. Il <xref:System.Windows.Freezable> tipo fornisce una base comune per alcuni elementi grafici, ad esempio geometrie e pennelli, nonché le animazioni. In particolare, un <xref:System.Windows.Freezable> non è un <xref:System.Windows.Media.Visual>; può contenere proprietà che diventano sottoproprietà quando la <xref:System.Windows.Freezable> viene applicato per riempire un valore della proprietà di un altro oggetto, e tali sottoproprietà possono influire sul rendering. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable> è un <xref:System.Windows.Freezable> classe derivata che specificamente aggiunge il livello di controllo animazione e alcuni membri dell'utilità in modo che sia possono distinguere le proprietà attualmente animate da animate.  
  
### <a name="control"></a>Control  
 <xref:System.Windows.Controls.Control> è la classe base desiderata per il tipo di oggetto noto come controllo o componente, a seconda della tecnologia. In genere, le classi di controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono classi che rappresentano direttamente un controllo dell'interfaccia utente o partecipano alla composizione di tale controllo. La funzionalità principale che <xref:System.Windows.Controls.Control> consente sia sui modelli di controllo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Control>
- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md)
- [Architettura WPF](wpf-architecture.md)

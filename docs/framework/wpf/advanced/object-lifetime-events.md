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
ms.openlocfilehash: 8ecc3f716061dfd08ac95652d1a9d8e06e26d949
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175792"
---
# <a name="object-lifetime-events"></a>Eventi di durata degli oggetti
In questo argomento vengono descritti gli eventi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] specifici che denotano le fasi della durata di un oggetto in termini di creazione, uso e distruzione.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 In questo argomento si presuppongono la conoscenza delle proprietà di dipendenza dal punto di vista di un consumer di proprietà di dipendenza esistenti nelle classi [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], nonché la lettura dell'argomento [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md). Per seguire gli esempi illustrati in questo argomento, è anche necessario conoscere [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] (vedere [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)) e saper scrivere applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="intro"></a>   
## <a name="object-lifetime-events"></a>Eventi di durata degli oggetti  
 Tutti gli oggetti nel codice gestito di Microsoft .NET Framework passano attraverso un insieme simile di fasi del ciclo di vita, creazione, uso e distruzione. Per molti oggetti la fase di finalizzazione della vita si verifica nell'ambito della fase di distruzione. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gli oggetti, più specificamente gli oggetti visivi che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] identifica come elementi, hanno anche un insieme comune di fasi di vita dell'oggetto. I modelli di programmazione e applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] espongono queste fasi come una serie di eventi. Esistono quattro tipi principali di oggetti in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in relazione agli eventi di durata: gli elementi in generale, gli elementi finestra, gli host di navigazione e gli oggetti applicazione. Le finestre e gli host di navigazione fanno parte anche del più ampio raggruppamento di oggetti visivi (elementi). In questo argomento vengono descritti gli eventi di durata che sono comuni a tutti gli elementi; vengono quindi introdotti quelli più specifici che si applicano alle definizioni dell'applicazione, alle finestre o agli host di navigazione.  
  
<a name="common_events"></a>   
## <a name="common-lifetime-events-for-elements"></a>Eventi di durata comuni degli elementi  
 Qualsiasi elemento a livello di framework WPF (gli oggetti che derivano da uno <xref:System.Windows.FrameworkElement> oppure <xref:System.Windows.FrameworkContentElement>) hanno in comune tre eventi di durata: <xref:System.Windows.FrameworkElement.Initialized>, <xref:System.Windows.FrameworkElement.Loaded>, e <xref:System.Windows.FrameworkElement.Unloaded>.  
  
### <a name="initialized"></a>Inizializzato  
 <xref:System.Windows.FrameworkElement.Initialized> viene generato per primo e corrisponde approssimativamente all'inizializzazione dell'oggetto tramite la chiamata al costruttore. Poiché l'evento si verifica in seguito all'inizializzazione, tutte le proprietà dell'oggetto sono sicuramente impostate. Un'eccezione può verificarsi nei casi di utilizzo di espressioni quali risorse dinamiche o binding; queste saranno espressioni non valutate. Come conseguenza del requisito che tutte le proprietà sono impostate, la sequenza di <xref:System.Windows.FrameworkElement.Initialized> generata dagli elementi annidati definiti nel markup viene si verificano nell'ordine degli elementi più in basso nell'albero degli elementi in primo luogo, quindi gli elementi verso la radice padre. Questo ordine è determinato dal fatto che le relazioni padre-figlio e il contenimento sono proprietà e pertanto l'elemento padre non può segnalare l'inizializzazione finché tutti gli elementi figlio che riempiono la proprietà non sono stati completamente inizializzati.  
  
 Durante la scrittura dei gestori in risposta al <xref:System.Windows.FrameworkElement.Initialized> evento, è necessario considerare che non è garantito che tutti gli altri elementi nell'albero degli elementi (albero logico o struttura ad albero visuale) nell'area in cui è associato il gestore siano stati creati, in particolare elementi padre. Le variabili membro potrebbero essere Null oppure le origini dati potrebbero non essere ancora popolate dall'associazione sottostante (anche a livello di espressione).  
  
### <a name="loaded"></a>Caricato  
 <xref:System.Windows.FrameworkElement.Loaded> viene generato successivamente. Il <xref:System.Windows.FrameworkElement.Loaded> evento viene generato prima del rendering finale, ma dopo che il sistema di layout ha calcolato tutti i valori necessari per il rendering. <xref:System.Windows.FrameworkElement.Loaded> comporta che l'albero logico contenuta all'interno di un elemento è stata completata e si connette a un'origine della presentazione che fornisce HWND e la superficie di rendering. Il data binding standard (binding alle origini locali, ad esempio altre proprietà o le origini dati definite in modo diretto) verranno apportate nelle versioni precedenti a <xref:System.Windows.FrameworkElement.Loaded>. È possibile che il data binding asincrono (a origini esterne o dinamiche) si sia verificato, ma a causa della sua natura asincrona non è possibile averne la certezza.  
  
 Il meccanismo con cui il <xref:System.Windows.FrameworkElement.Loaded> viene generato l'evento è diverso da quello <xref:System.Windows.FrameworkElement.Initialized>. Il <xref:System.Windows.FrameworkElement.Initialized> evento viene generato per elemento, senza una coordinazione diretta da parte di un albero degli elementi completato. Al contrario, il <xref:System.Windows.FrameworkElement.Loaded> evento viene generato come operazione coordinata attraverso l'intero albero degli elementi (in particolare, l'albero logico). Quando tutti gli elementi nell'albero sono in uno stato in cui sono considerati caricato, il <xref:System.Windows.FrameworkElement.Loaded> evento viene generato prima di tutto per l'elemento radice. Il <xref:System.Windows.FrameworkElement.Loaded> evento viene quindi generato in successione per ogni elemento figlio.  
  
> [!NOTE]
>  Questo comportamento potrebbe sembrare a prima vista analogo al tunneling per un evento indirizzato. Tuttavia, le informazioni non vengono passate da evento a evento. Ogni elemento ha sempre la possibilità di gestire il <xref:System.Windows.FrameworkElement.Loaded> evento e contrassegnando i dati dell'evento come gestito ha effetto di là di quell'elemento.  
  
### <a name="unloaded"></a>Scaricato  
 <xref:System.Windows.FrameworkElement.Unloaded> viene generato per ultimo e avviato tramite l'origine della presentazione o l'elemento padre visivo da rimuovere. Quando <xref:System.Windows.FrameworkElement.Unloaded> viene generato e gestito, l'elemento padre dell'origine dell'evento (come determinato dalla <xref:System.Windows.FrameworkElement.Parent%2A> proprietà) o qualsiasi elemento verso l'alto in alberi logici o oggetto visivo specificato potrebbe già essere stata annullata, il che significa che il data binding, i riferimenti alle risorse , e gli stili non possono essere impostati sul rispettivo valore in fase di esecuzione normale o nell'ultimo noto.  
  
<a name="application_model_elements"></a>   
## <a name="lifetime-events-application-model-elements"></a>Elementi del modello di applicazione di eventi di durata  
 Sulla base di eventi di durata comuni per gli elementi sono elementi del modello di applicazione seguenti: <xref:System.Windows.Application>, <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, e <xref:System.Windows.Controls.Frame>. Questi estendono gli eventi di durata comuni con eventi aggiuntivi, pertinenti al relativo scopo specifico e vengono descritti in dettaglio nelle sezioni seguenti:  
  
-   <xref:System.Windows.Application>: [Panoramica di gestione di applicazioni](../app-development/application-management-overview.md).  
  
-   <xref:System.Windows.Window>: [Panoramica di Windows WPF](../app-development/wpf-windows-overview.md).  
  
-   <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, e <xref:System.Windows.Controls.Frame>: [Cenni preliminari sulla navigazione](../app-development/navigation-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Precedenza del valore della proprietà di dipendenza](dependency-property-value-precedence.md)
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)

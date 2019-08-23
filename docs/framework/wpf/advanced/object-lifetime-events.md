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
ms.openlocfilehash: dd2e116c4241a44786af3a56b931b0c3c0571814
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933494"
---
# <a name="object-lifetime-events"></a>Eventi di durata degli oggetti
In questo argomento vengono descritti gli eventi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] specifici che denotano le fasi della durata di un oggetto in termini di creazione, uso e distruzione.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 In questo argomento si presuppongono la conoscenza delle proprietà di dipendenza dal punto di vista di un consumer di proprietà di dipendenza esistenti nelle classi [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], nonché la lettura dell'argomento [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md). Per seguire gli esempi illustrati in questo argomento, è anche necessario conoscere [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] (vedere [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)) e saper scrivere applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="intro"></a>   
## <a name="object-lifetime-events"></a>Eventi di durata degli oggetti  
 Tutti gli oggetti nel codice gestito di Microsoft .NET Framework passano attraverso un insieme simile di fasi di vita, creazione, utilizzo e distruzione. Per molti oggetti la fase di finalizzazione della vita si verifica nell'ambito della fase di distruzione. Gli oggetti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] più specificamente gli oggetti visivi che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] identifica come elementi, hanno una serie comune di fasi di vita dell'oggetto. I modelli di programmazione e applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] espongono queste fasi come una serie di eventi. Esistono quattro tipi principali di oggetti in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in relazione agli eventi di durata: gli elementi in generale, gli elementi finestra, gli host di navigazione e gli oggetti applicazione. Le finestre e gli host di navigazione fanno parte anche del più ampio raggruppamento di oggetti visivi (elementi). In questo argomento vengono descritti gli eventi di durata che sono comuni a tutti gli elementi; vengono quindi introdotti quelli più specifici che si applicano alle definizioni dell'applicazione, alle finestre o agli host di navigazione.  
  
<a name="common_events"></a>   
## <a name="common-lifetime-events-for-elements"></a>Eventi di durata comuni degli elementi  
 Qualsiasi elemento a livello di Framework WPF (gli oggetti che derivano <xref:System.Windows.FrameworkContentElement>da <xref:System.Windows.FrameworkElement> o) presenta tre eventi di <xref:System.Windows.FrameworkElement.Initialized>durata <xref:System.Windows.FrameworkElement.Loaded>comuni: <xref:System.Windows.FrameworkElement.Unloaded>, e.  
  
### <a name="initialized"></a>Inizializzato  
 <xref:System.Windows.FrameworkElement.Initialized>viene generato per primo e corrisponde approssimativamente all'inizializzazione dell'oggetto da parte della chiamata al relativo costruttore. Poiché l'evento si verifica in seguito all'inizializzazione, tutte le proprietà dell'oggetto sono sicuramente impostate. Un'eccezione può verificarsi nei casi di utilizzo di espressioni quali risorse dinamiche o binding; queste saranno espressioni non valutate. Come conseguenza del requisito per il quale vengono impostate tutte le proprietà, la sequenza <xref:System.Windows.FrameworkElement.Initialized> di generazione da elementi annidati definiti nel markup sembra essere eseguita in ordine di elementi più profondi nell'albero degli elementi, quindi gli elementi padre verso la radice. Questo ordine è determinato dal fatto che le relazioni padre-figlio e il contenimento sono proprietà e pertanto l'elemento padre non può segnalare l'inizializzazione finché tutti gli elementi figlio che riempiono la proprietà non sono stati completamente inizializzati.  
  
 Quando si scrivono i <xref:System.Windows.FrameworkElement.Initialized> gestori in risposta all'evento, è necessario tenere presente che non esiste alcuna garanzia che tutti gli altri elementi nella struttura ad albero dell'elemento (albero logico o struttura ad albero visuale) in cui è collegato il gestore siano stati creati, in particolare elementi padre. Le variabili membro potrebbero essere Null oppure le origini dati potrebbero non essere ancora popolate dall'associazione sottostante (anche a livello di espressione).  
  
### <a name="loaded"></a>Caricato  
 <xref:System.Windows.FrameworkElement.Loaded>viene generato Next. L' <xref:System.Windows.FrameworkElement.Loaded> evento viene generato prima del rendering finale, ma dopo che il sistema di layout ha calcolato tutti i valori necessari per il rendering. <xref:System.Windows.FrameworkElement.Loaded>comporta che l'albero logico in cui è contenuto un elemento sia completato e si connette a un'origine della presentazione che fornisce l'HWND e la superficie di rendering. Le data binding standard (associazione a origini locali, ad esempio altre proprietà o origini dati definite direttamente), si sono verificate prima di <xref:System.Windows.FrameworkElement.Loaded>. È possibile che il data binding asincrono (a origini esterne o dinamiche) si sia verificato, ma a causa della sua natura asincrona non è possibile averne la certezza.  
  
 Il meccanismo in base al <xref:System.Windows.FrameworkElement.Loaded> quale viene generato l'evento è <xref:System.Windows.FrameworkElement.Initialized>diverso da. L' <xref:System.Windows.FrameworkElement.Initialized> evento viene generato in base all'elemento, senza un coordinamento diretto da parte di un albero degli elementi completato. Al contrario, l' <xref:System.Windows.FrameworkElement.Loaded> evento viene generato come sforzo coordinato nell'intero albero degli elementi (in particolare, l'albero logico). Quando tutti gli elementi dell'albero sono in uno stato in cui sono considerati caricati, l' <xref:System.Windows.FrameworkElement.Loaded> evento viene innanzitutto generato sull'elemento radice. L' <xref:System.Windows.FrameworkElement.Loaded> evento viene quindi generato successivamente in ogni elemento figlio.  
  
> [!NOTE]
> Questo comportamento potrebbe sembrare a prima vista analogo al tunneling per un evento indirizzato. Tuttavia, le informazioni non vengono passate da evento a evento. Ogni elemento ha sempre la possibilità di gestire <xref:System.Windows.FrameworkElement.Loaded> l'evento e contrassegnare i dati dell'evento come gestiti non ha alcun effetto oltre tale elemento.  
  
### <a name="unloaded"></a>Scaricato  
 <xref:System.Windows.FrameworkElement.Unloaded>viene generato per ultimo e viene avviato dall'origine della presentazione o dalla rimozione del padre visivo. Quando <xref:System.Windows.FrameworkElement.Unloaded> viene generato e gestito, l'elemento che rappresenta l'origine evento padre (come determinato dalla <xref:System.Windows.FrameworkElement.Parent%2A> proprietà) o qualsiasi elemento specificato verso l'alto negli alberi logici o visivi potrebbe essere già stato annullato, vale a dire che data binding e riferimenti alle risorse gli stili e non possono essere impostati sul valore di run-time normale o più recente.  
  
<a name="application_model_elements"></a>   
## <a name="lifetime-events-application-model-elements"></a>Elementi del modello di applicazione di eventi di durata  
 La compilazione sugli eventi di durata comuni per gli elementi sono gli elementi del modello <xref:System.Windows.Application>di <xref:System.Windows.Window>applicazione <xref:System.Windows.Controls.Page>seguenti <xref:System.Windows.Navigation.NavigationWindow>:, <xref:System.Windows.Controls.Frame>,, e. Questi estendono gli eventi di durata comuni con eventi aggiuntivi, pertinenti al relativo scopo specifico e vengono descritti in dettaglio nelle sezioni seguenti:  
  
- <xref:System.Windows.Application>: [Panoramica sulla gestione delle applicazioni](../app-development/application-management-overview.md).  
  
- <xref:System.Windows.Window>: [Cenni preliminari sulle finestre WPF](../app-development/wpf-windows-overview.md).  
  
- <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>e :<xref:System.Windows.Controls.Frame> [Cenni preliminari sulla navigazione](../app-development/navigation-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Precedenza del valore della proprietà di dipendenza](dependency-property-value-precedence.md)
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)

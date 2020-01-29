---
title: Gestisci eventi in Visual Basic
ms.date: 03/30/2017
helpviewer_keywords:
- Visual Basic [WPF], event handlers
- event handlers [WPF], Visual Basic
ms.assetid: ad4eb9aa-3afc-4a71-8cf6-add3fbea54a1
ms.openlocfilehash: 959ef66f41f6c5f06e18a202109fba058c522d1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735403"
---
# <a name="visual-basic-and-wpf-event-handling"></a>Visual Basic e la gestione degli eventi WPF
Per il linguaggio Microsoft Visual Basic .NET in particolare, è possibile usare la parola chiave `Handles` specifica del linguaggio per associare i gestori eventi alle istanze, anziché collegare i gestori eventi agli attributi o usare il metodo <xref:System.Windows.UIElement.AddHandler%2A>. Tuttavia, la tecnica `Handles` per collegare gestori alle istanze presenta alcuni limiti, in quanto la sintassi `Handles` non è in grado di supportare alcune delle funzioni degli eventi indirizzati specifiche del sistema di eventi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## <a name="using-handles-in-a-wpf-application"></a>Uso di "Handles" in un'applicazione WPF  
 I gestori eventi connessi a istanze ed eventi tramite `Handles` devono essere definiti tutti all'interno della dichiarazione di classe parziale dell'istanza. Ciò vale anche per i gestori eventi assegnati tramite valori di attributo negli elementi. È possibile specificare solo `Handles` per un elemento nella pagina che ha un valore di proprietà <xref:System.Windows.FrameworkContentElement.Name%2A> (o [direttiva x:Name](../../../desktop-wpf/xaml-services/xname-directive.md) dichiarata). Ciò è dovuto al fatto che il <xref:System.Windows.FrameworkContentElement.Name%2A> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] crea il riferimento all'istanza necessario per supportare il formato di riferimento dell' *istanza. evento* richiesto dalla sintassi `Handles`. L'unico elemento che può essere utilizzato per `Handles` senza un riferimento <xref:System.Windows.FrameworkContentElement.Name%2A> è l'istanza dell'elemento radice che definisce la classe parziale.  
  
 È possibile assegnare lo stesso gestore a più elementi separando i riferimenti *Istanza.Evento* dopo `Handles` con delle virgole.  
  
 È possibile usare `Handles` per assegnare più gestori allo stesso riferimento *Istanza.Evento*. Non attribuire alcuna importanza all'ordine in cui vengono forniti i gestori nel riferimento `Handles`. È necessario presupporre che gestori dello stesso evento possono essere richiamati in qualsiasi ordine.  
  
 Per rimuovere un gestore aggiunto con `Handles` nella dichiarazione, è possibile chiamare <xref:System.Windows.UIElement.RemoveHandler%2A>.  
  
 È possibile usare `Handles` per collegare i gestori per gli eventi indirizzati, purché i gestori vengano collegati a istanze che definiscono l'evento gestito nelle rispettive tabelle di membri. Per gli eventi indirizzati, i gestori collegati con `Handles` seguono le stesse regole di routing dei gestori collegati come [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributi o con la firma comune di <xref:System.Windows.UIElement.AddHandler%2A>. Ciò significa che se l'evento è già contrassegnato come gestito (la proprietà <xref:System.Windows.RoutedEventArgs.Handled%2A> nei dati dell'evento viene `True`), i gestori collegati con `Handles` non vengono richiamati in risposta a tale istanza di evento. L'evento potrebbe essere contrassegnato come gestito dai gestori dell'istanza in un altro elemento della route o dalla gestione delle classi nell'elemento corrente o negli elementi precedenti della route. Per gli eventi di input che supportano eventi accoppiati di tunneling e di bubbling, è possibile che la route di tunneling abbia contrassegnato la coppia di eventi come gestita. Per altre informazioni sugli eventi indirizzati, vedere [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
## <a name="limitations-of-handles-for-adding-handlers"></a>Limitazioni di "Handle" per l'aggiunta di gestori  
 `Handles` non può fare riferimento ai gestori per gli eventi associati. È necessario usare il metodo della funzione di accesso `add` per quello specifico evento associato oppure gli attributi dell'evento *nometipo.nomeevento* in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Per informazioni dettagliate, vedere [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
 Per gli eventi indirizzati, è possibile usare `Handles` unicamente per assegnare gestori per le istanze in cui quell'evento è presente nella tabella dei membri dell'istanza. Tuttavia, con gli eventi indirizzati in generale, un elemento padre può essere un listener per un evento degli elementi figlio anche se l'elemento padre non dispone di quell'evento nella relativa tabella dei membri. Nella sintassi dell'attributo, ciò può essere specificato tramite un formato di attributo *nometipo.nomemembro* che qualifica il tipo che definisce effettivamente l'evento che si vuole gestire. Ad esempio, un `Page` padre (senza `Click` evento definito) può restare in ascolto degli eventi click del pulsante assegnando un gestore attributi nel formato `Button.Click`. Tuttavia, `Handles` non supporta il formato *nometipo.nomemembro*, in quanto deve supportare un formato *Istanza.Evento* in conflitto. Per informazioni dettagliate, vedere [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
 `Handles` non è in grado di associare gestori richiamati per eventi che sono già contrassegnati come gestiti. Al contrario, è necessario usare il codice e chiamare l'overload `handledEventsToo` di <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>.  
  
> [!NOTE]
> Non usare la sintassi `Handles` nel codice Visual Basic quando si specifica un gestore eventi per lo stesso evento in XAML. In questo caso, il gestore eventi viene chiamato due volte.  
  
## <a name="how-wpf-implements-handles-functionality"></a>Come WPF implementa la funzionalità "Handles"  
 Quando viene compilata una pagina di [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], il file intermedio dichiara `Friend` `WithEvents` riferimenti a ogni elemento della pagina che dispone di una <xref:System.Windows.FrameworkContentElement.Name%2A> set di proprietà (o [direttiva x:Name](../../../desktop-wpf/xaml-services/xname-directive.md) dichiarata). Ogni istanza denominata è potenzialmente un elemento che può essere assegnato a un gestore tramite `Handles`.  
  
> [!NOTE]
> In Visual Studio, IntelliSense consente di visualizzare il completamento per cui sono disponibili elementi per un riferimento `Handles` in una pagina. Tuttavia, tale operazione potrebbe richiedere un passaggio di compilazione che consenta al file intermedio di popolare tutti i riferimenti `Friends`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.UIElement.AddHandler%2A>
- [Contrassegno degli eventi indirizzati come gestiti e gestione delle classi](marking-routed-events-as-handled-and-class-handling.md)
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
- [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)

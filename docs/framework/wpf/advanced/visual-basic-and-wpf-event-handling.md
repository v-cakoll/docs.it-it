---
title: Visual Basic e la gestione degli eventi WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Visual Basic [WPF], event handlers
- event handlers [WPF], Visual Basic
ms.assetid: ad4eb9aa-3afc-4a71-8cf6-add3fbea54a1
ms.openlocfilehash: c6e1863850ebf04408c7ffc7b784e9ca3ca12cf5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078023"
---
# <a name="visual-basic-and-wpf-event-handling"></a>Visual Basic e la gestione degli eventi WPF
Per la lingua di Microsoft Visual Basic .NET in particolare, è possibile usare le specifiche della lingua `Handles` parola chiave per associare i gestori eventi alle istanze, invece di collegare i gestori di eventi con gli attributi o usando il <xref:System.Windows.UIElement.AddHandler%2A> (metodo). Tuttavia, la tecnica `Handles` per collegare gestori alle istanze presenta alcuni limiti, in quanto la sintassi `Handles` non è in grado di supportare alcune delle funzioni degli eventi indirizzati specifiche del sistema di eventi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## <a name="using-handles-in-a-wpf-application"></a>Uso di "Handles" in un'applicazione WPF  
 I gestori eventi connessi a istanze ed eventi tramite `Handles` devono essere definiti tutti all'interno della dichiarazione di classe parziale dell'istanza. Ciò vale anche per i gestori eventi assegnati tramite valori di attributo negli elementi. È possibile specificare solo `Handles` per un elemento nella pagina che ha un <xref:System.Windows.FrameworkContentElement.Name%2A> il valore di proprietà (o [direttiva X:Name](../../xaml-services/x-name-directive.md) dichiarato). Infatti il <xref:System.Windows.FrameworkContentElement.Name%2A> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] crea il riferimento all'istanza che è necessario per supportare la *istanza* formato di riferimento necessario per il `Handles` sintassi. L'unico elemento che può essere usato per `Handles` senza un <xref:System.Windows.FrameworkContentElement.Name%2A> riferimento è l'istanza dell'elemento radice che definisce la classe parziale.  
  
 È possibile assegnare lo stesso gestore a più elementi separando i riferimenti *Istanza.Evento* dopo `Handles` con delle virgole.  
  
 È possibile usare `Handles` per assegnare più gestori allo stesso riferimento *Istanza.Evento*. Non attribuire alcuna importanza all'ordine in cui vengono forniti i gestori nel riferimento `Handles`. È necessario presupporre che gestori dello stesso evento possono essere richiamati in qualsiasi ordine.  
  
 Per rimuovere un gestore aggiunto con `Handles` nella dichiarazione, è possibile chiamare <xref:System.Windows.UIElement.RemoveHandler%2A>.  
  
 È possibile usare `Handles` per collegare i gestori per gli eventi indirizzati, purché i gestori vengano collegati a istanze che definiscono l'evento gestito nelle rispettive tabelle di membri. Per gli eventi indirizzati, i gestori associati con `Handles` seguono le stesse regole di routine dei gestori associati come [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributi, o con la firma comune di <xref:System.Windows.UIElement.AddHandler%2A>. Ciò significa che se l'evento è già contrassegnato come gestito (il <xref:System.Windows.RoutedEventArgs.Handled%2A> è di proprietà nei dati dell'evento `True`), i gestori associati con `Handles` non vengono richiamati in risposta a tale istanza dell'evento. L'evento potrebbe essere contrassegnato come gestito dai gestori dell'istanza in un altro elemento della route o dalla gestione delle classi nell'elemento corrente o negli elementi precedenti della route. Per gli eventi di input che supportano eventi accoppiati di tunneling e di bubbling, è possibile che la route di tunneling abbia contrassegnato la coppia di eventi come gestita. Per altre informazioni sugli eventi indirizzati, vedere [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
## <a name="limitations-of-handles-for-adding-handlers"></a>Limitazioni di "Handle" per l'aggiunta di gestori  
 `Handles` non è possibile fare riferimento ai gestori per gli eventi associati. È necessario usare il metodo della funzione di accesso `add` per quello specifico evento associato oppure gli attributi dell'evento *nometipo.nomeevento* in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Per informazioni dettagliate, vedere [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
 Per gli eventi indirizzati, è possibile usare `Handles` unicamente per assegnare gestori per le istanze in cui quell'evento è presente nella tabella dei membri dell'istanza. Tuttavia, con gli eventi indirizzati in generale, un elemento padre può essere un listener per un evento degli elementi figlio anche se l'elemento padre non dispone di quell'evento nella relativa tabella dei membri. Nella sintassi dell'attributo, ciò può essere specificato tramite un formato di attributo *nometipo.nomemembro* che qualifica il tipo che definisce effettivamente l'evento che si vuole gestire. Ad esempio, un elemento padre `Page` (con nessun `Click` evento definito) può restare in ascolto degli eventi clic del pulsante assegnando un gestore attributi nel formato `Button.Click`. Tuttavia, `Handles` non supporta il formato *nometipo.nomemembro*, in quanto deve supportare un formato *Istanza.Evento* in conflitto. Per informazioni dettagliate, vedere [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
 `Handles` non è possibile collegare i gestori vengono richiamati per eventi che sono già contrassegnati come gestiti. In alternativa, è necessario utilizzare codice e chiamare il `handledEventsToo` eseguire l'overload di <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>.  
  
> [!NOTE]
>  Non usare il `Handles` sintassi nel codice Visual Basic quando si specifica un gestore eventi per lo stesso evento in XAML. In questo caso, il gestore eventi viene chiamato due volte.  
  
## <a name="how-wpf-implements-handles-functionality"></a>Come WPF implementa la funzionalità "Handles"  
 Quando un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] pagina compilazione, il file intermedio dichiara `Friend` `WithEvents` riferimenti a ogni elemento della pagina contenente una <xref:System.Windows.FrameworkContentElement.Name%2A> set di proprietà (o [direttiva X:Name](../../xaml-services/x-name-directive.md) dichiarato). Ogni istanza denominata è potenzialmente un elemento che può essere assegnato a un gestore tramite `Handles`.  
  
> [!NOTE]
>  All'interno di [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], [!INCLUDE[TLA2#tla_intellisense](../../../../includes/tla2sharptla-intellisense-md.md)] è in grado di mostrare il completamento per il quale sono disponibili degli elementi per un riferimento `Handles` in una pagina. Tuttavia, tale operazione potrebbe richiedere un passaggio di compilazione che consenta al file intermedio di popolare tutti i riferimenti `Friends`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.UIElement.AddHandler%2A>
- [Impostazione degli eventi indirizzati come gestiti e gestione delle classi](marking-routed-events-as-handled-and-class-handling.md)
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
- [Panoramica di XAML (WPF)](xaml-overview-wpf.md)

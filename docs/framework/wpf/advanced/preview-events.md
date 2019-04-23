---
title: Eventi di anteprima
ms.date: 03/30/2017
helpviewer_keywords:
- Preview events [WPF]
- suppressing events [WPF]
- events [WPF], Preview
- events [WPF], suppressing
ms.assetid: b5032308-aa9c-4d02-af11-630ecec8df7e
ms.openlocfilehash: 75165df94aa8b508ef85cf970933efb98b9d62ca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211394"
---
# <a name="preview-events"></a>Eventi di anteprima
Eventi di anteprima, noti anche come eventi di tunneling, sono eventi indirizzati in cui la direzione della route viene trasferito dalla radice dell'applicazione verso l'elemento che ha generato l'evento e viene indicato come origine di dati dell'evento. Non tutti gli scenari di evento supportano o richiedono eventi di anteprima. questo argomento descrive le situazioni in cui gli eventi di anteprima sono presenti, come le applicazioni o componenti devono essere gestiti, e i casi in cui la creazione di eventi di anteprima in componenti personalizzati o classi potrebbe essere appropriata.  
  
## <a name="preview-events-and-input"></a>Input e gli eventi di anteprima  
 Quando si gestisce gli eventi in generale, è necessario prestare attenzione all'anteprima contrassegnare gli eventi gestiti nell'evento dati. Gestisce un evento di anteprima in qualsiasi elemento diverso dall'elemento che lo ha generato (l'elemento che viene segnalato come origine nei dati dell'evento) ha l'effetto di non fornisce la possibilità di gestire l'evento che ha avuto origine un elemento. In alcuni casi questo è il risultato desiderato, in particolare se sono presenti gli elementi in questione nelle relazioni all'interno della composizione di un controllo.  
  
 Per gli eventi di input in particolare, gli eventi di anteprima anche condividono le istanze dei dati di evento con l'evento di bubbling equivalente. Se si usa un gestore di classi di eventi di anteprima per contrassegnare l'evento di input gestita, il gestore di classi di evento di input bubbling non essere richiamato. In alternativa, se si usa un gestore di istanze evento anteprima per contrassegnare l'evento come gestito, i gestori per l'evento di bubbling non saranno in genere essere richiamati. I gestori classi o gestori istanze possono essere registrati o collegati con la possibilità di essere richiamati anche se l'evento è contrassegnato come gestito, ma tale tecnica non viene usata comunemente.  
  
 Per altre informazioni sulla gestione delle classi e la sua relazione con eventi di anteprima, vedere [contrassegno degli eventi indirizzati come gestiti e gestione delle classi](marking-routed-events-as-handled-and-class-handling.md).  
  
### <a name="working-around-event-suppression-by-controls"></a>Soluzioni alternative all'eliminazione di eventi da parte dei controlli  
 Uno scenario in cui gli eventi di anteprima vengono comunemente usati è per la gestione di controllo composito di eventi di input. In alcuni casi, l'autore del controllo evita la visualizzazione di un determinato evento originato dal loro controllo, ad esempio per sostituire un evento definito dal componente che contiene più informazioni o implica un comportamento più specifico. Ad esempio, un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> evita <xref:System.Windows.UIElement.MouseLeftButtonDown> e <xref:System.Windows.UIElement.MouseRightButtonDown> bubbling gli eventi generati dal <xref:System.Windows.Controls.Button> o sui suoi elementi compositi a favore lo stato mouse capture e la generazione di un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento che viene sempre generato dal <xref:System.Windows.Controls.Button> stesso. L'evento e i relativi dati comunque continuare lungo la route, tuttavia, poiché il <xref:System.Windows.Controls.Button> contrassegna i dati dell'evento come <xref:System.Windows.RoutedEventArgs.Handled%2A>, solo i gestori per l'evento che espressamente indicato agiscono nel `handledEventsToo` case vengono richiamati.  Se gli altri elementi verso la radice dell'applicazione voleva comunque la possibilità di gestire un evento eliminato di controllo, in alternativa è possibile associare i gestori nel codice con `handledEventsToo` specificato come `true`. Ma spesso una tecnica più semplice consiste nel modificare la direzione di routing è gestire per l'equivalente di anteprima di un evento di input. Ad esempio, se un controllo sopprime <xref:System.Windows.UIElement.MouseLeftButtonDown>, provare a collegare un gestore per <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> invece. Questa tecnica funziona solo per gli eventi di input di elementi di base, ad esempio <xref:System.Windows.UIElement.MouseLeftButtonDown>. Questi eventi di input usano coppie di tunneling/bubbling, generano entrambi gli eventi e condividono i dati dell'evento.  
  
 Ognuna di queste tecniche ha effetti collaterali o le limitazioni. L'effetto collaterale di gestione dell'evento di anteprima è che la gestione dell'evento a questo punto può disattivare i gestori che prevedono di gestire l'evento di bubbling e pertanto la limitazione è che in genere non è una buona idea per contrassegnare l'evento come gestito mentre è ancora attivata la Previ parte uova della route. La limitazione del `handledEventsToo` tecnica è che non è possibile specificare un `handledEventsToo` gestore in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] come un attributo, è necessario registrare il gestore dell'evento nel codice dopo aver ottenuto un riferimento all'oggetto per l'elemento in cui il gestore di è da collegare.  
  
## <a name="see-also"></a>Vedere anche

- [Contrassegno degli eventi indirizzati come gestiti e gestione delle classi](marking-routed-events-as-handled-and-class-handling.md)
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)

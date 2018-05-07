---
title: Eventi di anteprima
ms.date: 03/30/2017
helpviewer_keywords:
- Preview events [WPF]
- suppressing events [WPF]
- events [WPF], Preview
- events [WPF], suppressing
ms.assetid: b5032308-aa9c-4d02-af11-630ecec8df7e
ms.openlocfilehash: 2d6c1ab32cb43730af2f935f4bd4405059994c12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="preview-events"></a>Eventi di anteprima
Gli eventi di anteprima, noti anche come eventi di tunneling, sono gli eventi indirizzati in cui la direzione della route viene trasferito dalla radice dell'applicazione verso l'elemento che ha generato l'evento e viene restituito come origine dati di evento. Non tutti gli scenari supportano o richiedono eventi di anteprima. In questo argomento vengono descritte le situazioni in cui sono presenti tali eventi, come applicazioni o componenti deve essere gestita, e i casi in cui la creazione di eventi di anteprima in componenti personalizzati o classi potrebbe essere appropriata.  
  
## <a name="preview-events-and-input"></a>Eventi di anteprima e di Input  
 Quando si gestisce gli eventi in generale, è necessario prestare attenzione all'anteprima contrassegnare gli eventi gestiti nell'evento dati. La gestione di un evento di anteprima su qualsiasi elemento diverso dall'elemento che ha generato (l'elemento che viene segnalato come origine dei dati di evento) ha l'effetto di non specificare un elemento la possibilità di gestire l'evento che ha avuto origine. Talvolta, questo è il risultato desiderato, in particolare se sono presenti gli elementi in questione nelle relazioni all'interno della composizione di un controllo.  
  
 Per gli eventi di input in particolare, gli eventi di anteprima anche condividono le istanze dei dati di evento con l'evento di bubbling equivalente. Se si utilizza un gestore di classe di evento di anteprima per contrassegnare l'evento di input gestito, non verrà richiamato il gestore bubbling della classe di evento di input. In alternativa, se si utilizza un gestore di istanza di anteprima per contrassegnare l'evento gestito, gestori eventi per l'evento di bubbling non verranno in genere essere richiamati. Gestori di classi o gestori di istanze possono essere registrati o associati a un'opzione per essere richiamato anche se l'evento è contrassegnato come gestito, ma tale tecnica non è in genere utilizzata.  
  
 Per ulteriori informazioni sulla gestione delle classi e le relazioni con gli eventi di anteprima vedere [contrassegnare gli eventi indirizzati come Handled e la gestione della classe](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md).  
  
### <a name="working-around-event-suppression-by-controls"></a>Soluzioni alternative all'eliminazione di eventi da parte dei controlli  
 Uno scenario in cui gli eventi di anteprima utilizzati frequentemente è per la gestione di controllo composito di eventi di input. In alcuni casi, l'autore del controllo evita la visualizzazione di un determinato evento originato dal relativo controllo, ad esempio per sostituire un evento definito dal componente che fornisce maggiori informazioni o implica un comportamento più specifico. Ad esempio, un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> Elimina <xref:System.Windows.UIElement.MouseLeftButtonDown> e <xref:System.Windows.UIElement.MouseLeftButtonDown> bubbling gli eventi generati dal <xref:System.Windows.Controls.Button> o sui suoi elementi compositi a favore lo stato mouse capture e la generazione di un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento che viene sempre generato dal <xref:System.Windows.Controls.Button> se stesso. L'evento e i relativi dati proseguono lungo la route, tuttavia, poiché il <xref:System.Windows.Controls.Button> contrassegna i dati dell'evento come <xref:System.Windows.RoutedEventArgs.Handled%2A>, solo i gestori dell'evento che indicati agiscono nel `handledEventsToo` case vengono richiamati.  Se gli altri elementi verso la radice dell'applicazione si desidera comunque la possibilità di gestire un evento di controllo eliminato, un'alternativa consiste nell'associare un gestore nel codice con `handledEventsToo` specificato come `true`. È spesso una tecnica più semplice per modificare la direzione di routing è gestire per l'equivalente di anteprima di un evento di input. Ad esempio, se un controllo Elimina <xref:System.Windows.UIElement.MouseLeftButtonDown>, provare a collegare un gestore per <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> invece. Questa tecnica funziona solo per gli eventi di input dell'elemento di base, ad esempio <xref:System.Windows.UIElement.MouseLeftButtonDown>. Questi eventi di input utilizzano coppie di tunneling/bubbling, generano entrambi gli eventi e condividono i dati dell'evento.  
  
 Ognuna di queste tecniche ha effetti collaterali o limitazioni. L'effetto collaterale di gestione dell'evento di anteprima è che la gestione dell'evento a questo punto può disattivare i gestori che prevede di gestire l'evento bubbling e pertanto la limitazione è che non è consigliabile contrassegnare l'evento come gestito mentre è ancora presente il Previ parte uovo della route. La limitazione del `handledEventsToo` tecnica consiste nel fatto che non è possibile specificare un `handledEventsToo` gestore in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] come un attributo, è necessario registrare il gestore dell'evento nel codice dopo aver ottenuto un riferimento all'oggetto per l'elemento in cui il gestore deve essere collegato.  
  
## <a name="see-also"></a>Vedere anche  
 [Contrassegno degli eventi indirizzati come gestiti e gestione delle classi](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [Cenni preliminari sugli eventi indirizzati](../../../../docs/framework/wpf/advanced/routed-events-overview.md)

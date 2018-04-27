### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a>Arresto anomalo del sistema nel selettore quando si rimuove un elemento da una raccolta INCC personalizzata

|   |   |
|---|---|
|Dettagli|Un'eccezione <code>T:System.InvalidOperationException</code> può verificarsi negli scenari seguenti:<ul><li>ItemsSource per un <code>T:System.Windows.Controls.Primitives.Selector</code> è una raccolta con un'implementazione personalizzata di <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</li><li>L'elemento selezionato viene rimosso dalla raccolta.</li><li><code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> ha <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> = -1 (indica una posizione sconosciuta).</li></ul>Lo stack di chiamate dell'eccezione inizia in corrispondenza di System.Windows.Threading.Dispatcher.VerifyAccess() in System.Windows.DependencyObject.GetValue(DependencyProperty dp) in System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject element) Questa eccezione si può verificare in .Net 4.5 se l'applicazione ha più di un thread di Dispatcher. In .Net 4.7 l'eccezione può verificarsi anche in applicazioni con un singolo thread di Dispatcher. Il problema viene risolto in .Net 4.7.1.|
|Suggerimento|Eseguire l'aggiornamento a .NET 4.7.1.|
|Ambito|Secondario|
|Versione|4.7|
|Tipo|Runtime|


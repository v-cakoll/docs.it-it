---
title: Interfacce correlate al data binding
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], data-binding interfaces
- INotifyPropertyChanged interface
- IBindingListView interface
- IList interface [Windows Forms], Windows Forms data binding
- IBindingList interface [Windows Forms], Windows Forms data binding
- interfaces [Windows Forms], Windows Forms data binding
- IEditableObject interface [Windows Forms], Windows Forms data binding
- data binding [Windows Forms], interfaces
- IDataErrorInfo interface [Windows Forms], Windows Forms data binding
ms.assetid: 14e49a2e-3e46-47ca-b491-70d546333277
ms.openlocfilehash: 4e40f7ec1922cdf43e6a0b8f5734acaaeefbc514
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834595"
---
# <a name="interfaces-related-to-data-binding"></a>Interfacce correlate al data binding

Con ADO.NET è possibile creare molte strutture di dati diverse in base alle esigenze di binding dell'applicazione e ai dati in uso. Si consiglia di creare classi che forniscono o usano dati in Windows Forms. Questi oggetti possono offrire diversi livelli di funzionalità e complessità, dal data binding, all'offerta di supporto in fase di progettazione, al controllo degli errori, alla notifica delle modifiche o anche al supporto per un annullamento strutturato delle modifiche apportate ai dati.

## <a name="consumers-of-data-binding-interfaces"></a>Consumer delle interfacce di data binding

Nelle sezioni seguenti vengono descritti due gruppi di oggetti interfaccia. Nel primo gruppo sono elencate le interfacce implementate nell'origine dati dagli autori dell'origine dati. Queste interfacce sono progettate per essere usate dai consumer dell'origine dati, che sono nella maggior parte dei casi dei controlli o componenti di Windows Forms. Nel secondo gruppo sono elencate le interfacce destinate ad essere usate dagli autori di componenti. Gli autori di componenti usano queste interfacce al momento della creazione di un componente che supporta l'uso del data binding da parte del motore del data-binding di Windows Forms. È possibile implementare queste interfacce all'interno delle classi associate al modulo per consentire il data-binding; ogni caso presenta una classe che implementa un'interfaccia che abilita l'interazione con i dati. Gli strumenti dell'esperienza di progettazione dei dati di Visual Studio Rapid Application Development (RAD) sfruttano già questa funzionalità.

### <a name="interfaces-for-implementation-by-data-source-authors"></a>Interfacce per l'implementazione da parte degli autori dell'origine dati

Le interfacce seguenti sono progettate per essere usate dai controlli di Windows Forms:

- interfaccia <xref:System.Collections.IList>

  Una classe che implementa l'interfaccia <xref:System.Collections.IList> può essere un <xref:System.Array>, <xref:System.Collections.ArrayList> o <xref:System.Collections.CollectionBase>. Si tratta di elenchi indicizzati di elementi di tipo <xref:System.Object>. Questi elenchi devono contenere tipi omogenei, perché il primo elemento dell'indice determina il tipo. <xref:System.Collections.IList> sarebbe disponibile per l'associazione solo in fase di esecuzione.

  > [!NOTE]
  > Se si desidera creare un elenco di oggetti business per l'associazione con Windows Forms, è consigliabile utilizzare il <xref:System.ComponentModel.BindingList%601>. Il <xref:System.ComponentModel.BindingList%601> è una classe estendibile che implementa le interfacce primarie necessarie per il data binding di Windows Forms bidirezionale.

- interfaccia <xref:System.ComponentModel.IBindingList>

  Una classe che implementa l'interfaccia <xref:System.ComponentModel.IBindingList> fornisce un livello di funzionalità di data binding molto più elevato. Questa implementazione offre funzionalità di ordinamento di base e la notifica delle modifiche, sia quando gli elementi dell'elenco cambiano (ad esempio, il terzo elemento in un elenco di clienti include una modifica al campo indirizzo), sia quando l'elenco stesso cambia (ad esempio, il numero di elementi nell'elenco aumenta o diminuisce). La notifica della modifica è importante se si prevede di disporre di più controlli associati agli stessi dati e si desidera che le modifiche apportate in uno dei controlli si propaghi agli altri controlli associati.

  > [!NOTE]
  > La notifica delle modifiche è abilitata per l'interfaccia <xref:System.ComponentModel.IBindingList> tramite la proprietà <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> che, quando `true`, genera un evento <xref:System.ComponentModel.IBindingList.ListChanged>, che indica che l'elenco è stato modificato o che un elemento nell'elenco è stato modificato.

  Il tipo di modifica è descritto dalla proprietà <xref:System.ComponentModel.ListChangedType> del parametro <xref:System.ComponentModel.ListChangedEventArgs>. Di conseguenza, ogni volta che viene aggiornato il modello di dati, anche tutte le visualizzazioni dipendenti, ad esempio gli altri controlli associati alla stessa origine dati, verranno aggiornate. Tuttavia, gli oggetti contenuti all'interno dell'elenco dovranno inviare una notifica all'elenco quando cambiano, in modo che l'elenco possa generare l'evento <xref:System.ComponentModel.IBindingList.ListChanged>.

  > [!NOTE]
  > Il <xref:System.ComponentModel.BindingList%601> fornisce un'implementazione generica dell'interfaccia <xref:System.ComponentModel.IBindingList>.

- interfaccia <xref:System.ComponentModel.IBindingListView>

  Una classe che implementa l'interfaccia <xref:System.ComponentModel.IBindingListView> fornisce tutte le funzionalità di un'implementazione di <xref:System.ComponentModel.IBindingList>, nonché le funzionalità di filtro e ordinamento avanzato. Questa implementazione fornisce un filtro basato sulle stringhe, e un ordinamento a più colonne con coppie descrittore-direzione della proprietà.

- interfaccia <xref:System.ComponentModel.IEditableObject>

  Una classe che implementa l'interfaccia <xref:System.ComponentModel.IEditableObject> consente a un oggetto di controllare quando le modifiche apportate a tale oggetto vengono rese permanenti. Questa implementazione consente di eseguire il rollback delle modifiche apportate all'oggetto con i metodi <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A> e <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>. Di seguito è riportata una breve spiegazione del funzionamento dei metodi <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A> e <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> e del modo in cui funzionano insieme tra loro per consentire un possibile rollback delle modifiche apportate ai dati:

  - Il metodo <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> segnala l'inizio di una modifica in un oggetto. Un oggetto che implementa questa interfaccia dovrà archiviare eventuali aggiornamenti dopo la chiamata al metodo <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> in modo che gli aggiornamenti possano essere rimossi se viene chiamato il metodo <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>. In data binding Windows Forms è possibile chiamare più volte <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> nell'ambito di una singola transazione di modifica, ad esempio <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>. Le implementazioni di <xref:System.ComponentModel.IEditableObject> devono tenere traccia del fatto che <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> sia già stata chiamata e ignorare le chiamate successive a <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>. Poiché questo metodo può essere chiamato più volte, è importante che le chiamate successive non siano distruttive; ovvero, le chiamate successive a <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> non possono eliminare gli aggiornamenti che sono stati apportati o modificare i dati salvati nella prima chiamata <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>.

  - Il metodo <xref:System.ComponentModel.IEditableObject.EndEdit%2A> esegue il push di tutte le modifiche apportate dopo la chiamata di <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> nell'oggetto sottostante, se l'oggetto è attualmente in modalità di modifica.

  - Il metodo <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> Elimina tutte le modifiche apportate all'oggetto.

  Per ulteriori informazioni sul funzionamento dei metodi <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A> e <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>, vedere salvare i [dati nel database](/visualstudio/data-tools/save-data-back-to-the-database).

  Questa nozione transazionale della funzionalità dei dati viene utilizzata dal controllo <xref:System.Windows.Forms.DataGridView>.

- interfaccia <xref:System.ComponentModel.ICancelAddNew>

  Una classe che implementa l'interfaccia <xref:System.ComponentModel.ICancelAddNew> in genere implementa l'interfaccia <xref:System.ComponentModel.IBindingList> e consente di eseguire il rollback di un'aggiunta apportata all'origine dati con il metodo <xref:System.ComponentModel.IBindingList.AddNew%2A>. Se l'origine dati implementa l'interfaccia <xref:System.ComponentModel.IBindingList>, è necessario che venga implementata anche l'interfaccia <xref:System.ComponentModel.ICancelAddNew>.

- interfaccia <xref:System.ComponentModel.IDataErrorInfo>

  Una classe che implementa l'interfaccia <xref:System.ComponentModel.IDataErrorInfo> consente agli oggetti di offrire informazioni personalizzate sugli errori ai controlli associati:

  - La proprietà <xref:System.ComponentModel.IDataErrorInfo.Error%2A> restituisce il testo del messaggio di errore generale (ad esempio, "si è verificato un errore").

  - La proprietà <xref:System.ComponentModel.IDataErrorInfo.Item%2A> restituisce una stringa con il messaggio di errore specifico dalla colonna (ad esempio, "il valore nella colonna `State` non è valido").

- interfaccia <xref:System.Collections.IEnumerable>

  Una classe che implementa l'interfaccia <xref:System.Collections.IEnumerable> viene in genere utilizzata da ASP.NET. Windows Forms supporto per questa interfaccia è disponibile solo tramite il componente <xref:System.Windows.Forms.BindingSource>.

  > [!NOTE]
  > Il componente <xref:System.Windows.Forms.BindingSource> copia tutti gli elementi <xref:System.Collections.IEnumerable> in un elenco separato a scopo di associazione.

- interfaccia <xref:System.ComponentModel.ITypedList>

  Una classe Collections che implementa l'interfaccia <xref:System.ComponentModel.ITypedList> fornisce la possibilità di controllare l'ordine e il set di proprietà esposte al controllo associato.

  > [!NOTE]
  > Quando si implementa il metodo <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> e la matrice <xref:System.ComponentModel.PropertyDescriptor> non è null, l'ultima voce nella matrice sarà il descrittore di proprietà che descrive la proprietà List che rappresenta un altro elenco di elementi.

- interfaccia <xref:System.ComponentModel.ICustomTypeDescriptor>

  Una classe che implementa l'interfaccia <xref:System.ComponentModel.ICustomTypeDescriptor> fornisce informazioni dinamiche su se stessa. Questa interfaccia è simile a <xref:System.ComponentModel.ITypedList>, ma viene utilizzata per gli oggetti anziché gli elenchi. Questa interfaccia viene utilizzata da <xref:System.Data.DataRowView> per proiettare lo schema delle righe sottostanti. Una semplice implementazione di <xref:System.ComponentModel.ICustomTypeDescriptor> viene fornita dalla classe <xref:System.ComponentModel.CustomTypeDescriptor>.

  > [!NOTE]
  > Per supportare l'associazione in fase di progettazione ai tipi che implementano <xref:System.ComponentModel.ICustomTypeDescriptor>, il tipo deve implementare anche <xref:System.ComponentModel.IComponent> ed esistere come istanza nel form.

- interfaccia <xref:System.ComponentModel.IListSource>

  Una classe che implementa l'interfaccia <xref:System.ComponentModel.IListSource> Abilita l'associazione basata sull'elenco su oggetti non di elenco. Il metodo <xref:System.ComponentModel.IListSource.GetList%2A> di <xref:System.ComponentModel.IListSource> viene utilizzato per restituire un elenco associabile da un oggetto che non eredita da <xref:System.Collections.IList>. <xref:System.ComponentModel.IListSource> viene usato dalla classe <xref:System.Data.DataSet>.

- interfaccia <xref:System.ComponentModel.IRaiseItemChangedEvents>

  Una classe che implementa l'interfaccia <xref:System.ComponentModel.IRaiseItemChangedEvents> è un elenco associabile che implementa anche l'interfaccia <xref:System.ComponentModel.IBindingList>. Questa interfaccia viene utilizzata per indicare se il tipo genera eventi <xref:System.ComponentModel.IBindingList.ListChanged> di tipo <xref:System.ComponentModel.ListChangedType.ItemChanged> tramite la relativa proprietà <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A>.

  > [!NOTE]
  > È necessario implementare il <xref:System.ComponentModel.IRaiseItemChangedEvents> se l'origine dati fornisce la proprietà per elencare la conversione degli eventi descritta in precedenza e interagisce con il componente <xref:System.Windows.Forms.BindingSource>. In caso contrario, il <xref:System.Windows.Forms.BindingSource> eseguirà anche la proprietà per elencare la conversione degli eventi, con conseguente rallentamento delle prestazioni.

- interfaccia <xref:System.ComponentModel.ISupportInitialize>

  Un componente che implementa l'interfaccia <xref:System.ComponentModel.ISupportInitialize> trae vantaggio dalle ottimizzazioni batch per l'impostazione di proprietà e l'inizializzazione di proprietà co-dipendenti. Il <xref:System.ComponentModel.ISupportInitialize> contiene due metodi:

  - <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> segnala l'avvio dell'inizializzazione dell'oggetto.

  - <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> segnala che l'inizializzazione dell'oggetto sta per terminare.

- interfaccia <xref:System.ComponentModel.ISupportInitializeNotification>

  Un componente che implementa l'interfaccia <xref:System.ComponentModel.ISupportInitializeNotification> implementa anche l'interfaccia <xref:System.ComponentModel.ISupportInitialize>. Questa interfaccia consente di notificare ad altri componenti <xref:System.ComponentModel.ISupportInitialize> che l'inizializzazione è stata completata. L'interfaccia <xref:System.ComponentModel.ISupportInitializeNotification> contiene due membri:

  - <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A> restituisce un valore `boolean` che indica se il componente è inizializzato.

  - <xref:System.ComponentModel.ISupportInitializeNotification.Initialized> si verifica quando viene chiamato <xref:System.ComponentModel.ISupportInitialize.EndInit%2A>.

- interfaccia <xref:System.ComponentModel.INotifyPropertyChanged>

  Una classe che implementa questa interfaccia è un tipo che genera un evento quando uno dei valori delle proprietà viene modificato. Questa interfaccia è progettata per sostituire il criterio di disporre di un evento di modifica per ogni proprietà di un controllo. Quando viene utilizzato in un <xref:System.ComponentModel.BindingList%601>, un oggetto business deve implementare l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> e l'oggetto BindingList @ no__t-21 convertirà gli eventi <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> in eventi <xref:System.ComponentModel.BindingList%601.ListChanged> di tipo <xref:System.ComponentModel.ListChangedType.ItemChanged>.

  > [!NOTE]
  > Affinché la notifica delle modifiche venga eseguita in un'associazione tra un client associato e un'origine dati, il tipo di origine dati associato deve implementare l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> (scelta consigliata) oppure è possibile fornire eventi *propertyName*`Changed` per il tipo associato, ma si non deve eseguire entrambe le operazioni.

### <a name="interfaces-for-implementation-by-component-authors"></a>Interfacce per l'implementazione da parte degli autori del componente

Le interfacce seguenti sono progettate per l'uso da parte del motore di data-binding di Windows Forms:

- interfaccia <xref:System.Windows.Forms.IBindableComponent>

  Una classe che implementa questa interfaccia è un componente di non-controllo che supporta il data-binding. Questa classe restituisce le associazioni dati e il contesto di associazione del componente tramite le proprietà <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> e <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> di questa interfaccia.

  > [!NOTE]
  > Se il componente eredita da <xref:System.Windows.Forms.Control>, non è necessario implementare l'interfaccia <xref:System.Windows.Forms.IBindableComponent>.

- interfaccia <xref:System.Windows.Forms.ICurrencyManagerProvider>

  Una classe che implementa l'interfaccia <xref:System.Windows.Forms.ICurrencyManagerProvider> è un componente che fornisce il proprio <xref:System.Windows.Forms.CurrencyManager> per gestire le associazioni associate a questo particolare componente. L'accesso alla @no__t personalizzata-0 viene fornito dalla proprietà <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A>.

  > [!NOTE]
  > Una classe che eredita da <xref:System.Windows.Forms.Control> gestisce automaticamente le associazioni tramite la relativa proprietà <xref:System.Windows.Forms.Control.BindingContext%2A>, quindi i casi in cui è necessario implementare il <xref:System.Windows.Forms.ICurrencyManagerProvider> sono piuttosto rari.

## <a name="see-also"></a>Vedere anche

- [Data binding e Windows Forms](data-binding-and-windows-forms.md)
- [Procedura: Creare un controllo con associazione semplice in un Windows Form @ no__t-0
- [Data binding in Windows Form](windows-forms-data-binding.md)

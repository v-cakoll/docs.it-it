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
ms.openlocfilehash: 9f102b584d2ed0b5a9d2bbb0e7ce3f7871ec40b2
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046364"
---
# <a name="interfaces-related-to-data-binding"></a>Interfacce correlate al data binding

Con ADO.NET è possibile creare molte strutture di dati diverse in base alle esigenze di binding dell'applicazione e ai dati in uso. Si consiglia di creare classi che forniscono o usano dati in Windows Forms. Questi oggetti possono offrire diversi livelli di funzionalità e complessità, dal data binding, all'offerta di supporto in fase di progettazione, al controllo degli errori, alla notifica delle modifiche o anche al supporto per un annullamento strutturato delle modifiche apportate ai dati.

## <a name="consumers-of-data-binding-interfaces"></a>Consumer delle interfacce di data binding

Nelle sezioni seguenti vengono descritti due gruppi di oggetti dell'interfaccia. Nel primo gruppo sono elencate le interfacce implementate nell'origine dati dagli autori dell'origine dati. Queste interfacce sono progettate per essere usate dai consumer dell'origine dati, che sono nella maggior parte dei casi dei controlli o componenti di Windows Forms. Nel secondo gruppo sono elencate le interfacce destinate ad essere usate dagli autori di componenti. Gli autori di componenti usano queste interfacce al momento della creazione di un componente che supporta l'uso del data binding da parte del motore del data-binding di Windows Forms. È possibile implementare queste interfacce all'interno delle classi associate al modulo per consentire il data-binding; ogni caso presenta una classe che implementa un'interfaccia che abilita l'interazione con i dati. Gli strumenti dell'esperienza di progettazione dei dati di Visual Studio Rapid Application Development (RAD) sfruttano già questa funzionalità.

### <a name="interfaces-for-implementation-by-data-source-authors"></a>Interfacce per l'implementazione da parte degli autori dell'origine dati

Le interfacce seguenti sono progettate per essere usate dai controlli di Windows Forms:

- <xref:System.Collections.IList>interfaccia

  Una classe che implementa l' <xref:System.Collections.IList> interfaccia può <xref:System.Array>essere, <xref:System.Collections.ArrayList>o <xref:System.Collections.CollectionBase>. Si tratta di elenchi indicizzati di elementi di <xref:System.Object>tipo. Questi elenchi devono contenere tipi omogenei, perché il primo elemento dell'indice determina il tipo. <xref:System.Collections.IList>sarebbe disponibile per l'associazione solo in fase di esecuzione.

  > [!NOTE]
  > Se si desidera creare un elenco di oggetti business per l' <xref:System.ComponentModel.BindingList%601>associazione con Windows Forms, è consigliabile utilizzare. <xref:System.ComponentModel.BindingList%601> È una classe estendibile che implementa le interfacce primarie necessarie per la data binding di Windows Forms bidirezionale.

- <xref:System.ComponentModel.IBindingList>interfaccia

  Una classe che implementa l' <xref:System.ComponentModel.IBindingList> interfaccia fornisce un livello di funzionalità di data binding molto più elevato. Questa implementazione offre funzionalità di ordinamento di base e la notifica delle modifiche, sia quando gli elementi dell'elenco cambiano (ad esempio, il terzo elemento in un elenco di clienti include una modifica al campo indirizzo), sia quando l'elenco stesso cambia (ad esempio, il numero di elementi nell'elenco aumenta o diminuisce). La notifica della modifica è importante se si prevede di disporre di più controlli associati agli stessi dati e si desidera che le modifiche apportate in uno dei controlli si propaghi agli altri controlli associati.

  > [!NOTE]
  > La notifica delle modifiche <xref:System.ComponentModel.IBindingList> è abilitata per l' <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> interfaccia tramite la proprietà `true`che, quando <xref:System.ComponentModel.IBindingList.ListChanged> , genera un evento, che indica che l'elenco è stato modificato o che un elemento nell'elenco è stato modificato.

  Il tipo di modifica è descritto dalla <xref:System.ComponentModel.ListChangedType> proprietà <xref:System.ComponentModel.ListChangedEventArgs> del parametro. Di conseguenza, ogni volta che viene aggiornato il modello di dati, anche tutte le visualizzazioni dipendenti, ad esempio gli altri controlli associati alla stessa origine dati, verranno aggiornate. Tuttavia, gli oggetti contenuti all'interno dell'elenco dovranno inviare una notifica all'elenco quando cambiano, in modo che l'elenco <xref:System.ComponentModel.IBindingList.ListChanged> possa generare l'evento.

  > [!NOTE]
  > Fornisce un'implementazione generica <xref:System.ComponentModel.IBindingList> dell'interfaccia. <xref:System.ComponentModel.BindingList%601>

- <xref:System.ComponentModel.IBindingListView>interfaccia

  Una classe che implementa l' <xref:System.ComponentModel.IBindingListView> interfaccia fornisce tutte le funzionalità di un'implementazione di <xref:System.ComponentModel.IBindingList>, nonché le funzionalità di filtro e ordinamento avanzato. Questa implementazione fornisce un filtro basato sulle stringhe, e un ordinamento a più colonne con coppie descrittore-direzione della proprietà.

- <xref:System.ComponentModel.IEditableObject>interfaccia

  Una classe che implementa l' <xref:System.ComponentModel.IEditableObject> interfaccia consente a un oggetto di controllare quando le modifiche apportate a tale oggetto vengono rese permanenti. Questa implementazione fornisce i <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>metodi, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>e <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> , che consentono di eseguire il rollback delle modifiche apportate all'oggetto. Di seguito è riportata una breve spiegazione del funzionamento dei <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> metodi <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, e e del modo in cui funzionano insieme tra loro per consentire un possibile rollback delle modifiche apportate ai dati:

  - Il <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> metodo segnala l'inizio di una modifica in un oggetto. Un oggetto che implementa questa interfaccia dovrà archiviare eventuali aggiornamenti dopo la <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> chiamata al metodo in modo che gli aggiornamenti possano essere rimossi se viene chiamato il <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> metodo. In data binding <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> Windows Forms è possibile chiamare più volte nell'ambito di una singola transazione di modifica, ad <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>esempio <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> <xref:System.ComponentModel.IEditableObject.EndEdit%2A>,,. Le implementazioni <xref:System.ComponentModel.IEditableObject> di devono tenere traccia di <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> se è già stato chiamato e ignorare le chiamate <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>successive a. Poiché questo metodo può essere chiamato più volte, è importante che le chiamate successive non siano distruttive; ovvero, le chiamate <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> successive non possono eliminare gli aggiornamenti che sono stati apportati o modificare i dati salvati alla prima <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> chiamata.

  - Il <xref:System.ComponentModel.IEditableObject.EndEdit%2A> metodo effettua il push di tutte <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> le modifiche apportate dopo che è stato chiamato nell'oggetto sottostante, se l'oggetto è attualmente in modalità di modifica.

  - Il <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> metodo rimuove tutte le modifiche apportate all'oggetto.

  Per ulteriori informazioni sul funzionamento dei <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>metodi <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, e <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> , vedere salvare i [dati nel database](/visualstudio/data-tools/save-data-back-to-the-database).

  Questa nozione transazionale della funzionalità dei dati viene utilizzata <xref:System.Windows.Forms.DataGridView> dal controllo.

- <xref:System.ComponentModel.ICancelAddNew>interfaccia

  Una classe che implementa l' <xref:System.ComponentModel.ICancelAddNew> interfaccia in genere implementa <xref:System.ComponentModel.IBindingList> l'interfaccia e consente di eseguire il rollback di un'aggiunta apportata all'origine <xref:System.ComponentModel.IBindingList.AddNew%2A> dati con il metodo. Se l'origine dati implementa l' <xref:System.ComponentModel.IBindingList> interfaccia, è necessario che venga implementata anche <xref:System.ComponentModel.ICancelAddNew> l'interfaccia.

- <xref:System.ComponentModel.IDataErrorInfo>interfaccia

  Una classe che implementa l' <xref:System.ComponentModel.IDataErrorInfo> interfaccia consente agli oggetti di offrire informazioni personalizzate sugli errori ai controlli associati:

  - La <xref:System.ComponentModel.IDataErrorInfo.Error%2A> proprietà restituisce il testo del messaggio di errore generale (ad esempio, "si è verificato un errore").

  - La <xref:System.ComponentModel.IDataErrorInfo.Item%2A> proprietà restituisce una stringa con il messaggio di errore specifico della colonna (ad esempio, "il valore `State` nella colonna non è valido").

- <xref:System.Collections.IEnumerable>interfaccia

  Una classe che implementa l' <xref:System.Collections.IEnumerable> interfaccia viene in genere utilizzata da ASP.NET. Il supporto Windows Forms per questa interfaccia è disponibile solo tramite <xref:System.Windows.Forms.BindingSource> il componente.

  > [!NOTE]
  > Il <xref:System.Windows.Forms.BindingSource> componente copia tutti <xref:System.Collections.IEnumerable> gli elementi in un elenco separato a scopo di associazione.

- <xref:System.ComponentModel.ITypedList>interfaccia

  Una classe Collections che implementa <xref:System.ComponentModel.ITypedList> l'interfaccia fornisce la possibilità di controllare l'ordine e il set di proprietà esposte al controllo associato.

  > [!NOTE]
  > Quando si implementa il <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> metodo e la <xref:System.ComponentModel.PropertyDescriptor> matrice non è null, l'ultima voce nella matrice sarà il descrittore di proprietà che descrive la proprietà List che rappresenta un altro elenco di elementi.

- <xref:System.ComponentModel.ICustomTypeDescriptor>interfaccia

  Una classe che implementa l' <xref:System.ComponentModel.ICustomTypeDescriptor> interfaccia fornisce informazioni dinamiche su se stessa. Questa interfaccia è simile a <xref:System.ComponentModel.ITypedList> ma viene utilizzata per gli oggetti anziché gli elenchi. Questa interfaccia viene utilizzata da <xref:System.Data.DataRowView> per proiettare lo schema delle righe sottostanti. Una semplice implementazione di <xref:System.ComponentModel.ICustomTypeDescriptor> viene fornita <xref:System.ComponentModel.CustomTypeDescriptor> dalla classe.

  > [!NOTE]
  > Per supportare l'associazione in fase di progettazione ai tipi <xref:System.ComponentModel.ICustomTypeDescriptor>che implementano, il tipo <xref:System.ComponentModel.IComponent> deve implementare anche ed esistere come istanza nel form.

- <xref:System.ComponentModel.IListSource>interfaccia

  Una classe che implementa l' <xref:System.ComponentModel.IListSource> interfaccia consente l'associazione basata sull'elenco su oggetti non di elenco. Il <xref:System.ComponentModel.IListSource.GetList%2A> metodo di <xref:System.ComponentModel.IListSource> viene utilizzato per restituire un elenco associabile da un oggetto che non eredita da <xref:System.Collections.IList>. <xref:System.ComponentModel.IListSource>viene usato dalla <xref:System.Data.DataSet> classe.

- <xref:System.ComponentModel.IRaiseItemChangedEvents>interfaccia

  Una classe che implementa l' <xref:System.ComponentModel.IRaiseItemChangedEvents> interfaccia è un elenco associabile che implementa anche <xref:System.ComponentModel.IBindingList> l'interfaccia. Questa interfaccia viene utilizzata per indicare se il tipo genera <xref:System.ComponentModel.IBindingList.ListChanged> eventi di tipo <xref:System.ComponentModel.ListChangedType.ItemChanged> tramite la <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A> relativa proprietà.

  > [!NOTE]
  > È necessario implementare <xref:System.ComponentModel.IRaiseItemChangedEvents> se l'origine dati fornisce la proprietà per elencare la conversione degli eventi descritta in precedenza e interagisce <xref:System.Windows.Forms.BindingSource> con il componente. In caso contrario <xref:System.Windows.Forms.BindingSource> , eseguirà anche la proprietà per elencare la conversione degli eventi, con conseguente rallentamento delle prestazioni.

- <xref:System.ComponentModel.ISupportInitialize>interfaccia

  Un componente che implementa l' <xref:System.ComponentModel.ISupportInitialize> interfaccia trae vantaggio dalle ottimizzazioni batch per l'impostazione di proprietà e l'inizializzazione di proprietà co-dipendenti. <xref:System.ComponentModel.ISupportInitialize> Contiene due metodi:

  - <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A>segnala l'avvio dell'inizializzazione di un oggetto.

  - <xref:System.ComponentModel.ISupportInitialize.EndInit%2A>segnala la fine dell'inizializzazione dell'oggetto.

- <xref:System.ComponentModel.ISupportInitializeNotification>interfaccia

  Un componente che implementa l' <xref:System.ComponentModel.ISupportInitializeNotification> interfaccia implementa anche l' <xref:System.ComponentModel.ISupportInitialize> interfaccia. Questa interfaccia consente di notificare ad <xref:System.ComponentModel.ISupportInitialize> altri componenti che l'inizializzazione è stata completata. L' <xref:System.ComponentModel.ISupportInitializeNotification> interfaccia contiene due membri:

  - <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A>Restituisce un `boolean` valore che indica se il componente è inizializzato.

  - <xref:System.ComponentModel.ISupportInitializeNotification.Initialized>si verifica <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> quando viene chiamato il metodo.

- <xref:System.ComponentModel.INotifyPropertyChanged>interfaccia

  Una classe che implementa questa interfaccia è un tipo che genera un evento quando uno dei valori delle proprietà viene modificato. Questa interfaccia è progettata per sostituire il criterio di disporre di un evento di modifica per ogni proprietà di un controllo. Quando viene utilizzato in <xref:System.ComponentModel.BindingList%601>un oggetto, un oggetto business deve <xref:System.ComponentModel.INotifyPropertyChanged> implementare l'\`interfaccia e l'oggetto BindingList 1 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> convertirà <xref:System.ComponentModel.BindingList%601.ListChanged> gli eventi in <xref:System.ComponentModel.ListChangedType.ItemChanged>eventi di tipo.

  > [!NOTE]
  > Affinché la notifica delle modifiche venga eseguita in un'associazione tra un client associato e un'origine dati, il tipo di origine dati associato deve <xref:System.ComponentModel.INotifyPropertyChanged> implementare l'interfaccia (scelta consigliata) oppure è possibile fornire eventi *PropertyName* `Changed` per il tipo associato. Tuttavia, non è necessario eseguire entrambe le operazioni.

### <a name="interfaces-for-implementation-by-component-authors"></a>Interfacce per l'implementazione da parte degli autori del componente

Le interfacce seguenti sono progettate per l'uso da parte del motore di data-binding di Windows Forms:

- <xref:System.Windows.Forms.IBindableComponent>interfaccia

  Una classe che implementa questa interfaccia è un componente di non-controllo che supporta il data-binding. Questa classe restituisce le associazioni dati e il contesto di associazione del componente tramite le <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> proprietà <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> e di questa interfaccia.

  > [!NOTE]
  > Se il componente eredita da <xref:System.Windows.Forms.Control>, non è necessario implementare l' <xref:System.Windows.Forms.IBindableComponent> interfaccia.

- <xref:System.Windows.Forms.ICurrencyManagerProvider>interfaccia

  Una classe che implementa l' <xref:System.Windows.Forms.ICurrencyManagerProvider> interfaccia è un componente che fornisce un proprio <xref:System.Windows.Forms.CurrencyManager> oggetto per gestire le associazioni associate a questo particolare componente. L'accesso a custom <xref:System.Windows.Forms.CurrencyManager> viene fornito <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> dalla proprietà.

  > [!NOTE]
  > Una classe che eredita da <xref:System.Windows.Forms.Control> gestisce automaticamente le associazioni tramite la <xref:System.Windows.Forms.Control.BindingContext%2A> relativa proprietà, quindi i <xref:System.Windows.Forms.ICurrencyManagerProvider> casi in cui è necessario implementare sono piuttosto rari.

## <a name="see-also"></a>Vedere anche

- [Data binding e Windows Forms](data-binding-and-windows-forms.md)
- [Procedura: Creare un controllo con associazione semplice in un Windows Form](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Data binding in Windows Form](windows-forms-data-binding.md)

---
title: Interfacce correlate al data binding
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5278ccd34e556c33e4bc5c9f460573b399f265be
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="interfaces-related-to-data-binding"></a>Interfacce correlate al data binding
Con [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] è possibile creare molte strutture dati diverse per soddisfare le esigenze di associazione dell'applicazione e dei dati in uso. Si consiglia di creare classi che forniscono o usano dati in Windows Forms. Questi oggetti possono offrire diversi livelli di funzionalità e complessità, dal data binding, all'offerta di supporto in fase di progettazione, al controllo degli errori, alla notifica delle modifiche o anche al supporto per un annullamento strutturato delle modifiche apportate ai dati.  
  
## <a name="consumers-of-data-binding-interfaces"></a>Consumer delle interfacce di data binding  
 Nelle sezioni seguenti vengono descritti due gruppi di oggetti dell'interfaccia. Nel primo gruppo sono elencate le interfacce implementate nell'origine dati dagli autori dell'origine dati. Queste interfacce sono progettate per essere usate dai consumer dell'origine dati, che sono nella maggior parte dei casi dei controlli o componenti di Windows Forms. Nel secondo gruppo sono elencate le interfacce destinate ad essere usate dagli autori di componenti. Gli autori di componenti usano queste interfacce al momento della creazione di un componente che supporta l'uso del data binding da parte del motore del data-binding di Windows Forms. È possibile implementare queste interfacce all'interno delle classi associate al modulo per consentire il data-binding; ogni caso presenta una classe che implementa un'interfaccia che abilita l'interazione con i dati. Visual Studio rapido di applicazioni (RAD development) dati gli strumenti di progettazione già sfruttano questa funzionalità.  
  
### <a name="interfaces-for-implementation-by-data-source-authors"></a>Interfacce per l'implementazione da parte degli autori dell'origine dati  
 Le interfacce seguenti sono progettate per essere usate dai controlli di Windows Forms:  
  
-   <xref:System.Collections.IList> Interfaccia  
  
     Una classe che implementa il <xref:System.Collections.IList> interfaccia potrebbe essere un <xref:System.Array>, <xref:System.Collections.ArrayList>, o <xref:System.Collections.CollectionBase>. Questi sono indicizzati elenchi di elementi di tipo <xref:System.Object>. Questi elenchi devono contenere tipi omogenei, perché il primo elemento dell'indice determina il tipo. <xref:System.Collections.IList> saranno disponibili per il binding solo in fase di esecuzione.  
  
    > [!NOTE]
    >  Se si desidera creare un elenco di oggetti business per l'associazione con Windows Form, è consigliabile utilizzare il <xref:System.ComponentModel.BindingList%601>. Il <xref:System.ComponentModel.BindingList%601> è una classe estensibile che implementa le interfacce principali necessarie per l'associazione dati bidirezionale di Windows Form.  
  
-   <xref:System.ComponentModel.IBindingList> Interfaccia  
  
     Una classe che implementa il <xref:System.ComponentModel.IBindingList> interfaccia fornisce un livello di funzionalità di associazione dati decisamente superiore. Questa implementazione offre funzionalità di ordinamento di base e la notifica delle modifiche, sia quando gli elementi dell'elenco cambiano (ad esempio, il terzo elemento in un elenco di clienti include una modifica al campo indirizzo), sia quando l'elenco stesso cambia (ad esempio, il numero di elementi nell'elenco aumenta o diminuisce). La notifica della modifica è importante se si prevede di disporre di più controlli associati agli stessi dati e si desidera che le modifiche apportate in uno dei controlli si propaghi agli altri controlli associati.  
  
    > [!NOTE]
    >  Notifica delle modifiche è abilitata per il <xref:System.ComponentModel.IBindingList> interfaccia tramite la <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> proprietà che, quando `true`, genera un <xref:System.ComponentModel.IBindingList.ListChanged> evento, che indica l'elenco o un elemento nell'elenco modificato.  
  
     Viene descritto il tipo di modifica per il <xref:System.ComponentModel.ListChangedType> proprietà del <xref:System.ComponentModel.ListChangedEventArgs> parametro. Di conseguenza, ogni volta che viene aggiornato il modello di dati, anche tutte le visualizzazioni dipendenti, ad esempio gli altri controlli associati alla stessa origine dati, verranno aggiornate. Tuttavia, gli oggetti contenuti all'interno dell'elenco saranno necessario segnalare all'elenco quando vengono modificate in modo che l'elenco è possibile generare il <xref:System.ComponentModel.IBindingList.ListChanged> evento.  
  
    > [!NOTE]
    >  Il <xref:System.ComponentModel.BindingList%601> fornisce un'implementazione generica del <xref:System.ComponentModel.IBindingList> interfaccia.  
  
-   <xref:System.ComponentModel.IBindingListView> Interfaccia  
  
     Una classe che implementa il <xref:System.ComponentModel.IBindingListView> interfaccia fornisce tutte le funzionalità di un'implementazione di <xref:System.ComponentModel.IBindingList>, nonché come filtro e avanzate della funzionalità di ordinamento. Questa implementazione fornisce un filtro basato sulle stringhe, e un ordinamento a più colonne con coppie descrittore-direzione della proprietà.  
  
-   <xref:System.ComponentModel.IEditableObject> Interfaccia  
  
     Una classe che implementa il <xref:System.ComponentModel.IEditableObject> interfaccia consente a un oggetto controllare quando le modifiche apportate all'oggetto vengono rese permanenti. Questa implementazione mette a disposizione il <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, e <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> metodi, che consentono di eseguire il rollback delle modifiche apportate all'oggetto. Ecco una breve spiegazione del funzionamento del <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, e <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> metodi e come funzionano in combinazione con un'altra per abilitare un possibile eseguire il rollback delle modifiche apportate ai dati:  
  
    -   Il <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> metodo segnala l'inizio di una modifica di un oggetto. Oggetto che implementa questa interfaccia sarà necessario archiviare gli aggiornamenti dopo il <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> chiamata al metodo in modo che gli aggiornamenti possono essere ignorati se il <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> metodo viene chiamato. In Windows Form di associazione di dati, è possibile chiamare <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> più volte all'interno dell'ambito di una singola transazione di modifica (ad esempio, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>). Le implementazioni di <xref:System.ComponentModel.IEditableObject> deve consentire di controllare se <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> è già stato chiamato e ignorare le chiamate successive a <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>. Poiché questo metodo può essere chiamato più volte, è importante che le chiamate successive a esso siano distruttive; vale a dire successive <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> chiamate non è possibile eliminare definitivamente gli aggiornamenti che sono stati apportati o modificano i dati che è stati salvati il primo <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> chiamare.  
  
    -   Il <xref:System.ComponentModel.IEditableObject.EndEdit%2A> metodo inserisce le eventuali modifiche apportate dal <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> è stato chiamato nell'oggetto sottostante, se l'oggetto è attualmente in modalità di modifica.  
  
    -   Il <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> metodo ignora le eventuali modifiche apportate all'oggetto.  
  
     Per ulteriori informazioni su come <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, e <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> metodi di lavoro, vedere [salvare i dati nel database](/visualstudio/data-tools/save-data-back-to-the-database).  
  
     Questa nozione transazionale delle funzionalità dei dati viene utilizzata il <xref:System.Windows.Forms.DataGridView> controllo.  
  
-   <xref:System.ComponentModel.ICancelAddNew> Interfaccia  
  
     Una classe che implementa il <xref:System.ComponentModel.ICancelAddNew> interfaccia implementa in genere il <xref:System.ComponentModel.IBindingList> l'interfaccia e consente di eseguire il rollback di un'aggiunta apportata all'origine dati con il <xref:System.ComponentModel.IBindingList.AddNew%2A> metodo. Se l'origine dati implementa il <xref:System.ComponentModel.IBindingList> interfaccia, è necessario che anche implementare il <xref:System.ComponentModel.ICancelAddNew> interfaccia.  
  
-   <xref:System.ComponentModel.IDataErrorInfo> Interfaccia  
  
     Una classe che implementa il <xref:System.ComponentModel.IDataErrorInfo> interfaccia consente agli oggetti di fornire informazioni personalizzate sugli errori per i controlli con associazione:  
  
    -   Il <xref:System.ComponentModel.IDataErrorInfo.Error%2A> proprietà restituisce il testo messaggio di errore generici (ad esempio, "errore").  
  
    -   Il <xref:System.ComponentModel.IDataErrorInfo.Item%2A> proprietà restituisce una stringa con il messaggio di errore specifico dalla colonna (ad esempio, "il valore di `State` colonna non è valida").  
  
-   <xref:System.Collections.IEnumerable> Interfaccia  
  
     Una classe che implementa il <xref:System.Collections.IEnumerable> interfaccia viene in genere utilizzata dalla [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]. Supporto di Windows Form per questa interfaccia è disponibile solo tramite il <xref:System.Windows.Forms.BindingSource> componente.  
  
    > [!NOTE]
    >  Il <xref:System.Windows.Forms.BindingSource> componente copia tutti <xref:System.Collections.IEnumerable> gli elementi in un elenco separato per motivi di associazione.  
  
-   <xref:System.ComponentModel.ITypedList> Interfaccia  
  
     Una classe di raccolte che implementa il <xref:System.ComponentModel.ITypedList> interfaccia fornisce la possibilità di controllare l'ordine e il set di proprietà esposte per il controllo associato.  
  
    > [!NOTE]
    >  Quando si implementa il <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> (metodo) e <xref:System.ComponentModel.PropertyDescriptor> la matrice non è null, l'ultima voce della matrice sarà il descrittore di proprietà che descrivono la proprietà di elenco che è un altro elenco di elementi.  
  
-   <xref:System.ComponentModel.ICustomTypeDescriptor> Interfaccia  
  
     Una classe che implementa il <xref:System.ComponentModel.ICustomTypeDescriptor> interfaccia fornisce informazioni dinamiche su se stesso. Questa interfaccia è simile a <xref:System.ComponentModel.ITypedList> ma viene utilizzata per oggetti diversi dagli elenchi. Questa interfaccia viene utilizzata da <xref:System.Data.DataRowView> al progetto lo schema delle righe sottostanti. Un'implementazione semplice di <xref:System.ComponentModel.ICustomTypeDescriptor> viene fornito dalla <xref:System.ComponentModel.CustomTypeDescriptor> classe.  
  
    > [!NOTE]
    >  Per supportare l'associazione in fase di progettazione per i tipi che implementano <xref:System.ComponentModel.ICustomTypeDescriptor>, il tipo deve implementare anche <xref:System.ComponentModel.IComponent> ed esistere in un'istanza del form.  
  
-   <xref:System.ComponentModel.IListSource> Interfaccia  
  
     Una classe che implementa il <xref:System.ComponentModel.IListSource> interfaccia consente l'associazione elenco basata su oggetti non di elenco. Il <xref:System.ComponentModel.IListSource.GetList%2A> metodo <xref:System.ComponentModel.IListSource> viene utilizzata per restituire un elenco associabile da un oggetto che non eredita da <xref:System.Collections.IList>. <xref:System.ComponentModel.IListSource> viene utilizzato il <xref:System.Data.DataSet> classe.  
  
-   <xref:System.ComponentModel.IRaiseItemChangedEvents> Interfaccia  
  
     Una classe che implementa il <xref:System.ComponentModel.IRaiseItemChangedEvents> interfaccia è un elenco associabile che implementi anche il <xref:System.ComponentModel.IBindingList> interfaccia. Questa interfaccia viene utilizzata per indicare se il tipo genera <xref:System.ComponentModel.IBindingList.ListChanged> gli eventi di tipo <xref:System.ComponentModel.ListChangedType.ItemChanged> tramite il relativo <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A> proprietà.  
  
    > [!NOTE]
    >  È necessario implementare la <xref:System.ComponentModel.IRaiseItemChangedEvents> se l'origine dati fornisce la proprietà per la conversione degli eventi di elenco descritta in precedenza e interagisce con il <xref:System.Windows.Forms.BindingSource> componente. In caso contrario, il <xref:System.Windows.Forms.BindingSource> eseguirà anche la proprietà per la conversione degli eventi di elenco conseguente rallentamento delle prestazioni.  
  
-   <xref:System.ComponentModel.ISupportInitialize> Interfaccia  
  
     Un componente che implementa il <xref:System.ComponentModel.ISupportInitialize> interfaccia trae vantaggio dalle ottimizzazioni batch per l'impostazione delle proprietà e inizializzando le proprietà dipendenti dalla condivisione. Il <xref:System.ComponentModel.ISupportInitialize> contiene due metodi:  
  
    -   <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> segnala il che avvio di inizializzazione dell'oggetto.  
  
    -   <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> segnala che l'inizializzazione dell'oggetto terminando.  
  
-   <xref:System.ComponentModel.ISupportInitializeNotification> Interfaccia  
  
     Un componente che implementa il <xref:System.ComponentModel.ISupportInitializeNotification> interfaccia anche implementa il <xref:System.ComponentModel.ISupportInitialize> interfaccia. Questa interfaccia consente di segnalare ad altre <xref:System.ComponentModel.ISupportInitialize> componenti che l'inizializzazione è completa. Il <xref:System.ComponentModel.ISupportInitializeNotification> interfaccia contiene due membri:  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A> Restituisce un `boolean` valore che indica se il componente viene inizializzato.  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.Initialized> si verifica quando <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> viene chiamato.  
  
-   <xref:System.ComponentModel.INotifyPropertyChanged> Interfaccia  
  
     Una classe che implementa questa interfaccia è un tipo che genera un evento quando uno dei valori delle proprietà viene modificato. Questa interfaccia è progettata per sostituire il criterio di disporre di un evento di modifica per ogni proprietà di un controllo. Quando utilizzato in un <xref:System.ComponentModel.BindingList%601>, deve implementare un oggetto business di <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia e la classe BindingList\`1 convertirà <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> eventi da <xref:System.ComponentModel.BindingList%601.ListChanged> gli eventi di tipo <xref:System.ComponentModel.ListChangedType.ItemChanged>.  
  
    > [!NOTE]
    >  Modifica notifica in un'associazione tra un client associato e un tipo di dati di origine del tipo di origine dati associata deve implementare il <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia (preferito) oppure è possibile fornire *propertyName* `Changed` gli eventi per il tipo associato, ma è consigliabile non eseguire entrambe le operazioni.  
  
### <a name="interfaces-for-implementation-by-component-authors"></a>Interfacce per l'implementazione da parte degli autori del componente  
 Le interfacce seguenti sono progettate per l'uso da parte del motore di data-binding di Windows Forms:  
  
-   <xref:System.Windows.Forms.IBindableComponent> Interfaccia  
  
     Una classe che implementa questa interfaccia è un componente di non-controllo che supporta il data-binding. Questa classe restituisce le associazioni dati e il contesto di associazione del componente tramite il <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> e <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> le proprietà di questa interfaccia.  
  
    > [!NOTE]
    >  Se il componente eredita dalla <xref:System.Windows.Forms.Control>, non è necessario implementare la <xref:System.Windows.Forms.IBindableComponent> interfaccia.  
  
-   <xref:System.Windows.Forms.ICurrencyManagerProvider> Interfaccia  
  
     Una classe che implementa il <xref:System.Windows.Forms.ICurrencyManagerProvider> interfaccia è un componente che fornisce la propria <xref:System.Windows.Forms.CurrencyManager> per gestire i binding associati a questo componente. Accesso alla classe personalizzata <xref:System.Windows.Forms.CurrencyManager> viene fornito dal <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> proprietà.  
  
    > [!NOTE]
    >  Una classe che eredita da <xref:System.Windows.Forms.Control> gestisce automaticamente le associazioni mediante il relativo <xref:System.Windows.Forms.Control.BindingContext%2A> proprietà, i casi in cui è necessario implementare la <xref:System.Windows.Forms.ICurrencyManagerProvider> sono piuttosto rari.  
  
## <a name="see-also"></a>Vedere anche  
 [Data binding e Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Procedura: Creare un controllo con associazione semplice in un Windows Form](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)  
 [Data binding in Windows Form](../../../docs/framework/winforms/windows-forms-data-binding.md)

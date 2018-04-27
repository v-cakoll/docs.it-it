---
title: Linee guida per le raccolte
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5a1bb81a23a180c3f7738d811398a5a45abd9122
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="guidelines-for-collections"></a>Linee guida per le raccolte
Qualsiasi tipo progettato specificamente per la modifica di un gruppo di oggetti con alcune caratteristiche comuni può essere considerato come una raccolta. È quasi sempre appropriato per questi tipi implementare <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, pertanto in questa sezione vengono considerate solo i tipi che implementano una o entrambe le interfacce di raccolte.  
  
 **X non** utilizzare raccolte con tipizzazione nelle API pubbliche.  
  
 Il tipo di tutti i valori restituiti e parametri che rappresentano gli elementi della raccolta deve essere il tipo di elemento esatto, non di uno dei tipi di base (si applica solo ai membri pubblici della raccolta).  
  
 **X non** utilizzare <xref:System.Collections.ArrayList> o <xref:System.Collections.Generic.List%601> nelle API pubbliche.  
  
 Questi tipi sono strutture di dati progettate per essere usato nell'implementazione interna, non nelle API pubbliche. `List<T>` è ottimizzato per le prestazioni e potenza al costo di condizionamento l'API e flessibilità. Ad esempio, se si restituisce `List<T>`, non sempre sarà in grado di ricevere notifiche quando il codice client modifica la raccolta. Inoltre, `List<T>` espone molti membri, ad esempio <xref:System.Collections.Generic.List%601.BinarySearch%2A>, che non sono utili o applicabile in molti scenari. Due sezioni seguenti vengono descritti i tipi (astrazioni) progettati appositamente per l'utilizzo nelle API pubbliche.  
  
 **X non** utilizzare `Hashtable` o `Dictionary<TKey,TValue>` nelle API pubbliche.  
  
 Questi tipi sono strutture di dati progettate per essere usato nell'implementazione interna. Utilizzano le API pubbliche <xref:System.Collections.IDictionary>, `IDictionary <TKey, TValue>`, o un tipo personalizzato che implementa una o entrambe le interfacce.  
  
 **X non** utilizzare <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Collections.IEnumerator>, o qualsiasi altro tipo che implementa una di queste interfacce, ad eccezione di come il tipo restituito di un `GetEnumerator` metodo.  
  
 Restituzione di enumeratori da metodi diversi da tipi `GetEnumerator` non può essere utilizzato con il `foreach` istruzione.  
  
 **X non** implementare entrambi `IEnumerator<T>` e `IEnumerable<T>` sullo stesso tipo. Lo stesso vale per le interfacce non generiche `IEnumerator` e `IEnumerable`.  
  
## <a name="collection-parameters"></a>Parametri della raccolta  
 **✓ SI** utilizzare possibili tipo specializzato minimi come tipo di parametro. La maggior parte dei membri accetta raccolte come utilizzano i parametri di `IEnumerable<T>` interfaccia.  
  
 **X evitare** utilizzando <xref:System.Collections.Generic.ICollection%601> o <xref:System.Collections.ICollection> come parametro solo per accedere il `Count` proprietà.  
  
 Utilizzare invece `IEnumerable<T>` o `IEnumerable` e il controllo in modo dinamico se l'oggetto implementa `ICollection<T>` o `ICollection`.  
  
## <a name="collection-properties-and-return-values"></a>Le proprietà della raccolta e i valori restituiti  
 **X non** forniscono proprietà impostabili insieme.  
  
 Gli utenti possono sostituire il contenuto della raccolta deselezionando innanzitutto la raccolta e quindi aggiungere il nuovo contenuto. Se la sostituzione dell'intero insieme è uno scenario comune, si consiglia di fornire il `AddRange` metodo per la raccolta.  
  
 **✓ SI** utilizzare `Collection<T>` o una sottoclasse di `Collection<T>` per le raccolte di lettura/scrittura che rappresentano i valori restituiti o proprietà.  
  
 Se `Collection<T>` non soddisfa alcuni requisiti (ad esempio, la raccolta non è necessario implementare <xref:System.Collections.IList>), utilizzare una raccolta personalizzata implementando `IEnumerable<T>`, `ICollection<T>`, o <xref:System.Collections.Generic.IList%601>.  
  
 **✓ SI** utilizzare <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, una sottoclasse di `ReadOnlyCollection<T>`, o, in casi rari `IEnumerable<T>` per le raccolte di sola lettura che rappresenta i valori restituiti o proprietà.  
  
 In genere, è preferibile `ReadOnlyCollection<T>`. Se non vengono soddisfatti alcuni requisiti (ad esempio, la raccolta non è necessario implementare `IList`), utilizzare una raccolta personalizzata implementando `IEnumerable<T>`, `ICollection<T>`, o `IList<T>`. Se si implementa una raccolta di sola lettura personalizzata, implementare `ICollection<T>.IsReadOnly` per restituire `true`.  
  
 Nei casi in cui si è certi che l'unico scenario si desidera supportare mai iterazione forward-only, è possibile utilizzare semplicemente `IEnumerable<T>`.  
  
 **Provare a ✓** utilizzando le sottoclassi di raccolte generiche di base anziché utilizzare direttamente le raccolte.  
  
 In questo modo per un nome più significativo e per l'aggiunta di membri di supporto che non sono presenti i tipi di raccolta di base. Questo vale soprattutto per le API di alto livello.  
  
 **✓ Provare a** restituzione di una sottoclasse di `Collection<T>` o `ReadOnlyCollection<T>` da comunemente utilizzati i metodi e proprietà.  
  
 Ciò rende possibili per consentire di aggiungere metodi di supporto o modificare l'implementazione insieme in futuro.  
  
 **Provare a ✓** utilizzando una raccolta con chiave, se gli elementi archiviati nella raccolta dispongono di chiavi univoche (nomi, ID, ecc.). Raccolte con chiave sono raccolte che possono essere indicizzate da un numero intero sia una chiave e in genere vengono implementate tramite l'eredità da `KeyedCollection<TKey,TItem>`.  
  
 Raccolte con chiave in genere hanno footprint di dimensioni maggiori della memoria e non devono essere utilizzate se il sovraccarico della memoria supera i vantaggi di disporre di chiavi.  
  
 **X non** restituiranno valori null da una proprietà di raccolta o da metodi che restituiscono raccolte. Restituisce una raccolta vuota o una matrice vuota.  
  
 La regola generale è che devono essere null e vuote raccolte (0 elementi) o matrici considerati uguali.  
  
### <a name="snapshots-versus-live-collections"></a>Snapshot e le raccolte in tempo reale  
 Raccolte che rappresenta uno stato a un certo punto nel tempo vengono denominate le raccolte di snapshot. Ad esempio, una raccolta contenente le righe restituite da una query sul database sarebbe uno snapshot. Le raccolte che rappresentano sempre lo stato corrente vengono chiamate raccolte in tempo reale. Ad esempio, una raccolta di `ComboBox` elementi è una raccolta in tempo reale.  
  
 **X non** restituiscono raccolte di snapshot dalla proprietà. Le proprietà devono restituire raccolte in tempo reale.  
  
 Metodi get di proprietà devono essere operazioni molto semplici. Restituzione di uno snapshot richiede la creazione di una copia di una raccolta interna in un'operazione o (n).  
  
 **✓ SI** utilizzare attivo o una raccolta di snapshot `IEnumerable<T>` (o relativo sottotipo) per rappresentare le raccolte che sono volatili (ad esempio, che possono modificare senza modificare in modo esplicito la raccolta).  
  
 In generale, tutte le raccolte che rappresenta una risorsa condivisa (ad esempio, i file in una directory) sono volatili. Tali raccolte sono molto difficili o impossibili da implementare come raccolte in tempo reale, a meno che l'implementazione è semplicemente un enumeratore forward-only.  
  
## <a name="choosing-between-arrays-and-collections"></a>Scelta tra le matrici e raccolte  
 **✓ SI** Preferire matrici di raccolte.  
  
 Raccolte garantiscono maggiore controllo sul contenuto, possono evolversi nel tempo e sono più utilizzabili. Inoltre, l'utilizzo di matrici per gli scenari di sola lettura è sconsigliato perché il costo di clonando la matrice è troppo elevato. Studi hanno dimostrato che alcuni sviluppatori preferisce utilizzando le API basate sulle raccolte.  
  
 Tuttavia, se si siano sviluppando l'API di basso livello, potrebbe essere preferibile utilizzare matrici per scenari di lettura / scrittura. Le matrici presentano un footprint di memoria più piccolo, che consente di ridurre il working set, e l'accesso agli elementi nella matrice è più veloce perché è ottimizzato dal runtime.  
  
 **Provare a ✓** utilizzo delle matrici nelle API di basso livello per ridurre il consumo di memoria e ottimizzare le prestazioni.  
  
 **✓ SI** utilizzare matrici di byte anziché le raccolte di byte.  
  
 **X non** utilizzare matrici per le proprietà se la proprietà necessario tornare a una nuova matrice (ad esempio, una copia di una matrice interna) ogni volta che viene chiamato il metodo Get della proprietà.  
  
## <a name="implementing-custom-collections"></a>Implementazione di raccolte personalizzate  
 **Provare a ✓** che eredita da `Collection<T>`, `ReadOnlyCollection<T>`, o `KeyedCollection<TKey,TItem>` durante la progettazione di nuove raccolte.  
  
 **✓ SI** implementare `IEnumerable<T>` durante la progettazione di nuove raccolte. Si consiglia di implementare `ICollection<T>` o addirittura `IList<T>` dove risulta più appropriato.  
  
 Quando si implementa questo tipo di raccolta personalizzato, seguono il modello di API stabilito da `Collection<T>` e `ReadOnlyCollection<T>` fedelmente possibile. Vale a dire, implementare in modo esplicito gli stessi membri, denominare i parametri come nome di questi due raccolte loro e così via.  
  
 **Provare a ✓** implementazione di interfacce di raccolta non generica (`IList` e `ICollection`) se la raccolta verrà spesso passata alle API utilizza queste interfacce come input.  
  
 **X evitare** implementare interfacce di raccolta su tipi con API complesse non correlate al concetto di una raccolta.  
  
 **X non** ereditare le raccolte di base non generiche, ad esempio `CollectionBase`. Utilizzare `Collection<T>`, `ReadOnlyCollection<T>`, e `KeyedCollection<TKey,TItem>` invece.  
  
### <a name="naming-custom-collections"></a>Denominazione di raccolte personalizzate  
 Raccolte (tipi che implementano `IEnumerable`) vengono creati principalmente per due ragioni: (1) per creare una nuova struttura di dati con le operazioni di struttura specifico e spesso le caratteristiche di prestazioni diverse rispetto alle strutture di dati esistente (ad esempio, <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.LinkedList%601>, <xref:System.Collections.Generic.Stack%601>) e (2) per creare un insieme specifico per il mantenimento di un set specifico di elementi (ad esempio, <xref:System.Collections.Specialized.StringCollection>). Strutture di dati vengono spesso usate nell'implementazione interna di librerie e applicazioni. Raccolte specializzate sono principalmente a essere esposti nelle API (come proprietà e tipi di parametro).  
  
 **✓ SI** utilizzare il suffisso "Dictionary" nei nomi di astrazioni implementazione `IDictionary` o `IDictionary<TKey,TValue>`.  
  
 **✓ SI** utilizzare il suffisso "Collection" nei nomi di tipi che implementano `IEnumerable` (o uno qualsiasi dei relativi discendenti) e che rappresenta un elenco di elementi.  
  
 **✓ SI** utilizzare il nome della struttura di dati appropriato per le strutture di dati personalizzati.  
  
 **X evitare** usare eventuali suffissi implicando particolare implementazione, ad esempio "LinkedList" o "Tabella hash," nei nomi di astrazioni di raccolta.  
  
 **Provare a ✓** facendolo precedere i nomi di raccolta con il nome del tipo di elemento. Ad esempio, un insieme di archiviazione di elementi di tipo `Address` (implementazione `IEnumerable<Address>`) deve essere denominato `AddressCollection`. Se il tipo di elemento è un'interfaccia, "I" prefisso dell'elemento di tipo può essere omesso. Di conseguenza, una raccolta di <xref:System.IDisposable> elementi possono essere chiamati `DisposableCollection`.  
  
 **Provare a ✓** utilizzando il prefisso "ReadOnly" nei nomi delle raccolte di sola lettura, se una raccolta modificabile corrispondente potrebbe essere aggiunto o esiste già nel framework.  
  
 Ad esempio, una raccolta di sola lettura di stringhe deve essere chiamata `ReadOnlyStringCollection`.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)

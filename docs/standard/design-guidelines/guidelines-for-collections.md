---
title: Linee guida per le raccolte
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3571ebb2fdd2bcdfd8be1f0087d096e01f18790a
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45674091"
---
# <a name="guidelines-for-collections"></a>Linee guida per le raccolte
Qualsiasi tipo progettata specificamente per modificare un gruppo di oggetti con alcune caratteristiche comuni può essere considerato come una raccolta. È quasi sempre appropriato per questi tipi implementare <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, pertanto in questa sezione è considerare solo i tipi che implementano una o entrambe queste interfacce a essere raccolte.  
  
 **X DO NOT** utilizzare raccolte con tipizzazione nelle API pubbliche.  
  
 Il tipo di tutti i valori restituiti e parametri che rappresentano gli elementi della raccolta deve essere il tipo di elemento esatto, non uno qualsiasi dei tipi di base (si applica solo ai membri pubblici della raccolta).  
  
 **X DO NOT** utilizzare <xref:System.Collections.ArrayList> o <xref:System.Collections.Generic.List%601> nelle API pubbliche.  
  
 Questi tipi sono strutture di dati progettate per essere usato nell'implementazione interna, non nelle API pubbliche. `List<T>` è ottimizzato per le prestazioni e l'alimentazione al costo condizionamento l'API e flessibilità. Ad esempio, se si torna `List<T>`, non sempre sarà in grado di ricevere notifiche quando il codice client modifica la raccolta. È inoltre `List<T>` espone molti membri, ad esempio <xref:System.Collections.Generic.List%601.BinarySearch%2A>, che non sono utili o applicabili in molti scenari. Le due sezioni seguenti vengono descritti i tipi (astrazioni) progettati appositamente per l'utilizzo nelle API pubbliche.  
  
 **X DO NOT** utilizzare `Hashtable` o `Dictionary<TKey,TValue>` nelle API pubbliche.  
  
 Questi tipi sono strutture di dati progettate per essere usato nell'implementazione interna. Devono usare le API pubbliche <xref:System.Collections.IDictionary>, `IDictionary <TKey, TValue>`, o un tipo personalizzato che implementa una o entrambe le interfacce.  
  
 **X DO NOT** utilizzare <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Collections.IEnumerator>, o qualsiasi altro tipo che implementa una di queste interfacce, ad eccezione di come il tipo restituito di un `GetEnumerator` metodo.  
  
 Tipi di restituzione diversi da enumeratori dai metodi `GetEnumerator` non può essere usato con il `foreach` istruzione.  
  
 **X DO NOT** implementare entrambi `IEnumerator<T>` e `IEnumerable<T>` sullo stesso tipo. Lo stesso vale per le interfacce non generiche `IEnumerator` e `IEnumerable`.  
  
## <a name="collection-parameters"></a>Parametri della raccolta  
 **✓ DO** utilizzare possibili tipo specializzato minimi come tipo di parametro. La maggior parte dei membri accettando le raccolte come usano i parametri di `IEnumerable<T>` interfaccia.  
  
 **X AVOID** utilizzando <xref:System.Collections.Generic.ICollection%601> o <xref:System.Collections.ICollection> come parametro solo per accedere il `Count` proprietà.  
  
 In alternativa, è consigliabile usare `IEnumerable<T>` oppure `IEnumerable` e il controllo in modo dinamico se l'oggetto implementa `ICollection<T>` o `ICollection`.  
  
## <a name="collection-properties-and-return-values"></a>Le proprietà della raccolta e i valori restituiti  
 **X DO NOT** forniscono proprietà impostabili insieme.  
  
 Gli utenti possono sostituire il contenuto della raccolta da cancellare prima di tutto la raccolta e quindi aggiungere i nuovi contenuti. Se l'intera raccolta la sostituzione è uno scenario comune, si consiglia di fornire il `AddRange` metodo per la raccolta.  
  
 **✓ DO** utilizzare `Collection<T>` o una sottoclasse di `Collection<T>` per le raccolte di lettura/scrittura che rappresentano i valori restituiti o proprietà.  
  
 Se `Collection<T>` non soddisfa un requisito (ad esempio, la raccolta non è necessario implementare <xref:System.Collections.IList>), usare una raccolta personalizzata implementando `IEnumerable<T>`, `ICollection<T>`, o <xref:System.Collections.Generic.IList%601>.  
  
 **✓ DO** utilizzare <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, una sottoclasse di `ReadOnlyCollection<T>`, o, in casi rari `IEnumerable<T>` per le raccolte di sola lettura che rappresenta i valori restituiti o proprietà.  
  
 In generale, preferisce `ReadOnlyCollection<T>`. Se non vengono soddisfatti alcuni requisiti (ad esempio, la raccolta non è necessario implementare `IList`), usare una raccolta personalizzata implementando `IEnumerable<T>`, `ICollection<T>`, o `IList<T>`. Se si implementa una raccolta di sola lettura personalizzata, implementare `ICollection<T>.IsReadOnly` da restituire `true`.  
  
 Nei casi in cui si è certi che l'unico scenario si desidera supportare mai è forward-only iterazione, è possibile usare semplicemente `IEnumerable<T>`.  
  
 **✓ CONSIDER** utilizzando le sottoclassi di raccolte generiche di base anziché utilizzare direttamente le raccolte.  
  
 In questo modo per un nome migliore e per l'aggiunta di membri di helper che non sono presenti sui tipi di raccolta di base. Questo vale soprattutto per le API di alto livello.  
  
 **✓ CONSIDER** restituzione di una sottoclasse di `Collection<T>` o `ReadOnlyCollection<T>` da comunemente utilizzati i metodi e proprietà.  
  
 In questo modo sarà possibile per consentire di aggiungere metodi helper o modificare l'implementazione della raccolta in futuro.  
  
 **✓ CONSIDER** utilizzando una raccolta con chiave, se gli elementi archiviati nella raccolta dispongono di chiavi univoche (nomi, ID, ecc.). Le raccolte con chiave sono le raccolte che possono essere indicizzate da integer e una chiave e vengono in genere implementate ereditando da `KeyedCollection<TKey,TItem>`.  
  
 Raccolte con chiave in genere hanno footprint di memoria più grandi e non devono essere usate se l'overhead della memoria supera i vantaggi di avere le chiavi.  
  
 **X DO NOT** restituiranno valori null da una proprietà di raccolta o da metodi che restituiscono raccolte. Restituisce una raccolta vuota o una matrice vuota.  
  
 La regola generale prevede che le raccolte (elemento 0) null e vuote o le matrici devono essere considerati uguali.  
  
### <a name="snapshots-versus-live-collections"></a>Snapshot rispetto alle raccolte in tempo reale  
 Le raccolte che rappresenta uno stato a un certo punto nel tempo sono chiamate raccolte, dello snapshot. Ad esempio, una raccolta contenente le righe restituite da una query sul database sarebbe uno snapshot. Le raccolte che rappresentano sempre lo stato corrente vengono chiamate raccolte, in tempo reale. Ad esempio, una raccolta di `ComboBox` elementi è una raccolta in tempo reale.  
  
 **X DO NOT** restituiscono raccolte di snapshot dalla proprietà. Le proprietà devono restituire raccolte in tempo reale.  
  
 Getter proprietà devono essere operazioni molto semplici. Restituzione di uno snapshot, è necessario creare una copia di una raccolta interna in un'operazione o (n).  
  
 **✓ DO** utilizzare attivo o una raccolta di snapshot `IEnumerable<T>` (o relativo sottotipo) per rappresentare le raccolte che sono volatili (ad esempio, che possono modificare senza modificare in modo esplicito la raccolta).  
  
 In generale, tutte le raccolte che rappresenta una risorsa condivisa (ad esempio, i file in una directory) sono volatili. Tali raccolte sono molto difficili o impossibili da implementare le raccolte in tempo reale, a meno che l'implementazione è semplicemente un enumeratore di tipo forward-only.  
  
## <a name="choosing-between-arrays-and-collections"></a>Scelta tra le matrici e raccolte  
 **✓ DO** Preferire matrici di raccolte.  
  
 Le raccolte garantiscono maggiore controllo sul contenuto, possono evolversi nel tempo e sono più utilizzabili. Inoltre, l'uso delle matrici per gli scenari di sola lettura è sconsigliato perché il costo di clonazione della matrice è troppo elevato. Studi di usabilità hanno dimostrato che alcuni sviluppatori sentono più a proprio agio usando le API basate su raccolta.  
  
 Tuttavia, se si siano sviluppando l'API di basso livello, potrebbe essere preferibile utilizzare matrici per gli scenari di lettura / scrittura. Le matrici hanno un footprint di memoria più piccolo, che consente di ridurre il working set, e l'accesso agli elementi nella matrice è più veloce perché è ottimizzato dal runtime.  
  
 **✓ CONSIDER** utilizzo delle matrici nelle API di basso livello per ridurre il consumo di memoria e ottimizzare le prestazioni.  
  
 **✓ DO** utilizzare matrici di byte anziché le raccolte di byte.  
  
 **X DO NOT** utilizzare matrici per le proprietà se la proprietà necessario tornare a una nuova matrice (ad esempio, una copia di una matrice interna) ogni volta che viene chiamato il metodo Get della proprietà.  
  
## <a name="implementing-custom-collections"></a>Implementazione di raccolte personalizzate  
 **✓ CONSIDER** che eredita da `Collection<T>`, `ReadOnlyCollection<T>`, o `KeyedCollection<TKey,TItem>` durante la progettazione di nuove raccolte.  
  
 **✓ DO** implementare `IEnumerable<T>` durante la progettazione di nuove raccolte. È consigliabile implementare `ICollection<T>` o addirittura `IList<T>` dove risulta più appropriato.  
  
 Quando si implementa questo tipo raccolta personalizzata, seguire il modello API stabilito dallo `Collection<T>` e `ReadOnlyCollection<T>` fedelmente possibile. Vale a dire, implementare gli stessi membri in modo esplicito, denominare i parametri come assegnare un nome questi due raccolte stesse e così via.  
  
 **✓ CONSIDER** implementazione di interfacce di raccolta non generica (`IList` e `ICollection`) se la raccolta verrà spesso passata alle API utilizza queste interfacce come input.  
  
 **X AVOID** implementare interfacce di raccolta su tipi con API complesse non correlate al concetto di una raccolta.  
  
 **X DO NOT** ereditare le raccolte di base non generiche, ad esempio `CollectionBase`. Uso `Collection<T>`, `ReadOnlyCollection<T>`, e `KeyedCollection<TKey,TItem>` invece.  
  
### <a name="naming-custom-collections"></a>Denominazione di raccolte personalizzate  
 Raccolte (i tipi che implementano `IEnumerable`) vengono creati principalmente per due motivi: (1) per creare una nuova struttura di dati con le operazioni specifiche della struttura e spesso diverse caratteristiche di prestazioni rispetto alle strutture di dati esistente (ad esempio, <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.LinkedList%601>, <xref:System.Collections.Generic.Stack%601>) e (2) per creare una raccolta specializzata per mantenere un set specifico di elementi (ad esempio, <xref:System.Collections.Specialized.StringCollection>). Strutture di dati vengono spesso usate nell'implementazione interna di applicazioni e librerie. Raccolte specializzate sono principalmente a essere esposti nelle API (come i tipi di proprietà e parametri).  
  
 **✓ DO** utilizzare il suffisso "Dictionary" nei nomi di astrazioni implementazione `IDictionary` o `IDictionary<TKey,TValue>`.  
  
 **✓ DO** utilizzare il suffisso "Collection" nei nomi di tipi che implementano `IEnumerable` (o uno qualsiasi dei relativi discendenti) e che rappresenta un elenco di elementi.  
  
 **✓ DO** utilizzare il nome della struttura di dati appropriato per le strutture di dati personalizzati.  
  
 **X AVOID** usare eventuali suffissi implicando particolare implementazione, ad esempio "LinkedList" o "Tabella hash," nei nomi di astrazioni di raccolta.  
  
 **✓ CONSIDER** facendolo precedere i nomi di raccolta con il nome del tipo di elemento. Ad esempio, una raccolta di archiviare gli elementi di tipo `Address` (implementazione `IEnumerable<Address>`) devono essere denominati `AddressCollection`. Se il tipo di elemento è un'interfaccia, la "I" come prefisso dell'elemento del tipo può essere omesso. Di conseguenza, una raccolta di <xref:System.IDisposable> gli elementi possono essere chiamati `DisposableCollection`.  
  
 **✓ CONSIDER** utilizzando il prefisso "ReadOnly" nei nomi delle raccolte di sola lettura, se una raccolta modificabile corrispondente potrebbe essere aggiunto o esiste già nel framework.  
  
 Ad esempio, una raccolta di sola lettura di stringhe deve essere chiamata `ReadOnlyStringCollection`.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)

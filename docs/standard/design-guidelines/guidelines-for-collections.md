---
title: Linee guida per le raccolte
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
ms.openlocfilehash: 50497de6569b448ab036af8a1fbf76a47565e2bb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741871"
---
# <a name="guidelines-for-collections"></a>Linee guida per le raccolte
Qualsiasi tipo progettato specificamente per modificare un gruppo di oggetti con alcune caratteristiche comuni può essere considerato come una raccolta. È quasi sempre opportuno che tali tipi implementino <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, quindi in questa sezione consideriamo solo i tipi che implementano una o entrambe le interfacce come raccolte.

 ❌ non usano raccolte con tipizzazione debole nelle API pubbliche.

 Il tipo di tutti i valori restituiti e i parametri che rappresentano gli elementi della raccolta deve essere il tipo di elemento esatto, non uno dei tipi di base (si applica solo ai membri pubblici della raccolta).

 ❌ non usare <xref:System.Collections.ArrayList> o <xref:System.Collections.Generic.List%601> nelle API pubbliche.

 Questi tipi sono strutture di dati progettate per essere usate nell'implementazione interna, non nelle API pubbliche. `List<T>` è ottimizzato per le prestazioni e la potenza al costo della pulizia delle API e della flessibilità. Se, ad esempio, si restituisce `List<T>`, non sarà mai possibile ricevere notifiche quando il codice client modifica la raccolta. Inoltre, `List<T>` espone molti membri, ad esempio <xref:System.Collections.Generic.List%601.BinarySearch%2A>, che non sono utili o applicabili in molti scenari. Nelle due sezioni seguenti vengono descritti i tipi (astrazioni) progettati in modo specifico per l'utilizzo in API pubbliche.

 ❌ non usare `Hashtable` o `Dictionary<TKey,TValue>` nelle API pubbliche.

 Questi tipi sono strutture di dati progettate per essere usate nell'implementazione interna. Le API pubbliche devono usare <xref:System.Collections.IDictionary>, `IDictionary <TKey, TValue>`o un tipo personalizzato che implementa una o entrambe le interfacce.

 ❌ non utilizzano <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Collections.IEnumerator>o altri tipi che implementano una di queste interfacce, ad eccezione del tipo restituito di un metodo `GetEnumerator`.

 I tipi che restituiscono enumeratori da metodi diversi da `GetEnumerator` non possono essere utilizzati con l'istruzione `foreach`.

 ❌ non implementano sia `IEnumerator<T>` che `IEnumerable<T>` nello stesso tipo. Lo stesso vale per le interfacce non generiche `IEnumerator` e `IEnumerable`.

## <a name="collection-parameters"></a>Parametri della raccolta
 ✔️ utilizzare il tipo meno specializzato possibile come tipo di parametro. La maggior parte dei membri che accettano raccolte come parametri usa l'interfaccia `IEnumerable<T>`.

 ❌ evitare di usare <xref:System.Collections.Generic.ICollection%601> o <xref:System.Collections.ICollection> come parametro solo per accedere alla proprietà `Count`.

 È invece consigliabile utilizzare `IEnumerable<T>` o `IEnumerable` e verificare dinamicamente se l'oggetto implementa `ICollection<T>` o `ICollection`.

## <a name="collection-properties-and-return-values"></a>Proprietà della raccolta e valori restituiti
 ❌ non forniscono proprietà di raccolta impostabili.

 Gli utenti possono sostituire il contenuto della raccolta deselezionando prima di tutto la raccolta e quindi aggiungendo il nuovo contenuto. Se la sostituzione dell'intera raccolta è uno scenario comune, è consigliabile fornire il metodo `AddRange` sulla raccolta.

 ✔️ utilizzare `Collection<T>` o una sottoclasse di `Collection<T>` per le proprietà o i valori restituiti che rappresentano le raccolte di lettura/scrittura.

 Se `Collection<T>` non soddisfa alcuni requisiti (ad esempio, la raccolta non deve implementare <xref:System.Collections.IList>), usare una raccolta personalizzata implementando `IEnumerable<T>`, `ICollection<T>`o <xref:System.Collections.Generic.IList%601>.

 ✔️ utilizzare <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, una sottoclasse di `ReadOnlyCollection<T>`o in rari casi `IEnumerable<T>` per le proprietà o valori restituiti che rappresentano raccolte di sola lettura.

 In generale, preferisce `ReadOnlyCollection<T>`. Se non soddisfa alcuni requisiti (ad esempio, la raccolta non deve implementare `IList`), usare una raccolta personalizzata implementando `IEnumerable<T>`, `ICollection<T>`o `IList<T>`. Se si implementa una raccolta di sola lettura personalizzata, implementare `ICollection<T>.IsReadOnly` per restituire `true`.

 Nei casi in cui si è certi che l'unico scenario che si intende supportare è l'iterazione di sola trasmissione, è possibile utilizzare semplicemente `IEnumerable<T>`.

 ✔️ CONSIGLIABILE utilizzare le sottoclassi di raccolte di base generiche anziché utilizzare direttamente le raccolte.

 Questo consente un nome migliore e per l'aggiunta di membri helper che non sono presenti nei tipi di raccolta di base. Questa operazione è particolarmente applicabile alle API di alto livello.

 ✔️ valutare la possibilità di restituire una sottoclasse di `Collection<T>` o `ReadOnlyCollection<T>` da metodi e proprietà usati di frequente.

 In questo modo sarà possibile aggiungere metodi helper o modificare l'implementazione della raccolta in futuro.

 ✔️ CONSIGLIABILE usare una raccolta con chiave se gli elementi archiviati nella raccolta hanno chiavi univoche (nomi, ID e così via). Le raccolte con chiave sono raccolte che possono essere indicizzate sia da un numero intero che da una chiave e vengono in genere implementate ereditando da `KeyedCollection<TKey,TItem>`.

 Le raccolte con chiave hanno in genere footprint di memoria maggiori e non devono essere usate se l'overhead della memoria supera i vantaggi derivanti dall'uso delle chiavi.

 ❌ non restituiscono valori null dalle proprietà della raccolta o dai metodi che restituiscono raccolte. Restituisce invece una raccolta vuota o una matrice vuota.

 La regola generale prevede che le raccolte o le matrici null e vuote (0 item) debbano essere considerate uguali.

### <a name="snapshots-versus-live-collections"></a>Snapshot e raccolte Live
 Le raccolte che rappresentano uno stato in un determinato momento sono denominate raccolte snapshot. Una raccolta che contiene le righe restituite da una query di database, ad esempio, è uno snapshot. Le raccolte che rappresentano sempre lo stato corrente sono denominate raccolte Live. Ad esempio, una raccolta di elementi di `ComboBox` è una raccolta in tempo reale.

 ❌ non restituiscono raccolte snapshot dalle proprietà. Le proprietà devono restituire raccolte Live.

 I getter della proprietà devono essere operazioni molto leggere. Per restituire uno snapshot è necessario creare una copia di una raccolta interna in un'operazione O (n).

 ✔️ utilizzare una raccolta snapshot o un `IEnumerable<T>` attivo (o il relativo sottotipo) per rappresentare le raccolte volatili (ovvero, che possono essere modificate senza modificare esplicitamente la raccolta).

 In generale, tutte le raccolte che rappresentano una risorsa condivisa, ad esempio i file in una directory, sono volatili. Tali raccolte sono molto difficili o impossibili da implementare come raccolte Live, a meno che l'implementazione non sia semplicemente un enumeratore di tipo "solo".

## <a name="choosing-between-arrays-and-collections"></a>Scelta tra matrici e raccolte
 ✔️ preferiscono le raccolte sulle matrici.

 Le raccolte forniscono un maggiore controllo sul contenuto, possono evolversi nel tempo e sono più utilizzabili. Inoltre, l'utilizzo di matrici per scenari di sola lettura è sconsigliato perché il costo della clonazione della matrice è proibitivo. Gli studi di usabilità hanno dimostrato che alcuni sviluppatori si sentono più comodi usando le API basate su raccolte.

 Tuttavia, se si sviluppano API di basso livello, potrebbe essere preferibile utilizzare matrici per gli scenari di lettura e scrittura. Le matrici hanno un footprint di memoria inferiore, che consente di ridurre la working set e l'accesso agli elementi in una matrice è più veloce perché è ottimizzato dal runtime.

 ✔️ CONSIGLIABILE usare le matrici nelle API di basso livello per ridurre al minimo l'utilizzo della memoria e ottimizzare le prestazioni.

 ✔️ utilizzare matrici di byte anziché raccolte di byte.

 ❌ non utilizzano matrici per le proprietà se la proprietà deve restituire una nuova matrice, ad esempio una copia di una matrice interna, ogni volta che viene chiamato il metodo Get della proprietà.

## <a name="implementing-custom-collections"></a>Implementazione di raccolte personalizzate
 ✔️ considerare la possibilità di ereditare da `Collection<T>`, `ReadOnlyCollection<T>`o `KeyedCollection<TKey,TItem>` quando si progettano nuove raccolte.

 ✔️ implementano `IEnumerable<T>` quando si progettano nuove raccolte. Prendere in considerazione l'implementazione di `ICollection<T>` o persino `IList<T>` in cui è sensata.

 Quando si implementa tale raccolta personalizzata, seguire il modello di API stabilito da `Collection<T>` e `ReadOnlyCollection<T>` il più vicino possibile. Ovvero implementare gli stessi membri in modo esplicito, denominare i parametri come questi due insiemi denominarli e così via.

 ✔️ VALUTARE l'implementazione di interfacce di raccolta non generiche (`IList` e `ICollection`) se la raccolta viene spesso passata alle API che accettano queste interfacce come input.

 ❌ evitare di implementare interfacce di raccolta su tipi con API complesse non correlate al concetto di raccolta.

 ❌ non ereditano da raccolte di base non generiche, ad esempio `CollectionBase`. Usare invece `Collection<T>`, `ReadOnlyCollection<T>`e `KeyedCollection<TKey,TItem>`.

### <a name="naming-custom-collections"></a>Denominazione di raccolte personalizzate
 Le raccolte (tipi che implementano `IEnumerable`) vengono create principalmente per due motivi: (1) per creare una nuova struttura di dati con operazioni specifiche della struttura e spesso caratteristiche di prestazioni diverse rispetto alle strutture di dati esistenti (ad esempio, <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.LinkedList%601>, <xref:System.Collections.Generic.Stack%601>) e (2) per creare una raccolta specializzata per la conservazione di un set specifico di elementi (ad esempio, <xref:System.Collections.Specialized.StringCollection>). Le strutture di dati vengono spesso usate nell'implementazione interna di applicazioni e librerie. Le raccolte specializzate sono esposte principalmente nelle API (come tipi di proprietà e parametri).

 ✔️ utilizzare il suffisso "Dictionary" nei nomi delle astrazioni che implementano `IDictionary` o `IDictionary<TKey,TValue>`.

 ✔️ usano il suffisso "Collection" nei nomi dei tipi che implementano `IEnumerable` (o uno qualsiasi dei relativi discendenti) e che rappresentano un elenco di elementi.

 ✔️ utilizzare il nome della struttura di dati appropriato per le strutture di dati personalizzate.

 ❌ evitare di utilizzare suffissi che implicano un'implementazione particolare, ad esempio "LinkedList" o "Hashtable", nei nomi delle astrazioni della raccolta.

 ✔️ CONSIDERARE il prefisso dei nomi di raccolta con il nome del tipo di elemento. Ad esempio, una raccolta che archivia elementi di tipo `Address` (che implementano `IEnumerable<Address>`) deve essere denominata `AddressCollection`. Se il tipo di elemento è un'interfaccia, è possibile omettere il prefisso "I" del tipo di elemento. È quindi possibile chiamare una raccolta di elementi <xref:System.IDisposable> `DisposableCollection`.

 ✔️ CONSIGLIABILE utilizzare il prefisso "ReadOnly" nei nomi delle raccolte di sola lettura se è possibile che una raccolta scrivibile corrispondente venga aggiunta o esista già nel Framework.

 Una raccolta di stringhe di sola lettura, ad esempio, deve essere chiamata `ReadOnlyStringCollection`.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)

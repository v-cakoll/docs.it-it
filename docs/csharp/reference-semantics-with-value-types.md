---
title: Semantica di riferimento con i tipi valore
description: Informazioni sulle funzionalità del linguaggio che riducono al minimo la copia delle strutture in modo sicuro
ms.date: 11/10/2017
ms.custom: mvc
ms.openlocfilehash: f241219994d7a03192a4aea69b912bf1ac5ed29c
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930649"
---
# <a name="reference-semantics-with-value-types"></a>Semantica di riferimento con i tipi valore

Un vantaggio dell'uso dei tipi valore è che spesso evitano le allocazioni heap.
Lo svantaggio è invece che vengono copiati in base al valore. Risulta quindi più difficile ottimizzare gli algoritmi che operano su grandi quantità di dati. Le nuove funzionalità del linguaggio C# 7.2 forniscono meccanismi che abilitano la semantica pass-by-reference con i tipi valore. Usare queste funzionalità con criterio, per ridurre al minimo sia le allocazioni che le operazioni di copia. Questo articolo esamina le nuove funzionalità.

Gran parte del codice di esempio in questo articolo illustra le funzionalità aggiunte in C# 7.2. Per usare tali funzionalità, è necessario configurare il progetto per l'uso di C# 7.2 o versione successiva. Per altre informazioni sull'impostazione della versione in lingua, vedere [Configure the language version](language-reference/configure-language-version.md) (Configurare la versione in lingua).

## <a name="passing-arguments-by-readonly-reference"></a>Passaggio di argomenti per riferimento di sola lettura

In C# 7.2 è stata aggiunta la parola chiave `in` a complemento delle parole chiave `ref` e `out` esistenti per passare gli argomenti per riferimento. La parola chiave `in` specifica il passaggio dell'argomento per riferimento, ma il metodo chiamato non modifica il valore. 

Questa aggiunta fornisce un vocabolario completo per esprimere le finalità di progettazione. I tipi valore vengono copiati quando vengono passati a un metodo chiamato se nella firma del metodo non si specifica alcuno dei modificatori seguenti. Ognuno di questi modificatori specifica che un tipo valore viene passato per riferimento, evitando la copia. Ogni modificatore esprime una finalità diversa:

- `out`: questo metodo imposta il valore dell'argomento usato come parametro.
- `ref`: questo metodo può impostare il valore dell'argomento usato come parametro.
- `in`: questo metodo non modifica il valore dell'argomento usato come parametro.

Aggiungere il modificatore `in` per passare un argomento per riferimento e dichiarare che la finalità di passare argomenti per riferimento, per evitare operazioni di copia non necessarie, non quella di modificare l'oggetto usato come argomento. Il codice seguente illustra un esempio di metodo che calcola la distanza tra due punti nello spazio 3D. 

[!code-csharp[InArgument](../../samples/csharp/reference-semantics/Program.cs#InArgument "Specifying an In argument")]

Gli argomenti sono due strutture, contenenti ognuna tre valori double. Un valore double è pari a 8 byte, quindi ogni argomento è pari a 24 byte. Specificando il modificatore `in`, si passa un riferimento a 4 byte o 8 byte a tali argomenti, a seconda dell'architettura del computer. La differenza a livello di dimensioni è piccola, ma può aumentare rapidamente quando l'applicazione chiama questo metodo in un ciclo ridotto usando più valori diversi.
 
Il modificatore `in` integra `out` e `ref` anche in altri modi. Non è possibile creare overload di un metodo che si distinguono solo per la presenza di `in`, `out` o `ref`. Queste nuove regole estendono lo stesso comportamento da sempre definito per i parametri `out` e `ref`.

Il modificatore `in` può essere applicato a tutti i membri che accettano parametri: metodi, delegati, espressioni lambda, funzioni locali, indicizzatori, operatori.

Diversamente dagli argomenti `ref` e `out`, è possibile usare valori letterali o costanti per l'argomento in un parametro `in`. Inoltre, diversamente da un parametro `ref` o `out`, non è necessario applicare il modificatore `in` nel sito di chiamata. Il codice seguente illustra due esempi di chiamata al metodo `CalculateDistance`. Il primo usa due variabili locali passate per riferimento. Il secondo include una variabile temporanea creata durante la chiamata al metodo. 

[!code-csharp[UseInArgument](../../samples/csharp/reference-semantics/Program.cs#UseInArgument "Specifying an In argument")]

Il compilatore assicura che venga applicata la natura di sola lettura di un argomento `in` in diversi modi.  Prima di tutto il metodo chiamato non può essere direttamente assegnato a un parametro `in`. Non può essere direttamente assegnato ai campi di un parametro `in` se quel valore è un tipo `struct`. Non è neppure possibile passare un parametro `in` a metodi che usano il modificatore `ref` o `out`.
Queste regole sono valide per qualsiasi campo di un parametro `in`, a condizione che il campo sia di tipo `struct` e che anche il parametro sia di tipo `struct`. Queste regole, in effetti, vengono applicate per più livelli di accesso ai membri, a condizione che a tutti i livelli di accesso ai membri i tipi siano `structs`. Il compilatore impone che i tipi `struct` passati come argomenti `in` e i relativi membri `struct` siano variabili di sola lettura, se usati come argomenti per altri metodi.

L'uso di parametri `in` consente di evitare i costi potenziali sulle prestazioni per l'esecuzione di copie, ma non modifica la semantica delle chiamate a metodi. Non è quindi necessario specificare il modificatore `in` presso il sito di chiamata. Omettendo il modificatore `in` presso il sito di chiamata, tuttavia, si informa il compilatore che può effettuare una copia dell'argomento per i motivi seguenti:

- È presente una conversione implicita ma non una conversione di identità dal tipo di argomento al tipo di parametro.
- L'argomento è un'espressione, ma non ha una variabile di archiviazione nota.
- È presente un overload diverso per la presenza o l'assenza di `in`. In tal caso, l'overload in base al valore è una corrispondenza migliore.

Queste regole sono utili quando si aggiorna codice esistente per usare argomenti di riferimento di sola lettura. All'interno del metodo chiamato è possibile chiamare qualsiasi metodo di istanza che usa parametri in base al valore. In tali istanze viene creata una copia del parametro `in`. Poiché il compilatore può creare una variabile temporanea per qualsiasi parametro `in`, è anche possibile specificare i valori predefiniti per qualsiasi parametro `in`. Il codice seguente specifica l'origine (punto 0,0) come valore predefinito per il secondo punto:

[!code-csharp[InArgumentDefault](../../samples/csharp/reference-semantics/Program.cs#InArgumentDefault "Specifying defaults for an in parameter")]

Per imporre al compilatore di passare argomenti di sola lettura per riferimento, specificare il modificatore `in` per gli argomenti presso il sito di chiamata, come illustrato nel codice seguente:

[!code-csharp[UseInArgument](../../samples/csharp/reference-semantics/Program.cs#ExplicitInArgument "Specifying an In argument")]

Questo comportamento semplifica nel tempo l'adozione di parametri `in` in codebase di grandi dimensioni in cui è possibile ottenere miglioramenti delle prestazioni. È prima necessario aggiungere il modificatore `in` alle firme dei metodi. È quindi possibile aggiungere il modificatore `in` presso i siti di chiamata e creare tipi `readonly struct` per consentire al compilatore di evitare di creare copie difensive di parametri `in` in altre posizioni.

La designazione del parametro `in` può anche essere usata con tipi riferimento o valori numerici. Gli eventuali vantaggi in entrambi i casi sono tuttavia minimi.

## <a name="ref-readonly-returns"></a>Valori restituiti `ref readonly`

È anche possibile restituire un tipo valore per riferimento, ma non consentire al chiamante di modificare tale valore. Usare il modificatore `ref readonly` per esprimere tale finalità di progettazione. Notifica ai lettori che si restituirà un riferimento ai dati esistenti, ma non si consentirà la modifica. 

Il compilatore fa in modo che il chiamante non possa modificare il riferimento. I tentativi di assegnazione diretta del valore generano un errore in fase di compilazione. Il compilatore non può tuttavia sapere se un metodo del membro modifica lo stato dello struct.
Per assicurarsi che l'oggetto non venga modificato, il compilatore crea una copia e chiama i riferimenti al membro usando tale copia. Tutte le modifiche vengono apportate a tale copia difensiva. 

È probabile che la libreria che usa `Point3D` usi spesso l'origine in tutto il codice. Ogni istanza crea un nuovo oggetto nello stack. Può essere vantaggioso creare una costante e usarla per riferimento, ma, se si restituisce un riferimento alla risorsa di archiviazione interna, è possibile fare in modo che il chiamante non possa modificare la risorsa di archiviazione di riferimento. Il codice seguente definisce una proprietà di sola lettura che restituisce `readonly ref` a un oggetto `Point3D` che specifica l'origine.

[!code-csharp[OriginReference](../../samples/csharp/reference-semantics/Point3D.cs#OriginReference "Creating a readonly Origin reference")]

Per creare una copia di un valore restituito ref readonly, è sufficiente assegnarlo a una variabile non dichiarata con il modificatore `ref readonly`. Il compilatore genera il codice per copiare l'oggetto durante l'assegnazione. 

Quando si assegna una variabile a `ref readonly return`, è possibile specificare una variabile `ref readonly` o una copia per valore del riferimento di sola lettura:

[!code-csharp[AssignRefReadonly](../../samples/csharp/reference-semantics/Program.cs#AssignRefReadonly "Assigning a ref readonly")]

La prima assegnazione del codice precedente crea una copia della costante `Origin` e assegna tale copia. La seconda assegna un riferimento. Si noti che il modificatore `readonly` deve fare parte della dichiarazione della variabile. Il riferimento a cui viene fatto riferimento non può essere modificato. I tentativi di eseguire questa operazione generano un errore in fase di compilazione.

## <a name="readonly-struct-type"></a>Tipo `readonly struct`

Applicare `ref readonly` agli usi a traffico elevato di uno struct può essere sufficiente.
In altri casi, è possibile creare uno struct non modificabile. È quindi sempre possibile eseguire il passaggio per riferimento di sola lettura. Tale procedura rimuove le copie difensive che vengono eseguite quando si accede ai metodi di uno struct usato come parametro `in`.

A tale scopo, è possibile creare un tipo `readonly struct`. È possibile aggiungere il modificatore `readonly` a una dichiarazione di struct. Il compilatore fa in modo che tutti i membri di istanza dello struct siano `readonly`. `struct` deve essere non modificabile.

Esistono altre ottimizzazioni per `readonly struct`. È possibile usare il modificatore `in` in ogni posizione in cui `readonly struct` è un argomento. È anche possibile restituire `readonly struct` come `ref return` quando si restituisce un oggetto la cui durata si estende oltre l'ambito del metodo che restituisce l'oggetto.

Il compilatore genera infine un codice più efficiente quando si chiamano i membri di `readonly struct`: il riferimento `this`, invece di una copia del ricevitore, è sempre un parametro `in` passato per riferimento al metodo dei membri. Questa ottimizzazione consente un risparmio a livello di copie quando si usa `readonly struct`. `Point3D` è un candidato ideale per questa modifica. Nel codice seguente viene illustrata una struttura `ReadonlyPoint3D` aggiornata:

[!code-csharp[ReadonlyOnlyPoint3D](../../samples/csharp/reference-semantics/Point3D.cs#ReadonlyOnlyPoint3D "Defining an immutable structure")]

## <a name="ref-struct-type"></a>Tipo `ref struct`

Un'altra funzionalità del linguaggio correlata è la possibilità di dichiarare un tipo valore che deve essere allocato nello stack. In altre parole, questi tipi non possono mai essere creati nell'heap come membro di un'altra classe. La principale motivazione di questa funzionalità sono stati <xref:System.Span%601> e le strutture correlate. <xref:System.Span%601> può contenere un puntatore gestito come uno dei membri, mentre l'altro è la lunghezza dell'intervallo. L'implementazione è leggermente diversa perché C# non supporta i puntatori alla memoria gestita al di fuori di un contesto non sicuro. Le operazioni di scrittura che modificano il puntatore e la lunghezza non sono atomiche. Per questo <xref:System.Span%601> sarà soggetto a errori non compresi nell'intervallo o ad altre violazioni dell'indipendenza dai tipi se non è vincolato a un singolo stack frame. Inoltre l'inserimento di un puntatore gestito nell'heap GC provoca in genere un arresto anomalo del sistema in fase JIT.

Possono esistere requisiti simili quando si usa la memoria creata con [`stackalloc`](language-reference/keywords/stackalloc.md) o quando si usa la memoria delle API di interoperabilità. È possibile definire i tipi `ref struct` in base a tali esigenze. In questo articolo vengono illustrati esempi che usano `Span<T>` per semplicità.

La dichiarazione `ref struct` afferma che nello stack deve essere presente uno struct di questo tipo. Le regole del linguaggio garantiscono l'uso sicuro di questi tipi. Gli altri tipi dichiarati come `ref struct` includono <xref:System.ReadOnlySpan%601>. 

L'obiettivo di mantenere un tipo `ref struct` come variabile allocata nello stack comporta diverse regole che il compilatore applica per tutti i tipi `ref struct`.

- Non è possibile eseguire il boxing di `ref struct`. Non è possibile assegnare un tipo `ref struct` a una variabile di tipo `object`, `dynamic` o qualsiasi tipo di interfaccia.
- Non è possibile dichiarare `ref struct` come membro di una classe o di un normale struct.
- Non è possibile dichiarare variabili locali che sono tipi `ref struct` nei metodi asincroni. È possibile dichiararle nei metodi sincroni che restituiscono tipi `Task`, `Task<T>` o simili a Task.
- Non è possibile dichiarare variabili locali `ref struct` negli iteratori.
- Non è possibile acquisire variabili `ref struct` in espressioni lambda o funzioni locali.

Queste restrizioni garantiscono che non si possa usare accidentalmente `ref struct` in modo tale che possa essere alzato di livello nell'heap gestito.

## <a name="readonly-ref-struct-type"></a>Tipo `readonly ref struct`

Dichiarando uno struct come `readonly ref` si combinano i vantaggi e le restrizioni delle dichiarazioni `ref struct` e `readonly struct`. 

L'esempio seguente illustra la dichiarazione di `readonly ref struct`.

```csharp
readonly ref struct ReadOnlyRefPoint2D
{
    public int X { get; }
    public int Y { get; }
    
    public ReadOnlyRefPoint2D(int x, int y) => (X, Y) = (x, y);
}
```

## <a name="conclusions"></a>Conclusioni

Questi miglioramenti del linguaggio C# sono progettati per gli algoritmi con prestazioni critiche in cui le allocazioni della memoria possono essere strategiche per raggiungere le prestazioni necessarie. È possibile che non si usino spesso queste funzionalità nella scrittura del codice. Questi miglioramenti sono stati tuttavia adottati in diverse posizioni di .NET Framework. Il sempre maggior numero di API che useranno queste funzionalità renderà evidente il miglioramento delle prestazioni delle applicazioni.

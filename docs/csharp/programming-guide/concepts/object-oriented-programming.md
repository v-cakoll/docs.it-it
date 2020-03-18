---
title: Programmazione orientata a oggetti (C#)
ms.date: 02/08/2020
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 01d6f55bf0752f902f351675c4596abbb8ac85c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77627890"
---
# <a name="object-oriented-programming-c"></a>Programmazione orientata agli oggetti (C )Object-Oriented programming (C

C# offre un supporto completo per la programmazione orientata a oggetti che include incapsulamento, ereditarietà e polimorfismo.

- L'*incapsulamento* indica che un gruppo di proprietà, metodi e altri membri correlati vengono considerati come una singola unità o un singolo oggetto.
- L'*ereditarietà* indica la capacità di creare nuove classi sulla base di una classe esistente.
- Il *polimorfismo* indica la capacità di usare più classi in modo intercambiabile, anche se in ognuna di esse le stesse proprietà o gli stessi metodi sono implementati in modi diversi.

## <a name="classes-and-objects"></a>Classi e oggetti

I termini *class* e *object* descrivono rispettivamente il *tipo* di oggetti e le *istanze* delle classi. L'atto di creare un oggetto viene pertanto chiamato *creazione di istanze*. Rifacendoci all'analogia precedente, la classe corrisponde al progetto iniziale e l'oggetto all'edificio realizzato in base a tale progetto.

Per definire una classe:

```csharp
class SampleClass
{
}
```

In C' sono inoltre disponibili tipi denominati *strutture* che sono utili quando non è necessario il supporto per l'ereditarietà o il polimorfismo.

Per definire una struttura:

```csharp
struct SampleStruct
{
}
```

Per altre informazioni, vedere gli articoli sulle parole chiave [class](../../language-reference/keywords/class.md) e [struct.](../../language-reference/builtin-types/struct.md)

### <a name="class-members"></a>Membri di classe

Ogni classe può avere *membri di classe* diversi che includono proprietà che descrivono i dati della classe, i metodi che definiscono il comportamento della classe e gli eventi che offrono la comunicazione tra classi e oggetti diversi.

#### <a name="properties-and-fields"></a>Proprietà e campi

I campi e le proprietà rappresentano le informazioni contenute in un oggetto. I campi sono come variabili perché possono essere letti o impostati direttamente, in base ai modificatori di accesso applicabili.

Per definire un campo accessibile dall'interno di istanze della classe:

```csharp
public class SampleClass
{
    string sampleField;
}
```

Le `get` proprietà `set` dispongono di e funzioni di accesso, che forniscono un maggiore controllo sulla modalità di impostazione o restituzione dei valori.

Il linguaggio C, è possibile creare un campo privato per archiviare il valore della proprietà o usare proprietà implementate automaticamente che creano automaticamente questo campo dietro le quinte e forniscono la logica di base per le procedure della proprietà.

Per definire una proprietà implementata automaticamente:

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

Se è necessario eseguire alcune operazioni aggiuntive per la lettura e la scrittura del valore della proprietà, definire un campo per archiviare il valore della proprietà e fornire la logica di base per archiviarlo e recuperarlo:

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get => _sample;
        // Store the value in the field.
        set =>  _sample = value;
    }
}
```

La maggior parte delle proprietà dispone di metodi o di routine per impostare e ottenere il valore della proprietà. È possibile, tuttavia, creare proprietà di sola lettura o di sola scrittura per impedirne la modifica o la lettura. In C#, è possibile omettere il metodo della proprietà `get` o `set`. Tuttavia, le proprietà implementate automaticamente non possono essere di sola scrittura. Le proprietà implementate automaticamente di sola lettura possono essere impostate nei costruttori della classe contenitore.

Per altre informazioni, vedere:

- [get](../../language-reference/keywords/get.md)

- [Impostare](../../language-reference/keywords/set.md)

#### <a name="methods"></a>Metodi

Un *metodo* è un'azione che può essere eseguita da un oggetto.

Per definire un metodo di una classe:

```csharp
class SampleClass
{
    public int sampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

Una classe può disporre di diverse implementazioni, o *overload*, dello stesso metodo che differiscono per il numero di parametri o per i tipi di parametro.

Per essere in rapporto di overload con un metodo:

```csharp
public int sampleMethod(string sampleParam) {}
public int sampleMethod(int sampleParam) {}
```

Nella maggior parte dei casi si dichiara un metodo all'interno di una definizione della classe. C#, tuttavia, supporta anche i *metodi di estensione* che consentono di aggiungere metodi a una classe esistente al di fuori della definizione effettiva della classe.

Per altre informazioni, vedere:

- [Metodi](../classes-and-structs/methods.md)
- [Metodi di estensione](../classes-and-structs/extension-methods.md)

#### <a name="constructors"></a>Costruttori

I costruttori sono metodi di classe che vengono eseguiti automaticamente durante la creazione di un oggetto di un tipo specifico. I costruttori in genere inizializzano i membri dati del nuovo oggetto. Un costruttore può essere eseguito solo una volta alla creazione di una classe. Inoltre, il codice nel costruttore viene sempre eseguito prima di qualsiasi altro codice in una classe. Tuttavia, è possibile creare più overload del costruttore esattamente come per qualsiasi altro metodo.

Per definire un costruttore per una classe:

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

Per altre informazioni, vedere [Costruttori](../classes-and-structs/constructors.md).

#### <a name="finalizers"></a>Finalizzatori

I finalizzatori sono usati per distruggere istanze di classi. In .NET Framework, il Garbage Collector gestisce l'allocazione e il rilascio di memoria per gli oggetti gestiti di un'applicazione. Potrebbero, tuttavia, essere necessari finalizzatori per pulire eventuali risorse non gestite create dall'applicazione. Può esistere un solo finalizzatore per classe.

Per altre informazioni sui finalizzatori e sull'operazione di Garbage Collection in .NET Framework, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).

#### <a name="events"></a>Eventi

Tramite gli eventi una classe o un oggetto sono in grado di segnalare ad altre classi o oggetti una situazione di interesse. La classe che invia o genera l'evento è chiamata *editore* e le classi che ricevono o gestiscono l'evento sono chiamate *sottoscrittori*. Per altre informazioni sugli eventi e sulla loro generazione e gestione, vedere [Eventi](../../../standard/events/index.md).

- Per dichiarare un evento in una classe, usare la parola chiave [event](../../language-reference/keywords/event.md).

- Per generare un evento, richiamare il delegato dell'evento.

- Per sottoscrivere un evento, utilizzare l'operatore `+=`. Per annullare la sottoscrizione a un evento utilizzare l'operatore `-=`:

#### <a name="nested-classes"></a>Classi annidate

Una classe definita all'interno di un'altra classe è denominata *annidata*. Per impostazione predefinita, la classe annidata è privata.

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

Per creare un'istanza della classe annidata, utilizzare il nome della classe dei contenitori seguita dal punto, quindi dal nome della classe annidata:

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a>Modificatori di accesso e livelli di accessoAccess modifiers and access levels

Tutte le classi e i membri della classe possono specificare il livello di accesso offerto alle altre classi usando i *modificatori di accesso*.

Sono disponibili i seguenti modificatori di accesso:

|Modificatore di C#|Definizione|
|------------------|----------------|
|[pubblico](../../language-reference/keywords/public.md)|Il tipo o il membro è accessibile da altro codice nello stesso assembly o in un altro assembly che vi fa riferimento.|
|[Privato](../../language-reference/keywords/private.md)|Il tipo o il membro è accessibile solo dal codice nella stessa classe.|
|[Protetto](../../language-reference/keywords/protected.md)|Il tipo o il membro è accessibile solo dal codice nella stessa classe o in una classe derivata.|
|[Interno](../../language-reference/keywords/internal.md)|Il tipo o il membro è accessibile dal codice nello stesso assembly ma non da un altro assembly.|
|[protected internal](../../language-reference/keywords/protected-internal.md)|Il tipo o il membro è accessibile dal codice nello stesso assembly o da una classe derivata in un altro assembly.|
|[private protected](../../language-reference/keywords/private-protected.md)|Il tipo o membro è accessibile solo dal codice nella stessa classe o in una classe derivata all'interno dell'assembly della classe di base.|

Per altre informazioni, vedere [Modificatori di accesso](../classes-and-structs/access-modifiers.md).

### <a name="instantiating-classes"></a>Creazione di istanze di classi

Per creare un oggetto, è necessario creare un'istanza di una classe.

```csharp
SampleClass sampleObject = new SampleClass();
```

Dopo avere creato un'istanza di una classe, è possibile assegnare i valori alle proprietà e ai campi dell'istanza e richiamare i metodi della classe.

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.sampleMethod();
```

Per assegnare i valori alle proprietà durante il processo di creazione dell'istanza della classe, utilizzare gli inizializzatori di oggetto:

```csharp
// Set a property value.
SampleClass sampleObject = new SampleClass
    { FirstProperty = "A", SecondProperty = "B" };
```

Per altre informazioni, vedere:

- [nuovo operatore](../../language-reference/operators/new-operator.md)
- [Inizializzatori di oggetto e di raccoltaObject and Collection Initializers](../classes-and-structs/object-and-collection-initializers.md)

### <a name="static-classes-and-members"></a>Classi e membri statici

Un membro statico della classe è una proprietà, una routine o un campo condiviso da tutte le istanze di una classe.

Per definire un membro statico:

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

Per accedere al membro statico, usare il nome della classe senza creare un oggetto di questa classe:

```csharp
Console.WriteLine(SampleClass.SampleString);
```

Le classi statiche in C# hanno solo membri statici e non è possibile crearne un'istanza. I membri statici, inoltre, non possono accedere a proprietà, campi o metodi non statici.

Per altre informazioni, vedere [static](../../language-reference/keywords/static.md).

### <a name="anonymous-types"></a>Tipi anonimi

I tipi anonimi consentono di creare oggetti senza scrivere una definizione della classe per il tipo di dati. La classe viene generata direttamente dal compilatore. La classe non ha un nome utilizzabile e contiene le proprietà specificate nella dichiarazione dell'oggetto.

Per creare un'istanza di un tipo anonimo:

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject =
    new { FirstProperty = "A", SecondProperty = "B" };
```

Per altre informazioni, vedere [Tipi anonimi](../classes-and-structs/anonymous-types.md).

## <a name="inheritance"></a>Ereditarietà

L'ereditarietà permette di creare una nuova classe che riutilizza, estende e modifica il comportamento definito in un'altra classe. La classe i cui membri vengono ereditati è denominata *classe di base*, mentre la classe che eredita tali membri è denominata *classe derivata*. Tuttavia, tutte le classi in C# ereditano in modo implicito dalla classe <xref:System.Object> che supporta la gerarchia di classi .NET e offre servizi di basso livello a tutte le classi.

> [!NOTE]
> C# non supporta l'ereditarietà multipla. Vale a dire, è possibile specificare una sola classe base per una classe derivata.

Per ereditare da una classe base:

```csharp
class DerivedClass:BaseClass {}
```

Per impostazione predefinita, tutte le classi possono essere ereditate. Tuttavia, è possibile specificare se una classe non deve essere utilizzata come classe base oppure creare una classe utilizzabile solo come classe base.

Per specificare che una classe non può essere utilizzata come classe base:

```csharp
public sealed class A { }
```

Per specificare che una classe può essere utilizzata solo come classe base e che non è possibile crearne un'istanza:

```csharp
public abstract class B { }
```

Per altre informazioni, vedere:

- [Sigillato](../../language-reference/keywords/sealed.md)

- [astratto](../../language-reference/keywords/abstract.md)

### <a name="overriding-members"></a>Override di membri

Per impostazione predefinita, in una classe derivata vengono ereditati tutti i membri della classe base relativa. Se si desidera modificare il comportamento del membro ereditato, è necessario eseguirne l'override. È possibile definire una nuova implementazione del metodo, della proprietà o dell'evento nella classe derivata.

I seguenti modificatori consentono di controllare le modalità di override di proprietà e metodi:

|Modificatore di C#|Definizione|
|------------------|----------------|
|[Virtuale](../../language-reference/keywords/virtual.md)|Consente a un membro della classe di essere sottoposto a override in una classe derivata.|
|[prevalere](../../language-reference/keywords/override.md)|Esegue l'override di un membro virtuale (sottoponibile a override) definito nella classe base.|
|[astratto](../../language-reference/keywords/abstract.md)|Richiede che un membro della classe venga sottoposto a override nella classe derivata.|
|[nuovo modificatore](../../language-reference/keywords/new-modifier.md)|Nasconde un membro ereditato da una classe base.|

## <a name="interfaces"></a>Interfacce

Le interfacce, come le classi, consentono di definire un insieme di proprietà, metodi ed eventi. A differenza delle classi, però, le interfacce non forniscono l'implementazione. Esse sono infatti implementate dalle classi e definite come entità distinte da queste. Un'interfaccia rappresenta un contratto, in quanto è necessario che una classe che implementa un'interfaccia implementi ogni aspetto esattamente come è stato definito.

Per definire un'interfaccia:

```csharp
interface ISampleInterface
{
    void doSomething();
}
```

Per implementare un'interfaccia in una classe:

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.doSomething()
    {
        // Method implementation.
    }
}
```

Per altre informazioni, vedere l'articolo della guida alla programmazione [sulle interfacce](../interfaces/index.md) e l'articolo di riferimento del linguaggio sulla parola chiave [interface.](../../language-reference/keywords/interface.md)

## <a name="generics"></a>Generics

Classi, strutture, interfacce e metodi in .NET Framework possono includere *parametri di tipo* che definiscono tipi di oggetti che possono archiviare o usare. L'esempio più comune di generics è una raccolta, dove è possibile specificare il tipo di oggetti da archiviare in una raccolta.

Per definire una classe generica:

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

Per creare un'istanza di una classe generica:

```csharp
SampleGeneric<string> sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

Per altre informazioni, vedere:

- [Generics](../../../standard/generics/index.md)

- [Generics](../generics/index.md)

## <a name="delegates"></a>Delegati

Un *delegato* è un tipo che definisce una firma di metodo e può offrire un riferimento a qualsiasi metodo con una firma compatibile. Tramite il delegato è possibile invocare (o chiamare) il metodo. I delegati vengono utilizzati per passare metodi come argomenti ad altri metodi.

> [!NOTE]
> I gestori di evento non sono altro che metodi richiamati tramite delegati. Per altre informazioni sull'uso dei delegati nella gestione degli eventi, vedere [Eventi](../../../standard/events/index.md).

Per creare un delegato:

```csharp
public delegate void SampleDelegate(string str);
```

Per creare un riferimento a un metodo che corrisponde alla firma specificata dal delegato:

```csharp
class SampleClass
{
    // Method that matches the SampleDelegate signature.
    public static void sampleMethod(string message)
    {
        // Add code here.
    }
    // Method that instantiates the delegate.
    void SampleDelegate()
    {
        SampleDelegate sd = sampleMethod;
        sd("Sample string");
    }
}
```

Per altre informazioni, vedere l'articolo della guida alla programmazione [sui delegati](../delegates/index.md) e l'articolo di riferimento del linguaggio sulla parola chiave [delegate.](../../language-reference/builtin-types/reference-types.md)

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)

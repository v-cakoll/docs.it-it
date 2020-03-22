---
title: Programmazione orientata agli oggetti
ms.date: 07/20/2015
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
ms.openlocfilehash: 3739919273f4cdd285d519c414c542f1a82a16d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400687"
---
# <a name="object-oriented-programming-visual-basic"></a>Programmazione orientata agli oggetti (Visual Basic)Object-oriented programming (Visual Basic)

Visual Basic fornisce supporto completo per la programmazione orientata agli oggetti, inclusi incapsulamento, ereditarietà e polimorfismo.

 L'*incapsulamento* indica che un gruppo di proprietà, metodi e altri membri correlati vengono considerati come una singola unità o un singolo oggetto.

 L'*ereditarietà* indica la capacità di creare nuove classi sulla base di una classe esistente.

 Il *polimorfismo* indica la capacità di usare più classi in modo intercambiabile, anche se in ognuna di esse le stesse proprietà o gli stessi metodi sono implementati in modi diversi.

 In questa sezione vengono descritti i concetti seguenti:

- [Classi e oggetti](#classes-and-objects)
  - [Membri di classe](#class-members)
    - [Proprietà e campi](#properties-and-fields)
    - [Metodi](#methods)
    - [Costruttori](#constructors)
    - [Distruttori](#destructors)
    - [Events](#events)
    - [Classi annidate](#nested-classes)
  - [Modificatori di accesso e livelli di accessoAccess modifiers and access levels](#access-modifiers-and-access-levels)
    - [Creazione di istanze di classi](#instantiating-classes)
    - [Classi e membri condivisi](#shared-classes-and-members)
    - [Tipi anonimi](#anonymous-types)
- [Ereditarietà](#inheritance)
  - [Sostituzione dei membri](#overriding-members)
- [Interfacce](#interfaces)
- [Generics](#generics)
- [Delegati](#delegates)

## <a name="classes-and-objects"></a>Classi e oggetti

I termini *classe* e *oggetto* vengono talvolta usati in modo intercambiabile. Di fatto, però, le classi descrivono il *tipo* degli oggetti, mentre gli oggetti sono *istanze* utilizzabili delle classi. L'atto di creare un oggetto viene pertanto chiamato *creazione di istanze*. Rifacendoci all'analogia precedente, la classe corrisponde al progetto iniziale e l'oggetto all'edificio realizzato in base a tale progetto.

Per definire una classe:

```vb
Class SampleClass
End Class
```

Visual Basic fornisce anche una versione leggera delle classi denominate *strutture* che sono utili quando è necessario creare una grande matrice di oggetti e non si desidera utilizzare troppa memoria per questo.

Per definire una struttura:

```vb
Structure SampleStructure
End Structure
```

Per altre informazioni, vedere:

- [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)

### <a name="class-members"></a>Membri di classe

Ogni classe può avere *membri di classe* diversi che includono proprietà che descrivono i dati della classe, i metodi che definiscono il comportamento della classe e gli eventi che offrono la comunicazione tra classi e oggetti diversi.

#### <a name="properties-and-fields"></a>Proprietà e campi

I campi e le proprietà rappresentano le informazioni contenute in un oggetto. I campi sono simili a variabili in quanto possono essere letti o impostati direttamente.

Per definire un campo:

```vb
Class SampleClass
    Public SampleField As String
End Class
```

Le proprietà dispongono di routine Get e Set, che forniscono un maggiore controllo sul modo in cui i valori vengono impostati o restituiti.

Visual Basic consente di creare un campo privato per archiviare il valore della proprietà o utilizzare le cosiddette proprietà implementate automaticamente che creano automaticamente questo campo dietro le quinte e forniscono la logica di base per le routine della proprietà.

Per definire una proprietà implementata automaticamente:

```vb
Class SampleClass
    Public Property SampleProperty as String
End Class
```

Se è necessario eseguire alcune operazioni aggiuntive per la lettura e la scrittura del valore della proprietà, definire un campo per archiviare il valore della proprietà e fornire la logica di base per archiviarlo e recuperarlo:

```vb
Class SampleClass
    Private m_Sample As String
    Public Property Sample() As String
        Get
            ' Return the value stored in the field.
            Return m_Sample
        End Get
        Set(ByVal Value As String)
            ' Store the value in the field.
            m_Sample = Value
        End Set
    End Property
End Class
```

La maggior parte delle proprietà dispone di metodi o di routine per impostare e ottenere il valore della proprietà. È possibile, tuttavia, creare proprietà di sola lettura o di sola scrittura per impedirne la modifica o la lettura. In Visual Basic è possibile utilizzare le parole chiave `ReadOnly` e `WriteOnly`. Tuttavia, le proprietà implementate automaticamente non possono essere di sola lettura o di sola scrittura.

Per altre informazioni, vedere:

- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Istruzione Get](../../../visual-basic/language-reference/statements/get-statement.md)
- [Istruzione Set](../../../visual-basic/language-reference/statements/set-statement.md)
- [Readonly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [Writeonly](../../../visual-basic/language-reference/modifiers/writeonly.md)

#### <a name="methods"></a>Metodi

 Un *metodo* è un'azione che può essere eseguita da un oggetto.

> [!NOTE]
> In Visual Basic, è possibile creare un metodo in due modi: se il metodo non restituisce un valore, viene utilizzata l'istruzione `Sub`, se invece un metodo restituisce un valore, viene utilizzata l'istruzione `Function`.

Per definire un metodo di una classe:

```vb
Class SampleClass
    Public Function SampleFunc(ByVal SampleParam As String)
        ' Add code here
    End Function
End Class
```

Una classe può disporre di diverse implementazioni, o *overload*, dello stesso metodo che differiscono per il numero di parametri o per i tipi di parametro.

Per essere in rapporto di overload con un metodo:

```vb
Overloads Sub Display(ByVal theChar As Char)
    ' Add code that displays Char data.
End Sub
Overloads Sub Display(ByVal theInteger As Integer)
    ' Add code that displays Integer data.
End Sub
```

Nella maggior parte dei casi si dichiara un metodo all'interno di una definizione della classe. Tuttavia, Visual Basic supporta anche *i metodi* di estensione che consentono di aggiungere metodi a una classe esistente all'esterno della definizione effettiva della classe.

Per altre informazioni, vedere:

- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Overload](../../../visual-basic/language-reference/modifiers/overloads.md)
- [Metodi di estensione](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)

#### <a name="constructors"></a>Costruttori

I costruttori sono metodi di classe che vengono eseguiti automaticamente durante la creazione di un oggetto di un tipo specifico. I costruttori in genere inizializzano i membri dati del nuovo oggetto. Un costruttore può essere eseguito solo una volta alla creazione di una classe. Inoltre, il codice nel costruttore viene sempre eseguito prima di qualsiasi altro codice in una classe. Tuttavia, è possibile creare più overload del costruttore esattamente come per qualsiasi altro metodo.

Per definire un costruttore per una classe:

```vb
Class SampleClass
    Sub New(ByVal s As String)
        // Add code here.
    End Sub
End Class
```

Per ulteriori informazioni, vedere: [Durata degli oggetti: modalità](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)di creazione ed eliminazione degli oggetti.

#### <a name="destructors"></a>Distruttori

I distruttori sono utilizzati per distruggere istanze di classi. In .NET Framework, il Garbage Collector gestisce l'allocazione e il rilascio di memoria per gli oggetti gestiti di un'applicazione. Potrebbero, tuttavia, essere necessari distruttori per pulire eventuali risorse non gestite create dall'applicazione. Può esistere un solo distruttore per classe.

Per altre informazioni sui distruttori e sull'operazione di Garbage Collection in .NET Framework, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).

#### <a name="events"></a>Eventi

Tramite gli eventi una classe o un oggetto sono in grado di segnalare ad altre classi o oggetti una situazione di interesse. La classe che invia o genera l'evento è chiamata *editore* e le classi che ricevono o gestiscono l'evento sono chiamate *sottoscrittori*. Per altre informazioni sugli eventi e sulla loro generazione e gestione, vedere [Eventi](../../../standard/events/index.md).

- Per dichiarare eventi, utilizzare [l'istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).

- Per generare eventi, utilizzare [l'istruzione RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md).

- Per specificare i gestori eventi in modo dichiarativo, utilizzare l'istruzione [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) e la clausola [Handles.](../../../visual-basic/language-reference/statements/handles-clause.md)

- Per poter aggiungere, rimuovere e modificare dinamicamente il gestore eventi associato a un evento, utilizzare [l'istruzione AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md) e [l'istruzione RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md) insieme all'operatore [AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md).

#### <a name="nested-classes"></a>Classi annidate

Una classe definita all'interno di un'altra classe è denominata *annidata*. Per impostazione predefinita, la classe annidata è privata.

```vb
Class Container
    Class Nested
    ' Add code here.
    End Class
End Class
```

Per creare un'istanza della classe annidata, utilizzare il nome della classe dei contenitori seguita dal punto, quindi dal nome della classe annidata:

```vb
Dim nestedInstance As Container.Nested = New Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a>Modificatori di accesso e livelli di accessoAccess modifiers and access levels

Tutte le classi e i membri della classe possono specificare il livello di accesso offerto alle altre classi usando i *modificatori di accesso*.

Sono disponibili i seguenti modificatori di accesso:

|Modificatore di Visual Basic|Definizione|
|---------------------------|----------------|
|[Pubblico](../../../visual-basic/language-reference/modifiers/public.md)|Il tipo o il membro è accessibile da altro codice nello stesso assembly o in un altro assembly che vi fa riferimento.|
|[Privata](../../../visual-basic/language-reference/modifiers/private.md)|Il tipo o il membro è accessibile solo dal codice nella stessa classe.|
|[Protetto](../../../visual-basic/language-reference/modifiers/protected.md)|Il tipo o il membro è accessibile solo dal codice nella stessa classe o in una classe derivata.|
|[Amico](../../../visual-basic/language-reference/modifiers/friend.md)|Il tipo o il membro è accessibile dal codice nello stesso assembly ma non da un altro assembly.|
|`Protected Friend`|Il tipo o il membro è accessibile dal codice nello stesso assembly o da una classe derivata in un altro assembly.|

Per ulteriori informazioni, vedere [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

### <a name="instantiating-classes"></a>Creazione di istanze di classi

Per creare un oggetto, è necessario creare un'istanza di una classe.

```vb
Dim sampleObject as New SampleClass()
```

Dopo avere creato un'istanza di una classe, è possibile assegnare i valori alle proprietà e ai campi dell'istanza e richiamare i metodi della classe.

```vb
' Set a property value.
sampleObject.SampleProperty = "Sample String"
' Call a method.
sampleObject.SampleMethod()
```

Per assegnare i valori alle proprietà durante il processo di creazione dell'istanza della classe, utilizzare gli inizializzatori di oggetto:

```vb
Dim sampleObject = New SampleClass With
    {.FirstProperty = "A", .SecondProperty = "B"}
```

Per altre informazioni, vedere:

- [Nuovo operatore](../../../visual-basic/language-reference/operators/new-operator.md)
- [Inizializzatori di oggetto: tipi denominati e tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)

### <a name="shared-classes-and-members"></a>Classi e membri condivisi

 Un membro condiviso della classe è una proprietà, una routine o un campo condiviso da tutte le istanze di una classe.

 Per definire un membro condiviso:

```vb
Class SampleClass
    Public Shared SampleString As String = "Sample String"
End Class
```

 Per accedere al membro condiviso, utilizzare il nome della classe senza creare un oggetto di questa classe:

```vb
MsgBox(SampleClass.SampleString)
```

 I moduli condivisi in Visual Basic hanno solo membri condivisi e non è possibile crearne un'istanza. I membri condivisi non possono inoltre accedere a proprietà, campi o metodi non condivisi

 Per altre informazioni, vedere:

- [Condivisa](../../../visual-basic/language-reference/modifiers/shared.md)
- [Istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md)

### <a name="anonymous-types"></a>Tipi anonimi

I tipi anonimi consentono di creare oggetti senza scrivere una definizione della classe per il tipo di dati. La classe viene generata direttamente dal compilatore. La classe non ha un nome utilizzabile e contiene le proprietà specificate nella dichiarazione dell'oggetto.

Per creare un'istanza di un tipo anonimo:

```vb
' sampleObject is an instance of a simple anonymous type.
Dim sampleObject =
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}
```

Per altre informazioni, vedere [Tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).

## <a name="inheritance"></a>Ereditarietà

L'ereditarietà permette di creare una nuova classe che riutilizza, estende e modifica il comportamento definito in un'altra classe. La classe i cui membri vengono ereditati è denominata *classe di base*, mentre la classe che eredita tali membri è denominata *classe derivata*. Tuttavia, tutte le classi in <xref:System.Object> Visual Basic ereditano in modo implicito dalla classe che supporta la gerarchia delle classi .NET e fornisce servizi di basso livello a tutte le classi.

> [!NOTE]
> Visual Basic non supporta l'ereditarietà multipla. Vale a dire, è possibile specificare una sola classe base per una classe derivata.

Per ereditare da una classe base:

```vb
Class DerivedClass
    Inherits BaseClass
End Class
```

Per impostazione predefinita, tutte le classi possono essere ereditate. Tuttavia, è possibile specificare se una classe non deve essere utilizzata come classe base oppure creare una classe utilizzabile solo come classe base.

Per specificare che una classe non può essere utilizzata come classe base:

```vb
NotInheritable Class SampleClass
End Class
```

Per specificare che una classe può essere utilizzata solo come classe base e che non è possibile crearne un'istanza:

```vb
MustInherit Class BaseClass
End Class
```

Per altre informazioni, vedere:

- [Istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)

### <a name="overriding-members"></a>Sostituzione dei membri

Per impostazione predefinita, in una classe derivata vengono ereditati tutti i membri della classe base relativa. Se si desidera modificare il comportamento del membro ereditato, è necessario eseguirne l'override. È possibile definire una nuova implementazione del metodo, della proprietà o dell'evento nella classe derivata.

I seguenti modificatori consentono di controllare le modalità di override di proprietà e metodi:

|Modificatore di Visual Basic|Definizione|
|---------------------------|----------------|
|[Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)|Consente a un membro della classe di essere sottoposto a override in una classe derivata.|
|[Esegue l' override](../../../visual-basic/language-reference/modifiers/overrides.md)|Esegue l'override di un membro virtuale (sottoponibile a override) definito nella classe base.|
|[NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)|Consente di impedire l'override di un membro in una classe che eredita.|
|[MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)|Richiede che un membro della classe venga sottoposto a override nella classe derivata.|
|[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)|Nasconde un membro ereditato da una classe base.|

## <a name="interfaces"></a>Interfacce

Le interfacce, come le classi, consentono di definire un insieme di proprietà, metodi ed eventi. A differenza delle classi, però, le interfacce non forniscono l'implementazione. Esse sono infatti implementate dalle classi e definite come entità distinte da queste. Un'interfaccia rappresenta un contratto, in quanto è necessario che una classe che implementa un'interfaccia implementi ogni aspetto esattamente come è stato definito.

Per definire un'interfaccia:

```vb
Public Interface ISampleInterface
    Sub DoSomething()
End Interface
```

Per implementare un'interfaccia in una classe:

```vb
Class SampleClass
    Implements ISampleInterface
    Sub DoSomething
        ' Method implementation.
    End Sub
End Class
```

Per altre informazioni, vedere:

- [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md)

## <a name="generics"></a>Generics

Classi, strutture, interfacce e metodi in .NET possono includere parametri di *tipo* che definiscono tipi di oggetti che possono archiviare o utilizzare. L'esempio più comune di generics è una raccolta, dove è possibile specificare il tipo di oggetti da archiviare in una raccolta.

Per definire una classe generica:

```vb
Class SampleGeneric(Of T)
    Public Field As T
End Class
```

Per creare un'istanza di una classe generica:

```vb
Dim sampleObject As New SampleGeneric(Of String)
sampleObject.Field = "Sample string"
```

Per altre informazioni, vedere:

- [Generics](../../../standard/generics/index.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)

## <a name="delegates"></a>Delegati

 Un *delegato* è un tipo che definisce una firma di metodo e può offrire un riferimento a qualsiasi metodo con una firma compatibile. Tramite il delegato è possibile invocare (o chiamare) il metodo. I delegati vengono utilizzati per passare metodi come argomenti ad altri metodi.

> [!NOTE]
> I gestori di evento non sono altro che metodi richiamati tramite delegati. Per altre informazioni sull'uso dei delegati nella gestione degli eventi, vedere [Eventi](../../../standard/events/index.md).

Per creare un delegato:

```vb
Delegate Sub SampleDelegate(ByVal str As String)
```

Per creare un riferimento a un metodo che corrisponde alla firma specificata dal delegato:

```vb
Class SampleClass
    ' Method that matches the SampleDelegate signature.
    Sub SampleSub(ByVal str As String)
        ' Add code here.
    End Sub
    ' Method that instantiates the delegate.
    Sub SampleDelegateSub()
        Dim sd As SampleDelegate = AddressOf SampleSub
        sd("Sample string")
    End Sub
End Class
```

Per altre informazioni, vedere:

- [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori Visual Basic](../../../visual-basic/programming-guide/index.md)

---
title: Raccolte
ms.date: 07/20/2015
ms.assetid: 5f7749f3-aaf2-4319-b63c-bfa72e1e2b7a
ms.openlocfilehash: 232b9ec7b5975092e73daf0a7384fa816f55f72f
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646336"
---
# <a name="collections-visual-basic"></a>Raccolte (Visual Basic)

Per molte applicazioni è utile creare e gestire gruppi di oggetti correlati. È possibile raggruppare gli oggetti in due modi: creando matrici di oggetti e creando raccolte di oggetti.

Le matrici sono estremamente utili per la creazione e l'uso di un numero fisso di oggetti fortemente tipizzati. Per altre informazioni sulle matrici, vedere [Matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).

Le raccolte consentono di lavorare in modo più flessibile con gruppi di oggetti. A differenza delle matrici, il gruppo di oggetti con cui si lavora può aumentare e diminuire in modo dinamico in base alle esigenze dell'applicazione. Per alcune raccolte è possibile assegnare una chiave a qualsiasi oggetto inserito nella raccolta in modo da recuperare rapidamente l'oggetto usando la chiave.

Una raccolta è una classe. Di conseguenza, prima di poter aggiungere elementi a una nuova raccolta è necessario dichiarare la raccolta.

Se la raccolta contiene elementi di un solo tipo di dati, è possibile usare una delle classi dello spazio dei nomi <xref:System.Collections.Generic?displayProperty=nameWithType>. In una raccolta generica viene imposta l'indipendenza dai tipi, in modo da impedire che vengano aggiunti altri tipi di dati alla raccolta. Quando si recupera un elemento da una raccolta generica, non è necessario determinarne il tipo di dati né convertirlo.

> [!NOTE]
> Per gli esempi in questo argomento, includere `System.Collections.Generic` `System.Linq` [imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) istruzioni per gli spazi dei nomi e .

<a name="BKMK_SimpleCollection"></a>

## <a name="using-a-simple-collection"></a>Uso di una raccolta semplice

Gli esempi in questa sezione usano la classe generica <xref:System.Collections.Generic.List%601>, che consente di usare un elenco di oggetti fortemente tipizzato.

L'esempio seguente crea un elenco di stringhe e quindi scorre le stringhe utilizzando un [For Each... Prossima](../../../visual-basic/language-reference/statements/for-each-next-statement.md) dichiarazione.

```vb
' Create a list of strings.
Dim salmons As New List(Of String)
salmons.Add("chinook")
salmons.Add("coho")
salmons.Add("pink")
salmons.Add("sockeye")

' Iterate through the list.
For Each salmon As String In salmons
    Console.Write(salmon & " ")
Next
'Output: chinook coho pink sockeye
```

Se il contenuto di una raccolta è noto in anticipo, si può usare un *inizializzatore di raccolta* per inizializzare la raccolta. Per altre informazioni, vedere [Inizializzatori di insieme](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).

L'esempio seguente è identico all'esempio precedente, ma usa un inizializzatore di raccolta per aggiungere elementi alla raccolta.

```vb
' Create a list of strings by using a
' collection initializer.
Dim salmons As New List(Of String) From
    {"chinook", "coho", "pink", "sockeye"}

For Each salmon As String In salmons
    Console.Write(salmon & " ")
Next
'Output: chinook coho pink sockeye
```

È possibile utilizzare un [For... Next](../../../visual-basic/language-reference/statements/for-next-statement.md) anziché `For Each` un'istruzione per scorrere una raccolta. Questo è possibile mediante l'accesso agli elementi della raccolta dalla posizione di indice. L'indice degli elementi inizia da 0 e termina in corrispondenza del numero di elementi meno 1.

Nell'esempio seguente l'iterazione negli elementi di una raccolta avviene mediante `For…Next` anziché mediante `For Each`.

```vb
Dim salmons As New List(Of String) From
    {"chinook", "coho", "pink", "sockeye"}

For index = 0 To salmons.Count - 1
    Console.Write(salmons(index) & " ")
Next
'Output: chinook coho pink sockeye
```

Nell'esempio seguente viene rimosso un elemento dalla raccolta specificando l'oggetto da rimuovere.

```vb
' Create a list of strings by using a
' collection initializer.
Dim salmons As New List(Of String) From
    {"chinook", "coho", "pink", "sockeye"}

' Remove an element in the list by specifying
' the object.
salmons.Remove("coho")

For Each salmon As String In salmons
    Console.Write(salmon & " ")
Next
'Output: chinook pink sockeye
```

Nell'esempio seguente vengono rimossi elementi da un elenco generico. Invece `For Each` di una dichiarazione, un [For... Viene](../../../visual-basic/language-reference/statements/for-next-statement.md) utilizzata l'istruzione successiva che scorre in ordine decrescente. Ciò è necessario perché il metodo <xref:System.Collections.Generic.List%601.RemoveAt%2A> fa sì che gli elementi dopo un elemento rimosso abbiano un valore di indice inferiore.

```vb
Dim numbers As New List(Of Integer) From
    {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}

' Remove odd numbers.
For index As Integer = numbers.Count - 1 To 0 Step -1
    If numbers(index) Mod 2 = 1 Then
        ' Remove the element by specifying
        ' the zero-based index in the list.
        numbers.RemoveAt(index)
    End If
Next

' Iterate through the list.
' A lambda expression is placed in the ForEach method
' of the List(T) object.
numbers.ForEach(
    Sub(number) Console.Write(number & " "))
' Output: 0 2 4 6 8
```

Per il tipo di elementi in <xref:System.Collections.Generic.List%601>, è possibile anche definire una classe personalizzata. Nell'esempio seguente la classe `Galaxy` viene usata dall'oggetto <xref:System.Collections.Generic.List%601> definito nel codice.

```vb
Private Sub IterateThroughList()
    Dim theGalaxies As New List(Of Galaxy) From
        {
            New Galaxy With {.Name = "Tadpole", .MegaLightYears = 400},
            New Galaxy With {.Name = "Pinwheel", .MegaLightYears = 25},
            New Galaxy With {.Name = "Milky Way", .MegaLightYears = 0},
            New Galaxy With {.Name = "Andromeda", .MegaLightYears = 3}
        }

    For Each theGalaxy In theGalaxies
        With theGalaxy
            Console.WriteLine(.Name & "  " & .MegaLightYears)
        End With
    Next

    ' Output:
    '  Tadpole  400
    '  Pinwheel  25
    '  Milky Way  0
    '  Andromeda  3
End Sub

Public Class Galaxy
    Public Property Name As String
    Public Property MegaLightYears As Integer
End Class
```

<a name="BKMK_KindsOfCollections"></a>

## <a name="kinds-of-collections"></a>Tipi di raccolte

Molte raccolte comuni vengono fornite da .NET Framework. Ogni tipo di raccolta è progettato per uno scopo specifico.

In questa sezione sono descritte alcune classi di raccolte comuni:

- Classi <xref:System.Collections.Generic>

- Classi <xref:System.Collections.Concurrent>

- Classi <xref:System.Collections>

- Classe `Collection` di Visual Basic

<a name="BKMK_Generic"></a>

### <a name="systemcollectionsgeneric-classes"></a>Classi System.Collections.Generic

È possibile creare una raccolta generica usando una delle classi dello spazio dei nomi <xref:System.Collections.Generic>. Una raccolta generica è utile quando ogni elemento al suo interno presenta lo stesso tipo di dati. Una raccolta generica applica la tipizzazione forte consentendo di aggiungere soltanto i tipi di dati desiderati.

La tabella seguente elenca alcune delle classi di uso frequente dello spazio dei nomi <xref:System.Collections.Generic?displayProperty=nameWithType>:

|Classe|Descrizione|
|---|---|
|<xref:System.Collections.Generic.Dictionary%602>|Rappresenta una raccolta di coppie chiave/valore organizzate in base alla chiave.|
|<xref:System.Collections.Generic.List%601>|Rappresenta un elenco di oggetti accessibile in base all'indice. Fornisce metodi per la ricerca, l'ordinamento e la modifica degli elenchi.|
|<xref:System.Collections.Generic.Queue%601>|Rappresenta una raccolta di oggetti FIFO (First-In First-Out).|
|<xref:System.Collections.Generic.SortedList%602>|Rappresenta una raccolta di coppie chiave/valore ordinate per chiave in base all'implementazione <xref:System.Collections.Generic.IComparer%601> associata.|
|<xref:System.Collections.Generic.Stack%601>|Rappresenta una raccolta di oggetti LIFO (Last-In First-Out).|

Per altre informazioni, vedere [Tipi di raccolte comunemente utilizzate](../../../standard/collections/commonly-used-collection-types.md), [Selezione di una classe Collection](../../../standard/collections/selecting-a-collection-class.md) e <xref:System.Collections.Generic?displayProperty=nameWithType>.

<a name="BKMK_Concurrent"></a>

### <a name="systemcollectionsconcurrent-classes"></a>Classi System.Collections.Concurrent

In .NET Framework 4 o versioni successive le raccolte dello spazio dei nomi <xref:System.Collections.Concurrent> garantiscono operazioni thread-safe efficienti per accedere agli elementi della raccolta da più thread.

Le classi dello spazio dei nomi <xref:System.Collections.Concurrent> devono essere usate in sostituzione dei tipi corrispondenti negli spazi dei nomi <xref:System.Collections.Generic?displayProperty=nameWithType> e <xref:System.Collections?displayProperty=nameWithType> ogni volta che più thread accedono contemporaneamente alla raccolta. Per altre informazioni, vedere [Raccolte thread-safe](../../../standard/collections/thread-safe/index.md) e <xref:System.Collections.Concurrent>.

Alcune classi incluse nello spazio dei nomi <xref:System.Collections.Concurrent> sono <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601> e <xref:System.Collections.Concurrent.ConcurrentStack%601>.

<a name="BKMK_Collections"></a>

### <a name="systemcollections-classes"></a>Classi System.Collections

Le classi dello spazio dei nomi <xref:System.Collections?displayProperty=nameWithType> non archiviano gli elementi come oggetti tipizzati in modo specifico, ma come oggetti di tipo `Object`.

Quando possibile, usare le raccolte generiche degli spazi dei nomi <xref:System.Collections.Generic?displayProperty=nameWithType> o <xref:System.Collections.Concurrent> al posto dei tipi legacy dello spazio dei nomi `System.Collections`.

La tabella seguente elenca alcune classi di uso frequente nello spazio dei nomi `System.Collections`:

|Classe|Descrizione|
|---|---|
|<xref:System.Collections.ArrayList>|Rappresenta una matrice di oggetti le cui dimensioni sono incrementate in modo dinamico in base alle esigenze.|
|<xref:System.Collections.Hashtable>|Rappresenta una raccolta di coppie chiave/valore organizzate in base al codice hash della chiave.|
|<xref:System.Collections.Queue>|Rappresenta una raccolta di oggetti FIFO (First-In First-Out).|
|<xref:System.Collections.Stack>|Rappresenta una raccolta di oggetti LIFO (Last-In First-Out).|

Lo spazio dei nomi <xref:System.Collections.Specialized> offre classi di raccolte fortemente tipizzate e specializzate, ad esempio raccolte di sole stringhe, dizionari ibridi e dizionari a elenchi collegati.

<a name="BKMK_VisualBasic"></a>

### <a name="visual-basic-collection-class"></a>Classe Collection di Visual Basic

È possibile usare la classe <xref:Microsoft.VisualBasic.Collection> di Visual Basic per accedere a un elemento della raccolta usando un indice numerico o una chiave `String`. Per aggiungere elementi a un oggetto raccolta, è possibile specificare o non specificare una chiave. Se si aggiunge un elemento senza una chiave, è necessario usare il relativo indice numerico per accedervi.

La classe `Collection` di Visual Basic archivia tutti gli elementi di tipo `Object`, pertanto è possibile aggiungere un elemento di qualsiasi tipo di dati. Non esiste alcuna misura per impedire l'aggiunta di tipi di dati non appropriati.

Quando si usa la classe `Collection` di Visual Basic, il primo elemento di una raccolta ha indice 1. Questo comportamento è diverso rispetto alle classi Collection di .NET Framework, per cui l'indice iniziale è 0.

Quando possibile, usare le raccolte generiche negli spazi dei nomi <xref:System.Collections.Generic?displayProperty=nameWithType> o <xref:System.Collections.Concurrent> al posto della classe `Collection` di Visual Basic.

Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Collection>.

<a name="BKMK_KeyValuePairs"></a>

## <a name="implementing-a-collection-of-keyvalue-pairs"></a>Implementazione di una raccolta di coppie chiave/valore

La raccolta generica <xref:System.Collections.Generic.Dictionary%602> consente di accedere agli elementi di una raccolta usando la chiave di ogni elemento. Ogni aggiunta al dizionario è costituita da un valore e dalla chiave associata corrispondente. Il recupero di un valore tramite la relativa chiave è un'operazione veloce, perché la classe `Dictionary` viene implementata come tabella hash.

L'esempio seguente crea una raccolta `Dictionary` ed esegue l'iterazione nel dizionario usando un'istruzione `For Each`.

```vb
Private Sub IterateThroughDictionary()
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()

    For Each kvp As KeyValuePair(Of String, Element) In elements
        Dim theElement As Element = kvp.Value

        Console.WriteLine("key: " & kvp.Key)
        With theElement
            Console.WriteLine("values: " & .Symbol & " " &
                .Name & " " & .AtomicNumber)
        End With
    Next
End Sub

Private Function BuildDictionary() As Dictionary(Of String, Element)
    Dim elements As New Dictionary(Of String, Element)

    AddToDictionary(elements, "K", "Potassium", 19)
    AddToDictionary(elements, "Ca", "Calcium", 20)
    AddToDictionary(elements, "Sc", "Scandium", 21)
    AddToDictionary(elements, "Ti", "Titanium", 22)

    Return elements
End Function

Private Sub AddToDictionary(ByVal elements As Dictionary(Of String, Element),
ByVal symbol As String, ByVal name As String, ByVal atomicNumber As Integer)
    Dim theElement As New Element

    theElement.Symbol = symbol
    theElement.Name = name
    theElement.AtomicNumber = atomicNumber

    elements.Add(Key:=theElement.Symbol, value:=theElement)
End Sub

Public Class Element
    Public Property Symbol As String
    Public Property Name As String
    Public Property AtomicNumber As Integer
End Class
```

Per usare invece un inizializzatore di raccolta per compilare la raccolta `Dictionary`, è possibile sostituire i metodi `BuildDictionary` e `AddToDictionary` con il metodo seguente.

```vb
Private Function BuildDictionary2() As Dictionary(Of String, Element)
    Return New Dictionary(Of String, Element) From
        {
            {"K", New Element With
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},
            {"Ca", New Element With
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},
            {"Sc", New Element With
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},
            {"Ti", New Element With
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}
        }
End Function
```

L'esempio seguente usa il metodo <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> e la proprietà <xref:System.Collections.Generic.Dictionary%602.Item%2A> di `Dictionary` per trovare rapidamente un elemento in base alla chiave. La `Item` proprietà consente di accedere `elements` a un `elements(symbol)` elemento nell'insieme utilizzando il codice in Visual Basic.

```vb
Private Sub FindInDictionary(ByVal symbol As String)
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()

    If elements.ContainsKey(symbol) = False Then
        Console.WriteLine(symbol & " not found")
    Else
        Dim theElement = elements(symbol)
        Console.WriteLine("found: " & theElement.Name)
    End If
End Sub
```

L'esempio seguente usa invece il metodo <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> per individuare rapidamente un elemento in base alla chiave.

```vb
Private Sub FindInDictionary2(ByVal symbol As String)
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()

    Dim theElement As Element = Nothing
    If elements.TryGetValue(symbol, theElement) = False Then
        Console.WriteLine(symbol & " not found")
    Else
        Console.WriteLine("found: " & theElement.Name)
    End If
End Sub
```

<a name="BKMK_LINQ"></a>

## <a name="using-linq-to-access-a-collection"></a>Uso di LINQ per accedere a una raccolta

È possibile usare LINQ (Language-Integrated Query) per accedere alle raccolte. Le query LINQ forniscono funzionalità di filtro, ordinamento e raggruppamento. Per ulteriori informazioni, vedere [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).

Nell'esempio seguente viene eseguita una query LINQ su un oggetto `List` generico. La query LINQ restituisce una raccolta diversa che contiene i risultati.

```vb
Private Sub ShowLINQ()
    Dim elements As List(Of Element) = BuildList()

    ' LINQ Query.
    Dim subset = From theElement In elements
                  Where theElement.AtomicNumber < 22
                  Order By theElement.Name

    For Each theElement In subset
        Console.WriteLine(theElement.Name & " " & theElement.AtomicNumber)
    Next

    ' Output:
    '  Calcium 20
    '  Potassium 19
    '  Scandium 21
End Sub

Private Function BuildList() As List(Of Element)
    Return New List(Of Element) From
        {
            {New Element With
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},
            {New Element With
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},
            {New Element With
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},
            {New Element With
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}
        }
End Function

Public Class Element
    Public Property Symbol As String
    Public Property Name As String
    Public Property AtomicNumber As Integer
End Class
```

<a name="BKMK_Sorting"></a>

## <a name="sorting-a-collection"></a>Ordinamento di una raccolta

L'esempio seguente illustra una procedura per ordinare una raccolta. Nell'esempio vengono ordinate le istanze della classe `Car` archiviate in un oggetto <xref:System.Collections.Generic.List%601>. La classe `Car` implementa l'interfaccia <xref:System.IComparable%601>, che richiede l'implementazione del metodo <xref:System.IComparable%601.CompareTo%2A>.

Ogni chiamata al metodo <xref:System.IComparable%601.CompareTo%2A> effettua un confronto unico che viene usato per l'ordinamento. Il codice scritto dall'utente presente nel metodo `CompareTo` restituisce un valore per ogni confronto dell'oggetto corrente con un altro oggetto. Il valore restituito è minore di zero se l'oggetto corrente è inferiore all'altro oggetto, maggiore di zero se l'oggetto corrente è superiore all'altro oggetto e zero se sono uguali. In questo modo è possibile definire nel codice i criteri di maggiore, minore e uguale.

Nel metodo `ListCars` l'istruzione `cars.Sort()` ordina l'elenco. Questa chiamata al metodo <xref:System.Collections.Generic.List%601.Sort%2A> di <xref:System.Collections.Generic.List%601> determina la chiamata automatica al metodo `CompareTo` per gli oggetti `Car` in `List`.

```vb
Public Sub ListCars()

    ' Create some new cars.
    Dim cars As New List(Of Car) From
    {
        New Car With {.Name = "car1", .Color = "blue", .Speed = 20},
        New Car With {.Name = "car2", .Color = "red", .Speed = 50},
        New Car With {.Name = "car3", .Color = "green", .Speed = 10},
        New Car With {.Name = "car4", .Color = "blue", .Speed = 50},
        New Car With {.Name = "car5", .Color = "blue", .Speed = 30},
        New Car With {.Name = "car6", .Color = "red", .Speed = 60},
        New Car With {.Name = "car7", .Color = "green", .Speed = 50}
    }

    ' Sort the cars by color alphabetically, and then by speed
    ' in descending order.
    cars.Sort()

    ' View all of the cars.
    For Each thisCar As Car In cars
        Console.Write(thisCar.Color.PadRight(5) & " ")
        Console.Write(thisCar.Speed.ToString & " ")
        Console.Write(thisCar.Name)
        Console.WriteLine()
    Next

    ' Output:
    '  blue  50 car4
    '  blue  30 car5
    '  blue  20 car1
    '  green 50 car7
    '  green 10 car3
    '  red   60 car6
    '  red   50 car2
End Sub

Public Class Car
    Implements IComparable(Of Car)

    Public Property Name As String
    Public Property Speed As Integer
    Public Property Color As String

    Public Function CompareTo(ByVal other As Car) As Integer _
        Implements System.IComparable(Of Car).CompareTo
        ' A call to this method makes a single comparison that is
        ' used for sorting.

        ' Determine the relative order of the objects being compared.
        ' Sort by color alphabetically, and then by speed in
        ' descending order.

        ' Compare the colors.
        Dim compare As Integer
        compare = String.Compare(Me.Color, other.Color, True)

        ' If the colors are the same, compare the speeds.
        If compare = 0 Then
            compare = Me.Speed.CompareTo(other.Speed)

            ' Use descending order for speed.
            compare = -compare
        End If

        Return compare
    End Function
End Class
```

<a name="BKMK_CustomCollection"></a>

## <a name="defining-a-custom-collection"></a>Definizione di una raccolta personalizzata

È possibile definire una raccolta implementando l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Collections.IEnumerable>. Per ulteriori informazioni, vedere [Enumerazione di una raccolta](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hwyysy67(v=vs.100)).

Sebbene sia possibile definire una raccolta personalizzata, in genere è preferibile usare le raccolte incluse in .NET Framework, descritte in [Tipi di raccolte](#kinds-of-collections) in precedenza in questo argomento.

L'esempio seguente definisce una classe di raccolte personalizzata denominata `AllColors`. Questa classe implementa l'interfaccia <xref:System.Collections.IEnumerable> che richiede l'implementazione del metodo <xref:System.Collections.IEnumerable.GetEnumerator%2A>.

Il metodo `GetEnumerator` restituisce un'istanza della classe `ColorEnumerator`. `ColorEnumerator` implementa l'interfaccia <xref:System.Collections.IEnumerator> che richiede l'implementazione della proprietà <xref:System.Collections.IEnumerator.Current%2A> e dei metodi <xref:System.Collections.IEnumerator.MoveNext%2A> e <xref:System.Collections.IEnumerator.Reset%2A>.

```vb
Public Sub ListColors()
    Dim colors As New AllColors()

    For Each theColor As Color In colors
        Console.Write(theColor.Name & " ")
    Next
    Console.WriteLine()
    ' Output: red blue green
End Sub

' Collection class.
Public Class AllColors
    Implements System.Collections.IEnumerable

    Private _colors() As Color =
    {
        New Color With {.Name = "red"},
        New Color With {.Name = "blue"},
        New Color With {.Name = "green"}
    }

    Public Function GetEnumerator() As System.Collections.IEnumerator _
        Implements System.Collections.IEnumerable.GetEnumerator

        Return New ColorEnumerator(_colors)

        ' Instead of creating a custom enumerator, you could
        ' use the GetEnumerator of the array.
        'Return _colors.GetEnumerator
    End Function

    ' Custom enumerator.
    Private Class ColorEnumerator
        Implements System.Collections.IEnumerator

        Private _colors() As Color
        Private _position As Integer = -1

        Public Sub New(ByVal colors() As Color)
            _colors = colors
        End Sub

        Public ReadOnly Property Current() As Object _
            Implements System.Collections.IEnumerator.Current
            Get
                Return _colors(_position)
            End Get
        End Property

        Public Function MoveNext() As Boolean _
            Implements System.Collections.IEnumerator.MoveNext
            _position += 1
            Return (_position < _colors.Length)
        End Function

        Public Sub Reset() Implements System.Collections.IEnumerator.Reset
            _position = -1
        End Sub
    End Class
End Class

' Element class.
Public Class Color
    Public Property Name As String
End Class
```

<a name="BKMK_Iterators"></a>

## <a name="iterators"></a>Iterators

Un *iteratore* viene usato per eseguire un'iterazione personalizzata in una raccolta. Un iteratore può essere un metodo o una funzione di accesso `get`. Un iteratore utilizza un [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) istruzione per restituire ogni elemento della raccolta uno alla volta.

Chiamare un iteratore utilizzando un [For Each... Prossima](../../../visual-basic/language-reference/statements/for-each-next-statement.md) dichiarazione. Ogni iterazione del ciclo `For Each` chiama l'iteratore. Quando si raggiunge un'istruzione `Yield` nell'iteratore, viene restituita un'espressione e viene mantenuta la posizione corrente nel codice. L'esecuzione viene ripresa a partire da quella posizione la volta successiva che viene chiamato l'iteratore.

Per ulteriori informazioni, vedere [Iteratori (Visual Basic)](../../../visual-basic/programming-guide/concepts/iterators.md).

Nell'esempio seguente viene usato un metodo iteratore. Il metodo iteratore ha un'istruzione `Yield` che si trova all'interno di un [For... Loop successivo.](../../../visual-basic/language-reference/statements/for-next-statement.md) Nel metodo `ListEvenNumbers` ogni iterazione del corpo dell'istruzione `For Each` crea una chiamata al metodo iteratore, che procede all'istruzione `Yield` successiva.

```vb
Public Sub ListEvenNumbers()
    For Each number As Integer In EvenSequence(5, 18)
        Console.Write(number & " ")
    Next
    Console.WriteLine()
    ' Output: 6 8 10 12 14 16 18
End Sub

Private Iterator Function EvenSequence(
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _
As IEnumerable(Of Integer)

' Yield even numbers in the range.
    For number = firstNumber To lastNumber
        If number Mod 2 = 0 Then
            Yield number
        End If
    Next
End Function
```

## <a name="see-also"></a>Vedere anche

- [Inizializzatori di raccolta](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Concetti di programmazione (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)
- [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [LINQ to Objects (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- [Parallel LINQ (PLINQ)](../../../standard/parallel-programming/introduction-to-plinq.md)
- [Raccolte e strutture di dati](../../../standard/collections/index.md)
- [Selezione di una classe Collection](../../../standard/collections/selecting-a-collection-class.md)
- [Confronti e ordinamenti all'interno delle raccolte](../../../standard/collections/comparisons-and-sorts-within-collections.md)
- [Quando utilizzare raccolte genericheWhen to Use Generic Collections](../../../standard/collections/when-to-use-generic-collections.md)

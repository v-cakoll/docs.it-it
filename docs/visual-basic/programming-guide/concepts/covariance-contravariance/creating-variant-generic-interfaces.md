---
title: Creazione di interfacce generiche variant
ms.date: 07/20/2015
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
ms.openlocfilehash: 884349159d2738d8481b217f9dab383483616f2b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400642"
---
# <a name="creating-variant-generic-interfaces-visual-basic"></a>Creazione di interfacce generiche varianti (Visual Basic)

È possibile dichiarare parametri di tipo generico nelle interfacce come covarianti o controvarianti. La *covarianza* consente ai metodi di interfaccia di avere tipi restituiti più derivati rispetto a quelli definiti dai parametri di tipo generico. La *controvarianza* consente ai metodi di interfaccia di avere tipi di argomenti meno derivati rispetto a quelli specificati dai parametri generici. Un'interfaccia generica che ha parametri di tipo generico varianti e covarianti è definita *variante*.

> [!NOTE]
> In .NET framework 4 è stato introdotto il supporto della varianza per diverse interfacce generiche esistenti. Per l'elenco delle interfacce variant nella .NET Framework, vedere [varianza nelle interfacce generiche (Visual Basic)](variance-in-generic-interfaces.md).

## <a name="declaring-variant-generic-interfaces"></a>Dichiarazione delle interfacce generiche varianti

È possibile dichiarare le interfacce generiche varianti usando le parole chiave `in` e `out` per i parametri di tipo generico.

> [!IMPORTANT]
> `ByRef`i parametri in Visual Basic non possono essere varianti. Anche i tipi di valore non supportano la varianza.

È possibile dichiarare un parametro di tipo generico covariante usando la parola chiave `out`. Il tipo covariante deve soddisfare le condizioni seguenti:

- Il tipo viene usato solo come tipo restituito dei metodi di interfaccia e non come tipo di argomenti del metodo. Come illustrato nell'esempio seguente, il tipo `R` viene dichiarato covariante.

    ```vb
    Interface ICovariant(Of Out R)
        Function GetSomething() As R
        ' The following statement generates a compiler error.
        ' Sub SetSomething(ByVal sampleArg As R)
    End Interface
    ```

    Esiste un'eccezione a questa regola. Se si usa un delegato generico controvariante come parametro di metodo, è possibile usare il tipo come parametro di tipo generico per il delegato. Questo aspetto è illustrato nell'esempio seguente dal tipo `R`. Per altre informazioni, vedere [varianza nei delegati (Visual Basic)](variance-in-delegates.md) e [uso della varianza per i delegati generici Func e Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).

    ```vb
    Interface ICovariant(Of Out R)
        Sub DoSomething(ByVal callback As Action(Of R))
    End Interface
    ```

- Il tipo non viene usato come vincolo generico per i metodi di interfaccia. Questa situazione è illustrata nel codice seguente.

    ```vb
    Interface ICovariant(Of Out R)
        ' The following statement generates a compiler error
        ' because you can use only contravariant or invariant types
        ' in generic constraints.
        ' Sub DoSomething(Of T As R)()
    End Interface
    ```

È possibile dichiarare un parametro di tipo generico controvariante usando la parola chiave `in`. Il tipo controvariante può essere usato solo come tipo di argomenti del metodo e non come tipo restituito dei metodi di interfaccia. Il tipo controvariante può essere usato anche per i vincoli generici. Il codice seguente illustra come dichiarare un'interfaccia controvariante e usare un vincolo generico per uno dei relativi metodi.

```vb
Interface IContravariant(Of In A)
    Sub SetSomething(ByVal sampleArg As A)
    Sub DoSomething(Of T As A)()
    ' The following statement generates a compiler error.
    ' Function GetSomething() As A
End Interface
```

È anche possibile supportare sia la covarianza che la controvarianza nella stessa interfaccia, ma per parametri di tipo diverso, come illustrato nell'esempio di codice seguente.

```vb
Interface IVariant(Of Out R, In A)
    Function GetSomething() As R
    Sub SetSomething(ByVal sampleArg As A)
    Function GetSetSomething(ByVal sampleArg As A) As R
End Interface
```

In Visual Basic non è possibile dichiarare gli eventi nelle interfacce variant senza specificare il tipo di delegato. Inoltre, un'interfaccia variant non può includere classi, enumerazioni o strutture annidate, ma può avere interfacce nidificate. Questa situazione è illustrata nel codice seguente.

```vb
Interface ICovariant(Of Out R)
    ' The following statement generates a compiler error.
    ' Event SampleEvent()
    ' The following statement specifies the delegate type and
    ' does not generate an error.
    Event AnotherEvent As EventHandler

    ' The following statements generate compiler errors,
    ' because a variant interface cannot have
    ' nested enums, classes, or structures.

    'Enum SampleEnum : test : End Enum
    'Class SampleClass : End Class
    'Structure SampleStructure : Dim value As Integer : End Structure

    ' Variant interfaces can have nested interfaces.
    Interface INested : End Interface
End Interface
```

## <a name="implementing-variant-generic-interfaces"></a>Implementazione di interfacce generiche varianti

Implementare le interfacce generiche varianti nelle classi usando la stessa sintassi usata per le interfacce invariabili. L'esempio di codice seguente illustra come implementare un'interfaccia covariante in una classe generica.

```vb
Interface ICovariant(Of Out R)
    Function GetSomething() As R
End Interface

Class SampleImplementation(Of R)
    Implements ICovariant(Of R)
    Public Function GetSomething() As R _
    Implements ICovariant(Of R).GetSomething
        ' Some code.
    End Function
End Class
```

Le classi che implementano le interfacce varianti sono invariabili. Si consideri il codice di esempio seguente.

```vb
 The interface is covariant.
Dim ibutton As ICovariant(Of Button) =
    New SampleImplementation(Of Button)
Dim iobj As ICovariant(Of Object) = ibutton

' The class is invariant.
Dim button As SampleImplementation(Of Button) =
    New SampleImplementation(Of Button)
' The following statement generates a compiler error
' because classes are invariant.
' Dim obj As SampleImplementation(Of Object) = button
```

## <a name="extending-variant-generic-interfaces"></a>Estensione di interfacce generiche varianti

Quando si estende un'interfaccia generica variante è necessario usare le parole chiave `in` e `out` per specificare in modo esplicito se l'interfaccia derivata supporta la varianza. Il compilatore non deduce la varianza dall'interfaccia che viene estesa. Si considerino ad esempio le interfacce seguenti.

```vb
Interface ICovariant(Of Out T)
End Interface

Interface IInvariant(Of T)
    Inherits ICovariant(Of T)
End Interface

Interface IExtCovariant(Of Out T)
    Inherits ICovariant(Of T)
End Interface
```

Nell' `Invariant(Of T)` interfaccia, il parametro di tipo generico `T` è invariante, mentre nel `IExtCovariant (Of Out T)` parametro di tipo è covariante, sebbene entrambe le interfacce estendano la stessa interfaccia. La stessa regola viene applicata ai parametri di tipo generico controvarianti.

È possibile creare un'interfaccia che estende sia l'interfaccia in cui il parametro di tipo generico `T` è covariante, sia l'interfaccia in cui è controvariante se nell'interfaccia che viene estesa il parametro di tipo generico `T` è invariabile, come illustra l'esempio di codice riportato di seguito.

```vb
Interface ICovariant(Of Out T)
End Interface

Interface IContravariant(Of In T)
End Interface

Interface IInvariant(Of T)
    Inherits ICovariant(Of T), IContravariant(Of T)
End Interface
```

Tuttavia, se un parametro di tipo generico `T` è dichiarato covariante in una sola interfaccia, non è possibile dichiararlo controvariante nell'interfaccia da estendere o viceversa, come illustra l'esempio di codice riportato di seguito.

```vb
Interface ICovariant(Of Out T)
End Interface

' The following statements generate a compiler error.
' Interface ICoContraVariant(Of In T)
'     Inherits ICovariant(Of T)
' End Interface
```

### <a name="avoiding-ambiguity"></a>Evitare le ambiguità

Quando si implementano le interfacce generiche varianti, la varianza può talvolta causare ambiguità. Questa evenienza deve essere evitata.

Ad esempio, se si implementa in modo esplicito la stessa interfaccia generica variante con parametri di tipo generico diversi in una sola classe, è possibile creare ambiguità. Il compilatore non genera un errore in questo caso, ma non viene specificato quale implementazione dell'interfaccia verrà scelta in fase di esecuzione. Questo potrebbe causare bug nel codice. Si prenda in considerazione il seguente esempio di codice.

> [!NOTE]
> Con `Option Strict Off` , Visual Basic genera un avviso del compilatore quando è presente un'implementazione ambigua dell'interfaccia. Con `Option Strict On` , Visual Basic genera un errore del compilatore.

```vb
' Simple class hierarchy.
Class Animal
End Class

Class Cat
    Inherits Animal
End Class

Class Dog
    Inherits Animal
End Class

' This class introduces ambiguity
' because IEnumerable(Of Out T) is covariant.
Class Pets
    Implements IEnumerable(Of Cat), IEnumerable(Of Dog)

    Public Function GetEnumerator() As IEnumerator(Of Cat) _
        Implements IEnumerable(Of Cat).GetEnumerator
        Console.WriteLine("Cat")
        ' Some code.
    End Function

    Public Function GetEnumerator1() As IEnumerator(Of Dog) _
        Implements IEnumerable(Of Dog).GetEnumerator
        Console.WriteLine("Dog")
        ' Some code.
    End Function

    Public Function GetEnumerator2() As IEnumerator _
        Implements IEnumerable.GetEnumerator
        ' Some code.
    End Function
End Class

Sub Main()
    Dim pets As IEnumerable(Of Animal) = New Pets()
    pets.GetEnumerator()
End Sub
```

In questo esempio non viene specificato in che modo il metodo `pets.GetEnumerator` sceglie tra `Cat` e `Dog`. Ciò potrebbe causare problemi nel codice.

## <a name="see-also"></a>Vedere anche

- [Varianza nelle interfacce generiche (Visual Basic)](variance-in-generic-interfaces.md)
- [Utilizzo della varianza per i delegati generici Func e Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md)

---
title: Varianza nei delegati
ms.date: 07/20/2015
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
ms.openlocfilehash: 86ea9f3f744381bcff71a88e9d88485cafa4a568
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375616"
---
# <a name="variance-in-delegates-visual-basic"></a>Varianza nei delegati (Visual Basic)

.NET Framework 3,5 ha introdotto il supporto della varianza per le firme di metodo corrispondenti con tipi delegati in tutti i delegati in C# e Visual Basic. Ciò significa che è possibile assegnare ai delegati non solo i metodi con firme corrispondenti, ma anche i metodi che restituiscono più tipi derivati (covarianza) o accettano parametri con meno tipi derivati (controvarianza) rispetto a quelli specificati dal tipo di delegato. Sono inclusi sia i delegati generici che quelli non generici.

Ad esempio, si consideri il codice seguente, che ha due classi e due delegati: generico e non generico.

```vb
Public Class First
End Class

Public Class Second
    Inherits First
End Class

Public Delegate Function SampleDelegate(ByVal a As Second) As First
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R
```

Quando si creano i delegati dei tipi `SampleDelegate` o `SampleDelegate(Of A, R)` è possibile assegnare uno qualsiasi dei metodi seguenti ai delegati.

```vb
' Matching signature.
Public Shared Function ASecondRFirst(
    ByVal second As Second) As First
    Return New First()
End Function

' The return type is more derived.
Public Shared Function ASecondRSecond(
    ByVal second As Second) As Second
    Return New Second()
End Function

' The argument type is less derived.
Public Shared Function AFirstRFirst(
    ByVal first As First) As First
    Return New First()
End Function

' The return type is more derived
' and the argument type is less derived.
Public Shared Function AFirstRSecond(
    ByVal first As First) As Second
    Return New Second()
End Function
```

L'esempio di codice seguente viene illustra la conversione implicita tra la firma del metodo e il tipo di delegato.

```vb
' Assigning a method with a matching signature
' to a non-generic delegate. No conversion is necessary.
Dim dNonGeneric As SampleDelegate = AddressOf ASecondRFirst
' Assigning a method with a more derived return type
' and less derived argument type to a non-generic delegate.
' The implicit conversion is used.
Dim dNonGenericConversion As SampleDelegate = AddressOf AFirstRSecond

' Assigning a method with a matching signature to a generic delegate.
' No conversion is necessary.
Dim dGeneric As SampleGenericDelegate(Of Second, First) = AddressOf ASecondRFirst
' Assigning a method with a more derived return type
' and less derived argument type to a generic delegate.
' The implicit conversion is used.
Dim dGenericConversion As SampleGenericDelegate(Of Second, First) = AddressOf AFirstRSecond
```

Per altri esempi, vedere [uso della varianza nei delegati (Visual Basic)](using-variance-in-delegates.md) e [uso della varianza per i delegati generici Func e Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).

## <a name="variance-in-generic-type-parameters"></a>Varianza nei parametri di tipo generico

In .NET Framework 4 e versioni successive è possibile abilitare la conversione implicita tra delegati, in modo che i delegati generici con tipi diversi specificati da parametri di tipo generico possano essere assegnati tra loro, se i tipi vengono ereditati l'uno dall'altro come richiesto dalla varianza.

Per abilitare la conversione implicita, è necessario dichiarare esplicitamente i parametri generici in un delegato come covariante o controvariante usando la parola chiave `in` o `out`.

L'esempio di codice seguente illustra come creare un delegato con un parametro di tipo generico covariante.

```vb
' Type T is declared covariant by using the out keyword.
Public Delegate Function SampleGenericDelegate(Of Out T)() As T
Sub Test()
    Dim dString As SampleGenericDelegate(Of String) = Function() " "
    ' You can assign delegates to each other,
    ' because the type T is declared covariant.
    Dim dObject As SampleGenericDelegate(Of Object) = dString
End Sub
```

Se si usa solo il supporto della varianza per la corrispondenza delle firme del metodo con i tipi delegati e non si usano le parole chiave `in` e `out`, è possibile che in alcuni casi si possano creare istanze di delegati con metodi o espressioni lambda identici, ma non è possibile assegnare un delegato a un altro.

Nell'esempio di codice seguente `SampleGenericDelegate(Of String)` non è possibile convertire in modo esplicito in `SampleGenericDelegate(Of Object)` , sebbene `String` erediti `Object` . È possibile correggere questo problema contrassegnando il parametro generico `T` con la parola chiave `out`.

```vb
Public Delegate Function SampleGenericDelegate(Of T)() As T
Sub Test()
    Dim dString As SampleGenericDelegate(Of String) = Function() " "

    ' You can assign the dObject delegate
    ' to the same lambda expression as dString delegate
    ' because of the variance support for
    ' matching method signatures with delegate types.
    Dim dObject As SampleGenericDelegate(Of Object) = Function() " "

    ' The following statement generates a compiler error
    ' because the generic type T is not marked as covariant.
    ' Dim dObject As SampleGenericDelegate(Of Object) = dString

End Sub
```

### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a>Delegati generici con parametri di tipo variante in .NET Framework

In .NET framework 4 è stato introdotto il supporto della varianza per i parametri di tipo generico in diversi delegati generici esistenti:

- Delegati `Action` dallo spazio dei nomi <xref:System>, ad esempio <xref:System.Action%601> e <xref:System.Action%602>

- Delegati `Func` dallo spazio dei nomi <xref:System>, ad esempio <xref:System.Func%601> e <xref:System.Func%602>

- Delegato <xref:System.Predicate%601>.

- Delegato <xref:System.Comparison%601>.

- Delegato <xref:System.Converter%602>.

Per ulteriori informazioni ed esempi, vedere [utilizzo della varianza per i delegati generici Func e Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).

### <a name="declaring-variant-type-parameters-in-generic-delegates"></a>Dichiarare parametri di tipo variante nei delegati generici

Se un delegato generico ha parametri di tipo generico covariante o controvariante, può essere indicato come un *delegato generico variante*.

È possibile dichiarare un parametro di tipo generico covariante in un delegato generico usando la parola chiave `out`. Il tipo covariante può essere usato solo come tipo restituito del metodo e non come tipo di argomenti del metodo. Nell'esempio di codice seguente viene illustrato come dichiarare un delegato generico covariante.

```vb
Public Delegate Function DCovariant(Of Out R)() As R
```

È possibile dichiarare un parametro di tipo generico controvariante in un delegato generico usando la parola chiave `in`. Il tipo controvariante può essere usato solo come tipo di argomenti del metodo e non come tipo restituito del metodo. Nell'esempio di codice seguente viene illustrato come dichiarare un delegato generico controvariante.

```vb
Public Delegate Sub DContravariant(Of In A)(ByVal a As A)
```

> [!IMPORTANT]
> `ByRef`i parametri in Visual Basic non possono essere contrassegnati come Variant.

È anche possibile supportare sia la varianza che la covarianza nello stesso delegato, ma per parametri di tipo diverso. come illustrato nell'esempio seguente.

```vb
Public Delegate Function DVariant(Of In A, Out R)(ByVal a As A) As R
```

### <a name="instantiating-and-invoking-variant-generic-delegates"></a>Creare un'istanza e richiamare delegati generici varianti

È possibile creare un'istanza e richiamare delegati varianti con la stessa procedura con cui si crea un'istanza e si richiamano i delegati invariabili. Nell'esempio seguente viene creata un'istanza del delegato da un'espressione lambda.

```vb
Dim dvariant As DVariant(Of String, String) = Function(str) str + " "
dvariant("test")
```

### <a name="combining-variant-generic-delegates"></a>Combinare delegati generici varianti

È consigliabile non combinare i delegati varianti. Il metodo <xref:System.Delegate.Combine%2A> non supporta la conversione dei delegati varianti e prevede che i delegati siano esattamente dello stesso tipo. Questo può causare un'eccezione in fase di esecuzione quando si combinano delegati usando il <xref:System.Delegate.Combine%2A> Metodo (in c# e Visual Basic) o usando l' `+` operatore (in c#), come illustrato nell'esempio di codice seguente.

```vb
Dim actObj As Action(Of Object) = Sub(x) Console.WriteLine("object: {0}", x)
Dim actStr As Action(Of String) = Sub(x) Console.WriteLine("string: {0}", x)

' The following statement throws an exception at run time.
' Dim actCombine = [Delegate].Combine(actStr, actObj)
```

## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a>Varianza nei parametri di tipo generico per tipi di valore e riferimento

La varianza per i parametri di tipo generico è supportata solo per i tipi di riferimento. Ad esempio, `DVariant(Of Int)` non può essere convertito in modo implicito in `DVariant(Of Object)` o `DVariant(Of Long)` , perché Integer è un tipo valore.

L'esempio seguente dimostra che la varianza nei parametri di tipo generico non è supportata per i tipi di valore.

```vb
' The type T is covariant.
Public Delegate Function DVariant(Of Out T)() As T
' The type T is invariant.
Public Delegate Function DInvariant(Of T)() As T
Sub Test()
    Dim i As Integer = 0
    Dim dInt As DInvariant(Of Integer) = Function() i
    Dim dVariantInt As DVariant(Of Integer) = Function() i

    ' All of the following statements generate a compiler error
    ' because type variance in generic parameters is not supported
    ' for value types, even if generic type parameters are declared variant.
    ' Dim dObject As DInvariant(Of Object) = dInt
    ' Dim dLong As DInvariant(Of Long) = dInt
    ' Dim dVariantObject As DInvariant(Of Object) = dInt
    ' Dim dVariantLong As DInvariant(Of Long) = dInt
End Sub
```

## <a name="relaxed-delegate-conversion-in-visual-basic"></a>Conversione di delegati rilassati in Visual Basic

La conversione di un delegato rilassato consente una maggiore flessibilità nelle firme dei metodi corrispondenti con i tipi delegati. Ad esempio, consente di omettere le specifiche dei parametri e di omettere i valori restituiti della funzione quando si assegna un metodo a un delegato. Per ulteriori informazioni, vedere [conversione di un delegato rilassato](../../language-features/delegates/relaxed-delegate-conversion.md).

## <a name="see-also"></a>Vedere anche

- [Generics](../../../../standard/generics/index.md)
- [Utilizzo della varianza per i delegati generici Func e Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md)

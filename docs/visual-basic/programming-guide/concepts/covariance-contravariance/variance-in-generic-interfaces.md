---
title: Varianza nelle interfacce generiche
ms.date: 07/20/2015
ms.assetid: cf4096d0-4bb3-45a9-9a6b-f01e29a60333
ms.openlocfilehash: df28a9f24518f24d1be89acba726da7dfbbf9570
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375590"
---
# <a name="variance-in-generic-interfaces-visual-basic"></a>Varianza nelle interfacce generiche (Visual Basic)

In .NET framework 4 è stato introdotto il supporto della varianza per diverse interfacce generiche esistenti. Il supporto della varianza consente la conversione implicita delle classi che implementano tali interfacce. Le interfacce seguenti sono ora varianti:

- <xref:System.Collections.Generic.IEnumerable%601> (T è covariante)

- <xref:System.Collections.Generic.IEnumerator%601> (T è covariante)

- <xref:System.Linq.IQueryable%601> (T è covariante)

- <xref:System.Linq.IGrouping%602> (`TKey` e `TElement` sono covarianti)

- <xref:System.Collections.Generic.IComparer%601> (T è controvariante)

- <xref:System.Collections.Generic.IEqualityComparer%601> (T è controvariante)

- <xref:System.IComparable%601> (T è controvariante)

La covarianza consente a un metodo di avere un tipo restituito più derivato rispetto a quello definito dal parametro di tipo generico dell'interfaccia. Per illustrare la funzionalità di covarianza, considerare le seguenti interfacce generiche: `IEnumerable(Of Object)` e `IEnumerable(Of String)`. L'interfaccia `IEnumerable(Of String)` non eredita l'interfaccia`IEnumerable(Of Object)`. Tuttavia, il tipo `String` eredita il tipo `Object` e in alcuni casi è opportuno assegnare gli oggetti di ogni interfaccia all'altra. Vedere il codice di esempio seguente.

```vb
Dim strings As IEnumerable(Of String) = New List(Of String)
Dim objects As IEnumerable(Of Object) = strings
```

Nelle versioni precedenti del .NET Framework, questo codice causa un errore di compilazione in Visual Basic con `Option Strict On` . Ora è invece possibile usare `strings` anziché `objects`, come illustrato nell'esempio precedente, poiché l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> è covariante.

La controvarianza consente a un metodo di avere tipi di argomenti meno derivati rispetto a quelli specificati dal parametro generico dell'interfaccia. Per illustrare la controvarianza, si supponga di aver creato una classe `BaseComparer` per confrontare le istanze della classe `BaseClass`. La classe `BaseComparer` implementa l'interfaccia `IEqualityComparer(Of BaseClass)`. Poiché l'interfaccia `BaseClass` è ora controvariante, è possibile usare <xref:System.Collections.Generic.IEqualityComparer%601> per confrontare le istanze delle classi che ereditano la classe `BaseComparer`. Vedere il codice di esempio seguente.

```vb
' Simple hierarchy of classes.
Class BaseClass
End Class

Class DerivedClass
    Inherits BaseClass
End Class

' Comparer class.
Class BaseComparer
    Implements IEqualityComparer(Of BaseClass)

    Public Function Equals1(ByVal x As BaseClass,
                            ByVal y As BaseClass) As Boolean _
                            Implements IEqualityComparer(Of BaseClass).Equals
        Return (x.Equals(y))
    End Function

    Public Function GetHashCode1(ByVal obj As BaseClass) As Integer _
        Implements IEqualityComparer(Of BaseClass).GetHashCode
        Return obj.GetHashCode
    End Function
End Class
Sub Test()
    Dim baseComparer As IEqualityComparer(Of BaseClass) = New BaseComparer
    ' Implicit conversion of IEqualityComparer(Of BaseClass) to
    ' IEqualityComparer(Of DerivedClass).
    Dim childComparer As IEqualityComparer(Of DerivedClass) = baseComparer
End Sub
```

Per altri esempi, vedere [uso della varianza nelle interfacce per le raccolte generiche (Visual Basic)](using-variance-in-interfaces-for-generic-collections.md).

La varianza nelle interfacce generiche è supportata solo per i tipi di riferimento. I tipi di valore non supportano la varianza. Ad esempio, non è possibile convertire `IEnumerable(Of Integer)` in modo implicito in `IEnumerable(Of Object)` perché i valori integer sono rappresentati da un tipo di valore.

```vb
Dim integers As IEnumerable(Of Integer) = New List(Of Integer)
' The following statement generates a compiler error
' with Option Strict On, because Integer is a value type.
' Dim objects As IEnumerable(Of Object) = integers
```

È anche importante ricordare che le classi che implementano le interfacce varianti sono comunque invariabili. Ad esempio, sebbene <xref:System.Collections.Generic.List%601> implementi l'interfaccia covariante <xref:System.Collections.Generic.IEnumerable%601>, non è possibile convertire `List(Of Object)` in `List(Of String)` in modo implicito. come illustra l'esempio di codice riportato di seguito.

```vb
' The following statement generates a compiler error
' because classes are invariant.
' Dim list As List(Of Object) = New List(Of String)

' You can use the interface object instead.
Dim listObjects As IEnumerable(Of Object) = New List(Of String)
```

## <a name="see-also"></a>Vedere anche

- [Uso della varianza nelle interfacce per le raccolte generiche (Visual Basic)](using-variance-in-interfaces-for-generic-collections.md)
- [Creazione di interfacce generiche varianti (Visual Basic)](creating-variant-generic-interfaces.md)
- [Interfacce generiche](../../../../standard/generics/interfaces.md)
- [Varianza nei delegati (Visual Basic)](variance-in-delegates.md)

---
title: Covarianza e controvarianza
ms.date: 07/20/2015
ms.assetid: 59224c46-9931-466b-8c6e-3648c3e609c6
ms.openlocfilehash: 11dd71a8cfde12b7af1de79e3f5a095f79d8aa6e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400630"
---
# <a name="covariance-and-contravariance-visual-basic"></a>Covarianza e controvarianza (Visual Basic)

In Visual Basic, covarianza e controvarianza abilitano la conversione implicita del riferimento per i tipi di matrice, i tipi delegati e gli argomenti di tipo generico. La covarianza mantiene la compatibilità dell'assegnazione e la controvarianza la inverte.

Il codice seguente illustra la differenza tra la compatibilità dell'assegnazione, covarianza e controvarianza.

```vb
' Assignment compatibility.
Dim str As String = "test"
' An object of a more derived type is assigned to an object of a less derived type.
Dim obj As Object = str

' Covariance.
Dim strings As IEnumerable(Of String) = New List(Of String)()
' An object that is instantiated with a more derived type argument
' is assigned to an object instantiated with a less derived type argument.
' Assignment compatibility is preserved.
Dim objects As IEnumerable(Of Object) = strings

' Contravariance.
' Assume that there is the following method in the class:
' Shared Sub SetObject(ByVal o As Object)
' End Sub
Dim actObject As Action(Of Object) = AddressOf SetObject

' An object that is instantiated with a less derived type argument
' is assigned to an object instantiated with a more derived type argument.
' Assignment compatibility is reversed.
Dim actString As Action(Of String) = actObject
```

La covarianza per le matrici consente la conversione implicita di una matrice di un tipo più derivato in una matrice di un tipo meno derivato. Ma questa operazione non è indipendente dai tipi, come illustrato nell'esempio di codice seguente.

```vb
Dim array() As Object = New String(10) {}
' The following statement produces a run-time exception.
' array(0) = 10
```

Il supporto di covarianza e controvarianza per i gruppi di metodi consente la corrispondenza delle firme del metodo con i tipi delegati. Ciò consente di assegnare ai delegati non solo i metodi con firme corrispondenti, ma anche i metodi che restituiscono più tipi derivati (covarianza) o accettano parametri con meno tipi derivati (controvarianza) rispetto a quelli specificati dal tipo delegato. Per altre informazioni, vedere [Varianza nei delegati (Visual Basic)](variance-in-delegates.md) e [Uso della varianza nei delegati (Visual Basic)](using-variance-in-delegates.md).

L'esempio di codice seguente illustra il supporto di covarianza e controvarianza per i gruppi di metodi.

```vb
Shared Function GetObject() As Object
    Return Nothing
End Function

Shared Sub SetObject(ByVal obj As Object)
End Sub

Shared Function GetString() As String
    Return ""
End Function

Shared Sub SetString(ByVal str As String)

End Sub

Shared Sub Test()
    ' Covariance. A delegate specifies a return type as object,
    ' but you can assign a method that returns a string.
    Dim del As Func(Of Object) = AddressOf GetString

    ' Contravariance. A delegate specifies a parameter type as string,
    ' but you can assign a method that takes an object.
    Dim del2 As Action(Of String) = AddressOf SetObject
End Sub
```

In .NET Framework 4 o versioni successive Visual Basic supporta la covarianza e la controvarianza nelle interfacce e nei delegati generici e consente la conversione implicita di parametri di tipo generico. Per altre informazioni, vedere [Varianza nelle interfacce generiche (Visual Basic)](variance-in-generic-interfaces.md) e [Varianza nei delegati (Visual Basic)](variance-in-delegates.md).

L'esempio di codice seguente illustra la conversione implicita del riferimento per le interfacce generiche.

```vb
Dim strings As IEnumerable(Of String) = New List(Of String)
Dim objects As IEnumerable(Of Object) = strings
```

Le interfacce o i delegati generici sono detti *varianti* se i relativi parametri generici vengono dichiarati come covarianti o controvarianti. Visual Basic consente di creare i propri delegati e interfacce varianti. Per altre informazioni, vedere [Creazione di interfacce generiche varianti (Visual Basic)](creating-variant-generic-interfaces.md) e [Varianza nei delegati (Visual Basic)](variance-in-delegates.md).

## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|-----------|-----------------|
|[Varianza nelle interfacce generiche (Visual Basic)](variance-in-generic-interfaces.md)|Illustra la covarianza e la controvarianza nelle interfacce generiche e fornisce un elenco di interfacce generiche variant in .NET Framework.|
|[Creazione di interfacce generiche varianti (Visual Basic)](creating-variant-generic-interfaces.md)|Spiega come creare interfacce varianti personalizzate.|
|[Uso della varianza nelle interfacce per le raccolte generiche (Visual Basic)](using-variance-in-interfaces-for-generic-collections.md)|Spiega come il supporto di covarianza e controvarianza nelle interfacce <xref:System.Collections.Generic.IEnumerable%601> e <xref:System.IComparable%601> consente di riutilizzare il codice.|
|[Varianza nei delegati (Visual Basic)](variance-in-delegates.md)|Illustra la covarianza e la controvarianza nei delegati generici e non generici e offre un elenco di delegati generici varianti in .NET Framework.|
|[Uso della varianza nei delegati (Visual Basic)](using-variance-in-delegates.md)|Spiega come usare il supporto di covarianza e controvarianza nei delegati non generici per la corrispondenza delle firme del metodo con i tipi delegati.|
|[Utilizzo della varianza per i delegati generici Func e Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md)|Spiega come il supporto di covarianza e controvarianza nei delegati `Func` e `Action` consente di riutilizzare il codice.|

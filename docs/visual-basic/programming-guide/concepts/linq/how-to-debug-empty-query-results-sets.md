---
title: 'Procedura: Eseguire il debug di set di risultati vuoti di query'
ms.date: 07/20/2015
ms.assetid: b242c90a-d2b8-4309-8a1e-e4e70736c727
ms.openlocfilehash: b2059ccd4638d2fb77c524773cb4bd50f721b5b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398038"
---
# <a name="how-to-debug-empty-query-results-sets-visual-basic"></a>Procedura: eseguire il debug di set di risultati di query vuoti (Visual Basic)

Uno dei problemi più comuni che viene riscontrato durante l'esecuzione di query su alberi XML è che, se l'albero XML include uno spazio dei nomi predefinito, lo sviluppatore scrive talvolta la query come se il codice XML non fosse incluso in uno spazio dei nomi.

Nel primo set di esempi riportati in questo argomento viene illustrato il tipico caricamento del codice XML in uno spazio dei nomi predefinito e l'esecuzione errata di query su tale codice.

Nel secondo set di esempi sono illustrate le correzioni necessarie da effettuare per poter eseguire query su codice XML in uno spazio dei nomi.

Per ulteriori informazioni, vedere [Cenni preliminari sugli spazi dei nomi (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).

## <a name="example"></a>Esempio

In questo esempio è illustrata la creazione di codice XML in uno spazio dei nomi e una query che restituisce un set di risultati vuoto.

```vb
Dim root As XElement = _
    <Root xmlns='http://www.adventure-works.com'>
        <Child>1</Child>
        <Child>2</Child>
        <Child>3</Child>
        <AnotherChild>4</AnotherChild>
        <AnotherChild>5</AnotherChild>
        <AnotherChild>6</AnotherChild>
    </Root>
Dim c1 As IEnumerable(Of XElement) = _
        From el In root.<Child> _
        Select el
Console.WriteLine("Result set follows:")
For Each el As XElement In c1
    Console.WriteLine(el.Value)
Next
Console.WriteLine("End of result set")
```

Il risultato ottenuto dall'esempio è il seguente:

```console
Result set follows:
End of result set
```

## <a name="example"></a>Esempio

In questo esempio vengono illustrate la creazione di codice XML in uno spazio dei nomi, nonché una query codificata correttamente.

La soluzione consiste nel dichiarare e inizializzare uno spazio dei nomi predefinito globale. In questo modo tutte le proprietà XML vengono inserite nello spazio dei nomi predefinito. Non è necessario apportare altre modifiche all'esempio per fare in modo che venga eseguito correttamente.

```vb
Imports <xmlns="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = _
            <Root xmlns='http://www.adventure-works.com'>
                <Child>1</Child>
                <Child>2</Child>
                <Child>3</Child>
                <AnotherChild>4</AnotherChild>
                <AnotherChild>5</AnotherChild>
                <AnotherChild>6</AnotherChild>
            </Root>
        Dim c1 As IEnumerable(Of XElement) = _
                From el In root.<Child> _
                Select el
        Console.WriteLine("Result set follows:")
        For Each el As XElement In c1
            Console.WriteLine(CInt(el))
        Next
        Console.WriteLine("End of result set")
    End Sub
End Module
```

Il risultato ottenuto dall'esempio è il seguente:

```console
Result set follows:
1
2
3
End of result set
```

## <a name="see-also"></a>Vedere anche

- [Query di base (LINQ to XML) (Visual Basic)](basic-queries-linq-to-xml.md)

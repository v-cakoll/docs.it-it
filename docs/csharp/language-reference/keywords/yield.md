---
title: Parola chiave contestuale yield - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- yield
- yield_CSharpKeyword
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
ms.openlocfilehash: e3c9e37e7b543eaddae837a85604c4ba91fbc744
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712780"
---
# <a name="yield-c-reference"></a>yield (Riferimenti per C#)

Quando si usa la  [parola chiave contestuale](index.md#contextual-keywords)`yield` in un'istruzione, si indica che il metodo, l'operatore o la funzione di accesso `get` in cui appare è un iteratore. Utilizzando `yield` per definire un iteratore, si elimina la necessità di una classe esplicita aggiuntiva (la classe che contiene lo stato per un'enumerazione, vedere <xref:System.Collections.Generic.IEnumerator%601> per un esempio) quando si implementano i modelli <xref:System.Collections.IEnumerable> e di <xref:System.Collections.IEnumerator> per un tipo di raccolta personalizzato.

Nell'esempio seguente vengono illustrate le due forme dell'istruzione `yield`.

```csharp
yield return <expression>;
yield break;
```

## <a name="remarks"></a>Osservazioni

Si utilizza un'istruzione `yield return` per restituire un elemento alla volta.

La sequenza restituita da un metodo iteratore può essere usata con un'istruzione [foreach](foreach-in.md) o una query LINQ. Ogni iterazione del ciclo `foreach` chiama il metodo iteratore. Quando si raggiunge un'istruzione `yield return` nel metodo iteratore, viene restituito `expression` e viene mantenuta la posizione corrente nel codice. L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.

È possibile utilizzare un'istruzione `yield break` per terminare l'iterazione.

Per altre informazioni sugli iteratori, vedere [Iteratori](../../iterators.md).

## <a name="iterator-methods-and-get-accessors"></a>Metodi e funzioni di accesso get dell'iteratore

La dichiarazione di un iteratore deve soddisfare i seguenti requisiti:

- Il tipo restituito deve essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.

- La dichiarazione non può avere parametri [in](in-parameter-modifier.md) [ref](ref.md) o [out](out-parameter-modifier.md).

Il tipo `yield` di un iteratore che restituisce <xref:System.Collections.IEnumerable> o <xref:System.Collections.IEnumerator> è `object`.  Se l'iteratore restituisce <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Collections.Generic.IEnumerator%601>, deve essere presente una conversione implicita dal tipo dell'espressione nell'istruzione `yield return` al parametro di tipo generico.

Non è possibile includere un'istruzione `yield return` o `yield break` in:

- [Espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) e [metodi anonimi](../operators/delegate-operator.md).

- Metodi contenenti blocchi unsafe. Per altre informazioni, vedere [unsafe](unsafe.md).

## <a name="exception-handling"></a>Gestione delle eccezioni

Un'istruzione `yield return` non può essere inclusa in un blocco try-catch. Un'istruzione `yield return` può essere inclusa nel blocco try di un'istruzione try-finally.

Un'istruzione `yield break` può essere inclusa in un blocco try o in un blocco catch ma non in un blocco finally.

Se il corpo di `foreach` (esterno al metodo iteratore) genera un'eccezione, viene eseguito un blocco `finally` nel metodo iteratore.

## <a name="technical-implementation"></a>Implementazione tecnica

Il codice seguente restituisce `IEnumerable<string>` da un metodo iteratore e quindi scorre i relativi elementi.

```csharp
IEnumerable<string> elements = MyIteratorMethod();
foreach (string element in elements)
{
   ...
}
```

La chiamata a `MyIteratorMethod` non esegue il corpo del metodo. La chiamata restituisce invece `IEnumerable<string>` nella variabile `elements`.

In un'iterazione del ciclo `foreach`, il metodo <xref:System.Collections.IEnumerator.MoveNext%2A> viene chiamato per `elements`. Questa chiamata esegue il corpo di `MyIteratorMethod` fino a quando non viene raggiunta l'istruzione `yield return` successiva. L'espressione restituita dall'istruzione `yield return` determina non solo il valore della variabile `element` per l'utilizzo da parte del corpo del ciclo, ma anche la proprietà <xref:System.Collections.Generic.IEnumerator%601.Current%2A> di `elements`, che è `IEnumerable<string>`.

In ogni iterazione successiva del ciclo `foreach`, l'esecuzione del corpo dell'iteratore continua da dove è stata interrotta, fermandosi ancora quando raggiunge un'istruzione `yield return`. Il ciclo `foreach` termina quando si raggiunge la fine del metodo iteratore o un'istruzione `yield break`.

## <a name="example"></a>Esempio

L'esempio seguente contiene un'istruzione `yield return` all'interno di un ciclo `for`. Ogni iterazione del corpo dell'istruzione `foreach` nel metodo `Main` crea una chiamata alla funzione iteratore `Power`. Ogni chiamata alla funzione iteratore procede fino alla prossima esecuzione dell'istruzione `yield return`, che si verifica durante l'iterazione successiva del ciclo `for`.

Il tipo restituito del metodo iteratore è <xref:System.Collections.IEnumerable>, ovvero un tipo di interfaccia iteratore. Quando il metodo iteratore viene chiamato, restituisce un oggetto enumerabile che contiene le potenze di un numero.

[!code-csharp[csrefKeywordsContextual#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#5)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata una funzione di accesso `get` che è un iteratore. Nell'esempio, ogni istruzione `yield return` restituisce un'istanza di una classe definita dall'utente.

[!code-csharp[csrefKeywordsContextual#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#21)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../../language-reference/index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [foreach, in](foreach-in.md)
- [Iteratori](../../iterators.md)

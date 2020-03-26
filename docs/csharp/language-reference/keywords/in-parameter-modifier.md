---
title: Modificatore del parametro in - Riferimenti per C#
ms.date: 03/19/2020
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
ms.openlocfilehash: 20956f9e25b6830a8876824a4c9dad1dbc4c4f3e
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249370"
---
# <a name="in-parameter-modifier-c-reference"></a>Modificatore del parametro in (Riferimenti per C#)

La parola chiave `in` fa sì che gli argomenti vengono passati per riferimento. Imposta il parametro formale come alias dell'argomento, che deve essere una variabile. In altre parole, qualsiasi operazione sul parametro viene eseguita sull'argomento. È simile alle parole chiave [ref](ref.md) o [out](out-parameter-modifier.md), ma gli argomenti `in` non possono essere modificati dal metodo chiamato. Mentre gli argomenti `ref` possono essere modificati, gli argomenti `out` devono essere modificati dal metodo chiamato e queste modifiche sono osservabili nel contesto di chiamata.

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

L'esempio precedente dimostra che il modificatore `in` non è in genere necessario nel sito di chiamata. Viene richiesto soltanto nella dichiarazione di metodo.

> [!NOTE]
> La parola chiave `in` può essere usata anche con un parametro di tipo generico per specificare che il parametro è di tipo controvariante, quale parte di un'istruzione `foreach` o parte di una clausola `join` in una query LINQ. Per altre informazioni sull'uso della parola chiave `in` in questi contesti, vedere la pagina [in](in.md), in cui sono presenti collegamenti a tutti gli usi.
  
Le variabili passate come argomenti `in` devono essere inizializzate prima di essere passate in una chiamata al metodo. Tuttavia, il metodo chiamato non può assegnare un valore o modificare l'argomento.  

Il modificatore di parametro `in` è disponibile in C# 7.2 e versioni successive. Nelle versioni precedenti viene generato l'errore del compilatore `CS8107` ("La funzionalità 'riferimenti di sola lettura' non è disponibile in C# 7.0. Usare la versione 7.2 o versioni successive del linguaggio.") Per configurare la versione del linguaggio del compilatore, vedere [Selezionare la versione del linguaggio C#](../configure-language-version.md).

Le parole chiave `in`, `ref` e `out` non sono considerate parte della firma del metodo ai fini della risoluzione dell'overload. Non è quindi possibile eseguirne l'overload se l'unica differenza è che un metodo accetta un argomento `ref` o `in` e l'altro un argomento `out`. Il codice seguente, ad esempio, non verrà compilato:  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
È consentito l'overload in base alla presenza di `in`:  
  
```csharp
class InOverloads
{
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

## <a name="overload-resolution-rules"></a>Regole di risoluzione dell'overload

È possibile comprendere le regole di risoluzione dell'overload per i metodi con argomenti per valore rispetto ai metodi con argomenti `in` se si comprende la motivazione per gli argomenti `in`. La definizione di metodi tramite parametri `in` costituisce un'ottimizzazione potenziale delle prestazioni. Alcuni argomenti di tipo `struct` possono essere di grandi dimensioni e quando vengono chiamati metodi all'interno di cicli ristretti o in percorsi di codice critici, il costo della copia di tali strutture ha una rilevanza fondamentale. I metodi dichiarano parametri `in` per specificare che è possibile passare argomenti per riferimento in modo sicuro, perché il metodo chiamato non modifica lo stato degli argomenti. Il passaggio di tali argomenti per riferimento consente di evitare una copia potenzialmente dispendiosa.

Specificare `in` per gli argomenti presso il sito di chiamata è in genere facoltativo. Non esiste alcuna differenza semantica tra il passaggio di argomenti per valore e il passaggio per riferimento tramite il modificatore `in`. Il modificatore `in` presso il sito di chiamata è facoltativo perché non è necessario indicare che il valore dell'argomento può essere modificato. Si aggiunge il modificatore `in` in modo esplicito presso il sito di chiamata per assicurarsi che l'argomento venga passato per riferimento, non per valore. L'uso di `in` in modo esplicito ha i due effetti seguenti:

In primo luogo, se si specifica `in` presso il sito di chiamata si impone al compilatore di selezionare un metodo definito con un parametro `in` corrispondente. In caso contrario, se due metodi si differenziano solo per la presenza di `in`, l'overload per valore rappresenta una corrispondenza migliore.

In secondo luogo, se si specifica `in` si dichiara l'intenzione di passare un argomento per riferimento. L'argomento usato con `in` deve rappresentare una posizione a cui sia possibile fare riferimento direttamente. Sono valide le stesse regole generali di `out` e `ref`: non è possibile usare costanti, proprietà ordinarie o altre espressioni che producono valori. In caso contrario, l'omissione di `in` presso il sito di chiamata informa il compilatore che è consentito creare una variabile temporanea da passare per riferimento di sola lettura al metodo. Il compilatore crea una variabile temporanea per superare diverse restrizioni degli argomenti `in`:

- Una variabile temporanea consente costanti in fase di compilazione come parametri `in`.
- Una variabile temporanea consente proprietà o altre espressioni per i parametri `in`.
- Una variabile temporanea consente argomenti che includono una conversione implicita dal tipo di argomento al tipo di parametro.

In tutte le istanze precedenti, il compilatore crea una variabile temporanea che archivia il valore della costante, della proprietà o di un'altra espressione.

Il codice seguente illustra queste regole:

```csharp
static void Method(in int argument)
{
    // implementation removed
}

Method(5); // OK, temporary variable created.
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // OK, temporary int created with the value 0
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // passed by readonly reference
Method(in i); // passed by readonly reference, explicitly using `in`
```

Si supponga a questo punto che sia disponibile un altro metodo che usa argomenti per valore. I risultati cambiano, come illustrato nel codice seguente:

```csharp
static void Method(int argument)
{
    // implementation removed
}

static void Method(in int argument)
{
    // implementation removed
}

Method(5); // Calls overload passed by value
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // Calls overload passed by value.
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // Calls overload passed by value
Method(in i); // passed by readonly reference, explicitly using `in`
```

L'unica chiamata a un metodo in cui l'argomento viene passato per riferimento è quella finale.

> [!NOTE]
> Per semplicità, il codice precedente usa `int` come tipo di argomento. Poiché nella maggior parte dei computer moderni le dimensioni di `int` non sono maggiori di quelle di un riferimento, non si ottiene alcun vantaggio dal passaggio di un unico `int` come riferimento di sola lettura.

## <a name="limitations-on-in-parameters"></a>Limitazioni dei parametri `in`

Non è possibile usare le parole chiave `in`, `ref` e `out` per i seguenti tipi di metodi:  
  
- Metodi asincroni definiti usando il modificatore [async](async.md).  
- Metodi iteratori che includono un'istruzione [yield return](yield.md) o `yield break`.
- Il primo argomento di un `in` metodo di estensione non può avere il modificatore a meno che tale argomento non sia uno struct.
- Il primo argomento di un metodo di estensione in cui tale argomento è un tipo generico (anche quando tale tipo è vincolato a essere uno struct).The first argument of an extension method where that argument is a generic type (even when that type is constrained to be a struct.)

## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida alla programmazione in C](../../programming-guide/index.md)
- [Parole chiave di C](index.md)
- [Parametri di metodo](method-parameters.md)
- [Scrivere codice efficiente sicuro](../../write-safe-efficient-code.md)

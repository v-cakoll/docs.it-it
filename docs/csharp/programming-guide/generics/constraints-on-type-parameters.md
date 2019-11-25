---
title: Vincoli sui parametri di tipo - Guida per programmatori C#
ms.custom: seodec18
ms.date: 04/12/2018
helpviewer_keywords:
- generics [C#], type constraints
- type constraints [C#]
- type parameters [C#], constraints
- unbound type parameter [C#]
ms.openlocfilehash: d05307735506db0f0e4abab067334e4f0466ee6a
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204645"
---
# <a name="constraints-on-type-parameters-c-programming-guide"></a>Vincoli sui parametri di tipo (Guida per programmatori C#)

I vincoli indicano al compilatore quali funzionalità deve usare un argomento tipo. Senza i vincoli, l'argomento tipo può essere qualsiasi tipo. Il compilatore è in grado di dedurre solo i membri di <xref:System.Object?displayProperty=nameWithType>, che è la principale classe di base per qualsiasi tipo .NET. Per altre informazioni, vedere [Motivi per cui usare i vincoli](#why-use-constraints). Se il codice client tenta di creare un'istanza della classe con un tipo non consentito da un vincolo, viene restituito un errore in fase di compilazione. I vincoli vengono specificati usando la parola chiave contestuale `where`. Nella tabella seguente sono riportati i sette tipi di vincoli:

|Vincolo|Descrizione|
|----------------|-----------------|
|`where T : struct`|The type argument must be a non-nullable value type. For information about nullable value types, see [Nullable value types](../../language-reference/builtin-types/nullable-value-types.md). Because all value types have an accessible parameterless constructor, the `struct` constraint implies the `new()` constraint and can't be combined with the `new()` constraint. You also cannot combine the `struct` constraint with the `unmanaged` constraint.|
|`where T : class`|L'argomento tipo deve essere un tipo riferimento. Questo vincolo si applica anche a qualsiasi tipo di classe, interfaccia, delegato o matrice.|
|`where T : notnull`|The type argument must be a non-nullable type. The argument can be a non-nullable reference type in C# 8.0 or later, or a not nullable value type. Questo vincolo si applica anche a qualsiasi tipo di classe, interfaccia, delegato o matrice.|
|`where T : unmanaged`|The type argument must be a non-nullable [unmanaged type](../../language-reference/builtin-types/unmanaged-types.md). The `unmanaged` constraint implies the `struct` constraint and can't be combined with either the `struct` or `new()` constraints.|
|`where T : new()`|L'argomento tipo deve avere un costruttore pubblico senza parametri. Quando il vincolo `new()` viene usato con altri vincoli, deve essere specificato per ultimo. The `new()` constraint can't be combined with the `struct` and `unmanaged` constraints.|
|`where T :` *\<nome della classe di base>*|L'argomento tipo deve corrispondere alla classe di base specificata o derivare da essa.|
|`where T :` *\<nome dell'interfaccia>*|L'argomento tipo deve corrispondere all'interfaccia specificata o implementare tale interfaccia. È possibile specificare più vincoli di interfaccia. L'interfaccia vincolante può anche essere generica.|
|`where T : U`|L'argomento tipo fornito per T deve corrispondere all'argomento fornito per U o derivare da esso.|

## <a name="why-use-constraints"></a>Motivi per cui usare i vincoli

Vincolando il parametro di tipo, il numero di operazioni e di chiamate ai metodi consentite viene ampliato includendo quelle supportate dal tipo vincolante e da tutti i tipi nella relativa gerarchia di ereditarietà. When you design generic classes or methods, if you'll be performing any operation on the generic members beyond simple assignment or calling any methods not supported by <xref:System.Object?displayProperty=nameWithType>, you'll have to apply constraints to the type parameter. Specificando il vincolo della classe di base, ad esempio, si indica al compilatore che verranno usati come argomenti tipo solo gli oggetti del tipo specificato o derivati da esso. In presenza di questa garanzia, il compilatore può consentire le chiamate ai metodi del tipo all'interno della classe generica. L'esempio di codice seguente illustra la funzionalità che è possibile aggiungere alla classe `GenericList<T>` (in [Introduzione ai generics](../../../standard/generics/index.md)) applicando un vincolo della classe di base.

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#9)]

Il vincolo consente alla classe generica di usare la proprietà `Employee.Name`. Il vincolo specifica che tutti gli elementi di tipo `T` sono sicuramente un oggetto `Employee` o un oggetto che eredita da `Employee`.

È possibile applicare più vincoli allo stesso parametro di tipo. I vincoli stessi possono essere tipi generici, come illustrato di seguito:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#10)]

Quando si applica il vincolo `where T : class`, evitare gli operatori `==` e `!=` nel parametro di tipo perché questi operatori verificano solo l'identità del riferimento e non l'uguaglianza dei valori. Questo comportamento si verifica anche se si esegue l'overload degli operatori in un tipo usato come argomento. Il codice seguente illustra questo aspetto. L'output è false anche se la classe <xref:System.String> esegue l'overload dell'operatore `==`.

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#11)]

The compiler only knows that `T` is a reference type at compile time and must use the default operators that are valid for all reference types. Per verificare l'uguaglianza dei valori, è consigliabile applicare anche il vincolo `where T : IEquatable<T>` o `where T : IComparable<T>` e implementare l'interfaccia nelle classi che verranno usate per costruire la classe generica.

## <a name="constraining-multiple-parameters"></a>Vincolo di più parametri

È possibile applicare vincoli a più parametri e più vincoli a un singolo parametro, come illustrato nell'esempio seguente:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#12)]

## <a name="unbounded-type-parameters"></a>Parametri di tipo senza vincoli

 I parametri di tipo che non hanno vincoli, ad esempio T nella classe pubblica `SampleClass<T>{}`, sono detti parametri di tipo senza vincoli. I parametri di tipo senza vincoli prevedono le regole seguenti:

- The `!=` and `==` operators can't be used because there's no guarantee that the concrete type argument will support these operators.
- Possono essere convertiti in e da `System.Object` oppure convertiti in modo esplicito in qualsiasi tipo di interfaccia.
- È possibile confrontarli con [Null](../../language-reference/keywords/null.md). Se si confronta un parametro senza vincoli con `null` e l'argomento tipo è un tipo valore, verrà sempre restituito false.

## <a name="type-parameters-as-constraints"></a>Parametri di tipo come vincoli

L'uso di un parametro di tipo generico come vincolo è utile quando una funzione membro con il proprio parametro di tipo deve vincolare tale parametro a quello del tipo che lo contiene, come illustrato nell'esempio seguente:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#13)]

Nell'esempio precedente `T` è un vincolo di tipo nel contesto del metodo `Add` e un parametro di tipo senza vincoli nel contesto della classe `List`.

I parametri di tipo possono anche essere usati come vincoli nelle definizioni di classi generiche. Il parametro di tipo deve essere dichiarato tra parentesi acute, insieme a eventuali altri parametri di tipo:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#14)]

L'utilità dei parametri di tipo usati come vincoli in classi generiche è limitata poiché il compilatore non può presupporre niente riguardo al parametro di tipo, tranne il fatto che deriva da `System.Object`. Usare i parametri di tipo come vincoli nelle classi generiche in scenari in cui si vuole applicare una relazione di ereditarietà tra due parametri di tipo.

## <a name="notnull-constraint"></a>NotNull constraint

Beginning with C# 8.0, you can use the `notnull` constraint to specify that the type argument must be a non-nullable value type or non-nullable reference type. The `notnull` constraint can only be used in a `nullable enable` context. The compiler generates a warning if you add the `notnull` constraint in a nullable oblivious context. 

Unlike other constraints, when a type argument violates the `notnull` constraint, the compiler generates a warning when that code is compiled in a `nullable enable` context. If the code is compiled in a nullable oblivious context, the compiler doesn't generate any warnings or errors.

## <a name="unmanaged-constraint"></a>Vincolo non gestito

Beginning with C# 7.3, you can use the `unmanaged` constraint to specify that the type parameter must be a non-nullable [unmanaged type](../../language-reference/builtin-types/unmanaged-types.md). Il vincolo `unmanaged` consente di scrivere routine riutilizzabili per lavorare con tipi che possono essere modificati come blocchi di memoria, come illustrato nell'esempio seguente:

[!code-csharp[using the unmanaged constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#15)]

Il metodo precedente deve essere compilato in un contesto `unsafe` perché usa l'operatore `sizeof` per un tipo non noto come tipo predefinito. Senza il vincolo `unmanaged` l'operatore `sizeof` non è disponibile.

The `unmanaged` constraint implies the `struct` constraint and can't be combined with it. Because the `struct` constraint implies the `new()` constraint, the `unmanaged` constraint can't be combined with the `new()` constraint as well.

## <a name="delegate-constraints"></a>Vincoli dei delegati

A partire da C# 7.3 è inoltre possibile usare <xref:System.Delegate?displayProperty=nameWithType> o <xref:System.MulticastDelegate?displayProperty=nameWithType> come vincolo di classe di base. Il supporto Common Language Runtime (CLR) consente sempre questo vincolo, a differenza del linguaggio C#. Il vincolo `System.Delegate` consente di scrivere codice che funziona con i delegati in modo indipendente dai tipi. The following code defines an extension method that combines two delegates provided they're the same type:

[!code-csharp[using the delegate constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#16)]

Per combinare delegati dello stesso tipo, è possibile usare il metodo riportato sopra:

[!code-csharp[using the unmanaged constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#17)]

Se si rimuove il commento dall'ultima riga, non verrà compilata. Both `first` and `test` are delegate types, but they're different delegate types.

## <a name="enum-constraints"></a>Vincoli di enumerazione

A partire da C# 7.3 è anche possibile specificare il tipo <xref:System.Enum?displayProperty=nameWithType> come vincolo di classe di base. Il supporto Common Language Runtime (CLR) consente sempre questo vincolo, a differenza del linguaggio C#. I generics che usano `System.Enum` offrono una programmazione indipendente dai tipi che consente di memorizzare nella cache i risultati dei metodi statici in `System.Enum`. Nell'esempio seguente vengono individuati tutti i valori validi per un tipo di enumerazione e viene compilato un dizionario che esegue il mapping di tali valori alla propria rappresentazione di stringa.

[!code-csharp[using the unmanaged constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#18)]

I metodi usano la reflection, che presenta implicazioni a livello di prestazioni. È possibile chiamare questo metodo per creare una raccolta da memorizzare nella cache e riusare anziché ripetere le chiamate che richiedono reflection.

Il metodo può essere usato come illustrato nell'esempio seguente per creare un'enumerazione e compilare un dizionario dei relativi valori e nomi:

[!code-csharp[using the unmanaged constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#19)]

[!code-csharp[using the unmanaged constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#20)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic>
- [Guida per programmatori C#](../index.md)
- [Introduzione ai generics](./index.md)
- [Classi generiche](./generic-classes.md)
- [Vincolo new](../../language-reference/keywords/new-constraint.md)

---
title: Vincoli sui parametri di tipo - Guida per programmatori C#
ms.custom: seodec18
ms.date: 04/12/2018
helpviewer_keywords:
- generics [C#], type constraints
- type constraints [C#]
- type parameters [C#], constraints
- unbound type parameter [C#]
ms.openlocfilehash: 19bf511ee7252bc305dbb4b6f32636955eba0ab8
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337263"
---
# <a name="constraints-on-type-parameters-c-programming-guide"></a>Vincoli sui parametri di tipo (Guida per programmatori C#)

I vincoli indicano al compilatore quali funzionalità deve usare un argomento tipo. Senza i vincoli, l'argomento tipo può essere qualsiasi tipo. Il compilatore è in grado di dedurre solo i membri di <xref:System.Object?displayProperty=nameWithType>, che è la principale classe di base per qualsiasi tipo .NET. Per altre informazioni, vedere [Motivi per cui usare i vincoli](#why-use-constraints). Se il codice client tenta di creare un'istanza della classe con un tipo non consentito da un vincolo, viene restituito un errore in fase di compilazione. I vincoli vengono specificati usando la parola chiave contestuale `where`. Nella tabella seguente sono riportati i sette tipi di vincoli:

|Vincolo|Descrizione|
|----------------|-----------------|
|`where T : struct`|L'argomento di tipo deve essere un tipo di valore non nullable. Per informazioni sui tipi di valore Nullable, vedere [tipi di valore Nullable](../../language-reference/builtin-types/nullable-value-types.md). Poiché tutti i tipi di valore hanno un costruttore senza parametri accessibile, il vincolo `struct` implica il vincolo `new()` e non può essere combinato con il vincolo `new()`. Non è inoltre possibile combinare il vincolo di `struct` con il vincolo di `unmanaged`.|
|`where T : class`|L'argomento tipo deve essere un tipo riferimento. Questo vincolo si applica anche a qualsiasi tipo di classe, interfaccia, delegato o matrice.|
|`where T : notnull`|L'argomento di tipo deve essere un tipo non nullable. L'argomento può essere un tipo di riferimento non nullable in C# 8,0 o versione successiva oppure un tipo di valore non nullable. Questo vincolo si applica anche a qualsiasi tipo di classe, interfaccia, delegato o matrice.|
|`where T : unmanaged`|L'argomento di tipo deve essere un tipo non [gestito](../../language-reference/builtin-types/unmanaged-types.md)che non ammette i valori null. Il vincolo `unmanaged` implica il vincolo `struct` e non può essere combinato con i vincoli `struct` o `new()`.|
|`where T : new()`|L'argomento tipo deve avere un costruttore pubblico senza parametri. Quando il vincolo `new()` viene usato con altri vincoli, deve essere specificato per ultimo. Non è possibile combinare il vincolo `new()` con i vincoli `struct` e `unmanaged`.|
|`where T :` *\<nome della classe base >*|L'argomento tipo deve corrispondere alla classe di base specificata o derivare da essa.|
|`where T :` *\<nome dell'interfaccia >*|L'argomento tipo deve corrispondere all'interfaccia specificata o implementare tale interfaccia. È possibile specificare più vincoli di interfaccia. L'interfaccia vincolante può anche essere generica.|
|`where T : U`|L'argomento tipo fornito per T deve corrispondere all'argomento fornito per U o derivare da esso.|

## <a name="why-use-constraints"></a>Motivi per cui usare i vincoli

Vincolando il parametro di tipo, il numero di operazioni e di chiamate ai metodi consentite viene ampliato includendo quelle supportate dal tipo vincolante e da tutti i tipi nella relativa gerarchia di ereditarietà. Quando si progettano classi o metodi generici, se si eseguono operazioni sui membri generici che esulano dall'assegnazione semplice o che chiamano metodi non supportati da <xref:System.Object?displayProperty=nameWithType>, sarà necessario applicare vincoli al parametro di tipo. Specificando il vincolo della classe di base, ad esempio, si indica al compilatore che verranno usati come argomenti tipo solo gli oggetti del tipo specificato o derivati da esso. In presenza di questa garanzia, il compilatore può consentire le chiamate ai metodi del tipo all'interno della classe generica. L'esempio di codice seguente illustra la funzionalità che è possibile aggiungere alla classe `GenericList<T>` (in [Introduzione ai generics](../../../standard/generics/index.md)) applicando un vincolo della classe di base.

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#9)]

Il vincolo consente alla classe generica di usare la proprietà `Employee.Name`. Il vincolo specifica che tutti gli elementi di tipo `T` sono sicuramente un oggetto `Employee` o un oggetto che eredita da `Employee`.

È possibile applicare più vincoli allo stesso parametro di tipo. I vincoli stessi possono essere tipi generici, come illustrato di seguito:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#10)]

Quando si applica il vincolo `where T : class`, evitare gli operatori `==` e `!=` nel parametro di tipo perché questi operatori verificano solo l'identità del riferimento e non l'uguaglianza dei valori. Questo comportamento si verifica anche se si esegue l'overload degli operatori in un tipo usato come argomento. Il codice seguente illustra questo aspetto. L'output è false anche se la classe <xref:System.String> esegue l'overload dell'operatore `==`.

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#11)]

Il compilatore sa solo che `T` è un tipo di riferimento in fase di compilazione e deve usare gli operatori predefiniti validi per tutti i tipi di riferimento. Per verificare l'uguaglianza dei valori, è consigliabile applicare anche il vincolo `where T : IEquatable<T>` o `where T : IComparable<T>` e implementare l'interfaccia nelle classi che verranno usate per costruire la classe generica.

## <a name="constraining-multiple-parameters"></a>Vincolo di più parametri

È possibile applicare vincoli a più parametri e più vincoli a un singolo parametro, come illustrato nell'esempio seguente:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#12)]

## <a name="unbounded-type-parameters"></a>Parametri di tipo senza vincoli

 I parametri di tipo che non hanno vincoli, ad esempio T nella classe pubblica `SampleClass<T>{}`, sono detti parametri di tipo senza vincoli. I parametri di tipo senza vincoli prevedono le regole seguenti:

- Non è possibile usare gli operatori `!=` e `==` perché non vi è alcuna garanzia che l'argomento di tipo concreto supporterà questi operatori.
- Possono essere convertiti in e da `System.Object` oppure convertiti in modo esplicito in qualsiasi tipo di interfaccia.
- È possibile confrontarli con [Null](../../language-reference/keywords/null.md). Se si confronta un parametro senza vincoli con `null` e l'argomento tipo è un tipo valore, verrà sempre restituito false.

## <a name="type-parameters-as-constraints"></a>Parametri di tipo come vincoli

L'uso di un parametro di tipo generico come vincolo è utile quando una funzione membro con il proprio parametro di tipo deve vincolare tale parametro a quello del tipo che lo contiene, come illustrato nell'esempio seguente:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#13)]

Nell'esempio precedente `T` è un vincolo di tipo nel contesto del metodo `Add` e un parametro di tipo senza vincoli nel contesto della classe `List`.

I parametri di tipo possono anche essere usati come vincoli nelle definizioni di classi generiche. Il parametro di tipo deve essere dichiarato tra parentesi acute, insieme a eventuali altri parametri di tipo:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#14)]

L'utilità dei parametri di tipo usati come vincoli in classi generiche è limitata poiché il compilatore non può presupporre niente riguardo al parametro di tipo, tranne il fatto che deriva da `System.Object`. Usare i parametri di tipo come vincoli nelle classi generiche in scenari in cui si vuole applicare una relazione di ereditarietà tra due parametri di tipo.

## <a name="notnull-constraint"></a>Vincolo NotNull

A partire C# da 8,0, è possibile usare il vincolo `notnull` per specificare che l'argomento di tipo deve essere un tipo di valore non nullable o un tipo di riferimento non nullable. Il vincolo `notnull` può essere utilizzato solo in un contesto di `nullable enable`. Il compilatore genera un avviso se si aggiunge il vincolo `notnull` in un contesto ignaro Nullable. 

Diversamente da altri vincoli, quando un argomento di tipo viola il vincolo di `notnull`, il compilatore genera un avviso quando il codice viene compilato in un contesto di `nullable enable`. Se il codice viene compilato in un contesto ignaro Nullable, il compilatore non genera avvisi o errori.

## <a name="unmanaged-constraint"></a>Vincolo non gestito

A partire C# da 7,3, è possibile usare il vincolo `unmanaged` per specificare che il parametro di tipo deve essere un [tipo non gestito](../../language-reference/builtin-types/unmanaged-types.md)che non ammette i valori null. Il vincolo `unmanaged` consente di scrivere routine riutilizzabili per lavorare con tipi che possono essere modificati come blocchi di memoria, come illustrato nell'esempio seguente:

[!code-csharp[using the unmanaged constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#15)]

Il metodo precedente deve essere compilato in un contesto `unsafe` perché usa l'operatore `sizeof` per un tipo non noto come tipo predefinito. Senza il vincolo `unmanaged` l'operatore `sizeof` non è disponibile.

Il vincolo `unmanaged` implica il vincolo `struct` e non può essere combinato con esso. Poiché il vincolo `struct` implica il vincolo `new()`, il vincolo `unmanaged` non può essere combinato anche con il vincolo `new()`.

## <a name="delegate-constraints"></a>Vincoli dei delegati

A partire da C# 7.3 è inoltre possibile usare <xref:System.Delegate?displayProperty=nameWithType> o <xref:System.MulticastDelegate?displayProperty=nameWithType> come vincolo di classe di base. Il supporto Common Language Runtime (CLR) consente sempre questo vincolo, a differenza del linguaggio C#. Il vincolo `System.Delegate` consente di scrivere codice che funziona con i delegati in modo indipendente dai tipi. Il codice seguente definisce un metodo di estensione che combina due delegati purché siano dello stesso tipo:

[!code-csharp[using the delegate constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#16)]

Per combinare delegati dello stesso tipo, è possibile usare il metodo riportato sopra:

[!code-csharp[using the unmanaged constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#17)]

Se si rimuove il commento dall'ultima riga, non verrà compilata. Sia `first` che `test` sono tipi delegati, ma si tratta di tipi delegati diversi.

## <a name="enum-constraints"></a>Vincoli di enumerazione

A partire da C# 7.3 è anche possibile specificare il tipo <xref:System.Enum?displayProperty=nameWithType> come vincolo di classe di base. Il supporto Common Language Runtime (CLR) consente sempre questo vincolo, a differenza del linguaggio C#. I generics che usano `System.Enum` offrono una programmazione indipendente dai tipi che consente di memorizzare nella cache i risultati dei metodi statici in `System.Enum`. Nell'esempio seguente vengono individuati tutti i valori validi per un tipo di enumerazione e viene compilato un dizionario che esegue il mapping di tali valori alla propria rappresentazione di stringa.

[!code-csharp[using the enum constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#18)]

Metodi utilizzati per utilizzare la reflection, che ha implicazioni sulle prestazioni. È possibile chiamare questo metodo per creare una raccolta da memorizzare nella cache e riusare anziché ripetere le chiamate che richiedono reflection.

Il metodo può essere usato come illustrato nell'esempio seguente per creare un'enumerazione e compilare un dizionario dei relativi valori e nomi:

[!code-csharp[enum definition](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#19)]

[!code-csharp[using the enum constrained method](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#20)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic>
- [Guida per programmatori C#](../index.md)
- [Introduzione ai generics](./index.md)
- [Classi generiche](./generic-classes.md)
- [Vincolo new](../../language-reference/keywords/new-constraint.md)

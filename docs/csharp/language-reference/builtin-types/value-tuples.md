---
title: Tipi di tupla-riferimenti per C#
description: 'Informazioni sulle tuple C#: strutture di dati lightweight che è possibile usare per raggruppare elementi di dati vagamente correlati'
ms.date: 07/09/2020
helpviewer_keywords:
- value tuples [C#]
ms.openlocfilehash: 3d79ab19117847e2364b154db33a1521416bb3f4
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174991"
---
# <a name="tuple-types-c-reference"></a>Tipi di tupla (riferimenti per C#)

Disponibile in C# 7,0 e versioni successive, la funzionalità *Tuple* offre una sintassi concisa per raggruppare più elementi dati in una struttura di dati semplice. Nell'esempio seguente viene illustrato come è possibile dichiarare una variabile di tupla, inizializzarla e accedere ai relativi membri dati:

[!code-csharp-interactive[tuple intro](snippets/ValueTuples.cs#Introduction)]

Come illustrato nell'esempio precedente, per definire un tipo di tupla, è necessario specificare i tipi di tutti i relativi membri dati e, facoltativamente, i [nomi dei campi](#tuple-field-names). Non è possibile definire metodi in un tipo di tupla, ma è possibile usare i metodi forniti da .NET, come illustrato nell'esempio seguente:

[!code-csharp-interactive[tuple methods](snippets/ValueTuples.cs#MethodOnTuples)]

A partire da C# 7,3, i tipi di tupla supportano [gli operatori di uguaglianza](../operators/equality-operators.md) `==` e `!=` . Per ulteriori informazioni, vedere la sezione relativa all' [uguaglianza delle tuple](#tuple-equality) .

I tipi di tupla sono [tipi valore](value-types.md); gli elementi della tupla sono campi pubblici. Che rende i tipi di valore *modificabili* delle tuple.

> [!NOTE]
> La funzionalità Tuple richiede il <xref:System.ValueTuple?displayProperty=nameWithType> tipo e i tipi generici correlati, ad esempio, <xref:System.ValueTuple%602?displayProperty=nameWithType> che sono disponibili in .NET Core e .NET Framework 4,7 e versioni successive. Per usare le tuple in un progetto che ha come destinazione .NET Framework 4.6.2 o versione precedente, aggiungere il pacchetto NuGet [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) al progetto.

È possibile definire tuple con un numero elevato arbitrario di elementi:

[!code-csharp-interactive[large tuple](snippets/ValueTuples.cs#LargeTuple)]

## <a name="use-cases-of-tuples"></a>Casi d'uso delle tuple

Uno dei casi d'uso più comuni delle tuple è come tipo restituito del metodo. Ovvero, anziché definire i [ `out` parametri del metodo](../keywords/out-parameter-modifier.md), è possibile raggruppare i risultati del metodo in un tipo restituito della tupla, come illustrato nell'esempio seguente:

[!code-csharp-interactive[multiple method outputs](snippets/ValueTuples.cs#MultipleReturns)]

Come illustrato nell'esempio precedente, è possibile usare direttamente l'istanza di tupla restituita o [decostruirla](#tuple-assignment-and-deconstruction) in variabili separate.

È inoltre possibile utilizzare tipi di tupla anziché [tipi anonimi](../../programming-guide/classes-and-structs/anonymous-types.md); ad esempio, nelle query LINQ. Per ulteriori informazioni, vedere [scelta tra tipi anonimi e Tuple](../../../standard/base-types/choosing-between-anonymous-and-tuple.md).

In genere, le tuple vengono utilizzate per raggruppare elementi di dati debolmente correlati. Questo è in genere utile all'interno di metodi di utilità privati e interni. Nel caso di un'API pubblica, è consigliabile definire una [classe](../keywords/class.md) o un tipo di [struttura](struct.md) .

## <a name="tuple-field-names"></a>Nomi dei campi di tupla

È possibile specificare in modo esplicito i nomi dei campi di tupla in un'espressione di inizializzazione della tupla o nella definizione di un tipo di tupla, come illustrato nell'esempio seguente:

[!code-csharp-interactive[explicit field names](snippets/ValueTuples.cs#ExplicitFieldNames)]

A partire da C# 7,1, se non si specifica un nome di campo, può essere dedotto dal nome della variabile corrispondente in un'espressione di inizializzazione della tupla, come illustrato nell'esempio seguente:

[!code-csharp-interactive[inferred field names](snippets/ValueTuples.cs#InferFieldNames)]

Noto come inizializzatori di proiezione della tupla. Il nome di una variabile non è proiettato su un nome di campo di tupla nei casi seguenti:

- Il nome candidato è un nome di membro di un tipo di tupla, ad esempio,, `Item3` `ToString` o `Rest` .
- Il nome candidato è un duplicato di un altro nome di campo di tupla, esplicito o implicito.

In questi casi è possibile specificare in modo esplicito il nome di un campo o accedere a un campo con il nome predefinito.

I nomi predefiniti dei campi di tupla sono `Item1` , `Item2` `Item3` e così via. È sempre possibile usare il nome predefinito di un campo, anche quando un nome di campo viene specificato in modo esplicito o dedotto, come illustrato nell'esempio seguente:

[!code-csharp-interactive[default field names](snippets/ValueTuples.cs#DefaultFieldNames)]

L' [assegnazione di Tuple](#tuple-assignment-and-deconstruction) e i [confronti di uguaglianza delle tuple](#tuple-equality) non accettano nomi di campo.

In fase di compilazione, il compilatore sostituisce i nomi di campo non predefiniti con i nomi predefiniti corrispondenti. Di conseguenza, i nomi di campo specificati in modo esplicito o dedotti non sono disponibili in fase di esecuzione.

## <a name="tuple-assignment-and-deconstruction"></a>Assegnazione e decostruzione di Tuple

C# supporta l'assegnazione tra tipi di tupla che soddisfano entrambe le condizioni seguenti:

- entrambi i tipi di tupla hanno lo stesso numero di elementi
- per ogni posizione di tupla, il tipo dell'elemento di tupla a destra è uguale o convertibile in modo implicito nel tipo dell'elemento tupla a sinistra corrispondente.

I valori degli elementi di tupla vengono assegnati in base all'ordine degli elementi della tupla. I nomi dei campi di tupla vengono ignorati e non assegnati, come illustrato nell'esempio seguente:

[!code-csharp-interactive[tuple assignment](snippets/ValueTuples.cs#Assignment)]

È anche possibile usare l'operatore `=` di assegnazione per *decostruire* un'istanza di tupla in variabili separate. Questa operazione può essere eseguita in uno dei modi seguenti:

- Dichiarare in modo esplicito il tipo di ogni variabile racchiusa tra parentesi:

  [!code-csharp-interactive[specify types of variables](snippets/ValueTuples.cs#DeconstructExplicit)]

- Usare la `var` parola chiave all'esterno delle parentesi per dichiarare le variabili tipizzate in modo implicito e consentire al compilatore di dedurre i tipi:

  [!code-csharp-interactive[implicitly typed variables](snippets/ValueTuples.cs#DeconstructVar)]

- USA variabili esistenti:

  [!code-csharp-interactive[existing variables](snippets/ValueTuples.cs#DeconstructExisting)]

Per ulteriori informazioni sulla decostruzione di tuple e altri tipi, vedere decostruzione di [Tuple e altri tipi](../../deconstruct.md).

## <a name="tuple-equality"></a>Uguaglianza Tuple

A partire da C# 7.3, i tipi tupla supportano gli operatori `==` e `!=`. Questi operatori confrontano i membri dell'operando sinistro con i membri corrispondenti dell'operando destro che segue l'ordine degli elementi della tupla.

[!code-csharp-interactive[tuple equality](snippets/ValueTuples.cs#TupleEquality)]

Come illustrato nell'esempio precedente, le `==` `!=` operazioni e non prendono in considerazione i nomi dei campi di tupla.

Due tuple sono confrontabili quando sono soddisfatte entrambe le condizioni seguenti:

- Entrambe le tuple hanno lo stesso numero di elementi. Ad esempio, `t1 != t2` non compila se `t1` e `t2` hanno numeri di elementi diversi.
- Per ogni posizione di tupla, gli elementi corrispondenti dagli operandi di tupla a sinistra e a destra sono confrontabili con `==` gli `!=` operatori e. Ad esempio, `(1, (2, 3)) == ((1, 2), 3)` non viene compilato perché `1` non è confrontabile con `(1, 2)` .

Gli `==` `!=` operatori e confrontano le tuple in modalità di corto circuito. In altre termini, un'operazione viene arrestata non appena incontra una coppia di elementi non uguali o raggiunge le estremità delle tuple. Tuttavia, prima di qualsiasi confronto, vengono valutati *tutti* gli elementi della tupla, come illustrato nell'esempio seguente:

[!code-csharp-interactive[tuple element evaluation](snippets/ValueTuples.cs#TupleEvaluationForEquality)]

## <a name="tuples-as-out-parameters"></a>Tuple come parametri out

In genere, si effettua il refactoring di un metodo che dispone di [ `out` parametri](../keywords/out-parameter-modifier.md) in un metodo che restituisce una tupla. Tuttavia, esistono casi in cui un `out` parametro può essere di un tipo di tupla. Nell'esempio seguente viene illustrato come utilizzare le tuple come `out` parametri:

[!code-csharp-interactive[tuple as out parameter](snippets/ValueTuples.cs#TupleAsOutParameter)]

## <a name="tuples-vs-systemtuple"></a>Confronto tra tuple e`System.Tuple`

Le tuple C#, supportate dai <xref:System.ValueTuple?displayProperty=nameWithType> tipi, sono diverse dalle tuple rappresentate dai <xref:System.Tuple?displayProperty=nameWithType> tipi. Di seguito sono riportate le differenze principali:

- `ValueTuple`i tipi sono [tipi di valore](value-types.md). `Tuple`i tipi sono [tipi di riferimento](../keywords/reference-types.md).
- `ValueTuple`i tipi sono modificabili. `Tuple`i tipi non sono modificabili.
- I membri dati di `ValueTuple` tipo sono campi. I membri dati di `Tuple` tipo sono proprietà.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni, vedere le note sulla proposta di funzionalità seguenti:

- [Deduce i nomi delle Tuple (noti anche come inizializzatori di proiezione della tupla)](~/_csharplang/proposals/csharp-7.1/infer-tuple-names.md)
- [Supporto per `==` e `!=` su tipi di tupla](~/_csharplang/proposals/csharp-7.3/tuple-equality.md)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Tipi di valori](value-types.md)
- [Scelta tra tipi anonimi e di tupla](../../../standard/base-types/choosing-between-anonymous-and-tuple.md)
- <xref:System.ValueTuple?displayProperty=nameWithType>

---
title: Parola chiave ref - Riferimenti per C#
ms.date: 03/19/2020
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: 8d04f888befae2cad815c88a0d27bd836f458c63
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523784"
---
# <a name="ref-c-reference"></a>ref (Riferimenti per C#)

La parola chiave `ref` indica un valore che viene passato per riferimento. Viene usata in quattro contesti diversi:

- Nella firma di un metodo e in una chiamata al metodo, per passare un argomento a un metodo per riferimento. Per altre informazioni, vedere [Passaggio di un argomento per riferimento](#passing-an-argument-by-reference).
- Nella firma di un metodo, per restituire un valore al chiamante per riferimento. Per altre informazioni, vedere [Valori di riferimento restituiti](#reference-return-values).
- Nel corpo di un membro, per indicare che un valore restituito di riferimento è archiviato in locale come un riferimento che il chiamante intende modificare o, in generale, che una variabile locale accede a un altro valore per riferimento. Per altre informazioni, vedere [Variabili locali ref](#ref-locals).
- In una dichiarazione `struct` per dichiarare `ref struct` o `readonly ref struct`. Per altre informazioni, vedere [Tipi ref struct](#ref-struct-types).

## <a name="passing-an-argument-by-reference"></a>Passaggio di un argomento per riferimento

Quando viene usata nell'elenco di parametri di un metodo, la parola chiave `ref` indica che un argomento viene passato per riferimento, non per valore. La parola chiave `ref` imposta il parametro formale come alias dell'argomento, che deve essere una variabile. In altre parole, qualsiasi operazione sul parametro viene eseguita sull'argomento. Ad esempio, se il chiamante passa un'espressione di accesso a una variabile locale o un'espressione di accesso all'elemento di matrice e il metodo chiamato sostituisce l'oggetto a cui fa riferimento il parametro ref, la variabile locale del chiamante o l'elemento della matrice fa ora riferimento al nuovo oggetto quando il metodo restituisce .

> [!NOTE]
> Non confondere il concetto di passaggio per riferimento con il concetto di tipi di riferimento. I due concetti non sono uguali. Un parametro di metodo può essere modificato da `ref` che si tratti di un tipo di valore o di un tipo di riferimento. Non viene eseguito il boxing di un tipo di valore quando viene passato per riferimento.  

Per usare un parametro `ref`, la definizione del metodo e il metodo chiamante devono usare in modo esplicito la parola chiave `ref`, come illustrato nell'esempio seguente.  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

Un argomento passato a un parametro `ref` o `in` deve essere inizializzato prima di essere passato. Questo comportamento è diverso dai parametri [out](out-parameter-modifier.md), i cui argomenti non devono essere inizializzati in modo esplicito prima di essere passati.

I membri di una classe non possono avere firme che differiscono solo per `ref`, `in` o `out`. Un errore del compilatore si verifica se l'unica differenza tra due membri di un tipo è che uno di essi ha un parametro `ref` e l'altro ha un parametro `out` o `in`. Il codice seguente, ad esempio, non viene compilato.  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

È tuttavia possibile eseguire l'overload dei metodi quando un metodo ha un parametro `ref`, `in` o `out` e l'altro ha un parametro di valore, come illustrato nell'esempio seguente.
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 In altre situazioni che richiedono la firma corrispondente, ad esempio nascondere o sottoporre a override, `in`, `ref` e `out` fanno parte della firma e non sono corrispondenti tra loro.  
  
 Le proprietà non sono variabili. Sono metodi e non possono essere passate ai parametri `ref`.  
  
 Non è possibile usare le parole chiave `ref`, `in` e `out` per i seguenti tipi di metodi:  
  
- Metodi asincroni definiti usando il modificatore [async](async.md).  
- Metodi iteratori che includono un'istruzione [yield return](yield.md) o `yield break`.

Inoltre, i metodi di [estensione](../../programming-guide/classes-and-structs/extension-methods.md) hanno le seguenti restrizioni:

- La `out` parola chiave non può essere utilizzata sul primo argomento di un metodo di estensione.
- La `ref` parola chiave non può essere utilizzata sul primo argomento di un metodo di estensione quando l'argomento non è uno struct o un tipo generico non vincolato a essere uno struct.
- La `in` parola chiave non può essere utilizzata a meno che il primo argomento non sia uno struct. La `in` parola chiave non può essere utilizzata su qualsiasi tipo generico, anche quando vincolata a essere uno struct.

## <a name="passing-an-argument-by-reference-an-example"></a>Passaggio di un argomento per riferimento: un esempio

Negli esempi precedenti vengono passati tipi valore per riferimento. È anche possibile usare la parola chiave `ref` per passare tipi riferimento per riferimento. Il passaggio di un tipo riferimento per riferimento consente al metodo chiamato di sostituire l'oggetto a cui fa riferimento il parametro per riferimento nel chiamante. Il percorso di archiviazione dell'oggetto viene passato al metodo come valore del parametro referenziato. Se si modifica il valore nella posizione di archiviazione del parametro (in modo che punti a un nuovo oggetto), è anche possibile modificare il percorso di archiviazione a cui fa riferimento il chiamante. Nell'esempio seguente viene passata un'istanza di un tipo di riferimento come parametro `ref`.
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

Per altre informazioni su come passare i tipi di riferimento per valore e per riferimento, vedere [Passaggio di parametri di tipi di riferimento](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).
  
## <a name="reference-return-values"></a>Valori restituiti di riferimento

I valori restituiti di riferimento (o valori restituiti ref) sono i valori che un metodo restituisce per riferimento al chiamante. In altre parole, il chiamante può modificare il valore restituito da un metodo e tale modifica viene riflessa nello stato dell'oggetto che contiene il metodo.

Un valore restituito di riferimento viene definito mediante la parola chiave `ref`:

- Nella firma del metodo. Ad esempio, la firma del metodo seguente indica che il metodo `GetCurrentPrice` restituisce un valore <xref:System.Decimal> per riferimento.

```csharp
public ref decimal GetCurrentPrice()
```

- Tra il token `return` e la variabile restituita in un'istruzione `return` nel metodo. Ad esempio:

```csharp
return ref DecimalArray[0];
```

Affinché il chiamante modifichi lo stato dell'oggetto, il valore restituito di riferimento deve essere archiviato in una variabile definita in modo esplicito come [variabile locale ref](#ref-locals).

Il metodo chiamato può anche dichiarare il valore restituito come `ref readonly` per restituire il valore per riferimento e specificare che il codice chiamante non può modificare il valore restituito. Il metodo chiamante può evitare la copia del valore restituito archiviando il valore in una variabile [ref readonly](#ref-readonly-locals) locale.

Per un esempio, vedere A ref returns and ref locals example (Esempio di [valori restituiti ref e variabili locali di riferimento).](#a-ref-returns-and-ref-locals-example)

## <a name="ref-locals"></a>Variabili locali ref

Una variabile locale ref viene usata per fare riferimento ai valori restituiti mediante `return ref`. Non è possibile inizializzare una variabile locale ref in un valore restituito non ref. In altre parole, il lato destro dell'inizializzazione deve essere un riferimento. Tutte le modifiche apportate al valore della variabile locale ref vengono riflesse nello stato dell'oggetto di cui metodo ha restituito il valore per riferimento.

Per definire una variabile locale ref, usare la parola chiave `ref` prima della dichiarazione di variabile, nonché immediatamente prima della chiamata al metodo che restituisce il valore per riferimento.

Ad esempio, l'istruzione seguente definisce un valore di variabile locale ref restituito da un metodo denominato `GetEstimatedValue`:

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

È possibile accedere a un valore per riferimento nello stesso modo. In alcuni casi, l'accesso a un valore per riferimento migliora le prestazioni evitando un'operazione di copia potenzialmente dispendiosa. L'istruzione seguente, ad esempio, spiega come sia possibile definire un valore locale di riferimento usato per fare riferimento a un valore.

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

Si noti che nei due esempi la parola chiave `ref` deve essere usata in entrambe le posizioni. In caso contrario, il compilatore genera l'errore CS8172, "Non è possibile inizializzare una variabile per riferimento con un valore".

A partire da C# 7.3, la variabile di iterazione dell'istruzione `foreach` può essere una variabile locale ref o locale ref readonly. Per altre informazioni, vedere l'articolo sull'[istruzione foreach](foreach-in.md).

Inoltre, a partire dalla versione 7.3 di C, è possibile riassegnare una variabile locale ref o ref readonly con l'operatore di [assegnazione ref](../operators/assignment-operator.md#ref-assignment-operator).

## <a name="ref-readonly-locals"></a>Variabili ref readonly

Una variabile locale ref readonly viene usata per fare riferimento ai valori restituiti dal metodo o dalla proprietà che include `ref readonly` nella propria firma e usa `return ref`. Una variabile `ref readonly` combina le proprietà di una variabile locale `ref` con una variabile `readonly`: è un alias per l'archiviazione cui è assegnata e non può essere modificata.

## <a name="a-ref-returns-and-ref-locals-example"></a>Esempio di valori restituiti e variabili locali ref

Nell'esempio seguente viene definita una classe `Book` che ha due campi <xref:System.String>, `Title` e `Author`. Definisce inoltre una classe `BookCollection` che include una matrice privata di oggetti `Book`. I singoli oggetti book vengono restituiti per riferimento chiamando il relativo metodo `GetBookByTitle`.

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

Quando il chiamante archivia il valore restituito dal metodo `GetBookByTitle` come una variabile locale ref, le modifiche apportate al valore restituito dal chiamante vengono riflesse nell'oggetto `BookCollection`, come illustrato nell'esempio seguente.

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="ref-struct-types"></a>Tipi ref struct

L'aggiunta del modificatore `ref` a una dichiarazione `struct` specifica che le istanze di questo tipo devono essere allocate nello stack. In altre parole, questi tipi non possono mai essere creati nell'heap come membro di un'altra classe. La principale motivazione di questa funzionalità sono stati <xref:System.Span%601> e le strutture correlate.

L'obiettivo di mantenere un tipo `ref struct` come variabile allocata nello stack comporta diverse regole che il compilatore applica per tutti i tipi `ref struct`.

- Non è possibile eseguire il boxing di `ref struct`. Non è possibile assegnare un tipo `ref struct` a una variabile di tipo `object`, `dynamic` o qualsiasi tipo di interfaccia.
- I tipi `ref struct` non possono implementare interfacce.
- Non è possibile dichiarare `ref struct` come campo membro di una classe o di un normale struct. Questo include la dichiarazione di una proprietà implementata automaticamente, che crea un campo sottostante generato dal compilatore.
- Non è possibile dichiarare variabili locali che sono tipi `ref struct` nei metodi asincroni. È possibile dichiararle nei metodi sincroni che restituiscono tipi simili a <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> o `Task`.
- Non è possibile dichiarare variabili locali `ref struct` negli iteratori.
- Non è possibile acquisire variabili `ref struct` in espressioni lambda o funzioni locali.

Queste restrizioni evitano l'uso accidentale di un tipo `ref struct` in modo che possa essere alzato di livello nell'heap gestito.

È possibile combinare i modificatori per dichiarare uno struct come `readonly ref`. `readonly ref struct` combina i vantaggi e le restrizioni delle dichiarazioni `ref struct` e `readonly struct`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Scrivere codice efficiente sicuro](../../write-safe-efficient-code.md)
- [Valori restituiti e variabili locali ref](../../programming-guide/classes-and-structs/ref-returns.md)
- [Espressione condizionale ref](../operators/conditional-operator.md#conditional-ref-expression)
- [Passaggio di parametriPassing Parameters](../../programming-guide/classes-and-structs/passing-parameters.md)
- [Parametri di metodo](method-parameters.md)
- [Guida di riferimento a C](../index.md)
- [Guida alla programmazione in C](../../programming-guide/index.md)
- [Parole chiave di C](index.md)

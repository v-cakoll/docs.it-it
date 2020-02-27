---
title: Tipi di riferimento predefiniti - Riferimenti per C#
description: Informazioni sui tipi di riferimento con parole chiave C# che è possibile usare per la dichiarazione.
ms.date: 06/25/2019
f1_keywords:
- object_CSharpKeyword
- object
- delegate_CSharpKeyword
- delegate
- dynamic_CSharpKeyword
- string
- string_CSharpKeyword
helpviewer_keywords:
- object keyword [C#]
- delegate keyword [C#]
- function pointers [C#]
- dynamic [C#]
- dynamic keyword [C#]
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.openlocfilehash: 6b65d7e79e4eac30171eb0aad650f7c1e3880e30
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627270"
---
# <a name="built-in-reference-types-c-reference"></a>Tipi di riferimento predefiniti (riferimenti per C#)

C# ha un numero di tipi di riferimento predefiniti. Hanno parole chiave o operatori che sono sinonimi per un tipo nella libreria .NET. 

## <a name="the-object-type"></a>Tipo di oggetto

Il tipo `object` è un alias per <xref:System.Object?displayProperty=nameWithType> in .NET. Nel sistema di tipi unificato di C#, tutti i tipi, predefiniti e definiti dall'utente, i tipi riferimento e i tipi valore ereditano direttamente o indirettamente da <xref:System.Object?displayProperty=nameWithType>. Alle variabili di tipo `object` è possibile assegnare valori di qualsiasi tipo. Qualsiasi variabile `object` può essere assegnata al suo valore predefinito usando il valore letterale `null`. Una variabile di un tipo di valore convertita in oggetto viene definita *boxed*. Quando una variabile di tipo `object` viene convertita in un tipo valore, viene definito *unboxed*. Per altre informazioni, vedere [Boxing e unboxing](../../programming-guide/types/boxing-and-unboxing.md). 

## <a name="the-string-type"></a>Tipo di stringa

Il tipo `string` rappresenta una sequenza di zero o più caratteri Unicode. `string` è un alias per <xref:System.String?displayProperty=nameWithType> in .NET.

Sebbene `string` sia un tipo riferimento, gli [operatori di uguaglianza`==` e `!=`](../operators/equality-operators.md#string-equality) vengono definiti per confrontare i valori degli oggetti `string` e non dei riferimenti. In questo modo il test di uguaglianza delle stringhe è più intuitivo. Ad esempio,

```csharp-interactive
string a = "hello";
string b = "h";
// Append to contents of 'b'
b += "ello";
Console.WriteLine(a == b);
Console.WriteLine(object.ReferenceEquals(a, b));
```

Viene visualizzato "True" e quindi "False" perché il contenuto delle stringhe è equivalente, ma `a` e `b` non fanno riferimento alla stessa istanza della stringa.

L'[operatore +](../operators/addition-operator.md#string-concatenation) concatena le stringhe:

```csharp
string a = "good " + "morning";
```

Questo crea un oggetto stringa contenente "good morning".

Le stringhe sono *immutabili*: non è possibile modificare il contenuto di un oggetto stringa dopo la creazione dell'oggetto, sebbene la sintassi sembri indicare che è possibile apportare modifiche. Ad esempio, quando si scrive il codice, il compilatore crea un nuovo oggetto stringa per archiviare la nuova sequenza di caratteri e il nuovo oggetto viene assegnato a `b`. La memoria allocata per `b` (quando conteneva la stringa "h") è quindi idonea per la garbage collection.

```csharp
string b = "h";
b += "ello";
```

L' [operatore](../operators/member-access-operators.md#indexer-operator-) `[]` può essere usato per l'accesso di sola lettura a singoli caratteri di una stringa. I valori di indice validi iniziano da `0` e devono essere minori della lunghezza della stringa:

```csharp
string str = "test";
char x = str[2];  // x = 's';
```

Analogamente, l'operatore `[]` può essere usato anche per scorrere ogni carattere in una stringa:

```csharp-interactive
string str = "test";

for (int i = 0; i < str.Length; i++)
{
  Console.Write(str[i] + " ");
}
// Output: t e s t
``` 

I valori letterali della stringa sono di tipo `string` e possono essere scritti in due formati, tra virgolette e delimitati da `@`. I valori letterali della stringa tra virgolette sono racchiusi in virgolette doppie ("):

```csharp
"good morning"  // a string literal
```

I valori letterali della stringa possono contenere qualsiasi carattere letterale. Sono incluse le sequenze di escape. L'esempio seguente usa una sequenza di escape `\\` per la barra rovesciata, `\u0066` per la lettera f e `\n` per la nuova riga.

```csharp-interactive
string a = "\\\u0066\n F";
Console.WriteLine(a);
// Output:
// \f
//  F
```

> [!NOTE]
> Il codice di escape `\udddd` (dove `dddd` è un numero a quattro cifre) rappresenta il carattere Unicode U+`dddd`. Vengono riconosciuti anche i codici di escape Unicode a otto cifre: `\Udddddddd`.

I [valori letterali della stringa verbatim](../tokens/verbatim.md) iniziano con `@` e sono anche racchiusi tra virgolette doppie. Ad esempio,

```csharp
@"good morning"  // a string literal
```

Il vantaggio delle stringhe verbatim è che le sequenze di escape *non* sono elaborate, quindi rendono più semplice scrivere ad esempio un nome file di Windows completo:

```csharp
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"
```

Per includere le virgolette doppie in una stringa @-quoted, duplicarla:

```csharp
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.
```

## <a name="the-delegate-type"></a>Tipo di delegato

La dichiarazione di un tipo delegato è simile alla firma di un metodo. Ha un valore restituito e una serie di parametri di qualsiasi tipo:

```csharp
public delegate void MessageDelegate(string message);
public delegate int AnotherDelegate(MyType m, long num);
```

In .NET i tipi `System.Action` e `System.Func` offrono definizioni generiche per molti delegati comuni. Probabilmente non è necessario definire nuovi tipi di delegato. È possibile eventualmente creare istanze dei tipi generici disponibili.

`delegate` è un tipo riferimento che può essere usato per incapsulare un metodo denominato o anonimo. I delegati sono simili ai puntatori a funzioni in C++, ma sono indipendenti dai tipi e protetti. Per le applicazioni dei delegati, vedere  [Delegati](../../programming-guide/delegates/index.md) e [Delegati generici](../../programming-guide/generics/generic-delegates.md). I delegati sono la base degli [eventi](../../programming-guide/events/index.md). È possibile creare un'istanza di un delegato associandolo a un metodo denominato o anonimo.

È necessario creare un'istanza del delegato con un metodo o un'espressione lambda con tipo restituito compatibile e parametri di input. Per altre informazioni sul grado di varianza consentito nella firma del metodo, vedere [Varianza nei delegati](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md). Per l'uso con i metodi anonimi, è necessario dichiarare insieme il delegato e il codice da associare ad esso. 

## <a name="the-dynamic-type"></a>Tipo dinamico

Il tipo `dynamic` indica l'uso della variabile e dei riferimenti ai relativi membri per escludere il controllo del tipo in fase di compilazione. Queste operazioni vengono risolte in fase di esecuzione. Il tipo `dynamic` semplifica l'accesso alle API COM, ad esempio le API di automazione di Office, alle API dinamiche, ad esempio le librerie di IronPython, e al modello DOM (Document Object Model) HTML.

Il tipo `dynamic` si comporta come tipo `object` nella maggior parte dei casi. In particolare, qualsiasi espressione non null può essere convertita nel tipo `dynamic`. Il tipo `dynamic` si comporta diversamente da `object` nelle operazioni che contengono espressioni di tipo `dynamic` che non vengono risolte o il tipo non viene verificato dal compilatore. Il compilatore raggruppa le informazioni sull'operazione e tali informazioni successivamente vengono usate per valutare l'operazione in fase di esecuzione. Come parte del processo, le variabili di tipo `dynamic` vengono compilate in variabili di tipo `object`. Di conseguenza, il tipo `dynamic` esiste solo in fase di compilazione, non in fase di esecuzione.

Nell'esempio seguente vengono messe a confronto una variabile di tipo `dynamic` e una variabile di tipo `object`. Per verificare il tipo di ogni variabile in fase di compilazione, posizionare il puntatore del mouse su `dyn` o `obj` nelle istruzioni `WriteLine`. Copiare il codice seguente in un editor in cui IntelliSense è disponibile. IntelliSense visualizza **dynamic** per `dyn` e **object** per `obj`.

[!code-csharp[csrefKeywordsTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#21)]

Le istruzioni <xref:System.Console.WriteLine%2A> visualizzano i tipi in fase di esecuzione di `dyn` e `obj`. A questo punto, entrambe hanno lo stesso tipo, un numero intero. Viene generato l'output seguente:

```console
System.Int32
System.Int32
```

Per vedere la differenza tra `dyn` e `obj` in fase di compilazione, aggiungere le due righe seguenti tra le dichiarazioni e le istruzioni `WriteLine` dell'esempio precedente.

```csharp
dyn = dyn + 3;
obj = obj + 3;
```

 Viene segnalato un errore del compilatore per il tentativo di aggiunta di un numero intero e di un oggetto nell'espressione `obj + 3`. Tuttavia non vengono segnalati errori per `dyn + 3`. L'espressione che contiene `dyn` non viene controllata in fase di compilazione perché il tipo di `dyn` è `dynamic`.

Nell'esempio seguente viene usato `dynamic` in diverse dichiarazioni. Il metodo `Main` confronta anche il controllo dei tipi in fase di compilazione con il controllo dei tipi in fase di esecuzione.

[!code-csharp[csrefKeywordsTypes#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic2.cs#25)]

### <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Parole chiave di C#](../keywords/index.md)
- [Eventi](../../programming-guide/events/index.md)
- [Uso del tipo dinamico](../../programming-guide/types/using-type-dynamic.md)
- [Procedure consigliate per l'uso delle stringhe](../../../standard/base-types/best-practices-strings.md)
- [Operazioni di base su stringhe](../../../standard/base-types/basic-string-operations.md)
- [Creazione di nuove stringhe](../../../standard/base-types/creating-new.md)
- [Operatori di cast e di test del tipo](../operators/type-testing-and-cast.md)
- [Come eseguire il cast sicuro usando i criteri di ricerca e gli operatori As e is](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [Procedura dettagliata: Creazione e utilizzo di oggetti dinamici](../../programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- <xref:System.Object?displayProperty=nameWithType>
- <xref:System.String?displayProperty=nameWithType>
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>

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
ms.openlocfilehash: d5ca0593d802d331d980cf35c701e0a79d54abee
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163098"
---
# <a name="built-in-reference-types-c-reference"></a><span data-ttu-id="49e36-103">Tipi di riferimento predefiniti (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="49e36-103">Built-in reference types (C# reference)</span></span>

<span data-ttu-id="49e36-104">C# ha un numero di tipi di riferimento predefiniti.</span><span class="sxs-lookup"><span data-stu-id="49e36-104">C# has a number of built-in reference types.</span></span> <span data-ttu-id="49e36-105">Hanno parole chiave o operatori che sono sinonimi per un tipo nella libreria .NET.</span><span class="sxs-lookup"><span data-stu-id="49e36-105">They have keywords or operators that are synonyms for a type in the .NET library.</span></span> 

## <a name="the-object-type"></a><span data-ttu-id="49e36-106">Tipo di oggetto</span><span class="sxs-lookup"><span data-stu-id="49e36-106">The object type</span></span>

<span data-ttu-id="49e36-107">Il tipo `object` è un alias per <xref:System.Object?displayProperty=nameWithType> in .NET.</span><span class="sxs-lookup"><span data-stu-id="49e36-107">The `object` type is an alias for <xref:System.Object?displayProperty=nameWithType> in .NET.</span></span> <span data-ttu-id="49e36-108">Nel sistema di tipi unificato di C#, tutti i tipi, predefiniti e definiti dall'utente, i tipi riferimento e i tipi valore ereditano direttamente o indirettamente da <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="49e36-108">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="49e36-109">Alle variabili di tipo `object` è possibile assegnare valori di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="49e36-109">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="49e36-110">Qualsiasi variabile `object` può essere assegnata al suo valore predefinito usando il valore letterale `null`.</span><span class="sxs-lookup"><span data-stu-id="49e36-110">Any `object` variable can be assigned to its default value using the literal `null`.</span></span> <span data-ttu-id="49e36-111">Una variabile di un tipo di valore convertita in oggetto viene definita *boxed*.</span><span class="sxs-lookup"><span data-stu-id="49e36-111">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="49e36-112">Quando una variabile di tipo `object` viene convertita in un tipo valore, viene definito *unboxed*.</span><span class="sxs-lookup"><span data-stu-id="49e36-112">When a variable of type `object` is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="49e36-113">Per altre informazioni, vedere [Boxing e unboxing](../../programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="49e36-113">For more information, see [Boxing and Unboxing](../../programming-guide/types/boxing-and-unboxing.md).</span></span> 

## <a name="the-string-type"></a><span data-ttu-id="49e36-114">Tipo di stringa</span><span class="sxs-lookup"><span data-stu-id="49e36-114">The string type</span></span>

<span data-ttu-id="49e36-115">Il tipo `string` rappresenta una sequenza di zero o più caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="49e36-115">The `string` type represents a sequence of zero or more Unicode characters.</span></span> <span data-ttu-id="49e36-116">`string` è un alias per <xref:System.String?displayProperty=nameWithType> in .NET.</span><span class="sxs-lookup"><span data-stu-id="49e36-116">`string` is an alias for <xref:System.String?displayProperty=nameWithType> in .NET.</span></span>

<span data-ttu-id="49e36-117">Sebbene `string` sia un tipo riferimento, gli [operatori di uguaglianza`==` e `!=`](../operators/equality-operators.md#string-equality) vengono definiti per confrontare i valori degli oggetti `string` e non dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="49e36-117">Although `string` is a reference type, the [equality operators `==` and `!=`](../operators/equality-operators.md#string-equality) are defined to compare the values of `string` objects, not references.</span></span> <span data-ttu-id="49e36-118">In questo modo il test di uguaglianza delle stringhe è più intuitivo.</span><span class="sxs-lookup"><span data-stu-id="49e36-118">This makes testing for string equality more intuitive.</span></span> <span data-ttu-id="49e36-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="49e36-119">For example:</span></span>

```csharp-interactive
string a = "hello";
string b = "h";
// Append to contents of 'b'
b += "ello";
Console.WriteLine(a == b);
Console.WriteLine(object.ReferenceEquals(a, b));
```

<span data-ttu-id="49e36-120">Viene visualizzato "True" e quindi "False" perché il contenuto delle stringhe è equivalente, ma `a` e `b` non fanno riferimento alla stessa istanza della stringa.</span><span class="sxs-lookup"><span data-stu-id="49e36-120">This displays "True" and then "False" because the content of the strings are equivalent, but `a` and `b` do not refer to the same string instance.</span></span>

<span data-ttu-id="49e36-121">L'[operatore +](../operators/addition-operator.md#string-concatenation) concatena le stringhe:</span><span class="sxs-lookup"><span data-stu-id="49e36-121">The [+ operator](../operators/addition-operator.md#string-concatenation) concatenates strings:</span></span>

```csharp
string a = "good " + "morning";
```

<span data-ttu-id="49e36-122">Questo crea un oggetto stringa contenente "good morning".</span><span class="sxs-lookup"><span data-stu-id="49e36-122">This creates a string object that contains "good morning".</span></span>

<span data-ttu-id="49e36-123">Le stringhe sono *immutabili*: non è possibile modificare il contenuto di un oggetto stringa dopo la creazione dell'oggetto, sebbene la sintassi sembri indicare che è possibile apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="49e36-123">Strings are *immutable*--the contents of a string object cannot be changed after the object is created, although the syntax makes it appear as if you can do this.</span></span> <span data-ttu-id="49e36-124">Ad esempio, quando si scrive il codice, il compilatore crea un nuovo oggetto stringa per archiviare la nuova sequenza di caratteri e il nuovo oggetto viene assegnato a `b`.</span><span class="sxs-lookup"><span data-stu-id="49e36-124">For example, when you write this code, the compiler actually creates a new string object to hold the new sequence of characters, and that new object is assigned to `b`.</span></span> <span data-ttu-id="49e36-125">La memoria allocata per `b` (quando conteneva la stringa "h") è quindi idonea per la garbage collection.</span><span class="sxs-lookup"><span data-stu-id="49e36-125">The memory that had been allocated for `b` (when it contained the string "h") is then eligible for garbage collection.</span></span>

```csharp
string b = "h";
b += "ello";
```

<span data-ttu-id="49e36-126">L' [operatore](../operators/member-access-operators.md#indexer-operator-) `[]` può essere usato per l'accesso di sola lettura a singoli caratteri di una stringa.</span><span class="sxs-lookup"><span data-stu-id="49e36-126">The `[]` [operator](../operators/member-access-operators.md#indexer-operator-) can be used for readonly access to individual characters of a string.</span></span> <span data-ttu-id="49e36-127">I valori di indice validi iniziano da `0` e devono essere minori della lunghezza della stringa:</span><span class="sxs-lookup"><span data-stu-id="49e36-127">Valid index values start at `0` and must be less than the length of the string:</span></span>

```csharp
string str = "test";
char x = str[2];  // x = 's';
```

<span data-ttu-id="49e36-128">Analogamente, l'operatore `[]` può essere usato anche per scorrere ogni carattere in una stringa:</span><span class="sxs-lookup"><span data-stu-id="49e36-128">In similar fashion, the `[]` operator can also be used for iterating over each character in a string:</span></span>

```csharp-interactive
string str = "test";

for (int i = 0; i < str.Length; i++)
{
  Console.Write(str[i] + " ");
}
// Output: t e s t
``` 

<span data-ttu-id="49e36-129">I valori letterali della stringa sono di tipo `string` e possono essere scritti in due formati, tra virgolette e delimitati da `@`.</span><span class="sxs-lookup"><span data-stu-id="49e36-129">String literals are of type `string` and can be written in two forms, quoted and `@`-quoted.</span></span> <span data-ttu-id="49e36-130">I valori letterali della stringa tra virgolette sono racchiusi in virgolette doppie ("):</span><span class="sxs-lookup"><span data-stu-id="49e36-130">Quoted string literals are enclosed in double quotation marks ("):</span></span>

```csharp
"good morning"  // a string literal
```

<span data-ttu-id="49e36-131">I valori letterali della stringa possono contenere qualsiasi carattere letterale.</span><span class="sxs-lookup"><span data-stu-id="49e36-131">String literals can contain any character literal.</span></span> <span data-ttu-id="49e36-132">Sono incluse le sequenze di escape.</span><span class="sxs-lookup"><span data-stu-id="49e36-132">Escape sequences are included.</span></span> <span data-ttu-id="49e36-133">L'esempio seguente usa una sequenza di escape `\\` per la barra rovesciata, `\u0066` per la lettera f e `\n` per la nuova riga.</span><span class="sxs-lookup"><span data-stu-id="49e36-133">The following example uses escape sequence `\\` for backslash, `\u0066` for the letter f, and `\n` for newline.</span></span>

```csharp-interactive
string a = "\\\u0066\n F";
Console.WriteLine(a);
\\ Output:
\\ \f
\\  F
```

> [!NOTE]
> <span data-ttu-id="49e36-134">Il codice di escape `\udddd` (dove `dddd` è un numero a quattro cifre) rappresenta il carattere Unicode U+`dddd`.</span><span class="sxs-lookup"><span data-stu-id="49e36-134">The escape code `\udddd` (where `dddd` is a four-digit number) represents the Unicode character U+`dddd`.</span></span> <span data-ttu-id="49e36-135">Vengono riconosciuti anche i codici di escape Unicode a otto cifre: `\Udddddddd`.</span><span class="sxs-lookup"><span data-stu-id="49e36-135">Eight-digit Unicode escape codes are also recognized: `\Udddddddd`.</span></span>

<span data-ttu-id="49e36-136">I [valori letterali della stringa verbatim](../tokens/verbatim.md) iniziano con `@` e sono anche racchiusi tra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="49e36-136">[Verbatim string literals](../tokens/verbatim.md) start with `@` and are also enclosed in double quotation marks.</span></span> <span data-ttu-id="49e36-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="49e36-137">For example:</span></span>

```csharp
@"good morning"  // a string literal
```

<span data-ttu-id="49e36-138">Il vantaggio delle stringhe verbatim è che le sequenze di escape *non* sono elaborate, quindi rendono più semplice scrivere ad esempio un nome file di Windows completo:</span><span class="sxs-lookup"><span data-stu-id="49e36-138">The advantage of verbatim strings is that escape sequences are *not* processed, which makes it easy to write, for example, a fully qualified Windows file name:</span></span>

```csharp
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"
```

<span data-ttu-id="49e36-139">Per includere le virgolette doppie in una stringa @-quoted, duplicarla:</span><span class="sxs-lookup"><span data-stu-id="49e36-139">To include a double quotation mark in an @-quoted string, double it:</span></span>

```csharp
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.
```

## <a name="the-delegate-type"></a><span data-ttu-id="49e36-140">Tipo di delegato</span><span class="sxs-lookup"><span data-stu-id="49e36-140">The delegate type</span></span>

<span data-ttu-id="49e36-141">La dichiarazione di un tipo delegato è simile alla firma di un metodo.</span><span class="sxs-lookup"><span data-stu-id="49e36-141">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="49e36-142">Ha un valore restituito e una serie di parametri di qualsiasi tipo:</span><span class="sxs-lookup"><span data-stu-id="49e36-142">It has a return value and any number of parameters of any type:</span></span>

```csharp
public delegate void MessageDelegate(string message);
public delegate int AnotherDelegate(MyType m, long num);
```

<span data-ttu-id="49e36-143">In .NET i tipi `System.Action` e `System.Func` offrono definizioni generiche per molti delegati comuni.</span><span class="sxs-lookup"><span data-stu-id="49e36-143">In .NET, `System.Action` and `System.Func` types provide generic definitions for many common delegates.</span></span> <span data-ttu-id="49e36-144">Probabilmente non è necessario definire nuovi tipi di delegato.</span><span class="sxs-lookup"><span data-stu-id="49e36-144">You likely don't need to define new custom delegate types.</span></span> <span data-ttu-id="49e36-145">È possibile eventualmente creare istanze dei tipi generici disponibili.</span><span class="sxs-lookup"><span data-stu-id="49e36-145">Instead, you can create instantiations of the provided generic types.</span></span>

<span data-ttu-id="49e36-146">`delegate` è un tipo riferimento che può essere usato per incapsulare un metodo denominato o anonimo.</span><span class="sxs-lookup"><span data-stu-id="49e36-146">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="49e36-147">I delegati sono simili ai puntatori a funzioni in C++, ma sono indipendenti dai tipi e protetti.</span><span class="sxs-lookup"><span data-stu-id="49e36-147">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="49e36-148">Per le applicazioni dei delegati, vedere  [Delegati](../../programming-guide/delegates/index.md) e [Delegati generici](../../programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="49e36-148">For applications of delegates, see [Delegates](../../programming-guide/delegates/index.md) and [Generic Delegates](../../programming-guide/generics/generic-delegates.md).</span></span> <span data-ttu-id="49e36-149">I delegati sono la base degli [eventi](../../programming-guide/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="49e36-149">Delegates are the basis for [Events](../../programming-guide/events/index.md).</span></span> <span data-ttu-id="49e36-150">È possibile creare un'istanza di un delegato associandolo a un metodo denominato o anonimo.</span><span class="sxs-lookup"><span data-stu-id="49e36-150">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span>

<span data-ttu-id="49e36-151">È necessario creare un'istanza del delegato con un metodo o un'espressione lambda con tipo restituito compatibile e parametri di input.</span><span class="sxs-lookup"><span data-stu-id="49e36-151">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="49e36-152">Per altre informazioni sul grado di varianza consentito nella firma del metodo, vedere [Varianza nei delegati](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="49e36-152">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span> <span data-ttu-id="49e36-153">Per l'uso con i metodi anonimi, è necessario dichiarare insieme il delegato e il codice da associare ad esso.</span><span class="sxs-lookup"><span data-stu-id="49e36-153">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> 

## <a name="the-dynamic-type"></a><span data-ttu-id="49e36-154">Tipo dinamico</span><span class="sxs-lookup"><span data-stu-id="49e36-154">The dynamic type</span></span>

<span data-ttu-id="49e36-155">Il tipo `dynamic` indica l'uso della variabile e dei riferimenti ai relativi membri per escludere il controllo del tipo in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="49e36-155">The `dynamic` type indicates that use of the variable and references to its members bypass compile-time type checking.</span></span> <span data-ttu-id="49e36-156">Queste operazioni vengono risolte in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="49e36-156">Instead, these operations are resolved at run time.</span></span> <span data-ttu-id="49e36-157">Il tipo `dynamic` semplifica l'accesso alle API COM, ad esempio le API di automazione di Office, alle API dinamiche, ad esempio le librerie di IronPython, e al modello DOM (Document Object Model) HTML.</span><span class="sxs-lookup"><span data-stu-id="49e36-157">The `dynamic` type simplifies access to COM APIs such as the Office Automation APIs, to dynamic APIs such as IronPython libraries, and to the HTML Document Object Model (DOM).</span></span>

<span data-ttu-id="49e36-158">Il tipo `dynamic` si comporta come tipo `object` nella maggior parte dei casi.</span><span class="sxs-lookup"><span data-stu-id="49e36-158">Type `dynamic` behaves like type `object` in most circumstances.</span></span> <span data-ttu-id="49e36-159">In particolare, qualsiasi espressione non null può essere convertita nel tipo `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="49e36-159">In particular, any non-null expression can be converted to the `dynamic` type.</span></span> <span data-ttu-id="49e36-160">Il tipo `dynamic` si comporta diversamente da `object` nelle operazioni che contengono espressioni di tipo `dynamic` che non vengono risolte o il tipo non viene verificato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="49e36-160">The `dynamic` type differs from `object` in that operations that contain expressions of type `dynamic` are not resolved or type checked by the compiler.</span></span> <span data-ttu-id="49e36-161">Il compilatore raggruppa le informazioni sull'operazione e tali informazioni successivamente vengono usate per valutare l'operazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="49e36-161">The compiler packages together information about the operation, and that information is later used to evaluate the operation at run time.</span></span> <span data-ttu-id="49e36-162">Come parte del processo, le variabili di tipo `dynamic` vengono compilate in variabili di tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="49e36-162">As part of the process, variables of type `dynamic` are compiled into variables of type `object`.</span></span> <span data-ttu-id="49e36-163">Di conseguenza, il tipo `dynamic` esiste solo in fase di compilazione, non in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="49e36-163">Therefore, type `dynamic` exists only at compile time, not at run time.</span></span>

<span data-ttu-id="49e36-164">Nell'esempio seguente vengono messe a confronto una variabile di tipo `dynamic` e una variabile di tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="49e36-164">The following example contrasts a variable of type `dynamic` to a variable of type `object`.</span></span> <span data-ttu-id="49e36-165">Per verificare il tipo di ogni variabile in fase di compilazione, posizionare il puntatore del mouse su `dyn` o `obj` nelle istruzioni `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="49e36-165">To verify the type of each variable at compile time, place the mouse pointer over `dyn` or `obj` in the `WriteLine` statements.</span></span> <span data-ttu-id="49e36-166">Copiare il codice seguente in un editor in cui IntelliSense è disponibile.</span><span class="sxs-lookup"><span data-stu-id="49e36-166">Copy the following code into an editor where IntelliSense is available.</span></span> <span data-ttu-id="49e36-167">IntelliSense visualizza **dynamic** per `dyn` e **object** per `obj`.</span><span class="sxs-lookup"><span data-stu-id="49e36-167">IntelliSense shows **dynamic** for `dyn` and **object** for `obj`.</span></span>

[!code-csharp[csrefKeywordsTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#21)]

<span data-ttu-id="49e36-168">Le istruzioni <xref:System.Console.WriteLine%2A> visualizzano i tipi in fase di esecuzione di `dyn` e `obj`.</span><span class="sxs-lookup"><span data-stu-id="49e36-168">The <xref:System.Console.WriteLine%2A> statements display the run-time types of `dyn` and `obj`.</span></span> <span data-ttu-id="49e36-169">A questo punto, entrambe hanno lo stesso tipo, un numero intero.</span><span class="sxs-lookup"><span data-stu-id="49e36-169">At that point, both have the same type, integer.</span></span> <span data-ttu-id="49e36-170">Viene generato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="49e36-170">The following output is produced:</span></span>

```console
System.Int32
System.Int32
```

<span data-ttu-id="49e36-171">Per vedere la differenza tra `dyn` e `obj` in fase di compilazione, aggiungere le due righe seguenti tra le dichiarazioni e le istruzioni `WriteLine` dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="49e36-171">To see the difference between `dyn` and `obj` at compile time, add the following two lines between the declarations and the `WriteLine` statements in the previous example.</span></span>

```csharp
dyn = dyn + 3;
obj = obj + 3;
```

 <span data-ttu-id="49e36-172">Viene segnalato un errore del compilatore per il tentativo di aggiunta di un numero intero e di un oggetto nell'espressione `obj + 3`.</span><span class="sxs-lookup"><span data-stu-id="49e36-172">A compiler error is reported for the attempted addition of an integer and an object in expression `obj + 3`.</span></span> <span data-ttu-id="49e36-173">Tuttavia non vengono segnalati errori per `dyn + 3`.</span><span class="sxs-lookup"><span data-stu-id="49e36-173">However, no error is reported for `dyn + 3`.</span></span> <span data-ttu-id="49e36-174">L'espressione che contiene `dyn` non viene controllata in fase di compilazione perché il tipo di `dyn` è `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="49e36-174">The expression that contains `dyn` is not checked at compile time because the type of `dyn` is `dynamic`.</span></span>

<span data-ttu-id="49e36-175">Nell'esempio seguente viene usato `dynamic` in diverse dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="49e36-175">The following example uses `dynamic` in several declarations.</span></span> <span data-ttu-id="49e36-176">Il metodo `Main` confronta anche il controllo dei tipi in fase di compilazione con il controllo dei tipi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="49e36-176">The `Main` method also contrasts compile-time type checking with run-time type checking.</span></span>

[!code-csharp[csrefKeywordsTypes#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic2.cs#25)]

### <a name="see-also"></a><span data-ttu-id="49e36-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49e36-177">See also</span></span>

- [<span data-ttu-id="49e36-178">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="49e36-178">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="49e36-179">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="49e36-179">C# Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="49e36-180">Eventi</span><span class="sxs-lookup"><span data-stu-id="49e36-180">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="49e36-181">Uso del tipo dinamico</span><span class="sxs-lookup"><span data-stu-id="49e36-181">Using Type dynamic</span></span>](../../programming-guide/types/using-type-dynamic.md)
- [<span data-ttu-id="49e36-182">Procedure consigliate per l'uso delle stringhe</span><span class="sxs-lookup"><span data-stu-id="49e36-182">Best Practices for Using Strings</span></span>](../../../standard/base-types/best-practices-strings.md)
- [<span data-ttu-id="49e36-183">Operazioni di base su stringhe</span><span class="sxs-lookup"><span data-stu-id="49e36-183">Basic String Operations</span></span>](../../../standard/base-types/basic-string-operations.md)
- [<span data-ttu-id="49e36-184">Creazione di nuove stringhe</span><span class="sxs-lookup"><span data-stu-id="49e36-184">Creating New Strings</span></span>](../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="49e36-185">Operatori di cast e di test del tipo</span><span class="sxs-lookup"><span data-stu-id="49e36-185">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
- [<span data-ttu-id="49e36-186">Come eseguire il cast sicuro usando i criteri di ricerca e gli operatori As e is</span><span class="sxs-lookup"><span data-stu-id="49e36-186">How to safely cast using pattern matching and the as and is operators</span></span>](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [<span data-ttu-id="49e36-187">Procedura dettagliata: Creazione e utilizzo di oggetti dinamici</span><span class="sxs-lookup"><span data-stu-id="49e36-187">Walkthrough: creating and using dynamic objects</span></span>](../../programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- <xref:System.Object?displayProperty=nameWithType>
- <xref:System.String?displayProperty=nameWithType>
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>

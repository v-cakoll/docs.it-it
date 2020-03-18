---
title: if-else - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- if_CSharpKeyword
- else
- else_CSharpKeyword
- if
helpviewer_keywords:
- else keyword [C#]
- if keyword [C#]
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
ms.openlocfilehash: 98c1a8dceec3e5a47627841988e2d722c56fc36c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715269"
---
# <a name="if-else-c-reference"></a>if-else (Riferimenti per C#)

Un'istruzione `if` identifica quale istruzione eseguire in base al valore di un'espressione booleana. Nell'esempio seguente la variabile `bool``condition` viene impostata su `true` e quindi archiviata nell'istruzione `if` . L'output è `The variable is set to true.`.

[!code-csharp[csrefKeywordsSelection#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#1)]

È possibile eseguire gli esempi di questo argomento posizionandoli nel metodo `Main` di un'app console.

Un'istruzione `if` in C# può essere usata in due modi, come illustrato nell'esempio seguente.

```csharp
// if-else statement
if (condition)
{
    then-statement;
}
else
{
    else-statement;
}
// Next statement in the program.

// if statement without an else
if (condition)
{
    then-statement;
}
// Next statement in the program.
```

In un'istruzione `if-else` se `condition` restituisce true, viene eseguito `then-statement` . Se `condition` è false, viene eseguito `else-statement` . Poiché `condition` non può essere contemporaneamente true e false, `then-statement` e `else-statement` di un'istruzione `if-else` non possono mai essere eseguiti insieme. Dopo l'esecuzione di `then-statement` o `else-statement` il controllo viene trasferito all'istruzione successiva dopo l'istruzione `if` .

In un'istruzione `if` che non include un'istruzione `else` , se `condition` è true, viene eseguito `then-statement` . Se `condition` è false, il controllo viene trasferito all'istruzione successiva dopo l'istruzione `if` .

`then-statement` e `else-statement` possono essere entrambi costituiti da una singola istruzione o da più istruzioni racchiuse tra parentesi graffe (`{}`). Per una singola istruzione le parentesi graffe sono facoltative ma consigliate.

L'istruzione o le istruzioni in `then-statement` e `else-statement` possono essere di qualsiasi tipo, compresa un'altra istruzione `if` annidata all'interno dell'istruzione `if` originale. Nelle istruzioni `if` annidate ogni clausola `else` appartiene all'ultima istruzione `if` che non ha un'istruzione `else`corrispondente. Nell'esempio seguente viene visualizzato `Result1` se `m > 10` e `n > 20` restituiscono entrambi true. Se `m > 10` è true ma `n > 20` è false, viene visualizzato `Result2` .

[!code-csharp[csrefKeywordsSelection#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#2)]

Se invece si vuole che venga visualizzato `Result2` quando `(m > 10)` è false, è possibile specificare tale associazione usando le parentesi graffe per stabilire l'inizio e la fine dell'istruzione `if` annidata, come illustrato nell'esempio seguente.

[!code-csharp[csrefKeywordsSelection#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#3)]

`Result2` viene visualizzato se la condizione `(m > 10)` restituisce false.

## <a name="example"></a>Esempio

Nell'esempio seguente si immette un carattere dalla tastiera e il programma usa un'istruzione `if` annidata per determinare se il carattere di input è un carattere alfabetico. Se il carattere di input è un carattere alfabetico, il programma verifica se il carattere di input è maiuscolo o minuscolo. Viene visualizzato un messaggio per ogni situazione.

[!code-csharp[csrefKeywordsSelection#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#4)]

## <a name="example"></a>Esempio

È anche possibile annidare un'istruzione `if` all'interno di un blocco else, come illustrato nella parte di codice seguente. Nell'esempio le istruzioni `if` vengono annidate all'interno di due blocchi else e di un blocco then. I commenti specificano che le condizioni sono true o false in ogni blocco.

[!code-csharp[csrefKeywordsSelection#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#5)]

## <a name="example"></a>Esempio

L'esempio seguente determina se un carattere di input è una lettera minuscola, una lettera maiuscola o un numero. Se tutte e tre le condizioni sono false, il carattere non è un carattere alfanumerico. Nell'esempio viene visualizzato un messaggio per ogni situazione.

[!code-csharp[csrefKeywordsSelection#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#6)]

Come per un'istruzione nel blocco else o nel blocco then è possibile usare qualsiasi istruzione valida, allo stesso modo per la condizione è possibile usare qualsiasi espressione booleana valida. È possibile utilizzare operatori `!` `&&` [logici](../operators/boolean-logical-operators.md) `|`quali `^` , , `||`, `&`, e per creare condizioni composte. Il codice seguente illustra alcuni esempi.

```csharp
// NOT
bool result = true;
if (!result)
{
    Console.WriteLine("The condition is true (result is false).");
}
else
{
    Console.WriteLine("The condition is false (result is true).");
}

// Short-circuit AND
int m = 9;
int n = 7;
int p = 5;
if (m >= n && m >= p)
{
    Console.WriteLine("Nothing is larger than m.");
}

// AND and NOT
if (m >= n && !(p > m))
{
    Console.WriteLine("Nothing is larger than m.");
}

// Short-circuit OR
if (m > n || m > p)
{
    Console.WriteLine("m isn't the smallest.");
}

// NOT and OR
m = 4;
if (!(m >= n || m >= p))
{
    Console.WriteLine("Now m is the smallest.");
}
// Output:
// The condition is false (result is true).
// Nothing is larger than m.
// Nothing is larger than m.
// m isn't the smallest.
// Now m is the smallest.
```

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [?: Operatore](../operators/conditional-operator.md)
- [Istruzione if-else (C++)](/cpp/cpp/if-else-statement-cpp)
- [Interruttore](switch.md)

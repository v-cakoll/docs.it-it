---
title: Parola chiave bool - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 3e4e83b52cd6b275e68039693c774f6490f2b88f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606054"
---
# <a name="bool-c-reference"></a>bool (Riferimenti per C#)

La parola chiave `bool` è un alias per <xref:System.Boolean?displayProperty=nameWithType>. Viene usata per dichiarare le variabili che archiviano i valori booleani, [true](true-literal.md) e [false](false-literal.md).

> [!NOTE]
> Usare il tipo `bool?` se occorre supportare la logica a tre valori, ad esempio quando si lavora con database che supportano un tipo booleano a tre valori. Per gli operandi `bool?`, gli operatori `&` e `|` predefiniti supportano la logica a tre valori. Per altre informazioni, vedere la sezione [Operatori logici booleani nullable](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) dell'articolo [Operatori logici booleani](../operators/boolean-logical-operators.md).

## <a name="literals"></a>Valori letterali

È possibile assegnare un valore booleano a una variabile `bool`. È possibile anche assegnare un'espressione che restituisce `bool` per una variabile `bool`.

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

Il valore predefinito di una variabile `bool` è `false`. Il valore predefinito di una variabile `bool?` è `null`.

## <a name="conversions"></a>Conversioni

In C++, un valore di tipo `bool` può essere convertito in un valore di tipo `int`; in altre parole, `false` equivale a zero e `true` equivale a valori diversi da zero. In C#, non c'è nessuna conversione tra il tipo `bool` e altri tipi. Ad esempio, l'istruzione `if` seguente non è valida in C#:

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

Per testare una variabile del tipo `int`, è necessario confrontarla esplicitamente con un valore, ad esempio zero, come indicato di seguito:

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a>Esempio

In questo esempio si immette un carattere dalla tastiera e il programma controlla se il carattere di input è una lettera. Se è una lettera, controlla se è maiuscola o minuscola. Questi controlli vengono eseguiti con <xref:System.Char.IsLetter%2A> e <xref:System.Char.IsLower%2A>, che restituiscono entrambi il tipo `bool`:

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](./index.md)
- [Tipi integrali](../builtin-types/integral-numeric-types.md)
- [Tabella dei tipi incorporati](./built-in-types-table.md)
- [Tabella delle conversioni numeriche implicite](./implicit-numeric-conversions-table.md)
- [Tabella delle conversioni numeriche esplicite](./explicit-numeric-conversions-table.md)

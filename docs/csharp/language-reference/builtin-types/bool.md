---
title: tipo bool- C# riferimento
ms.date: 11/26/2019
f1_keywords:
- bool
- bool_CSharpKeyword
helpviewer_keywords:
- bool data type [C#]
- Boolean [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 0e01c183ef07c23203619e0cbbf550c6268bdd46
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78239833"
---
# <a name="bool-c-reference"></a>bool (C# riferimento)

La parola chiave `bool` Type è un alias per il tipo di struttura <xref:System.Boolean?displayProperty=nameWithType> .NET che rappresenta un valore booleano, che può essere `true` o `false`.

Per eseguire operazioni logiche con valori del tipo di `bool`, utilizzare operatori [logici booleani](../operators/boolean-logical-operators.md) . Il tipo di `bool` è il tipo di risultato degli operatori di [confronto](../operators/comparison-operators.md) e di [uguaglianza](../operators/equality-operators.md) . Un'espressione `bool` può essere un'espressione condizionale di controllo nelle istruzioni [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md)e [for](../keywords/for.md) e nell' [operatore condizionale `?:`](../operators/conditional-operator.md).

Il valore predefinito del tipo di `bool` è `false`.

## <a name="literals"></a>Valori letterali

È possibile usare i valori letterali `true` e `false` per inizializzare una variabile di `bool` o per passare un valore di `bool`:

[!code-csharp-interactive[bool literals](~/samples/snippets/csharp/language-reference/builtin-types/BoolType.cs#Literals)]

## <a name="three-valued-boolean-logic"></a>Logica booleana a tre valori

Usare il tipo Nullable `bool?`, se è necessario supportare la logica a tre valori, ad esempio quando si lavora con database che supportano un tipo booleano a tre valori. Per gli operandi `bool?`, gli operatori `&` e `|` predefiniti supportano la logica a tre valori. Per altre informazioni, vedere la sezione [Operatori logici booleani nullable](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) dell'articolo [Operatori logici booleani](../operators/boolean-logical-operators.md).

Per ulteriori informazioni sui tipi di valore Nullable, vedere [tipi di valore Nullable](nullable-value-types.md).

## <a name="conversions"></a>Conversioni

C#fornisce solo due conversioni che coinvolgono il tipo di `bool`. Si tratta di una conversione implicita al tipo di `bool?` nullable corrispondente e a una conversione esplicita dal tipo di `bool?`. .NET fornisce tuttavia metodi aggiuntivi che è possibile usare per eseguire la conversione da o verso il tipo di `bool`. Per ulteriori informazioni, vedere la sezione [conversione da e verso valori booleani](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) della pagina di riferimento dell'API <xref:System.Boolean?displayProperty=nameWithType>.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni, vedere [la sezione tipo bool](~/_csharplang/spec/types.md#the-bool-type) della [ C# specifica del linguaggio](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Tipi di valore](value-types.md)
- [Operatori true e false](../operators/true-false-operators.md)
